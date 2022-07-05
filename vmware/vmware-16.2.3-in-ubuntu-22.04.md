<!--
 * @Author: Ada J
 * @Date: 2022-07-05 13:47:50
 * @LastEditTime: 2022-07-05 16:07:11
 * @Description: 
-->
# How to fix VMware-16.2.3 error after upgrading ubuntu to 22.04
After I've upgraded my ubuntu from 20.04 to 22.04, I got an error when I open VMware. It can not install new required modules.

Here is how I fixed it.

1. Download VMware16.2.3 bundle
```bash
  wget https://download3.vmware.com/software/WKST-1623-LX-New/VMware-Workstation-Full-16.2.3-19376536.x86_64.bundle
```
2. Execute the bundle
```bash
  ./VMware-Workstation-Full-16.2.3-19376536.x86_64.bundle ./VMware-Workstation-Full-16.2.3-19376536.x86_64.bundle
```
3. Clone modules from github -  [vmware-host-modules(branch: workstation-16.2.3)](https://github.com/mkubecek/vmware-host-modules.githttps://github.com/mkubecek/vmware-host-modules/tree/workstation-16.2.3)
```bash 
  git clone https://github.com/mkubecek/vmware-host-modules.git
```
4. Compile modules
```bash
  cd vmware-host-modules/
  make clean && make && make install
```
5. restart VMware
```bash
  systemctl restart vmware.service
```
