<!--
 * @Author: Ada J
 * @Date: 2022-07-19 22:11:46
 * @LastEditTime: 2022-07-22 23:29:40
 * @Description: 
-->
# Day 42 - zsh-vi-mode advance

**surround**(same as vim in vscode)
`S"` / `ys"` -> add
`cs"'` -> change
`ds"` -> delete

**change ke&y**($ => L; 0 => H)

copy code below into `/usr/local/opt/zsh-vi-mode/share/zsh-vi-mode/zsh-vi-mode.zsh`
```zsh
# Your custom widget
function jump_to_beginning() {
  zvm_navigation_handler ^
}

function jump_to_end() {
  zvm_navigation_handler $
}
# The plugin will auto execute this zvm_after_lazy_keybindings function
function zvm_after_lazy_keybindings() {
  # Here we define the custom widget
  zvm_define_widget jump_to_beginning
  zvm_define_widget jump_to_end

  # In normal mode, press Ctrl-E to invoke this widget
  zvm_bindkey vicmd 'H' jump_to_beginning
  zvm_bindkey visual'H' jump_to_beginning
  zvm_bindkey vicmd 'L' jump_to_end
  zvm_bindkey vicmd 'L' jump_to_end
}
```

**setup**: zvm_conﬁg

* `ctrl + a` -> increment
* `ctrl + x` -> decrement