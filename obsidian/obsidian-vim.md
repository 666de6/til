<!--
 * @Author: Ada J
 * @Date: 2022-08-07 14:48:16
 * @LastEditTime: 2022-08-07 17:17:49
 * @Description: 
-->
# Day 54 - Using vim in obsidian

First and foremost, make sure you have the Obsidian Vim key bindings turned on -- see Editor -> Vim key bindings. Then you should install a [plugin](https://github.com/esm7/obsidian-vimrc-support) to support it -- Editor -> Community Plugins -> install Vimrc support. Create a file named `.obsidian.vimrc` in your vault root for vim key bindings.

## vim key bindings

### mode-specific
* `map` -> normal, visual, operator pending modes
* `map! / imap` -> insert
* `nmap` -> normal
* `vmap` -> visual
* `omap` -> operator pending

### non-recursive
* `noremap` -> normal, visual, operator pending modes
* `noremap! / inoremap` -> insert
* `nnoremap` -> normal
* `vnoremap` -> visual
* `onoremap` -> operator pending

### Yank to system clipboard
```bash
set clipboard=unnamed
```

### Executing Obsidian Commands with obcommand

1. list all obsidian commands
`shift + ;` get into developer mode, then type `:obcommand` you'll get in the Developer Console (Ctrl+Shift+I) the list of commands that are currently defined by the app. 

2. Execute
```bash
obcommand app:toggle-left-sidebar
```

### Mapping Obsidian Commands Within Vim

```bash
exmap back obcommand app:go-back
nmap <C-o> :back
```
tips: Use **camelCase** when naming

### Binding Space Chords
```bash
unmap <Space>
exmap dailyNote obcommand daily-notes
nmap <Space>nn :dailyNote
```

### Surround text
```bash
exmap wiki surround [[ ]]
map [[ :wiki
```
