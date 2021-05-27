# VS Code

* `settings.json` => `~/.config/Code/User/settings.json`
  * basic editor behaviour (Atom like feeling)
  * Python related settings
* `keybindings.json` => `~/.config/Code/User/keybindings.json`
  * convert case line in Atom
 
## Per directory specific settings
Create `.vscode/settings.json` in the target directory. These settings override globals and are automatically picked up when starting the editor with `code .`.
Add `.vscode/` to `.git/info/exclude`, if it's not already in `.gitignore`, to exlude your local settings from versioning.

### 1st party paths not resolved (intellisense not working)
The below should help when you start VS Code from terminal with `code .` and intellisense is not working for 1st party imports.

Add `python.analysis.extraPaths` to `.vscode/settings.json` with path(s) to your main code dir.E.g. if you have a Django project called "my_app" then use a path like `"python.analysis.extraPaths": ["/tmp/code/my_app/my_app"]`.

Source
* [Enable IntelliSense for custom package locations](https://code.visualstudio.com/docs/python/editing#_enable-intellisense-for-custom-package-locations)
* [Import “Path.to.own.script” could not be resolved Pylance](https://stackoverflow.com/questions/65252074/import-path-to-own-script-could-not-be-resolved-pylance-reportmissingimports)



## Shortcuts

https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf


### Navigation

| Action                         | Shortcut         |
| :----------------------------- |:---------------- |
| Toggle Sidebar                 | Ctrl + B         |
| Toggle Sidebar Focus           | Ctrl + 0         |
| Toggle Editor Focus            | Ctrl + 1         |
| Toggle bottom Panel            | Ctrl + J         |
| Toggle Problems Panel          | Ctrl + Shift + M |
| Go to Line                     | Ctrl + G         |
| Go to File                     | Ctrl + P         |
| Go to Symbol                   | Ctrl + Shift + O |
| Go to Definition               | F12              |
| Undo Cursor Position           | Ctrl + U         |


#### Search

| Action                         | Shortcut         |
| :----------------------------- |:---------------- |
| Go to next search result       | F4               |
| Go to previous search result   | Shift + F4       |


### Activity bar

| Action                         | Shortcut         |
| :----------------------------- |:---------------- |
| Show Explorer                  | Ctrl + Shift + E |
| Show Source Control            | Ctrl + Shift + G |
| Show Extensions                | Ctrl + Shift + X |


### Aux

| Action                         | Shortcut         |
| :----------------------------- |:---------------- |
| Live Markdown Edit & Preview   | Ctrl + K V       |


## Themes

`Atom One Dark`


## Other Resources
 * https://github.com/microsoft/vscode-tips-and-tricks
 * https://github.com/viatsko/awesome-vscode
 * https://vscodecandothat.com/
