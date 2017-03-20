# Python 설치 및 개발환경 세팅
- Python 3.5.3 버전으로 진행합니다.

---

## 목차
- Windows
- Unix 계열 (pyenv)
- pip 사용법
- virtualenv 사용법

---

## Windows
- https://docs.python.org/3.5/using/windows.html#installing-python
- https://docs.python.org/3.5/using/windows.html#python-launcher-for-windows

---

## Unix 계열
기본적으로 Python이 설치되어 있기는 하지만 [pyenv](https://github.com/pyenv/pyenv)를 사용하면 더욱 쉽게 설치 및 버전 별 관리가 가능함.

- https://github.com/pyenv/pyenv-installer#github-way-recommended
- `pyenv install 3.5.3`

---

## pip 사용법
- [PyPi](https://pypi.python.org)에 있는 Python 패키지들을 다운로드하는 도구
- https://pip.pypa.io/en/stable/
- Python 2.7.9 나 Python 3.4 부터는 이미 pip가 설치되어 있지만 만약 그렇지 않은 시스템이라면 https://pip.pypa.io/en/stable/installing/#installing-with-get-pip-py 참고

---

### 패키지 설치하기
- https://pip.pypa.io/en/stable/user_guide/#installing-packages
- 기본적으로 패키지명을 입력해서 설치할 수 있음
    ```sh
    $ pip install SomePackage            # latest version
    $ pip install SomePackage==1.0.4     # specific version
    $ pip install 'SomePackage>=1.0.4'   # minimum version
    ```
- PyPi에 올라와 있는 패키지 말고도 VCS 프로젝트 URL 및 소스 코드 저장소, 로컬 디렉토리를 입력해서 설치할 수 있음(https://pip.pypa.io/en/stable/reference/pip_install/#argument-handling)

---

### pip freeze
- requirements 파일 format으로 현재 설치된 패키지 목록을 출력해줌
    ```sh
    $ pip freeze    # 목록 출력
    $ pip freeze > requirements.txt     # 목록을 파이프를 이용해 파일로 만듬
    ```
- 위에서 만든 requirements 파일을 이용해 패키지들을 설치할 수 있음
- `pip install -r requirements.txt`

---

## pip practice
1. `pep8` 패키지를 설치해보세요.
2. `pep8` 패키지를 포함한 requirements 파일을 만들어보세요.
3. `pep8` 패키지를 삭제하세요. (`pip uninstall pep8`)
4. requirement 파일을 이용해 패키지를 설치해보세요. (`pip install -r requirements.txt`)

---

## virtualenv
- `virtualenv`는 고립된 파이썬 환경을 만드는 데 사용하는 도구
- `foo` 패키지의 버전 1이 필요한 패키지가 있고 `foo`의 버전 2가 필요한 패키지가 각각 존재한다고 가정할 때 두 패키지를 동시에 한 파이썬 환경에 설치했을 경우 다른 패키지를 업그레이드 할 수 없는 사태가 발생한다. (https://virtualenv.pypa.io/en/stable/ 참고)

---

### 설치 및 사용법
- pip를 이용해 설치하면 됨.
    ```sh
    $ pip install virtualenv
    $ virtualenv foo
    $ source foo/bin/activate # Windows는 foo\Scripts\activate.bat
    $ deactivate # 비활성화
    ```
- 제거 시 그냥 virtualenv 폴더를 제거하면 됨.

---

## pyenv-virtualenv
- 위에서 이용한 `pyenv`를 기반으로 `virtualenv`를 사용할 수 있는 유용한 라이브러리 (https://github.com/pyenv/pyenv-virtualenv)
- 사용법(https://github.com/pyenv/pyenv-virtualenv#usage)

---

## Pratice virtualenv
- `virtualenv` 혹은 `pyenv-virtualenv` 아무거나 이용하셔도 됩니다.
- 연습할 디렉토리를 하나 생성하세요.
    1. `foo` 라는 가상환경을 생성하고 활성화 하세요.
    2. `ipython` 이라는 패키지를 설치하세요.
    3. `ipython` 을 터미널에 쳐서 가지고 놀아보세요.
    4. 가상환경을 비활성화하고 더이상 `ipython`이 동작하지 않음을 확인하세요.
    5. `foo2`라는 가상환경을 생성하고 활성화 하세요.
---

6. `flask`라는 패키지를 설치하세요.
7. 아래 코드를 `hello.py`라는 파일로 만들고 `python hello.py`로 실행해보세요.
```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
return "Hello World!"

if __name__ == "__main__":
app.run()
```

---

8. 웹서버가 동작하는 걸 확인하고 종료한 후 `foo2`환경을 비활성화하세요.
9. `foo` 환경을 활성화하고 `python hello.py`를 실행하세요.
10. `foo2/bin/python hello.py`를 실행하세요.
11. `foo3`이라는 가상환경을 만들고 `foo2` 와 똑같은 패키지를 설치헤보세요.
