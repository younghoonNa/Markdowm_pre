# 2022-1 파이썬과학프로그래밍 기초

`def fuction (a , b , c , / , pos1 , pos2 , * , init=1 ):` 이 존재한다고 할 떄.
  1. a,b,c는 Functional parameters : 함수가 호출 될 때 parameter의 순서대로 전달됨. 

    Functional parameter 인 이유는 `/` 앞에 왔기 때문이다.     
    
  2. pos1, pos2는 Funtional parameter or Keyword parameter 형식 : 함수가 호출될 때 `Keyword = value` 형태로 전달됨.

    둘 중 하나가 올 수 있는 이유는 `/` 와 `*` 사이에 있기 때문.
    또한 이 경우에, pos=1, pos 와 같은 형태는 Error 발생. pos, pos=1 형태는 
    
  3. init는 반드시 Keyword parameter 이다.

    이 * 뒤에 오는 Keyword Parameter는 반드시 Keyword = value 형태여야 함.
