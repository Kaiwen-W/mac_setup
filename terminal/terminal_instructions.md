The .example_zshrc should not be copy and pasted and instead used as a reference.

# Terminal with Oh My Zsh

Based on tutorials from Josean Martinez:

- https://www.josean.com/posts/terminal-setup
- https://www.josean.com/posts/how-to-setup-alacritty-terminal
- https://www.josean.com/posts/7-amazing-cli-tools

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

Then you will be prompted to install the Meslo Nerd Font (MesloLGS NF), accept by pressing "y" then restart the terminal.

Restart the terminal. You should now be seeing the PowerLevel10K configuration process. If you don’t, run: `p10k configure`.

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

zsh-autosuggestions:

```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

- when you want to use a suggestion, use the right arrow key.

zsh-syntax-highlighting:

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

Open `~/.zshrc` and modify the plugins line to:

```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
```

Then load with: `source ~/.zshrc`

zoxide - better cd, eza - better ls:

- switched from lsd to eza because eza is faster than lsd

```
brew install zoxide eza
```

Then add the following to `~/.zshrc`:

```
alias ls="eza --icons=always"

eval "$(zoxide init zsh)"
alias cd="z"
```

fzf - command line fuzzy finder
