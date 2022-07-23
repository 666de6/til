<!--
 * @Author: Ada J
 * @Date: 2022-07-19 22:11:46
 * @LastEditTime: 2022-07-23 18:38:52
 * @Description: 
-->
# Day 43 - zsh plugins

##  zsh-autosuggestions

**install**
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${zsh_custom:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

**config**
add it into plugin list in `~/.zshrc` 
```bash
plugins = (
  # other plugins...
  zsh-autosuggestions
)
```
**usage**
select by `right (->)`

**change style** (config in .zshrc)
```bash
zsh_autosuggest_highlight_style="fg= #ﬀ00ﬀ,bg=cyan,bold,underline"
```

## zsh-syntax-highlighting

**install**
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
**config**
add it into plugin list in `~/.zshrc` 
```bash
plugins = (
  # other plugins...
  zsh-syntax-highlighting
)
```

## autojump

**install**
```bash
brew install autojump
```

**usage**
* `j` -> alternative for `cd`
* `jo` -> open files in finder
* `j -s` -> list all records


## copypath
https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/copypath 

## copyfile
https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/copyfile

## web-search
https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/web-search

add new website(config in .zshrc)
```bash
ZSH_WEB_SEARCH_ENGINES=(yt "https://www.youtube.com/results?search_query=")
```
usage
```bash
web_search yt xxxxx
# you can config alias in .zshrc, such as "alias yt=web_search yt"
```


## macos
https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/macos