#

- pandas에서 index에는 hashable객체만 올 수 있다.
- pd.date_range()
  - pd.date_range()를 통해 시작날짜를 시작인덱스로, periods로 갯수 지정가능
  - 혹은 끝나는 날짜 지정하여 인덱스 생성 가능. 

- pandas에서 bool indexing을 통해 Data Frame에 적용하게 되면 False값은 NaN으로 바뀌고 False가 있는 열은 실수로 바뀌게 된다. 모두 True인 열은 기존의 int형이라면 그대로 유지한다.
- 








