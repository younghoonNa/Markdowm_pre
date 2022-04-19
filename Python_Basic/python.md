강의 1.

3+4j = Complex 자료형, 복소수 사용.
ord("가") :  파이썬의 식별자는 유니코드 기반, 유니코드는 거의 대부분의 언어와 숫자 심볼을 가지고 있음.
                    이 ord()는 길이가 1인 문자열 자료형에 대해 유니코드 포인트를 반환.

import unicodedata -> 유니코드 데이터 라는 모듈. 유니코드의 카테고리를 알려줌.
- Lu : uppercase letters
- Ll : lowercase letters
- Lo : other case letters
- Nd : number letters

강의 2.
- REPL 이라는 기능 : 대화형 셀에서 print()를 사용하지않아도 가능.
- 파이썬에서 다루는 모든 것은 객체 취급을 받음. 따라서 키워드를 변수이름으로 사용할 수 없음.
얕은 복사 : shallow copy -> 같은 주소값을 가지게 됨.  깊은 복사 : deep copy    -> 기존 정보를 통째로 복사하여 다른 메모리에 복사.
mutable 객체 복사할 때 a = [1,3,5] , b = a , id(a) == id(b) True, b += [7] , , id(a) == id(b) True
immutble 객체 복사할 때  a = "string", b = a, id(a) == id(b) True, b = "str", , id(a) == id(b) False
- 왈루스 연산자. := return도 해줌.!


실습1. 
- bin() 이진수로 표현해줌.
- import numbers | isinstance(23, numbers.Number) -> bool, complex 형까지 모두 더해줌.
- import random,  | random.sample(범위(range(1,11), 개수(5))
- for ~ else  or  while ~ else

========================================================================================1일차
강의 1

- is : 두 변수가 참조하는 내용이 같은지, 즉 두 객체의 id가 같은지 확인.
   정수 5를 할당하였을 때는 두 id가 같으므로 is가 True, 
   float 5. 를 할당하였을 떄는 두 값은 같으나 참조하는 객체가 다르므로 False why?????????????????
-  유니코드에서 키보드로 입력하기 힘든 문자를 표현하는 방법 \u + 유니코드 포인트를 16진수로 바꿈
.encode : 출력 문자를 바이트 type으로 바꿈. 바이트 type은 출력 될 때 ASCII 문자열로 표시 ASCII 문자열은  7비트 이기 때문에 128글자 표시가능. 유니코드 포인트 값이 128보다 작을 경 그대로 표시 but 128보다 큰 바이트 들은 각 자리가 8비트로 나누어 진 후 2자리의 16진수로 표현.
same code = bytes -> decode를 통해 원래의 유니코드로 복구 가능.

Lazy Evaluation 그리고 연산자 우선순

- list comprehension에서 if else 문 사용시 for문 앞에, if 문만 사용시 for문 뒤에.


