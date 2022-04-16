# 여러가지 파이썬 소스코드 모음
- 파이썬에서 함수를 호출 할 때 Argument를 객체로 전달하는 것이 아닌, Argument와 바인딩 된 주소가 Method의 Parameter에게 전달 됨.
  - 파이썬이 다루는 모든 것은 객체. 

- 파이썬의 연산자 우선순위
  |순위|연산자|  
  |---|---|  
  |1|()|
  |2|**|  
  |3|+x, -x, ~x|  
  |4|*, /, //, %|  
  |5|+, -|  
  |6|<<. >>|  
  |7|&|  
  |8|^|  
  |9|||  
  |10|==, !=, >, >=, <, <=, is, is not, not in|  
  |11|not|  
  |12|and|  
  |13|or|

## 파이썬 기초같지않은 기초 프로그래밍

- float.
  - 파이썬의 float는 문자열 혹은 정수형을 부동소수점으로 변환이 가능하게 한다. 
  - 0.1 + 0.1 + 0.1 != 0.3인 이유는 32bit, 64bit와 같이 제한된 리소스만 사용하기 때문에 근사치로 표현을 함.
  - IEEE-754에선 유효자리 숫자는 2진수 53자리를 의미하는데, 이는 대부분 소숫점의 첫번째 0을 제외한 그 이후의 15~17자리 숫자를 가리킨다. 이 유효자리가 같은 경우 True 반환.
    - log10(53) = 15.95 정도
    - import math 후 math.isclose 함수를 통해 비교 가능.

- mutable or immutable -> 원소 변경 불가능, 삽입, 삽제 포함
  - mutable : list, dict, set, bytearray, user-definded classes(특별히 immutable로 바꾸지않는 경우에 한하여)
  - immutable : 그 외 전부 다.. -> hashable

- Lazy Evaluation : 파이썬 해석기는 and와 or 평가 중간단계에서 최종값이 결정되면 더 이상 평가를 진행하지 않음.
  - A1 and A2 and .. An 일 때, 
    - Ai, 1<= i <= n 이 모두 True이면 An의값을 반환, 
    - False일 경우 첫번째로 False를 만드는 피연산자 반환.
  - A1 or A2 or .. An 일 때.
    - Ai , 1<= i <= n 이 모두 False일 때 An의 값 반환.
    - 그렇지 않다면 첫번재 True 피연산자 반환.
  - 섞여 있을 경우에는 연산자 우선순위가 and > or 이므로 and연산 모두 진행 후 or 연산 진행
  
- bit_length : 비트 길이 알랴줌

- tuple은 immutable이기 때문에 comprehension 없음. 대신 *을 붙일 경우 iterator 반환해줌.
  - next()를 통해 접근 가능
 
 - mutable 객체의 원소의 갯수 구하기 -> len(list)
 - mutable 객체의 특정 원소의 갯수 찾기 -> list.count(find)

