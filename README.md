# MahjongCopilot-win7

Fix from https://github.com/latorc/MahjongCopilot

Use tool https://github.com/jixunmoe/py3-win7 to install python 3.11（hadn't try under python 3.8）

＊FIX point：

mitmproxy==9.0.1（in version>=10，mitmproxy_rs has been splited from mitmproxy and cause compile "from .mitmproxy_rs import *" issue in win7）

playwright==1.29（in version>=1.30，there has "playwright._impl._api_types.Error: Browser closed" issue in win7）
still have to copy playwright._impl._errors.py from https://github.com/microsoft/playwright-python/blob/main/playwright/_impl/_errors.py because it only exist in version>=1.40.
before install chromium，you have to use command below to skip node's os check：
set NODE_SKIP_PLATFORM_CHECK=1

numpy==1.26.4（in version>=2，there has "Could not infer dtype of numpy.float32" issue in win7，it cause render fail）

add lang ZHT

＊little issue：win7 can't display unicode 16's MJ Tiles in /common/mj_helper.py；you may install supported font below https://zh.wikipedia.org/zh-tw/%E9%BA%BB%E5%B0%87%E7%89%8C_(Unicode%E5%8D%80%E6%AE%B5)

I guess the best one is win10 Segoe UI Emoji （include colored emoji）.


＊how to use：add command below after clone MahjongCopilot

git clone https://github.com/lushjohn/MahjongCopilot-win7 MahjongCopilot

set NODE_SKIP_PLATFORM_CHECK=1


also refer to：

VxKex series/win7 EXT（they're not a single project）

node（only support win7 in version<=19.X but not in 18.X）


maybe someone can tell me how to patch newest verison to support win7？
