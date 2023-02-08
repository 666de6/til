<!--
 * @Author: Ada J
 * @Date: 2023-02-08 16:20:27
 * @LastEditTime: 2023-02-08 16:58:19
 * @Description
-->

# Build a minimum local http experiment on Ubuntu

## Install OpenResty

```bash
# Install package that needed when import GPG public key.
sudo apt-get -y install --no-install-recommends wget gnupg ca-certificates

# Add GPG public key
wget -O - https://openresty.org/package/pubkey.gpg | sudo apt-key add -

# Install add-apt-repository
sudo apt-get -y install --no-install-recommends software-properties-common

# Add openresty repository
sudo add-apt-repository -y "deb http://openresty.org/package/ubuntu $(lsb_release -sc) main"

# Update apt-get
sudo apt-get update

# Install OpenResty
sudo apt-get -y install openresty

# Clone project(many thanks to @chronolaw)
git clone https://github.com/chronolaw/http_study

# Run!!
cd http_study/www/    #脚本必须在www目录下运行，才能找到nginx.conf
./run.sh start        #启动实验环境
./run.sh list         #列出实验环境的Nginx进程
./run.sh reload       #重启实验环境
./run.sh stop         #停止实验环境
```

## Edit hosts(`/etc/hosts`) if you wanna access by domain

```bash
# example
127.0.0.1	www.xxxx.com
```

## Install Wireshark

```bash
# Add Wireshark repository
sudo add-apt-repository ppa:wireshark-dev/stable

# Update the repository
sudo apt update

# Install Wireshark
sudo apt install wireshark

# Run!!
sudo wireshark
```

Now,you can capture packages by Wireshark. Go and explore more about http!!
