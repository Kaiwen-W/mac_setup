Ignore `detailed_terminal_instructions.md` in files.

# Terminal with Oh My Zsh

Install Oh My Zsh:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Install PowerLevel10K theme for Oh My Zsh:

```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Open `~/.zshrc` config file and change the value of `ZSH_THEME`:

```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Install the Meslo Nerd Font:

```
brew install font-meslo-lg-nerd-font
```

Restart the terminal. You should now be seeing the PowerLevel10K configuration process. If you don’t, run: `p10k configure`.

For the p10k config:

- Prompt Style -> (3) Rainbow.
- Character Set -> (1) Unicode.
- Show current time? -> (2) 24-hour format.
- Prompt Separators -> (3) Slanted.
- Prompt Heads -> (3) Sharp.
- Prompt Tails -> (1) Flat.
- Prompt Height -> (2) Two lines.
- Prompt Connection -> (3) Solid.
- Prompt Frame -> (3) Right.
- Frame Color -> (4) Darkest.
- Prompt Spacing -> (2) Sparse.
- Icons -> (2) Many icons.
- Prompt Flow -> (2) Fluent.
- Enable Transient Prompt? -> (y) Yes.
- Instant Prompt Mode -> (1) Verbose
- Apply changes to `~/.zshrc`? -> (y) Yes

# Installing the Tools

```
curl -O https://raw.githubusercontent.com/Kaiwen-W/mac_setup/refs/heads/main/terminal/files/tools.txt
```

```
xargs brew install < tools.txt
```

Copy and paste `.example_zshrc` into `~/.zshrc`.

Note: This does not include anything from `command_line_instructions.md` so do that after.

### Notes

#### Better zsh history completion

- Make sure to type `cat -v` then press on the up and down arrow keys and replace `^[[A` and `^[[B` with the key codes you got for up and down arrow keys if they are different.

#### Amazon Q

- Open the app, sign in, allow the accessibility settings it needs.
- Then run `q integrations install input-method` in ghostty.

#### Delta

- Open `code ~/.gitconfig` and add the following:

  ```
  [core]
      pager = delta

  [interactive]
      diffFilter = delta --color-only

  [delta]
      navigate = true    # use n and N to move between diff sections
      side-by-side = true

  [merge]
      conflictstyle = diff3

  [diff]
      colorMoved = default
  ```

#### Installing a custom theme for bat

For the first time, create the following directory:

```
mkdir -p "$(bat --config-dir)/themes"
```

Then cd into it:

```
cd "$(bat --config-dir)/themes"
```

Then download the theme into this directory (note the theme must end in the `.tmTheme` extension)

- e.g. using curl -O which downloads a file at a URL into the current working directory
- ```
  curl -O https://raw.githubusercontent.com/Kaiwen-W/mac_setup/refs/heads/main/terminal/files/synthwave_84.tmTheme
  ```
  - theme taken from https://github.com/lucasvscn/synthwave-sublime

Then run: `bat cache --build`

# Run `source ~/.zshrc` to reload the config
