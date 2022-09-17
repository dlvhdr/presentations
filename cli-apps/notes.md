OK, so **welcome everybody!**
So let me introduce myself before we begin with the slides.
I'm Dolev, I've been at Wix for about ~1.5 years.
I'm a frontend developer at the Velo team.

For those that don't know, Velo is a full-stack development platform that allows users to write custom logic on top of Wix's WYSIWYG editors.
My team is working on the online code editor itself and the its autocompletion engine.
For anyone interested in learning more, feel free to reach out after the slides.

So recently, I've been falling **in love** with the CLI.
I went through a rabbit hole of trying to make my developer experience better and found that a lot of stuff are snappier to do on the terminal.
On top of that there have been a lot of innovation surrounding the terminal.

So hopefully I can convince you to give the terminal more attention and that you find it rewarding.

---

Let's talk about those innovations that I mentioned.
You might think that the terminal is a boring interface and kind of depressing to stare at all day.
Well, actually, it can be **GLAMOUROUS** 🌈

_{ GO TO Charm's website }_

Charm, is a faily new startup that wrote a bunch of libraries to help us make the terminal less boring. We'll see some of those libraries later on, so no spoilers.

In 2016, Microsoft launched the Windows Subsystem for Linux, which lets developers run a GNU/Linux environment -- including most command-line tools.
And they also launched the new [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-il&gl=il)
_{ GO TO Windows Terminal website }_

Another new startup in the field is **Warp**, that are reimagining the terminal.
If we go to their site, you can see the terminal looks completely different.
You can edit commands like you're in VSCode with multi cursors, get "Intellisense" like autocompletion, jump between command blocks and more.
You even have a "GitHub Copilot" kind of assistant for when you forget how to perform some command.

_{ GO TO Warp's website }_

---

Ok, so what are some of the reason's you'd want to spend more time on the terminal?

First, CLIs are great for telling computers **exactly** what to do.
Unlike GUI applications, where a bunch of different workflows are hidden behing a naive looking button.

Sencond, they're composoble. That's basically the UNIX philosophy.
Write something that does one thing and does it well.
You can them pipe one command's output to another's input to compose more complex pipelines.

3. For those that care about ergonomics and staying on the keyboard for speed's sake (what I mean is you move less between the mouse and the keyboard), the terminal is a better choice.

4. The shell is the closest thing to the OS, so you can easily interact with it (files, network etc.)

5. Many times, GUI apps exist solely as friendlier but weaker versions of a CLI app. Knowing the CLI version gives more power with granularity.

6. And as a developer you're already in the CLI a lot, so why not learn to master it.

_{ read the quote }_

---

Ok, so let's see some examples of stuff you probably didn't know you could do in the terminal

First up, you can actually draw in the terminal.

---

You can celebrate wins!

---

You can play magic tricks!

I've included some of the bash script here.
You can see one the libraries that Charm made, one called _gum_.
gum let's you easily create user-interactable scripts, which also look good!
The code here is quite simple.
You use _gum_ to answer the first few questions using `gum choose`.
You then pick a card again with `gum choose`.
You then print the chosen card with `gum style` to give it a nice rounded border. etc.

---

Next, the GitHub CLI.
That's a pretty powerful CLI alternative to GitHub's website.
You can pretty much do everything from the comfort of your keyboard.
Here, I'm fetching the the last 5 PRs in `wix-private` (they're probably loki).

---

Ok, so `gh` actually allows you to write extensions for it.
I've written one, which is called `gh-dash` and I'd like to share it with you.
Hopefully it can be useful for you as it has been for me.

I've found GitHub's "Pull Requests" page lacking. While I was working in another company we had a nice dashboard to see all the Pull Requests we should care about.

And we all know following PRs among Wix's many many repos can be hard.
`gh-dash` is a Terminal UI app.
Let's see it in action.

At the top there are the list of sections you've defined at the app's `config.yml` file.
They define section names along with their search query.
I've defined the following to help me: _{ go over the list of sections }_
You can open up a side pane to see more details on a PR.

_{ open side pane }_

You can then perform multiple actions on them.

_{ show commenting etc. }_

Now that we know you can do a lot with the terminal, let's learn more about how all of this works.

---

The most basic term we need to learn about is _Escape Sequences_.
ANSI escape sequences are a standard for signaling terminal emulators to do special things.
Terminal emulators are the programs that render the user input and the commands output.
They send the input to a program called the SHELL (zsh, bash etc).

The terminal interprets these sequences as commands rather than display the text as is.

---

Let's see an example of an Escape Sequence.
Here's one: `\x1b[1;31m`.
The first few characters let's the terminal know that this is the start of an escape sequence.
There are multiple ways to write ESC, in its octal/hex notation etc.
Right after that, there is a separator: `[`.
Then the list of display attributes, each separated with a semicolumn.
Finally, `m` represents the end of the sequence.

Below is a table of some of the display attributes.
In this example we set `1` so the text is bold, and `31` so that it's red.

So running the example from earlier (this time with octal notation) we get a bold red text.

_{ run example }_

---

The 8 color display attribute I showed earlier is a bit limiting.
We also have 256 color support for most terminals.
To use them we can write the attribute: `38;5`, then the ID (out of 256) of the color.

Here's a simple python script to display all 256 colors.

---

But most newer terminals support TrueColor, strikethroughs, dotted underlines etc.

Here's a simple script to test your terminal's capabilities.

_{ run script }_

---

Using escape sequences we can also control where characters are printed.
The `H` command lets us specify coordinates.
Without any arguments, (0,0) is the default - the top left corner.

In the second script, I'm printing 3 cats spaced 5 columns apart horizontally.

This allows us to easily override existing text, to do stuff like progress bars etc.

---

Now that we have a low-level understanding of how a terminal works, let's forget all that and use a bunch of libraries that make it a lot easier!

We're going to write a simple app called **Roulette**.
The app can help you randomly choose between different items. E.g:
 * What to eat for dinner
 * Who's next to go in the daily
 * etc...

The libraries we're going to use are from **Charm**.
To write the app, we'll learn:
* Just a bit of Go.
* The Elm Architecture used by Charm's Bubbletea lib.
* Charm's libraries: bubbletea, lipgloss and glamour.

---

To get ourselves familiar with Charm's libraries we can simply ssh to `git.charm.sh`.
Here we can read each lib's README, see its files, commits, etc.
When we ssh into `git.charm.sh` we are actually connecting to another one of Charm's libs, called Wish.

_{ show wish}_

---

Now, to use Charm's libs we need some Go knowledge.
Again, we're going to use the terminal for that.
For those unfamiliar, [cheat.sh](cheat.sh) is a site that's built for consumption on the terminal.
You can write something like `cheat.sh/go/:learn` to get the basics of Go.

Go over:
- A function definition
- Variable declarations
- Multi value returns
- Defining a method on type pair

---

One last concept we need to know in order to use Charm's Bubbletea lib, is the Elm architecture.
Think of it like a React's app lifecycle.

We first define a Model.
This model represents our app's state. It's a simple object we define. 
In it, we need to store all the information we need to render our UI.

Given a Model, the ELM runtime calls our "View" function, which we use to return a string. That string is our UI!

Now that we know that given a Model we render a View, we need a way to change the model.

That's where the Update function comes in.
This function recieves a message when "things happen".
Here, we write logic to update the model, depending on what happened.

Messages are the way we declare what happened.

User input is just one thing that might happen, but it could also be a timer firing, a network call that was returned, a file read from disk etc.

---

For our Roulette app, we need a very simple model.
We need to hold the 


