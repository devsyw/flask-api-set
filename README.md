# flask-api-set

## Setting
 - <https://code.visualstudio.com/docs/python/tutorial-flask> 참조

## 1. vscode에서 python3, flask-snippets 다운로드
![스크린샷 2022-04-22 오후 5 21 08](https://user-images.githubusercontent.com/68832928/164648602-ee7f0004-5729-41ff-9503-b53860e26304.png)
   
   
   
## 2. flask project를 구성할 폴더 생성 후 vscode로 해당 폴더 open
   
   
   
## 3. 터미널에 아래 명령을 입력
### Linux
 - sudo apt-get install python3-venv    # If needed
 - python3 -m venv .venv
 - source .venv/bin/activate
   
   
   
### macOS
 - python3 -m venv .venv
 - source .venv/bin/activate
   
   
### Windows
 - py -3 -m venv .venv
 - .venv\scripts\activate
   
   
## 4. 터미널에서 다음 명령을 실행하여 가상 환경에서 pip를 업데이트
---
python -m pip install --upgrade pip
      
   
   
## 5. VS Code 터미널에서 다음 명령을 실행하여 가상 환경에 Flask를 설치
---
python -m pip install flask
   
   
   
## 6. app.py 파일 생성 후 아래 코드 입력
``` python
from flask import Flask
from datetime import datetime
import re

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello, Flask!"

@app.route("/hello/<name>")
def hello_there(name):
    now = datetime.now()
    formatted_now = now.strftime("%A, %d %B, %Y at %X")
    match_object = re.match("[a-zA-Z]+", name)

    if match_object:
        clean_name = match_object.group(0)
    else:
        clean_name = "Friend"

    content = "Hello there, " + clean_name + "! It's " + formatted_now
    return content
```
   
   
   
## 7. 터미널에 python -m flask run 명령으로 서버 실행
   
   
   
## 8. http://127.0.0.1:5000 접속. 끝. 서버 종료는 실행 터미널에서 ctrl+c
   