---
title:  "웹 앱 빌드"
excerpt: "ML 모델을 사용하도록 웹 앱 빌드해보기"

categories:
  - Blog
tags:
  - [Blog, practice, Github, Git]

toc: true
toc_sticky: true
 
date: 2023-05-05
last_modified_at: 2023-05-05
---

* https://github.com/microsoft/ML-For-Beginners/blob/main/3-Web-App/1-Web-App/README.md 

이 링크를 따라서 ML 모델을 사용하도록 웹 앱 빌드를 해보고

무료 호스팅을 이용하여 웹으로 구현해보기



* 웹 앱 빌드 이전에 필요한것


1. 플라스크와 플라스크 사용을 위한 파이썬 가상환경 구축
2. 피클



## 플라스크와 플라스크 사용을 위한 가상 환경 구축

일단 웹앱을 구축 하기 위해서는 피클과 플라스크가 필요하다.

플라스크란 마이크로 웹 프레임워크의 일종으로 웹 서버를 구축하는데 사용된다.

먼저 플라스크 사용을 위해 Visual Studio Code에서 가상 환경을 구축하기로 했다.



<img src ="https://raw.githubusercontent.com/theRepetition/therepetition.github.io/master/images/230505/vscode_2.JPG">

일단 플라스크와 파이썬을 VSCODE의 확장탭으로 설치 해준다.


이후 작업할 폴더를 지정해주고

터미널을 열어서 가상 환경을 구축해 준다.

```
python -m venv '만들고 싶은 가상환경 폴더'
```

여기서 폴더이름은 v이며, 터미널은 파워쉘이 아닌 cmd (Comand Prompt)로 열어줘야한다.

가상 환경 폴더를 만들었으면 이제 터미널을 가상환경으로 연결 해주는데,

컨트롤+쉬프트+P 를 눌러 파이썬 인터프리터를 가상환경 폴더로 지정해준다.

그리고 py 확장자 파일을 만든 후 다음과 같은 실험용 코드를 작성해 확인한다.

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return 'asdasdasdasds'

if __name__ == '__main__':
    app.run('0.0.0.0', port=5000, debug=True)
```

 
http://localhost:5000/ 로 접속해 잘 나오는지 확인 한다.

잘 나오면 어느정도 가상환경과 플라스크가 구축이 된것이다.


