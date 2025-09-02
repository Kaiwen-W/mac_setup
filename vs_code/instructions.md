# Extensions

Must have extensions are in `extensions.txt`.

Extensions to consider are in `consider.txt`.

cd into home directory: `cd`

```
curl -O https://raw.githubusercontent.com/Kaiwen-W/mac_setup/refs/heads/main/vs_code/instructions.md
```

To install run

```
cat extensions.txt | xargs -L 1 code --install-extension
```


## Must have (`extensions.txt`) explanations

- better comments: self-explanatory
- code spell checker: self-explanatory
- excel viewer: edit excel and CSV files in VS Code
- file utils: way of creating, duplicating, moving, renaming and deleting files and directories
- rainbow csv: highlights columns in CSV with distinct colours
- todo highlight: highlights `TODO`, `FIXME` and other annotations in code

- andromeda: dark theme
- night owl: dark theme
- synthwave: best dark theme
- custom ui style: customise VS Code's appearance using CSS
- material icon theme: material design icons

- amazon: adds Amazon Q for VS Code terminal

- auto rename tag: automatically renames paired HTML/XML tags
- css peek: adds support for `Go To Definition` and `Go To Symbol in Workspace` for css/scss/less classes and IDs found in HTML/React/Vue/Svelte/Pug/ejs/etc
- react js snippets: JavaScript and React/Redux snippets in ES7+
- html css: adds HTML `id` and `class` attribute completion
- live server: launches a development local server
- prettier: code formatter for web stuff
- pretty ts errors: makes typescript errors prettier
- stylelint: linting for CSS
- vscode-tailwindcss: tailwind CSS intellisense

- all ms-python extensions are defaults from VS Code
- python indent: correct python indentation
- ruff: linter and code formatter

## To consider (`consider.txt`) explanations

- inline fold: custom decorator that folds in Tailwind CSS className's
- vsfire: syntax highlighting, code completions and hover help for firestore security rules
- todo plus: to manage to do lists
- error lens: easier to view errors in inline code

# Keybindings / Keyboard Shortcuts

Put `keybindings.json` into `keybindings.json`

# User Settings

Put `settings.json` into `settings.json`

# Snippets

Put `python.json` into `python.json`

Also use https://snippet-generator.app/?description=&tabtrigger=&snippet=&mode=vscode to generate snippets.
