# How to fix a corrupt zsh history file

Occasionally you may find you have a corrupt zsh history file preventing you from using `CTRL+R` or from using the `fc` command. 

## Corrupt ZSH history file 

If you use zsh for your shell very occasionally you may find the following message appearing indicating a corrupt history file.

```sh
zsh: corrupt history file /home/go/.zsh_history
```

This prevents searching back through the history with `CTRL+R` and editing previous commands with `fc`.

## How to fix it!

Run the following commands:

```bash
cd ~
mv .zsh_history .zsh_history_bad
strings .zsh_history_bad > .zsh_history
fc -R .zsh_history
rm ~/.zsh_history_bad
```
