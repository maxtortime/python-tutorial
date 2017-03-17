# First Python Program
- http://www.diveintopython3.net/your-first-python-program.html 을 요약한 내용입니다.

---
 ## 첫 번쨰 Python 프로그램 실행하기
- `humanize.py`를 실행해보세요!
- Python에서 함수는 `def`라는 키워드로 시작하고 다음으로 함수명과 파라미터들이 차례대로 전개됨.
- `a_kilobyte_is_1024_bytes=True`를 보면 파이썬도 `Default argument`를 지원한다는 것을 알 수 있음.
- Python의 함수는 반환 자료형을 지정하지 않음
    - `return`이 있다면 그 값을 돌려주고 아니라면 `None`을 반환함.
- Python에서는 함수를 호출할 때 파라미터의 이름을 이용할 수 [있음](https://juehan.github.io/DiveIntoPython3_Korean_Translation/your-first-python-program.html#optional-arguments)

---
## docstring 이란?
- 위의 `approximate_size` 라는 함수 아래에 `'''...'''` 형태로 된 주석들을 발견할 수 있음
- 이처럼 함수의 구조 및 동작을 설명하는 주석을 `docstring`이라고 부름.
- Pycharm을 쓰면 함수의 선언부를 만들고 `'''`를 치면 알아서 기본적인 `docstring`의 구조를 만들어주기도 함.
- `help()`라는 함수나 `__doc__`이라는 속성을 이용해 런타임 때 `docstring`을 확인할 수 있음.

---
## import 검색 경로
- https://juehan.github.io/DiveIntoPython3_Korean_Translation/your-first-python-program.html#importsearchpath
- `sys.path` 에는 `import`의 검색 경로가 리스트로 저장되어 있음
- `sys.path.insert()`를 이용해 새로운 경로를 검색 대상으로 할 수 있음

---
## 파이썬에서는 모든것이 객체?..
- 위에서 만든 `humainze` 모듈을 다른 파이썬 스크립트에서 `import` 해봅시다.
- `import humanize` 했을 경우 `humanize.approximate_size()`를 통해 호출해야 하고, `from humanize import approximate_size` 하면 그냥 함수명으로만 호출이 가능함
- 제 경우는 프레임워크를 import 하는 경우 `from ... import`를 쓰고 내장모듈이나 라이브러리를 쓰는 경우는 `import`를 씁니다.