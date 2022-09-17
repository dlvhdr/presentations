# Modern IDEs Ecosystem

How do they work? What's the ecosystem like?

Let's get started

---

# What are IDEs?

There's a common confusion around IDEs and Text Editors.

- A **text editor** is simply a computer program and a tool used for editing plain text.
- An **IDE**, on the other hand, is a full-fledge software environment that consolidates basic developer tools required to build and test software.

### Examples for Text Editors are:

- Monaco
- Notepad
- Vim

### Examples of full-fledged IDEs:

- IntelliJ
- VSCode
- Android Studio

---

# What's at the core of modern IDEs?

LSP - the Language Server Protocol (LSP) - JSON based
Language Server - a process that provides language features
DAP - the Debug Adapter Protocol (DAP) defines the abstract protocol used between a development tool (e.g. IDE or editor) and a debugger.
Code Editor - the panel where the code is written
Workbench - all the UI that surrounds the code editor: file explorer, debug panel, source control panel etc.
Extensions - ability to add extra functionality to the IDE in the form of plugins
Language Clients - are extensions that add support for a language by running a Language Server and forwarding messages to the IDE

---

# Why LSP?

LSP reduces the number of IDEs each Language Server has to support

<img src="https://code.visualstudio.com/assets/api/language-extensions/language-server-extension-guide/lsp-languages-editors.png" class="h-80 rounded shadow bg-white p-8" />

---

# LSP Messages

An example of a LSP message saying some text was edited:

```ts
interface TextEdit {
  // The range at which the message applies.
  range: Range;
  newText: string;
}
```

Another message informing of diagnostic errors in a document:

```ts
export interface Diagnostic {
  range: Range;
  severity?: DiagnosticSeverity;
  code?: integer | string;

  /**
   * The diagnostic's message.
   */
  message: string;
}
```

---

# LSP in VSCode

<img src="https://code.visualstudio.com/assets/api/language-extensions/language-server-extension-guide/lsp-illustration.png" class="h-80 rounded shadow bg-white p-8" />

---

# Let's go over options I've researched

- monaco
- vscode
- codesandbox
- code-server
- theia
- stackblitz
- gitpod

---

# Monaco

Monaco is a **Text Editor.**
And with the additions of languages support, it can be more capable but still - not anywhere close to an IDE.

Monaco started as a browser based editor and later was pivoted to vscode which started off as a desktop app.

- Monaco is **copied** directly from the vscode codebase as a separate package.
- The devs at vscode wanted to share this piece with the community and so they released it independently of vscode
  Monaco itself remained browser based.
- NOTE: **Monaco is single file scoped**. It wasn't meant for projects and never will be.

<br />

> monaco actually comes from vscode
> ![Monaco Origin](/monaco-in-vscode-repo.png)

---

## layout: two-cols

# Visual Studio Code

As mentioned vscode started off as monaco.
It was later decided to build a full fledged desktop IDE as monaco at its base.

### VSCode is roughly divided into:

- The workbench - the surrounding UI
- The editor - monaco
- The extensions host - a separate node process to run the extensions
  - Provides an isolated environment for extensions
  - Doesn't block the UI

<img src="https://code.visualstudio.com/assets/docs/getstarted/userinterface/hero.png" class="h-80 p-8 rounded shadow" />

---

# Visual Studio Code

VSCode is an Electron app.

- Electron - a cross-platform framework to build desktop apps using web technologies
- Runs a full browser called Chromium.
  - Chrome is built on top of Chromium

### So how does monaco seem so capable?

- Monaco acts roughly like "Notepad"
- VSCode tells monaco:
  - how to add syntax highlighting
  - where are the problems in the code
  - which files to open, close, etc.
  - Most of this is done through vscode extensions
- Monaco can get smarter by using Language services (see [monaco-typescript](https://github.com/Microsoft/monaco-typescript))
  - Language services are scaled down Language Servers

---

## layout: two-cols

# VSCode Architecture

- Terminal - https://xtermjs.org/
- Electron - https://www.electronjs.org/
- [TextMate Language Grammer](https://en.wikipedia.org/wiki/TextMate#Language_Grammars)
  ```cson
  patterns = (
    {  name = 'keyword.control.untitled';
       match = '\b(if|while|for|return)\b';
    }
  )
  ```
- [monaco](https://github.com/microsoft/monaco-editor)
- [VSCode Workbench](https://github.com/microsoft/vscode/tree/main/src/vs/workbench)
  - Doesn't use a UI framework like React
  - Dependency Injection, MVVM like architecture
  - Uses plain JS
    ```js
    document.createElement("div");
    ```

<img src="https://2021.desosa.nl/projects/vscode/images/connector_view_hu25961360217c6ae4c55ac4c2eaa9b4a2_278047_1000x0_resize_q75_box_2.png" class="v-90 h-80" />

---

# codesandbox

> An instantly ready, full-featured online IDE for web development on any device with a browser
> Codesandbox was built with the idea of enabling users to code and **run** their webapps online.

- Its creator dug heavily into the vscode repo
- created a custom build that takes apart vscode and only uses what it needs
- Since codesandbox is not running in the desktop or electron, he needed to make changes

<br />

Hacking its way to a solution

- Emulate accessing the filesystem: uses <a href="https://github.com/jvilk/BrowserFS">BrowserFS</a>
- Has complex build scripts that separates vscode to different parts and uses only what it needs

<img src="https://codesandbox.io/static/video-e6a34ad1b9555966b2b8be018e27c2a2.png" class="h-60 rounded shadow" />

---

# code-server

> Run VS Code on any machine anywhere and access it in the browser

As you can see by now, _a lot_ of the online IDEs are based on vscode.
On top of providing vscode online, code server also allows users to build and run their code among other things.

<img src="https://raw.githubusercontent.com/cdr/code-server/main/docs/assets/screenshot.png" class="h-75 rounded shadow" />

---

# Theia

Theia was built by the guys at Gitpod - another company that provides a browser IDE as a service.

- Around 2017, vscode was far away from being able to run in a browser
- The guys at Gitpod decided to build their own browser based IDE.
- They started Theia around monaco.
- The entire workbench and extensions system was built from scratch - this involved A LOT of stuff.
  - Terminal, Debugger, File tree, etc.
  - Uses React and Inversify.js
- A couple of years later and Github would introduce the online version of vscode.

<img src="https://raw.githubusercontent.com/eclipse-theia/theia/master/doc/images/theia-screenshot.png" class="h-50 rounded shadow" />

---

# Theia

- At 2018, Gitpod gave the ownership of Theia so the Eclipse Open source Foundation.
- But there were still a few things missing from being OSS.
- Namely, the server code for vscode, the extensions marketplace and some key extensions developed by Microsoft.
- It is still very activley developed to this day and backed by some serious companies.
- **It's important to note that:** <br />
  - Theia is a **multitude** of orders more customizable than vscode.<br>
  - The workbench itself is a collection of extentions
  - They expose core services using DI
  - Check out the extensive API they provide: https://eclipse-theia.github.io/theia/docs/next/index.html

---

# Gitpod

- Cloud IDE as a service
- About a year ago, Gitpod announced that they are **moving away from Theia to VSCode.**
- This year those parts were open sourced except for the marketplace.
- So what did gitpod do after their move to vscode?
  - They kept the repo with their version of the vscode server but trimmed it down to only contain the missing pieces: **the marketplace**

This is open sourced under `openvscode-server` and allows installing most vscode extensions.

<img src="https://www.gitpod.io/images/index/vscode-browser.png" class="h-50 rounded shadow" />

---

# Stackblitz

- StackBlitz is an online IDE where you can create Angular & React projects that are immediately online & shareable via link **in just one click.**
- It automatically takes care of installing dependencies, compiling, bundling, and hot reloading as you type.
- Runs fully in the browser - can work offline

**The core of the tech powering StackBlitz is on source.**
The core is composed of:

1. [Turbo NPM client](https://github.com/stackblitz/core) - 5x faster than Yarn & NPM, and runs natively in-browser
2. [WebContainers](https://github.com/stackblitz/webcontainer-core/blob/main/Supported_frameworks.md) - a way to run Node.js in the browser using WebAssembly

---

# Conclusion

- Online IDEs have become a valid option for editing code
- Feature parity is there
- VSCode is insanely popular and provides a familiar user experience for web developers
- All (with minor exceptions) cloud / web-based IDEs are based on it

> Taken from the Stackoverflow 2021 developer survey
> <img src="/vscode-graph.png" class="h-70 rounded shadow" />

---

# So which are the best in class? (opinionated)

### After _my_ research I would narrow it down to:

- Gitpod's vscode based `openvscode-server`
- Theia's highly customizable vscode-like IDE

Both can run in the Desktop or the Browser and are fully open sourced.
They are welcoming PRs from the community as well.

---

# Questions?

---
