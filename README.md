# Outline for Sublime Text 3

This a **fork of [SublimeOutline](https://github.com/warmdev/SublimeOutline)**: Outline view for [Sublime Text](https://www.sublimetext.com/) editor.

Current '[**dev-ST3**](https://github.com/Gregory-K/SublimeOutline/tree/dev-ST3)' branch supports Sublime Text 3.

It provides a toggle argument for the 'outline' command.  
_(use the same key binding, keyboard shortcut, to open/close the Outline side-pane)_


## Try

for whomsoever wants to try it

### Install

Remove "Outline" from "Package Control", if previously installed.

Add to `Packages/User/Package Control.sublime-settings`,

```
  "ignore_vcs_packages":
  [
    "Outline"
  ]
```

#### Manual installation

1. Clone or download this repository branch.
2. Rename the cloned or extracted root folder to `Outline`.
3. Move the `Outline` folder to your Sublime Text's `Packages` folder. To find the `Packages` folder, click menu `Preferences` > `Browse Packages`.
4. Restart Sublime Text, and press `Ctrl + Shift + P` to select your preferred layout (`Browse Mode`)

_alt. way_  
1. Go to `Packages` folder (if you don't know, click menu `Preferences` > `Browse Packages`).
2. Create a directory named 'Outline' and 'cd' inside it.
3. From command line  
  `git clone --depth 1 --branch dev-ST3 https://github.com/Gregory-K/SublimeOutline .`

#### Update

Delete the contents of `Packages/Outline` folder and repeat installation,  

or

'cd' in `Packages/Outline` and  
`git fetch && git rebase` for Linux  
`git fetch; git rebase` for Windows

### Use

Toggle the Outline side-pane with a key binding,  
for example `alt + a` and outline pane on the left:  

`Packages/User/Default.sublime-keymap`

```json
{ "keys": ["alt+a"], "command": "outline", "args": {"toggle": true,"immediate": true,"other_group": "right","single_pane": true,"project": true,"layout": 1} }
```

In case you want to disable the "toggle" functionality, set `"toggle"` to `false`.


## Notes

_Note: As mentioned above, this is a "playground". Expect rebases, resets, branch renaming._

Branches:  
'[**dev**](https://github.com/Gregory-K/SublimeOutline)' : default branch for ST4 (WIP).  
'[**dev-ST3**](https://github.com/Gregory-K/SublimeOutline/tree/dev-ST3)' : branch for ST3.  
'[**dev-ST2**](https://github.com/Gregory-K/SublimeOutline/tree/dev-ST2)' : branch for ST2/ST3.

Other Branches:  
'[**upstream**](https://github.com/Gregory-K/SublimeOutline/tree/upstream)' : clone of the official upstream repository.  
'[**toggle_pane**](https://github.com/Gregory-K/SublimeOutline/tree/toggle_pane)' : just the "toggle outline command feat." applied with no other alterations to 'upstream'.

**All credits** goes to the original author [**warmdev**](https://github.com/warmdev).

Bellow resides the official README file.



---


## Outline for Sublime Text 3 (official)

### Overview

Inspired by [FileBrowser](https://github.com/aziz/SublimeFileBrowser), this package shows the outline of your file, class/function name list of your code, or table of content/toc of your markdown/LaTeX document in a sidebar-style tab.

![Screenshot](screenshot.png?raw=true "Screenshot")

### Installation

#### Install via Package Control

This package is available on [Package Control](https://packagecontrol.io/). Search for `Outline`.

#### Manual installation

1. Clone or download this repository to your hard drive using the green `Clone or download` button
2. Rename the cloned or extracted folder to `Outline`. Make sure `outline.py` is at the root of the `Outline` folder.
3. Move the `Outline` folder to your Sublime Text's `Packages` folder. To find the `Packages` folder, click menu `Preferences` > `Browse Packages`.
4. Restart Sublime Text, and press `Ctrl + Shift + P` to select your preferred layout (`Browse Mode`)

### Default layout

The outline tab can be set as a sidebar on the left or right. Press `Ctrl + Shift + P` and select either `Browse Mode: Outline (Left)` or `Browse Mode: Outline (Right)` to set your preferred layout.

If you also use [FileBrowser](https://github.com/aziz/SublimeFileBrowser), you can use both in three different layouts:

* `FileBrowser` left, `Outline` right
* `FileBrowser` top left, `Outline` bottom left
* `FileBrowser` top right, `Outline` bottom right

To use `FileBrowser` and `Outline` together, please close the `FileBrowser` sidebar first and then use the correponding `Browse Mode` command to set the layout, otherwise the `Outline` view may not work as intended.

### Color theme

`Outline` can be configured to use the current editor color scheme. To do so, change the setting below:

```json
"outline_inherit_color_scheme": true
```

`Outline` has two built-in color themes: Bright (default theme) and Dark. To switch to the Dark theme, add the following to your user settings file. Open the user settings file by "Preferences > Package Settings > Outline > Settings" (Sublime Text version 3124 or later), or "Settings - User":

```json
"outline_inherit_color_scheme": false
"color_scheme": "Packages/Outline/outline-Dark.hidden-tmTheme"
```

Remove `-Dark` or remove the entire line to return to the bright theme. To customize your own color theme, see [this issue](https://github.com/warmdev/SublimeOutline/issues/1).

### Outline content and indentation

Outline is updated when you save a file or switch between files.

Content and indentation in the `Outline` tab is controlled by the `Symbol List.tmPreferences` file (file name may differ) corresponding to the syntax of your file.

### Known issue

* This package may not work if you use a multi-column/row layout.

### License

This plugin is licensed under the MIT license.
