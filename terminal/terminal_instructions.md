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

For the better zsh history completion:

- Make sure to type `cat -v` then press on the up and down arrow keys and replace `^[[A` and `^[[B` with the key codes you got for up and down arrow keys if they are different.

# Installing the Tools

```
curl -O


```

xargs brew install < tools.txt

```

```
