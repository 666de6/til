<!--
 * @Author: Ada J
 * @Date: 2022-07-19 22:11:46
 * @LastEditTime: 2022-07-24 16:21:18
 * @Description: 
-->
# Day 44 - zsh shortcuts - bindkey

## bindkey

**read**
```bash
# list global shortcuts
bindkey
```

```bash
# query widgets by keystroke 
bindkey <keystroke>
# for example: bindkey "^A"
# output: "^A" beginning-of-line
```
**create**
```bash
# bindkey to a widget
bindkey <keystroke> <widget>

# bind key A to key B
bindkey -s <keystroke> <keystroke>

# bind key with specific mode
bindkey -M <keymap> <keystroke> <widget>
# keymaps

# such as: bindkey -M viins u <widget>
```

**delete**
```bash
bindkey -r <keystroke>
```
## widget
```bash
# list all widgets
zle -la

# create a widget
zle -N <widget name>
```
## keymaps
* `emacs` -> Emacs emulation
* `viins` -> Vi mode - INSERT mode
* `vicmd` -> Vi mode - NORMAL mode (also confusingly called COMMAND mode)
* `viopp` -> Vi mode - OPERATOR-PENDING mode
* `visual` -> Vi mode - VISUAL mode


## help
```bash
# help document in terminal
man zshzle

# help document in pdf
man-preview zshzle
```

## tips
```bash
# get your input by char
cat -v
```