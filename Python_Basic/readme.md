# 2022-1 파이썬과학프로그래밍 기초

`def fuction (a , b , c , / , pos1 , pos2 , * , init=1 ):` 이 존재한다고 할 떄.
  1. a,b,c는 Positional parameters : 함수가 호출 될 때 parameter의 순서대로 전달됨. 

    Positional parameter 인 이유는 `/` 앞에 왔기 때문이다.     
    
  2. pos1, pos2는 Positional parameter or Keyword parameter 형식 : 함수가 호출될 때 `Keyword = value` 형태로 전달됨.

    둘 중 하나가 올 수 있는 이유는 `/` 와 `*` 사이에 있기 때문.
    또한 이 경우에, pos=1, pos 와 같은 형태는 Error 발생. pos, pos=1 형태는 가능
    
  3. init는 반드시 Keyword parameter 이다.

    이 * 뒤에 오는 Keyword Parameter는 반드시 Keyword = value 형태여야 함.

4.  `return 1 if n==0 else n*fact_rec_2n(n-1)` 반환에서 if else 문 사용하는 법. `:` 연산자를 빼면 됨.

5. List comprehension에서 if문을 쓰려면 다음과 같이 쓰면 된다. 

    ```
    odd_lst = [x for x in lst if x%2]                   # if문을 하나만 쓸 때 
    odd_lst = sum([x if x%2==0 else 0 for x in lst])    # if else문을 사용할 때.
    ```
     
7. set comprehension은 없다!. set은 ineterception 이나 기억하자.
