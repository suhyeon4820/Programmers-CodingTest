# Programmers-CodingTest

🐢 프로그래머스 Level별 Swift 풀이 🚀

>지금은 느리지만 알고리즘 문제를 매일 꾸준히 풀어 1년뒤, 3년뒤, 5년뒤 성장하는 개발자가 되자!



### MySQL Level3 - (4/4) ![45%](https://progress-bar.dev/100) 

---

### 1) JOIN

>여러 테이이블에 흩어져 있는 정보 중 필요한 정보만 가져와 가상의 테이블로 만들어서 결과를 보여주는 것

- `INNER JOIN` : 키 값이 있는 테이블의 컬럼 값을 비교 후 조건에 맞는 값을 가져오는 것

  ```sql
  SELECT <select_list> 
  FROM Table_A A
  INNER JOIN Table_B B
  ON A.Key = B.Key
  ```

<img src = "image\01.png" width = "200">

<br>

- Left JOIN : 

  ```sql
  SELECT <select_list>
  FROM Table_A A
  LEFT JOIN Table_B B
  ON A.Key = B.Key
  ```

  <img src = "image\02.png" width = "200">

<br>

- Right JOIN : 

  ```sql
  SELECT <select_list>
  FROM Table_A A
  RIGHT JOIN Table_B B
  ON A.Key = B.Key
  ```

  <img src = "image\03.png" width = "200">

<br>

- Outer JOIN : 

  ```sql
  SELECT <select_list>
  FROM Table_A A
  FULL OUTER JOIN Table_B B
  ON A.Key = B.Key
  ```

  <img src = "image\04.png" width = "200">

<br>

- Left Excluding  JOIN : 

  ```sql
  SELECT <select_list> 
  FROM Table_A A
  LEFT JOIN Table_B B
  ON A.Key = B.Key
  WHERE B.Key IS NULL
  ```

  <img src = "image\05.png" width = "200">

<br>

- Right Excluding  JOIN : 

  ```sql
  SELECT <select_list>
  FROM Table_A A
  RIGHT JOIN Table_B B
  ON A.Key = B.Key
  WHERE A.Key IS NULL
  ```

  <img src = "image\06.png" width = "200">

<br>

- Outer Excluding JOIN : 

  ```sql
  SELECT <select_list>
  FROM Table_A A
  FULL OUTER JOIN Table_B B
  ON A.Key = B.Key
  WHERE A.Key IS NULL OR B.Key IS NULL
  ```

  <img src = "image\07.png" width = "200">

- CROSS JOIN : Cartesian Product(카디션 곱)이라고도 하며 조인되는 두 테이블에서 곱집합을 반환

  ```
  
  ```

  

- OUTER JOIN : 조인하는 여러테이블에서 한 쪽에는 데이터가 있고 한 쪽에는 데이터가 없는 경우, 데이터가 있는 쪽 테이블의 내용을 전부 출력하는 방법

  - **LEFT OUTER JOIN** : 조인문의 **왼쪽**에 있는 테이블의 모든 결과를 가져온 후 **오른쪽** 테이블의 데이터를 매칭하고, 매칭되는 **데이터가 없는 경우** NULL을 표시한다.
  - **RIGHT OUTER JOIN** : 조인문의 **오른쪽**에 있는 테이블의 모든 결과를 가져온 후 **왼쪽의** 테이블의 데이터를 매칭하고, 매칭되는 **데이터가 없는 경우** NULL을 표시
  - **FULL OUTER JOIN** : LEFT OUTER JOIN과 RIGHT OUTER JOIN을 합친 것이다. 양쪽 모두 조건이 일치하지 않는 것들까지 모두 결합하여 출력한다

https://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins

- SELF JOIN

<br>

### 2) 

- 

- 

<br>

### Ex 1) 없어진 기록 찾기 - Right Excluding JOIN

- 천재지변으로 인해 일부 데이터가 유실되었습니다. 입양을 간 기록은 있는데, 보호소에 들어온 기록이 없는 동물의 ID와 이름을 ID 순으로 조회하는 SQL문을 작성해주세요.

  ```sql
  SELECT OUTS.ANIMAL_ID, OUTS.NAME
  FROM ANIMAL_INS INS
  RIGHT JOIN ANIMAL_OUTS OUTS
  ON INS.ANIMAL_ID = OUTS.ANIMAL_ID
  WHERE INS.ANIMAL_ID IS NULL
  ORDER BY ANIMAL_ID
  ```

<br>

### Ex 2) 있었는데요 없었습니다 - LEFT JOIN

- 관리자의 실수로 일부 동물의 입양일이 잘못 입력되었습니다. 보호 시작일보다 입양일이 더 빠른 동물의 아이디와 이름을 조회하는 SQL문을 작성해주세요. 이때 결과는 보호 시작일이 빠른 순으로 조회해야합니다.

  ```sql
  SELECT INS.ANIMAL_ID, INS.NAME
  FROM ANIMAL_INS INS
  LEFT JOIN ANIMAL_OUTS OUTS
  ON INS.ANIMAL_ID = OUTS.ANIMAL_ID
  WHERE INS.DATETIME > OUTS.DATETIME
  ORDER BY INS.DATETIME
  ```

<br>

### Ex 3) 오랜 기간 보호한 동물(1)

- 아직 입양을 못 간 동물 중, 가장 오래 보호소에 있었던 동물 3마리의 이름과 보호 시작일을 조회하는 SQL문을 작성해주세요. 이때 결과는 보호 시작일 순으로 조회해야 합니다.

  ```sql
  
  ```


<br>

### 4) 오랜 기간 보호한 동물(2)

- 입양을 간 동물 중, 보호 기간이 가장 길었던 동물 두 마리의 아이디와 이름을 조회하는 SQL문을 작성해주세요. 이때 결과는 보호 기간이 긴 순으로 조회해야 합니다.

  ```sql
  
  ```

<br>

---

- https://clairdelunes.tistory.com/22