<!--
 * @Author: Ada J
 * @Date: 2022-08-05 16:18:37
 * @LastEditTime: 2022-08-05 16:34:47
 * @Description: 
-->
# Connect to specific WiFi network by shortcut(on ubuntu 22.04)

First of all, list all available WiFi networks, and **get the UUID** which you want to connect to.
```bash
nmcli c
```
Second, connect to the network by UUID for **test**.
```bash
nmcli c up uuid 9a2e76de-319a-4486-b71b-646492b5ffcc
```
Last one, go to system setting,  `KeyBoard` => `Keyboard Shortcuts`=> `Custom Shortcuts`=> copy and paste the command above. The text field is what Bash will run. Choose your keyboard shortcut.

