# blocklight: Pseudo visual programming extension for Visual Studio Code
Turn any code into visual understanding using highlight colors and a set of rules, for example:
* first highlight on "function" (blue block): to visualize function name and inputs line (identify beginning of blocks at a glance)
* second highlight on "return" (purple block): for function outputs
* third highlight on an  important variable (dark green): See its usage in all you files (if you don't reuse the variable name locally!)
* ...

All highlighted words are saved in your local project file (.vscode\highlighted.json).

So it's a different set and order for each project and language you use (first added will be blue, second is purple, etc).

Since you add your words to the list by selecting and applying highlight, you can use it to track words in any text.

![screencast](https://github.com/rsbondi/highlight-words/raw/master/images/highlight.gif)

This extension is adapted from [highlight-words](https://github.com/rsbondi/highlight-words) and the sample VS code extension decorator-sample, inspired by atom-quick-highlight.

I always wanted to "see" libraries and variables.

So far, all attempts at programming visually I've seen are dommed by static definitions (blocks or nodes are based on a language version, exemple: python 2) and visual limitations for code abstractions (classes?, extensions?, callbacks? threads? ...).

I took it the other way around, starting with any code and adding visual sense to be able to visualize blocks/nodes in your mind.

A highlighting tool was a first step, but it needed a set of rules to transform code to mind visualization making sense.

# Very Detailed Usage

* If you found this page on the web and don't get how to test this marvelous free tool, you need to install Visual Studio Code (free, any platform).
* Click on the squarish logo on the left (Extensions) or CTRL+SHIFT+X and search for blocklight, click once on it
* In the blocklight page, click on the "Install" button then on "reload" button to restart VS Code with this extension
* Open a project folder or a simple file and select some word (double click)
* If folder doesn't have a `.vscode` folder, you need to create it from VSCode (Windows Explore can't create folders starting with a dot)
* You can add words by chosing "Highlight Current" from the command pallet (CTRL+SHIFT+P) or simply CTRL+ALT+C, this will highlight the word at the cursor or the selection and all other words in all open files.
* To stop highlighting, choose "Highlight Remove", then the desired word or expression, or all
* You may also remove all from the command "Highlight Remove All" (CTRL+ALT+D) without the prompt for selection
* To highlight using regular expression choose "Highlight Expression" (CTRL+ALT+R) and enter expression(slashes optional, can ignore case with `/expression/i`(g flag is automatic, i flag accepted, all others ignored).  
* To highlight with options choose "Highlight Selection with Options" and choose `whole word`, `ignore case` or `both` when presented
* You can set the mode for "Highlight Current" from the "Set Highlight Mode" command.  The default can be set in the configuration.
* When you close and come back, highlights are not lit up by default, enter CTRL+ALT+O to highlight previous words
* At any time your file remains untouched, all highlights are stored near your file and processed on the fly by this VS Code extension

# Additional Configuration
The following option can be configured

`highlightwords.defaultMode`: the initial mode when initialized. 0=default, 1=whole word, 2=ignore case, 3=whole word and ignore case

In package.json
```
"highlightwords.colors": [
{    "light": "#2C589C",        "pen": "white"},
{    "light": "#c411ff",        "pen": "white"},
{    "light": "#068587",        "pen": "white"},
{    "light": "#5FB97D",        "pen": "black"},
{    "light": "#FFD137",        "pen": "black"},
{    "light": "#ED553B",        "pen": "white"},
{    "light": "#97ff28",        "pen": "black"},
{    "light": "#ff2897",        "pen": "white"},
{    "light": "#28fff4",        "pen": "black"},
{    "light": "#6da3ff",        "pen": "white"},
{    "light": "#fff06d",        "pen": "black"},
{    "light": "#ff6d88",        "pen": "black"}
],

"highlightwords.defaultMode": {
    "default": 0
}

```


# TODO
Feel free to fork and improve it to be able to:
* automatically highlights the same types of code (classes, function, loops)
* builds automatically a markov dictionary to analyze code completion
* generates a diagram of classes and functions based markov dictionary (or color neighborhood)
* ... more, to finally get some decent free visual programming :)

# BUT HOW?
* If you don't know how to develop a Visual Studio Extension, visit https://code.visualstudio.com/docs/extensions/example-hello-world
* Then fork this repo on github
* git clone it in C:\<user>\.vscode\extensions (or linux/mac path for VS Code extensions)
* Delete my extension folder from the same location to prevent conflict of commands and shortcuts with the same names
* Open your fork folder in VS Code
* Hit F5 to debug it (it opens a new VS Code worspace with your forked extension loaded)
* Make changes to code, when ready commit locally then push to github (VS Code "..." menu or github desktop or else)
* In your github fork page, click Pull requests then "New pull request" green button, then "Create a pull request"
* Congrats, you just helped everybody!
