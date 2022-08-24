<!--
 * @Author: Ada J
 * @Date: 2022-08-24 10:48:51
 * @LastEditTime: 2022-08-24 11:05:48
 * @Description: 
-->
# How to Record Your Screen in Ubuntu With SimpleScreenRecorder?

## install
run the following command in terminal
```bash
sudo apt install simplescreenrecorder
```
## setting
You can use default setting or custom by following the promote

## issue
After I installed successfully, I got a black screen after recording. 

* **problem is:**  
The reason behind that behavior is quite simple. My OS(ubuntu 22.04 with gdm3) by default uses the Wayland Compositor and not Xorg. But SSR was built for Xorg so it’s not able to communicate with the Wayland server to grab your display content. That simply ends up in a black screen.
* **solution is:**  
  To solve the problem, you can tell Ubuntu not to use the Wayland Compositor. In that case, Ubuntu will use the Xorg Server. To achieve that you can edit the “custom.conf” located under “/etc/gdm3”.

  In line 7 you will find an entry called “WaylandEnable=false” which is commented out. 
  ```bash
  ...
  #WaylandEnable=false
  ...
  ```
  Just edit the file as root / with sudo and remove the starting “#” so that the config look like below.
  ```bash
  ...
  WaylandEnable=false
  ...
  ```
  After saving the configuration, reboot your system and check the SSR functionality.