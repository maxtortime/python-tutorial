# First Python Program
- http://www.diveintopython3.net/your-first-python-program.html 을 요약한 내용입니다.

## 첫 번쨰 Python 프로그램 실행하기
- 아래 코드를 `humanize.py`라고 저장하고 실행해보세요!
```python
SUFFIXES = {1000: ['KB', 'MB', 'GB', 'TB', 'PB', 'EB', 'ZB', 'YB'],
            1024: ['KiB', 'MiB', 'GiB', 'TiB', 'PiB', 'EiB', 'ZiB', 'YiB']}

def approximate_size(size, a_kilobyte_is_1024_bytes=True):
    '''Convert a file size to human-readable form.

    Keyword arguments:
    size -- file size in bytes
    a_kilobyte_is_1024_bytes -- if True (default), use multiples of 1024
                                if False, use multiples of 1000

    Returns: string

    '''
    if size < 0:
        raise ValueError('number must be non-negative')

    multiple = 1024 if a_kilobyte_is_1024_bytes else 1000
    for suffix in SUFFIXES[multiple]:
        size /= multiple
        if size < multiple:
            return '{0:.1f} {1}'.format(size, suffix)

    raise ValueError('number too large')

if __name__ == '__main__':
    print(approximate_size(1000000000000, False))
    print(approximate_size(1000000000000))
```
- Python에서 함수는 `def`라는 키워드로 시작하고 다음으로 함수명과 파라미터들이 차례대로 전개됨.
- `a_kilobyte_is_1024_bytes=True`를 보면 파이썬도 `Default argument`를 지원한다는 것을 알 수 있음.
- Python의 함수는 반환 자료형을 지정하지 않음
    - `return`이 있다면 그 값을 돌려주고 아니라면 `None`을 반환함.
- Python에서는 함수를 호출할 때 파라미터의 이름을 이용할 수 [있음](https://juehan.github.io/DiveIntoPython3_Korean_Translation/your-first-python-program.html#optional-arguments)


## docstring 이란?
- 위의 `approximate_size` 라는 함수 아래에 `'''...'''` 형태로 된 주석들을 발견할 수 있음
- 이처럼 함수의 구조 및 동작을 설명하는 주석을 `docstring`이라고 부름.
- Pycharm을 쓰면 함수의 선언부를 만들고 `'''`를 치면 알아서 기본적인 `docstring`의 구조를 만들어주기도 함.
- `help()`라는 함수나 `__doc__`이라는 속성을 이용해 런타임 때 `docstring`을 확인할 수 있음.

## import 검색 경로
- https://juehan.github.io/DiveIntoPython3_Korean_Translation/your-first-python-program.html#importsearchpath
- 나머지는 책을 직접 보면서 하는게 빠를 것 같네요.. 