# MahjongCopilot-win7

Fix from https://github.com/latorc/MahjongCopilot

Use tool https://github.com/jixunmoe/py3-win7 to install python 3.11（hadn't try under python 3.8）


## FIX point：

* mitmproxy==9.0.1（in version>=10，mitmproxy_rs has been splited from mitmproxy and cause compile "from .mitmproxy_rs import *" issue in win7）


* playwright==1.29（in version>=1.30，there has "playwright._impl._api_types.Error: Browser closed" issue in win7）

still have to copy playwright._impl._errors.py from https://github.com/microsoft/playwright-python/blob/main/playwright/_impl/_errors.py because it only exist in version>=1.40.

* before install chromium，you have to use command below to skip node's os check：

set NODE_SKIP_PLATFORM_CHECK=1


* numpy==1.26.4（in version>=2，there has "Could not infer dtype of numpy.float32" issue in win7，it cause render fail）


* add lang ZHT


* little issue：you may install supported MJ Tile font below https://zh.wikipedia.org/zh-tw/%E9%BA%BB%E5%B0%87%E7%89%8C_(Unicode%E5%8D%80%E6%AE%B5)

I guess the best one is win10 Segoe UI Emoji （include colored emoji，but still display colorless）.

* still not fix：pyinstaller can't package _errors.py into exe file（I think maybe there has command to support this？）


### how to use first：

```batch
git clone https://github.com/latorc/MahjongCopilot.git
git clone https://github.com/lushjohn/MahjongCopilot-win7 MahjongCopilot
cd MahjongCopilot
python -m venv venv
CALL venv\Scripts\activate.bat
pip install -r requirements.txt
git clone https://github.com/microsoft/playwright-python/blob/main/playwright/_impl/_errors.py venv\Lib\site-packages\playwright\_impl
set NODE_SKIP_PLATFORM_CHECK=1
set PLAYWRIGHT_BROWSERS_PATH=0
playwright install chromium
python main.py
```
### how to use after：

```batch
cd MahjongCopilot
CALL venv\Scripts\activate.bat
set NODE_SKIP_PLATFORM_CHECK=1
set PLAYWRIGHT_BROWSERS_PATH=0
python main.py
```

## also refer to：

* VxKex series/win7 EXT（they're not a single project）

* node（only support win7 in version<=19.X but not in 18.X）


maybe someone can tell me how to patch newest verison to support win7？
