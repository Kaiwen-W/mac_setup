The .example_zshrc should not be copy and pasted and instead used as a reference.

# Terminal with Oh My Zsh

Based on tutorials from Josean Martinez:

- https://www.josean.com/posts/terminal-setup
- https://www.josean.com/posts/how-to-setup-alacritty-terminal
- https://www.josean.com/posts/7-amazing-cli-tools

`source ~/.zshrc` reloads the configuration

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

To reflect this change on your terminal, restart it or run `source ~/.zshrc`.

To install the Meslo Nerd Font:
 
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

# Better Zsh History Completion with Up and Down Arrows

This makes it such that you can view specific past history by searching what is at the start.

```
# Better zsh history completion
HISTFILE=$HOME/.zhistory
SAVEHIST=1000
HISTSIZE=999
setopt share_history
setopt hist_expire_dups_first
setopt hist_ignore_dups
setopt hist_verify

# completion using arrow keys (based on history)
bindkey '^[[A' history-search-backward
bindkey '^[[B' history-search-forward
```

Make sure to type `cat -v` then press on the up and down arrow keys and replace `^[[A` and `^[[B` with the key codes you got for up and down arrow keys if they are different.

# ZSH Plugins

Navigate to the home directory with: `cd`

### zsh-autosuggestions:

```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

```
brew install zsh-autosuggestions
```

then add the following to `~/.zshrc`
```
echo "source $(brew --prefix)/share/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
```

- when you want to use a suggestion, use the right arrow key.

### zsh-syntax-highlighting:

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

```
brew install zsh-syntax-highlighting
```

```
echo "source $(brew --prefix)/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc
```

Open `~/.zshrc` and modify the plugins line to:

```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
```

Then load with: `source ~/.zshrc`

### zoxide - better cd, eza - better ls:

- switched from lsd to eza because eza is faster than lsd

```
brew install zoxide eza
```

Then add the following to `~/.zshrc`:

```
alias ls="eza --color=always --long --icons=always --no-time --no-user --no-permissions --no-filesize"
alias lst="eza --color=always --tree --icons=always --level=2"

eval "$(zoxide init zsh)"
alias cd="z"
```

- lst will show a tree view only going down 2 levels

### fzf - command line fuzzy finder

- https://github.com/junegunn/fzf
- `brew install fzf`

Then in `~./zshrc` add: `eval "$(fzf --zsh)"`

Usage:

- when looking for files in command line: press `ctrl + t` to use fzf, then enter to use or use `**` then Tab
- to look at history: `ctrl + r`
- when looking at ENV variables: `unset **` then Tab
- when looking at exports: `export **` then Tab

#### fd - better find command (used here as an addon for fzf)

- https://github.com/sharkdp/fd
- allows ignoring files which are ignored by git
- `brew install fd`

Add the following to `~/.zshrc`:

```
# -- Use fd instead of fzf --

export FZF_DEFAULT_COMMAND="fd --hidden --strip-cwd-prefix --exclude .git"
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
export FZF_ALT_C_COMMAND="fd --type=d --hidden --strip-cwd-prefix --exclude .git"

# Use fd (https://github.com/sharkdp/fd) for listing path candidates.
# - The first argument to the function ($1) is the base path to start traversal
# - See the source code (completion.{bash,zsh}) for the details.
_fzf_compgen_path() {
  fd --hidden --exclude .git . "$1"
}

# Use fd to generate the list for directory completion
_fzf_compgen_dir() {
  fd --type=d --hidden --exclude .git . "$1"
}
```

- `export FZF_DEFAULT_COMMAND="fd --hidden --strip-cwd-prefix --exclude .git"` - changes the default command used by fzf to look for files and directories
  - use fd, look for hidden directories and files, don't include the current working directory and exclude any `.git` files
  - fd by default ignores any .gitignore files
- `export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"`
  - changes the assigns the ctrl + t command into the default command
- ```
  _fzf_compgen_path() {
      fd --hidden --exclude .git . "$1"
  }
  ```

  - function is for the \*\* completion when looking for files and directories

- ```
  _fzf_compgen_dir() {
  fd --type=d --hidden --exclude .git . "$1"
  }
  ```

  - function is for \*\* Tab functionality but with directories

Then run: `source ~/.zshrc`

#### fzf-git - script to look for git related things with fzf

- https://github.com/junegunn/fzf-git.sh

```
git clone https://github.com/junegunn/fzf-git.sh.git
```

Open `~/.zshrc` and add: `source ~/fzf-git.sh/fzf-git.sh`
Then run: `source ~/.zshrc`.

| **Keybind** | **Description**                     |
| ----------- | ----------------------------------- |
| `CTRL-GF`   | Look for git files with fzf         |
| `CTRL-GB`   | Look for git branches with fzf      |
| `CTRL-GT`   | Look for git tags with fzf          |
| `CTRL-GR`   | Look for git remotes with fzf       |
| `CTRL-GH`   | Look for git commit hashes with fzf |
| `CTRL-GS`   | Look for git stashes with fzf       |
| `CTRL-GL`   | Look for git reflogs with fzf       |
| `CTRL-GW`   | Look for git worktrees with fzf     |
| `CTRL-GE`   | Look for git for-each-ref with fzf  |

Done by holding down `ctrl` and pressing a key combo consecutively and quickly.

- by itself to look at the git thing mentioned
- or after:
  - git diff `keybind`
  - git switch `keybind`

#### fzf previews

Use bat and eza to preview a file/directory while using fzf.

In `~/.zshrc`:

```
show_file_or_dir_preview="if [ -d {} ]; then eza --tree --color=always {} | head -200; else bat -n --color=always --line-range :500 {}; fi"

export FZF_CTRL_T_OPTS="--preview '$show_file_or_dir_preview'"
export FZF_ALT_C_OPTS="--preview 'eza --tree --color=always {} | head -200'"

_fzf_comprun() {
  local command=$1
  shift

  case "$command" in
    cd)           fzf --preview 'eza --tree --color=always {} | head -200' "$@" ;;
    export|unset) fzf --preview "eval 'echo ${}'"         "$@" ;;
    ssh)          fzf --preview 'dig {}'                   "$@" ;;
    *)            fzf --preview "$show_file_or_dir_preview" "$@" ;;
  esac
}
```

### bat - better cat

- alternative to cat to display file contents in the terminal with syntax highlighting
- https://github.com/sharkdp/bat
- `brew install bat`

Add `alias cat="bat"` to `~/.zshrc`
To use: `bat filename.txt`

#### Installing a custom theme

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
  curl -O https://raw.githubusercontent.com/Kaiwen-W/mac_setup/refs/heads/main/terminal/synthwave_84.tmTheme
  ```
  - theme taken from https://github.com/lucasvscn/synthwave-sublime

Then run: `bat cache --build`
And add the following to `~/.zshrc`:

```
# ----- Bat (better cat) -----

export BAT_THEME=synthwave_84
```

Then run: `source ~/.zshrc`

### Delta - better git diff

- https://github.com/dandavison/delta
- `brew install git-delta`

Then open `code ~/.gitconfig` and add the following:

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

### tldr - shorter man (summary of CLI tools)

- https://github.com/tldr-pages/tldr
- `brew install tlrc`
  - use tlrc instead of tldr as we want to use the rust client
- usage: `tldr eza` - this will tell you more about eza

### thefuck - autocorrect mistyped commands

- https://github.com/nvbn/thefuck
- `brew install thefuck`

Then add the following to `~/.zshrc`: `eval $(thefuck --alias fk)`

Now if mistype a command you can run `fk` afterwards.

If there are more than one result you can use your up and down arrow keys and then enter to select the one you want.

# Amazon Q
Open the app, sign in, allow the accessibility setttings it needs. 
Then run `q integrations install input-method` in ghostty.

