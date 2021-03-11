# FZF Command Bookmarks

This is a kind replacement of the deceased [marker](https://github.com/pindexis/marker).
It uses `fzf` and `highlight` - its only requirements.

It lets you add a command in the bookmarks and then search through your bookmarks.
Never forget

![Screenshot of bookmark show](screenshot_show.png)

## Installation

For ZSH you can use any plugin manager, for example for [antigen](https://github.com/zsh-users/antigen)
put in your `.zshrc` before `antigen apply`:

```bash
antigen bundle dzervas/fzf-command-bookmarks
```

For bash or if you don't want to use a plugin manager with ZSH, you can just
clone the project somewhere cozy and source the script from your `.bashrc` or
`.zshrc`:

```bash
source ~/Lab/fzf-command-bookmarks/fzf-command-bookmarks.sh
```

## Key assignment

### Bash

```bash
# Shortcut to trigger the bookmark addition functionality
bind -x "\"\C-k\":_fzf_command_bookmark_add"
# Shortcut to trigger the bookmark showing functionality
bind -x "\"\C-@\":_fzf_command_bookmark_show"
```

### Zsh

```zsh
# Shortcut to trigger the bookmark addition functionality
zle -N fzf-command-bookmark-add-widget _fzf_command_bookmark_add
bindkey '^k' fzf-command-bookmark-add-widget
# Shortcut to trigger the bookmark showing functionality
zle -N fzf-command-bookmark-show-widget _fzf_command_bookmark_show
bindkey '^@' fzf-command-bookmark-show-widget
```

## Saving format

The bookmarks are saved in a file (`~/.fzf-command-bookmarks.txt` by default,
managed by `FZF_COMMAND_BOOKMARKS_FILE`) in the following notation:

```
my awesome command##This is the title
```

---

There is currently both bash and zsh support but more tests should be conducted
(old versions, weird setups, etc.). I don't use fish, so feel free to open an MR.
