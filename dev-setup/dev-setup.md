author: ""
paging: "%d / %d"
theme: ./theme.json
date: ""

## Why?

Our development environment has a **big influence** on how good we can perform as software engineers.

It comes down to:

- 🤔 Mental overload
- 📉 Time saving
- 🧘 Ease of use
- 🧰 Proficiency with our tools

## Why am I busy optmizing my dev setup?

- Wallak lama lo...
- I care way too much about things feeling _"right"_ 🧘
- I need stuff to be catered 🌈 to my needs.
- If something annoys me, I get obssessed on fixing and optimizing it.
- ... and you get to enjoy from my nitpicking :)

## Ricing

> A term applied to Japanese motorcycles and which later expanded to include Japanese cars.
> **Riced out** descripts a badly customized sports compact car, usually with oversized or ill-matched exterior appointments

- In **programming**, _ricing_ refers to the effort of customizing your `*nix` installation.
- From wallpapers, fonts and themes to window managers, terminal emulators and CLI utilities.

https://flaxplax.com/images/meme/ricing.png

https://www.youtube.com/watch?v=LGpH_aYBvqY

## My dev setup is mostly built around

- Using the ⌨️ keyboard as much as possible
- Reducing time spent on tasks that annoy me
- Finding the best tools for those tasks

## What we'll cover

- Mac setup
- O-launching
- Keyboard everything
- Terminal
  - Alacritty
  - tmux
  - zsh
- Brew packages
- Neovim
- My workflow

## Mac

- The **first thing** (!!!) I do on a new mac is set it's key repeat and delay speed

```sh
  defaults write -g InitialKeyRepeat -int 20 # normal minimum is 15 (225 ms)
  defaults write -g KeyRepeat -int 1 # normal minimum is 2 (30 ms)
```

- Automatically Show/Hide the dock (this gives you more screen real-estate!)
- Changing where screenshots are saved

```sh
  mkdir -p ~/Pictures/Screenshots
  defaults write com.apple.screencapture location ~/Pictures/Screenshots
  defaults write com.apple.screencapture type jpg
```

- Mapping _<kbd>CAPS-LOCK</kbd>_ to _<kbd>ESC</kbd>_

[] Feel free to explore more settings [here](https://github.com/kevinSuttle/macOS-Defaults/blob/master/.macos)

## Window Manager

- I use **[Amethyst](https://github.com/ianyh/Amethyst)**.
- Amethyst is a tiling window manager.

**What's a tiling window manager?**

> A window manager with an organization of the screen into mutually **non-overlapping** frames
> as opposed to the more common approach of **coordinate-based stacking of overlapping** objects

## Application launcher

For launching applications I use **[Raycast](https://www.raycast.com/)**.

> _Raycast is a blazingly fast, totally extendable launcher. It lets you complete tasks, calculate, share common links, and much more._

- Clipboard history
- Snippets
- System shortcuts
- Scripts
  - Spotify
  - Kan 88FM
- Confetti

## Other goodies

- I often ask myself what's the name of the song that's playing.
  - For that I use 🎼 [spotmenu](https://kmikiy.github.io/SpotMenu/).
- Calender - 📅 [Cron](https://cron.com/)
  - Command menu
  - Menu bar
- [Spaceman](https://github.com/Jaysce/Spaceman) - An app to view Spaces / Virtual Desktops in the menu bar

## Keyboard everything

- O-launching: `skhd` or Raycast
- Chrome
  - [Vimium](https://github.com/philc/vimium)
  - [Bitwarden](https://github.com/bitwarden/browser)
  - [TickTick](https://ticktick.com)

## Terminal Emulator

- For my terminal emulator I use [Alacritty](https://github.com/alacritty/alacritty).
- It's main selling point is that it's GPU rendered.
- The reason I'm using it is that it's minimal and it's settings are stored in a `.yaml` file.

## tmux

- For managing mutiple terminal sessions I use **[tmux](https://github.com/tmux/tmux/wiki)**
- The sessions can be saved so that even if you restart your mac, you can restore them easily.
- It lets me switch easily between several programs in one terminal.

### Plugins

- [tmux-resurrect](https://github.com/tmux-plugins/tmux-ressurect)
- [url-view](https://github.com/tmux-plugins/tmux-urlview)

## Shell

For the shell I use `zsh`, most famous for it's plugin manager [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh).

### Plugins

- vi-mode
- zsh-syntax-highlighting
- auto-notify
- you-should-use
- yarn-autocompletions
- fzf-yarn
- zoxide

Also important:

- [starship](https://starship.rs/)
- [exa](https://github.com/ogham/exa)
- [ranger](https://github.com/ranger/ranger)
- aliases

## Brew Packages

- For installing and updating apps, I mainly use `brew`
- I have a `Brewfile` that lists everything I have installed with brew.
- If I were to switch computers, I can easily re-install everything.

A lot of the apps we've seen can be installed with `brew`.

Before downloading anything from the mac store / google, I first search it in brew

```sh
  brew info raycast
```

### Honorable Mentions

- fzf
- jq
- bat
- exa
- bpytop
- git-delta
- fnm
- gh
- tealdeer

## Editor: Neovim

### Why Neovim?

- Fully scriptable
- Keyboard oriented
- Fast...
- Interestingly enough, Neovim came in #1 in the [Stackoverflow 2021 Developer Survey](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-collaboration-tools) for the Most Loved Collaboration Tool!

### How to get started?

- `vimtutor`
- Barbariant Meets Coding
  - [Boost Your Coding Fu](https://www.barbarianmeetscoding.com/boost-your-coding-fu-with-vscode-and-vim/)
  - The [VSCode extension](https://marketplace.visualstudio.com/items?itemName=vintharas.learn-vim)

## Editor: Neovim

### Who it's not for?

- Some assembly required
  - For some it's a huge downside for others its a tinkering opportunity
- Erasing those little annoyances in my life
- Writing that plugin that brings a little more joy to my life
- Fully scriptable
  - Lua as primary scripting language
  - GUIs are plugins
- Doesn't have "Vim Emulator" problems.

## lua in a nutshell

```lua
  print 'Hello, world!'

  -- Variables are global by default.
  thisIsGlobal = 5  -- Camel case is common.

  -- How to make a variable local:
  local line = io.read()  -- Reads next stdin line

  -- tables
  t = {key1 = 'value1', key2 = false}
  -- are also, lists...?
  v = {'value1', 'value2', 1.21, 'gigawatts'}

  -- for loops
  for i = 1, 100 do
    -- ...
  end

  -- functions
  function fib(n)
    if n < 2 then return 1 end
    return fib(n - 2) + fib(n - 1)
  end

```

## Editor: Neovim

**Setup**

- Plugin manager: packer
- Statue line: lualine
- Completions: nvim-cmp
- LSP
- Syntax highlighting: treesitter
- Fuzzy finder: Telescope
- File tree: nvim-tree
- Snippets: LuaSnip
- other goodies...

## Workflow

- Git aliases
  - `amend-all = !git add -A && git commit --amend --no-verify`
  - `commit-all = !git add -A && git commit --no-verify`
  - `master = !git checkout $(git remote show origin | awk '/HEAD branch/ {print $NF}')`
- tig
- GitHub code search
  - Filtering options

```zsh
  function wix_code_search() {
    open "https://cs.github.com/?scope=org%3Awix-private&scopeName=wix-private&q=""$@"
  }
  alias wcs="wix_code_search"
```

- `gh` extension
  - `gh view pr --web`
  - `gh pr create`
  - `gh dash` (shameless plug)

## Graphite

> Graphite's command line tool helps you break up large engineering tasks into a series of small, incremental code changes, each of which can be tested, reviewed, and merged independently.
> This helps you stay unblocked as an author, and get faster, more thoughtful comments from your reviewers.

- `gt branch next` and `gt branch prev`
- `gt commit amend` and `gt commit create`
- `gt stack fix`
- `gt stack test`
- When security 🚓 ever approves this: `gt stack submit` and `gt stack push`

https://docs.graphite.dev/guides/graphite-cli

## My dotfiles on GitHub

📂 [https://github.com/dlvhdr/dotfiles](https://github.com/dlvhdr/dotfiles)
