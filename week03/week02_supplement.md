## Python 정수에서 오버플로우?
- 파이썬은 [Arbitrary-precision](https://en.wikipedia.org/wiki/Arbitrary-precision_arithmetic)을 지원함.
- 따라서 순수하게 파이썬만 가지고 코드를 짜게 되면 오버 플로우가 일어날 일이 없음 (인터프리터를 켜고 `2 ** 200`를 해보시길)
- 하지만 `numpy, pandas` 같은 라이브러리는 C언어 스타일의 `fixed-precision` 정수를 쓰기 때문에 오버플로우가 일어나게 됨.
- http://mortada.net/can-integer-operations-overflow-in-python.html
- 지난 시간에 열심히 더했던 `sys.getsizeof`는 저장할 수 있는 최대한의 정수 바이트를 의미함.

---
## List를 큐나 스택처럼 쓰기?
- https://docs.python.org/3.5/tutorial/datastructures.html
- 오늘 할 리스트 컴프리헨션도 여기 있음..