---
author: "Dolev Hadar"
paging: "%d / %d"
theme: ./theme.json
date: "DD MMMM, YYYY"
---

# The Reinassance of the Command Line

>⣿⣿⣿⣿⣿⣿⣿⢿⣿⣿⣿⣟⣛⡻⢿⣻⡿⠛⢹⢮⠄⢀⠌⠈⠂⠑⠂⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
>⣿⣿⣿⣿⣿⣿⠽⠿⢫⢽⣯⣿⣾⣿⣝⢻⢓⢾⡗⠘⠉⠁⠀⠀⠀⢀⣀⣀⣈⣀⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
>⣿⣿⣿⣿⣿⣿⣿⣿⣷⣿⡯⡯⠽⠋⠛⠛⠂⠀⠀⠀⠀⢀⣤⣶⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣤⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
>⣽⣿⣿⣿⣯⢩⣬⣋⣹⣏⠁⢈⠀⡐⠀⠀⠀⠀⠀⢀⣼⣿⣿⣿⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣤⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
>⣿⠿⠻⢣⡨⡍⣉⡈⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣾⠿⠛⠉⠁⠀⠀⠈⠉⠉⠙⠻⣿⣿⣿⣿⣿⣿⣿⣿⣷⣄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀     
>⠁⠐⠘⠳⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣰⡿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢻⣿⣿⣿⣿⣿⣿⣿⣿⣄⠀⠀⠀⠀⠀⠀⠀⠀⠀     
>⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣼⣿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿⣿⣿⣿⣿⣿⣿⣿⡆⠀⠀⠀⠀⠀⠀⠀⠀     
>⠀⠄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⣿⣿⡿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⣿⣿⣿⣿⣿⣿⣿⣿⣿⡀⠀⠀⠀⠀⠀⠀⠀     
>⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿⣿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣿⣿⣿⣿⣿⣿⣿⣿⣿⡇⠀⠀⠀⠀⠀⠀⠀     
>⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⣿⣿⣷⣤⢴⣒⣲⣄⠀⠀⢀⣾⡿⣓⣒⣲⣶⣶⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠀⠀⠀⠀⠀⠀⠀    → **Dolev Hadar**
>⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⣿⣿⣿⠙⠋⠙⠛⠛⠀⠀⢸⠟⠉⠀⠙⠛⠿⠛⠉⢙⣿⣿⣿⣿⣿⣿⣿⣿⣿⠀⠀⠀⠀⠀⠀⠀    → **Works @ Wix for _~1 year_ on the Velo team**
>⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣾⣿⣿⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⣿⣿⣿⣿⣿⣿⣿⣿⡄⠀⠀⠀⠀⠀⠀    → **Frontend developer that** _fell in love_ **with the CLI 💖**
>⣀⣀⡀⡀⠀⠀⠀⠀⠀⠀⠠⢸⣿⣿⣿⣿⣿⡀⠀⠀⠀⠀⠀⠀⠀⢀⠀⠀⠀⠀⠀⠀⢀⣾⣿⣿⣿⣿⣿⣿⣿⣿⣿⡇⠀⡀⢀⠀⡀⠀    → [ Github](https://github.com/dlvhdr)
>⣅⣀⣀⣀⣀⠀⠀⠀⠀⠀⠄⡜⣿⣿⣿⣿⣿⣧⠀⠀⠀⠀⢀⣤⣶⣾⠀⠀⠀⠀⠀⢀⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡑⡒⠐⠑⠀⢷    → ** Twitter: @dlvhdr**
>⣿⣵⣶⣿⣯⣾⣢⠵⡤⢉⠥⣀⣿⣿⣿⣿⣿⣿⡆⠀⢀⣀⣀⢉⣋⣡⣤⣤⠀⠀⠀⣼⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡇⠀⠀⠁⣠⣴
>⣿⣿⣟⢻⠝⠛⠃⠀⢖⠀⢄⣄⣿⣿⣿⣿⣿⣿⣿⣄⠀⠀⠀⢬⣭⣽⠋⠀⠀⠀⣼⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣧⣤⣾⣿⣿⣿
>⣿⣿⣷⣑⣀⣁⠘⠍⠲⣮⡴⠡⣿⣿⣿⣿⣿⣿⣿⣿⣷⣄⠀⠀⠀⠀⠀⣠⣴⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
>⣿⣯⣋⡋⠳⢈⠀⢨⢠⠒⡆⠒⠹⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣤⣤⣤⣶⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
>⣿⣿⣟⣶⣾⣶⢶⢠⡠⡄⣽⣾⣣⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
>⡿⣿⣭⡷⣷⣷⣿⣷⣶⣌⣬⣽⣾⣶⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡉⠛⠿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
>⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⠟⠃⠀⠀⠀⠉⠙⠛⠛⠿⠿⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
>⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⠋⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
>⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠛⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
>⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
>⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿

---

# The Reinassance of the Command Line

## CLI Apps

- The CLI doesn't have to be that boring interface, it can be **GLAMOROUS** 🌈
- Companies like [Charm](https://charm.sh/) are writing tools for making it so
- Microsoft launched WSL in 2016 (_Windows Subsystem For Linux_) which let Windows users join the party
  - And they also launched the new [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-il&gl=il)
- And [Warp](https://www.warp.dev/) are reimagining the terminal

---

# The Reinassance of the Command Line

## Benefits of using the CLI

- CLIs are great for telling computers **exactly** what to do
- Composable. It's Nearly impossible to chain GUI programs so that the output of one becomes the input for another.
  - `youtube-dl https://youtu.be/dQw4w9WgXcQ -q -o - | ffmpeg -i - piping_commands.mp4`
- Simple text input, keyboard oriented
- Hackable & Scriptable
- Many GUI apps exist solely as a friendlier but weaker abstraction over a CLI tool
  - Knowing the CLI equivalent gives more power
  - E.g git, package managers
- As a developer you're already in the CLI quite a lot
- Large ecosystem

> The problem with **WYSIWYG** is that it is usually equivalent to **WYSIATI** (What You See Is All There Is).

---

# The Reinassance of the Command Line

## Examples of CLI apps

### draw

```bash
tmux splitw -v bash -c "draw"
```

---

# The Reinassance of the Command Line

## Examples of CLI apps

### confetti

```bash
tmux splitw -v -l 30 bash -c "confetty"
```

---

# The Reinassance of the Command Line

## Examples of CLI apps

### gum

```bash
bat -f ./magic-tldr.sh
tmux splitw -h -l 50 "~/code/playground/gum/examples/magic.sh"
```

---

# The Reinassance of the Command Line

## Examples of CLI apps

### gh - the Github CLI

- `gh pr create`
- `gh search prs`
```bash
tmux splitw 'gh search prs "org:wix-private" --limit 5; fish -i'
```

---

# The Reinassance of the Command Line

## Examples of CLI apps

### `gh dash`

- We all know Wix has **A LOT** of repositories
- A TUI app I built that helps me to manage all of my pull requests and issues

```bash
tmux neww -n "gh dash" gh dash
```


---

# The Reinassance of the Command Line

## How do CLI apps work

### Escape Sequences

- On terminals, ANSI escape sequences are a standard for signaling, control cursor location, color, etc.
- Certain sequences of bytes, most starting with an **ASCII escape character**
- The terminal _interprets_ these sequences as commands, rather than text to display verbatim.

---

# The Reinassance of the Command Line

## Escape Sequences

For example:

`\x1b[1;31m` - to set style to bold, red foreground.

>  \x1b[ 1;31m
>  ───── ─────
>    ▲     ▲
>    │     │
>   ESC   SGR

- ESC - Ctrl-Key `^[`,  Octal `\033`, Hexadecimal `\x1b`, ...
- SGR - Select Graphic Rendition (SGR), sets display attributes

## SGR Table

| n | Name  | Note |
|---|---|---|
| 0 | Reset or normal | All attributes off |
| 1 | Bold | |
| ... | | |
| 30-37 | Set foreground color | |
| ... | | |
| 40-47	| Set background color  | |

---

# The Reinassance of the Command Line

## Escape Sequences

### Let's see them in action

A simple example

```bash
# Set style to bold, red foreground.
# -e flag can be used to enable escape sequences.
echo -e "\033[1;31mHello\033[0m"
```

---

# The Reinassance of the Command Line

## Escape Sequences

### ANSI colors - 256-color mode

- `ESC[38;5;{ID}m` - set foreground color
- `ESC[48;5;{ID}m` - set background color
- `ESC[0m` - reset all modes (styles and colors)

```python
import sys
for i in range(0, 16):
    for j in range(0, 16):
        code = str(i * 16 + j)
        sys.stdout.write(u"\u001b[48;5;" + code + "m " + code.ljust(4))
    print(u"\u001b[0m")
```

---

# The Reinassance of the Command Line

## Escape Sequences

### True color and other attributes

- If your terminal supports it, it can display **16 million colors**
- Strikethough, dotted underline, undercurl, etc.

```bash
tmux splitw -v -l 35 "curl -L https://bit.ly/3A5B3u3 | python3 | less -R"
```

---

# The Reinassance of the Command Line

## Escape Sequences

### Cursor control

* Setting cursor position to <ins>**H**</ins>OME (0,0)
```bash
echo -e '\033[HOMG 🙈'
```

* Setting cursor position to (20,20)
```bash
echo -e '\033[25;25H😽\033[25;30H😽\033[25;35H😽'
```

---

# The Reinassance of the Command Line

## Let's write a simple CLI app

We're going to built an app called **Roulette** 🎰

The app can help you randomly choose between different items.
E.g:
- What to eat for dinner
- Who's next to go in the daily
- etc...

For this we'll use the [Charm](https://charm.sh) suite of libraries:

- We're gonna learn a _little bit_ of Go
- We'll learn the Elm architecture
- We're going to use Charm's `Bubbletea`, `Lipgloss` and `Glamour` 

---

# The Reinassance of the Command Line

## Charm's CLI libraries

```bash
tmux splitw -v -l 35 ssh git.charm.sh
```

### Notable Libraries

- Soft Serve
- Gum
- Bubbletea
- Bubbles
- Lipgloss
- Glow
- Glamour

---

# The Reinassance of the Command Line

## Writing a Roulette

Now, to use Charm's libs we need some Go knowledge.

```bash
tmux neww -n "Learning Go" "curl cheat.sh/go/:learn | less -r"
```

---

# The Reinassance of the Command Line

## The Elm Architecture

```
~~~graph-easy --as=boxart
[  ELM Runtime ]
[  user input ] . fires .> [  message ]
[  message ] -> [  update ]
[  update ] -> [  model ]
[  model ] -> [  view ]
[  view ] - fires -> [  message ]
~~~
```

- ** Model** - Describes the application state
- ** Update**
  - The update function is called when _”things happen.”_
  - Its job is to look at what has happened and return an updated model in response.
- ** View**
  - We look at the model in its current state and use it to return a string.
  - _That string is our UI!_
- ** Message**
  - This is how the user interacts with out app.
  - It causes update to get fired with the message as the context.

---

# The Reinassance of the Command Line

## Bubbletea

> ** Model** - Describes the application state

```go
type model struct {
  title   string // Optional
  options []string
}
```

---

# The Reinassance of the Command Line

## Bubbletea

> ** Update**
> The update function is called when _”things happen.”_
> Its job is to look at what has happened and return an updated model in response.

```go
func (m model) Update(msg tea.Msg) (tea.Model, tea.Cmd) {
  switch msg := msg.(type) {
    // Change model accordingly...
  }

  return updatedModel, nil
}
```

---

# The Reinassance of the Command Line

## Bubbletea

> ** View**
> We look at the model in its current state and use it to return a string.
> _That string is our UI!_

```go
func (m Model) View() string {
  s := strings.Builder{}
  s.WriteString("Welcome to roulette!")
  s.WriteString("\n")
  options := m.renderOptions()
  return s.String()
}
```

---

# The Reinassance of the Command Line

## Demo - let's write it!

```bash
tmux neww fish -c "cd ./roulette; git checkout skeleton; nvim main.go"
```

---

# The Reinassance of the Command Line

## Reources

- [Charm](https://charm.sh)
- [ANSI escape codes](https://en.wikipedia.org/wiki/ANSI_escape_code)
- [Bubbletea](https://github.com/charmbracelet/bubbletea)
- [confetty](https://github.com/maaslalani/confetty)
- [gum](https://github.com/charmbraceletm/gum)
- [slides](https://github.com/maaslalani/slides) - used to power this presentation
- [gh](https://github.com/cli/cli) - the GitHub CLI
- [gh-dash](https://github.com/dlvhdr/gh-dash) - my GitHub dashboard extension
- [My blog](https://dlvhdr.me)

### Thank you! 🌟


