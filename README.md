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

## 파이썬 과학프로그래밍

- float. 
  - 디지털 컴퓨터는 모든 실수를 표현 할 수 없음.
  - IEEE 754애서 부동 소수점 표현은 sign bit 1bit, 유효비트 52비트 x 2의 지수승 1비트(-1023 ~ 1024) => 53비트, 
  - 파이썬의 float는 문자열 혹은 정수형을 부동소수점으로 변환이 가능하게 한다. 
  - 0.1 + 0.1 + 0.1 != 0.3인 이유는 32bit, 64bit와 같이 제한된 리소스만 사용하기 때문에 근사치로 표현을 함.
  - IEEE-754에선 유효자리 숫자는 2진수 53자리를 의미하는데, 이는 대부분 소숫점의 첫번째 0을 제외한 그 이후의 15~17자리 숫자를 가리킨다. 이 유효자리가 같은 경우 True 반환.
  - IEEE 754에서 실수는 정확한 값이 아닌 근사값으로 표현되며, 그래서 실제 값과는 다른 결과가 나올 수 있다.
    - log10(53) = 15.95 정도
    - import math 후 math.isclose 함수를 통해 비교 가능.
  - with np.printoptions(precision=3, suppress=True)
    - 이 문장을 통해 e로 표현되는 식을 풀어서 출력 가능.
    
- mutable or immutable -> 원소 변경 불가능, 삽입, 삽제 포함
  - mutable : list, dict, set, bytearray, user-definded classes(특별히 immutable로 바꾸지않는 경우에 한하여)
  - immutable : 그 외 전부 다.. (tuple, str) -> hashable

- Lazy Evaluation : 파이썬 해석기는 and와 or 평가 중간단계에서 최종값이 결정되면 더 이상 평가를 진행하지 않음.
  - A1 and A2 and .. An 일 때, 
    - Ai, 1<= i <= n 이 모두 True이면 An의값을 반환, 
    - False일 경우 첫번째로 False를 만드는 피연산자 반환.
  - A1 or A2 or .. An 일 때.
    - Ai , 1<= i <= n 이 모두 False일 때 An의 값 반환.
    - 그렇지 않다면 첫번재 True 피연산자 반환.
  - 섞여 있을 경우에는 연산자 우선순위가 and > or 이므로 and연산 모두 진행 후 or 연산 진행
  
#### bit 
- bit_length : 비트 길이 알랴줌
- `~` : 1의 보수 연산
- bin() : 2진수 알려주는 함수.
- Flaot 형의 2진수 변환. 
  - (float).hex() -> '0x1.__16진수 등장__p+3`
  - bin(16진수)   -> '0b + 2진수' -> 1.2진수 x 2^저위에 3'

#### Copy : 복사
- `=`을 통한 복사는 주소값을 같이 가짐.
- .copy()를 통한 복사는 제일 겉의 리스트만 다른 메모리에 복사 후 내부 element들의 참조는 같다.
- import copy, copy.deepcopy를 통한 복사는 아에 통째로 복사해서 다른곳에 ctrl + v

## 자료형

### Sequence type
- list   :   []               변경가능 자료형     -> mutable
- tuple  :   ()               변경 불가능 자료형 -> immutable
- str    : 유니코드 문자열     변경 불가능 자료형 -> immutable 
- bytes  : 0 ~ 255 사이 숫자들의 시퀀스,          -> immutable 
- bytearay : bytes의 변경 가능 버전              ->  mutable
- range  : range() 함수가 생성하는 변경 불가능 자료형 -> immutable
- `시퀀스 자료형의 경우 count(), index() 의 공통 method가 존재한다.`
  - count(val) : 시퀀스 자료형에서 val을 가진 element의 count를 반환
  - index(val) : 시퀀스 자료형에서 val값을 가진 element의 idx 반환. 

### Muatable vs Immutable : 변경가능 vs 변경 불가능.
- Immutable Object : 변경 불가능 Object
  - 모든 immutable 객체는 hashable 객체
  - int, float, complex, bool, string, tuple, range, frozenset, bytes 
- Mutable Object   : 변경 가능 Obejct
  - 모든 mutable객체는 Unhashable
  - list, dict, set, bytearray, user-defined-class
  - mutable 객체의 원소의 갯수 구하기 -> len(list)
  - mutable 객체의 특정 원소의 갯수 찾기 -> list.count(find)

### str
- 파이썬의 문자는 각각 Unicode code point에 대응된다. 따라서 두개의 문자를 비교할 때 내부적으로 변환되는 이 유니코드 포인트를 기반으로 비교를 한다.
- 유니코드 글자 표현시 `\u + 16진수 표현` 을 통해 입력할 수 없는 글자 표시가 가능하다.

### bytes
- str.encode('utf-8') : 문자열을 utf-8의 바이트 형식으로 변환.
- 바이트 문자열은 화면에 출력시 128비트의 ASCII 코드로 표현이 됨.
  - Unicode code point가 128보다 작은 ASCII 코드는 그대로 출력
  - 128비트 보다 클 경우 글자 하나를 1바이트 즉 8비트로 나누어진 다음 2자리의 16진수로 표현됨.

### List
- append() : object 형 원소들만 추가가능.
- extend() : iterable 원소들만 추가가능
- insert(idx, object) : idx 앞에 object 삽입
- pop(index)    : index 위치의 item 제거 후 그 item 반환
- remove(value) : value값을 가지는 element제거
- clear()       : 리스트의 모든 항목들을 제거 후 빈 리스트로
- sort()        : 리스트들의 원소들의 순서를 오름차순으로 재배치
- reverse()     : 리스트 뒤집기

### Dict()
- 모든 딕셔너리의 키는 해쉬가능한 객체 
- pop(k) : key가 k인 값 삭제 후 반환 없으면 Error
- popitem() : key-val 값 제거 후 제거된 쌍을 튜플로 반환
- Fromkeys(iterable, v = None) : iterable을 key로 사용하고 v를 val로 하는 딕셔러니 생성
- copy : shallow copy
- get : key가 있으면 value 반환 없으면 default
- items : Dict에 있는 모든 (key, value)쌍 반환
- keys() : Dict에 있는 모든 key 반환
- values() : Dict에 있는 모든 value 반환
- update() : Dict에 iterable 삽입 후 동일한 키가 있으면 새 val로 대치, 없는 경우는 새로 삽입

### set()
- set은 속도가 빠르당 {}
- add() 더하기, 원소 있으면 무시
- pop() 빼기 , 원소 있으면 제거 후 반환
- discard() , 원소 제거 없어도 에러 안남
- Remove() , 제거 후 반환 x
- intersection, union, difference, symmetric_difference
- issubset, superset 부분집합, 상위집합

### tuple
- tuple은 immutable이기 때문에 comprehension 없음. 대신 *을 붙일 경우 iterator 반환해줌.
  - next()를 통해 접근 가능
 


