# xiaomi-mjsxj02hl
Flash custom fireware to xiaomi mjsxj02hl

### build firmware
1. git clone https://github.com/OpenIPC/builder.git
2. modify devices/hi3518ev300_lite_xiaomi-mjsxj02hl/general/overlay/usr/share/openipc/customizer.sh
   
   change
   
       fw_setenv wlanssid Router
       fw_setenv wlanpass 12345678
   
   to your wifi ssid and password
3. ./builder hi3518ev300_lite_xiaomi-mjsxj02hl


### 构建固件

1. 克隆仓库
    ```bash
    git clone https://github.com/OpenIPC/builder.git
    ```

2. 修改 `devices/hi3518ev300_lite_xiaomi-mjsxj02hl/general/overlay/usr/share/openipc/customizer.sh`

    将以下内容：
    ```bash
    fw_setenv wlanssid Router
    fw_setenv wlanpass 12345678
    ```
    修改为您的 WiFi SSID 和密码。

3. 运行构建命令
    ```bash
    ./builder hi3518ev300_lite_xiaomi-mjsxj02hl
    ```

### Installation

1. Download the latest version of the [Zadig](https://zadig.akeo.ie) program. Run it and turn on the full list of devices (`Settings -> List of all devices`).
2. Connect the camera to the USB port of the computer (the wire that comes with the kit will not work - there are no data contacts in it) with the Reset button pressed, select the `HiUSBBurn` device from the list as quickly as possible and install the `libusbK` driver for it. Most likely you will not succeed the first time (the device disappears after a few seconds, you need to do everything very quickly).
3. Download the [HiTool](http://www.hihope.org/en/download/download.aspx?mtt=36) program. After its launch, select the `Hi3518EV300` chip. Having opened the HiBurn tool, select the [partition table file](https://raw.githubusercontent.com/OpenIPC/device-mjsxj02hl/master/usb-burn.xml) and specify the path to the [fastboot](https://github.com/OpenIPC/firmware/releases/download/latest/u-boot-hi3518ev300-universal.bin), [kernel and rootfs](https://github.com/OpenIPC/firmware/releases/download/latest/openipc.hi3518ev300-nor-lite.tgz) files.
4. Press `Burn` button, agree that some sections will be erased and connect the camera to USB with the Reset button pressed. If everything was done correctly, then the flashing process will begin. This usually takes about a minute and ends with an informational success message.

### 安装步骤

1. 下载最新版本的 [Zadig](https://zadig.akeo.ie) 程序。运行它并打开设备的完整列表（`Settings -> List of all devices`）。
2. 将相机连接到计算机的USB端口（套件附带的线材不适用，因为没有数据接触点），同时按住复位按钮，从列表中尽快选择 `HiUSBBurn` 设备并为其安装 `libusbK` 驱动程序。第一次操作很可能不会成功（设备在几秒钟后消失，因此需要非常迅速地操作）。
3. 下载 [HiTool](http://www.hihope.org/en/download/download.aspx?mtt=36) 程序。启动后，选择 `Hi3518EV300` 芯片。打开 HiBurn 工具，选择 [分区表文件](https://raw.githubusercontent.com/OpenIPC/device-mjsxj02hl/master/usb-burn.xml) 并指定 [fastboot](https://github.com/OpenIPC/firmware/releases/download/latest/u-boot-hi3518ev300-universal.bin)、[内核和rootfs](https://github.com/OpenIPC/firmware/releases/download/latest/openipc.hi3518ev300-nor-lite.tgz) 文件的路径。
4. 按下 `Burn` 按钮，确认某些分区将被擦除，并在按住复位按钮的同时将相机连接到USB。如果所有步骤都正确进行，闪存过程将开始。通常需要大约一分钟时间，最后会显示成功信息。
