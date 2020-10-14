# Index (DB)

- 데이터베이스에서 조회 및 검색을 더 빠르게 할 수 있는 방법/기술, 혹은 이에 쓰이는 자료구조 자체를 의미하기도 한다.

- 사용 이유 : select문을 사용하여 원하는 조건의 데이터를 검색할 때, 저장된 데이터의 양이 엄청나게 많다면 검색을 위한 순회에 많은 자원과 시간이 소모될 것이다. 이때 도움이 되는게 인덱스이다.

- 자주 조회되는 Column에 대한 Index Table을 따로 만들어 SELECT 문이 들어 왔을 때 Index 테이블에 있는 값들로 결과 값을 조회해 온다.
(검색 연산의 성능을 올림)

- 사용하는 자료구조는  B+ Tree
(inner node , leaf node)
inner node는 최대 2개의 key를 가지고
leaf node는 최대 3개의 key,value값을 가질 수 있다 

![B+Tree](./B+Tree.png)