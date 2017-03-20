# 파이썬의 자료형
- [책 링크](https://juehan.github.io/DiveIntoPython3_Korean_Translation/native-datatypes.html)
- 지난 시간에 파이썬의 **모든 값은 object** 라고 배움.
- 따라서 이 장에서 다룰 타입 말고도 더 많은 타입들이 있음

---
## Boolean
- 참(`True`)과 거짓(`False`) 중 하나를 의미하는 데이터 타입
- `True`는 1이고 `False`는 0이긴 하지만 숫자로 쓰는 건 별로 권장하지 않음.
- C처럼 0만 False로 판정되고 0이 아닌 숫자는 True가 된다.

---
## Numbers
- Python에서는 정수형과 실수형을 모두 지원함
- `int()` 함수를 통해 실수나 문자열로 된 정수를 정수로 바꿀 수 있음
    - 이 경우 소수점은 그냥 버림
- `float()` 함수를 통해 정수나 문자열로 된 실수를 정수로 바꿀 수 있음
    - 소수점 15자리까지만 표현 가능

---
## 사칙연산 하기
