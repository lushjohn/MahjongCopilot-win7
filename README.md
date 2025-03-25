# MahjongCopilot-win7

Fix from https://github.com/latorc/MahjongCopilot
Use tool https://github.com/jixunmoe/py3-win7 to install python 3.11（hadn't try under python 3.8）

FIX point：
mitmproxy==9.0.1（in version>=10，mitmproxy_rs has been splited from mitmproxy and cause compile "from .mitmproxy_rs import *" issue in win7）
playwright==1.29（in version>=1.30，there has "playwright._impl._api_types.Error: Browser closed" issue in win7）
add lang ZHT

git clone https://github.com/latorc/MahjongCopilot.git
git clone https://github.com/lushjohn/MahjongCopilot-win7 MahjongCopilot
cd MahjongCopilot
python -m venv venv
CALL venv\Scripts\activate.bat
pip install -r requirements.txt
set PLAYWRIGHT_BROWSERS_PATH=0
playwright install chromium
python main.py
