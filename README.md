# esp32

## 使用mac烧录小智AI

一、安装前置依赖

brew install cmake ninja dfu-util ccache python3

二、获取 ESP-IDF

mkdir ~/github
cd ~/github
git clone -b v5.4.1 --recursive https://github.com/espressif/esp-idf.git  //将ESP-IDF 下载至 ~/github/esp-idf 目录

三、设置工具

cd ~/github/esp-idf
./install.sh esp32s3

四、设置环境变量

alias get_idf='. $HOME/github/esp-idf/export.sh'
source ~/.zshrc   //这样在需要用到 ESP-IDF 环境的时候，只需要在终端中执行 get_idf 即可。

五、下载和编译小智 AI 固件

cd ~/github
git clone -b v1.6.2 git@github.com:78/xiaozhi-esp32.git
cd xiaozhi-esp32

六、然后接入 ESP32-S3 开发板，执行以下命令：

get_idf
idf.py set-target esp32s3
idf.py build
idf.py flash monitor

