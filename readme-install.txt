nuitka --standalone --output-dir=build-nk mtk.py 

�����¼�� 

1. Couldn't get device configuration.
 https://github.com/libusb/libusb/issues/767 �豸����,���� libusb ���⡣

     //beta���������������Ƴ��н��棬�����豸�͵���ϵͳ������ͬ����Ҫ�ȴ���ʱ��Ҳ��ͬ��
	 
	 
	 
	 
python -m even "env_name"
.\"env_name"\Scripts\activate
python -m pip install --upgrade pip



requirements.txt �ļ������β���ģ�鰲װ
#shiboken6
#pyside6
#capstone
#keystone


��־�������
utils.py�� 
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
    logger.setLevel(logging.CRITICAL) //��Ӵ���
    self.loglevel = loglevel
    return logger, self.info, self.debug, self.warning, self.error



	 
	 
����Ż�����ʹ�ü�¼

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
����������ֶ���������Դ

	 