# MahjongCopilot-win7

Fix from https://github.com/latorc/MahjongCopilot

Use tool https://github.com/jixunmoe/py3-win7 to install python 3.11（hadn't try under python 3.8）

FIX point：

mitmproxy==9.0.1（in version>=10，mitmproxy_rs has been splited from mitmproxy and cause compile "from .mitmproxy_rs import *" issue in win7）

playwright==1.29（in version>=1.30，there has "playwright._impl._api_types.Error: Browser closed" issue in win7）

numpy==1.26.4（in version>=2，there has "Could not infer dtype of numpy.float32" issue in win7，it cause render fail）

add lang ZHT

use：add command after clone

git clone https://github.com/lushjohn/MahjongCopilot-win7 MahjongCopilot

