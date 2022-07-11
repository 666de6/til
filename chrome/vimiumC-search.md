<!--
 * @Author: Ada J
 * @Date: 2022-07-11 09:54:02
 * @LastEditTime: 2022-07-11 10:45:31
 * @Description: 
-->
# Day 33 - search in VimiumC

* `o` -> show the versatile search bar
  * `link` -> open in current tab
  * `text` -> search in default search engine(you can config in [options](chrome-extension://hfjbmagddngcpeloejdejnfgbamkjaeg/pages/options.html#), default is baidu, if you want to change to google, input https://www.google.com/search?q=$s in `default search engine`)
  * `history` -> navigator to history
  * search in certain website, you can custom in [options](chrome-extension://hfjbmagddngcpeloejdejnfgbamkjaeg/pages/options.html#)
    * `g` -> google
    * `gh` -> github
    * `b` -> baidu
    * ...

* `O` -> same as `o`, but will open in a new tab
* `b` -> show search input and match results in bookmark
* `B` -> same as `b`, but will open in a new tab
* `ge` -> show search input and edit current url
* `gE` -> same as `ge`, but will open in a new tab
* `shift + t` -> show all tabs
* `/` -> search in current tab
  * `n` -> go ahead
  * `N` -> go back

**extension: how to run on chrome:/// pages?**
1. run `chrome://flags` and search `extensions-on-chrome-urls`
2. enable it
3. check the first two options in `Optional permissions` in [options](chrome-extension://hfjbmagddngcpeloejdejnfgbamkjaeg/pages/options.html#)
