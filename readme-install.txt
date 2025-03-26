nuitka --standalone --output-dir=build-nk mtk.py 

问题记录： 

1. Couldn't get device configuration.
 https://github.com/libusb/libusb/issues/767 设备坏了,不是 libusb 问题。

     //beta包，当出现正在移除中界面，根据设备和电脑系统环境不同，需要等待的时间也不同。
	 
	 
	 
	 
python -m even "env_name"
.\"env_name"\Scripts\activate
python -m pip install --upgrade pip



requirements.txt 文件中屏蔽部分模块安装
#shiboken6
#pyside6
#capstone
#keystone


日志输出管理
utils.py中 
def logsetup(self, logger, loglevel, signal=None):
    if not signal:
        self.info = logger.info
        self.debug = logger.debug
        self.error = logger.error
        self.warning = logger.warning
    else:
        self.info = signal.emit
        self.debug = signal.emit
        self.error = signal.emit
        self.warning = signal.emit
    if loglevel == logging.DEBUG:
        logfilename = os.path.join("logs", "log.txt")
        fh = logging.FileHandler(logfilename, encoding='utf-8')
        logger.addHandler(fh)
        logger.setLevel(logging.DEBUG)
    else:
        logger.setLevel(logging.INFO)
    logger.setLevel(logging.CRITICAL) //添加代码
    self.loglevel = loglevel
    return logger, self.info, self.debug, self.warning, self.error



	 
	 
打包优化过程使用记录

pyinstaller --onedir --noconfirm --clean --add-data C:\Windows\System32\libusb*.dll:.  --add-data .\mtkclient\Windows\*.dll:. --add-data .\mtkclient\payloads:mtkclient\payloads --add-data .\mtkclient\Loader:mtkclient\Loader  --contents-directory . --name mtk mtk --uac-admin

--upx-dir H:\workspace\android_unlock\mtk\mtkclient2\dist\upx-4.2.1-win64 



cx_Freeze:
pip install cx_Freeze
python setup.py build



nuitka :
pip install nuitka

packet success: using nuitka.
//--onefile
nuitka --standalone --output-dir=build-nk mtk.py

# datas=[('mtkclient/Windows/*', '.'), ('mtkclient/payloads', 'mtkclient/payloads'), ('mtkclient/Loader', 'mtkclient/Loader')],
根据这个，手动拷贝了资源

	 