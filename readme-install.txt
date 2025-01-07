nuitka --standalone --output-dir=build-nk mtk.py 

问题记录： 

1. Couldn't get device configuration.
 https://github.com/libusb/libusb/issues/767 设备坏了,不是 libusb 问题。

     //beta包，当出现正在移除中界面，根据设备和电脑系统环境不同，需要等待的时间也不同。