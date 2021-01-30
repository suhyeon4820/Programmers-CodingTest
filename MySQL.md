# Programmers-CodingTest

🐢 프로그래머스 Level별 Swift 풀이 🚀

>지금은 느리지만 알고리즘 문제를 매일 꾸준히 풀어 1년뒤, 3년뒤, 5년뒤 성장하는 개발자가 되자!



## MySQL Level1 - (10/10)  ![45%](https://progress-bar.dev/100)



## 1. SELECT

> 테이블에 입력된 데이터를 조회(특정 칼럼/행)하기 위해 SELECT문 사용

- `SELECT` : **특정 칼럼 조회** - 모든 칼럼 조회 `SELECT *`

- `FROM`: **테이블명**

- `WHERE` : **조건**

- `ORDER BY` : **정렬기준** - 오른차순 정렬 `ASC` <---> 내림차순  `DESC` 
  
  - 정렬은 모든 실행이 끝난 후 데이터를 출력해주기 바로 전에 실행
  
- GROUP BY : **결합기준**

- LIKE : 와일드카드를 사용해 **문자열 조회**

  - `%` : 어떤 문자를 포함한 모든 것을 조회 

    ```sql
    WHERE NAME LIKE '정%';       //'정'으로 시작하는 모든 데이터 조회
    WHERE NAME LIKE '%1';       // '1'로 끝나는 모든 데이터 조회
    WHERE NAME LIKE '%hello%';  //  중간에 'hello'를 포함하는 모든 데이터 조회
    ```

  - `_` : 한 개의 단일 문자를 의미 

    ```sql
    WHERE NAME LIKE 'test_';    // 'test'로 시작하고 하나의 글자만 더 있는 데이터 조회
    ```

- LIMIT : 조회 개수



###  Ex 1) 모든 레코드 조회하기

- 동물 보호소에 들어온 모든 동물의 정보를 ANIMAL_ID순으로 조회하는 SQL문을 작성해주세요.

  ```sql
  SELECT * 
  FROM ANIMAL_INS
  ORDER BY ANIMAL_ID;
  ```




### Ex 2) 역순 정렬하기

- 동물 보호소에 들어온 모든 동물의 이름과 보호 시작일을 조회하는 SQL문을 작성해주세요. 이때 결과는 ANIMAL_ID 역순으로 보여주세요. SQL을 실행하면 다음과 같이 출력되어야 합니다.

  ```sql
  SELECT NAME, DATETIME
  FROM ANIMAL_INS
  ORDER BY ANIMAL_ID DESC;
  ```



### Ex 3) 아픈 동물 찾기

- 동물 보호소에 들어온 동물 중 아픈 동물[1](https://programmers.co.kr/learn/courses/30/lessons/59036#fn1)의 아이디와 이름을 조회하는 SQL 문을 작성해주세요. 이때 결과는 아이디 순으로 조회해주세요.

  ```sql
  SELECT ANIMAL_ID, NAME
  FROM ANIMAL_INS
  WHERE INTAKE_CONDITION = 'Sick' 
  ORDER BY ANIMAL_ID;
  ```



### Ex 4) 어린 동물 찾기

- 동물 보호소에 들어온 동물 중 젊은 동물[1](https://programmers.co.kr/learn/courses/30/lessons/59037#fn1)의 아이디와 이름을 조회하는 SQL 문을 작성해주세요. 이때 결과는 아이디 순으로 조회해주세요.

  ```sql
  SELECT ANIMAL_ID, NAME
  FROM ANIMAL_INS
  WHERE INTAKE_CONDITION != "Aged"
  ORDER BY ANIMAL_ID;
  ```



### Ex 5) 동물의 아이디와 이름

- 동물 보호소에 들어온 모든 동물의 아이디와 이름을 ANIMAL_ID순으로 조회하는 SQL문을 작성해주세요.

  ```sql
  SELECT ANIMAL_ID, NAME
  FROM ANIMAL_INS
  ORDER BY ANIMAL_ID;
  ```



### Ex 6) 여러 기준으로 정렬하기 -

- 동물 보호소에 들어온 모든 동물의 아이디와 이름, 보호 시작일을 이름 순으로 조회하는 SQL문을 작성해주세요. 단, 이름이 같은 동물 중에서는 보호를 나중에 시작한 동물을 먼저 보여줘야 합니다.

  ```sql
  SELECT ANIMAL_ID, NAME, DATETIME
  FROM ANIMAL_INS
  ORDER BY NAME ASC, DATETIME DESC;
  ```



### Ex 7) 상위 n개 레코드-

- 동물 보호소에 가장 먼저 들어온 동물의 이름을 조회하는 SQL 문을 작성해주세요.

  ```sql
  SELECT NAME
  FROM ANIMAL_INS
  ORDER BY DATETIME 
  LIMIT 1;
  ```



## 2. SUM, MAX, MIN 집계함수

>집계함수(SUM , MAX, MIN, AVG, COUNT)는 계산을 수행하고 단일 값을 반환

- count 함수를 제외한 집계함수는 Null값을 무시
- SELECT문 또는 HAVING 절에만 사용 가능



### Ex 8) 최댓값 구하기

- 가장 최근에 들어온 동물은 언제 들어왔는지 조회하는 SQL 문을 작성해주세요.

  ```sql
  SELECT MAX(DATETIME)
  FROM ANIMAL_INS;
  ```



## 3. IS NULL

>NULL 값을 조회

- NULL은 모르는 값(값의 부재)
- NULL과 숫자 혹은 날짜를 더하면 NULL이 됨
- NULL과 어떤 값ㅇ르 비교할 때 '알 수 없음'이 반환
- `IS NOT NULL` : NULL값이 아닌 것을 조회



### Ex 9) 이름이 없는 동물의 아이디

- 동물 보호소에 들어온 동물 중, 이름이 없는 채로 들어온 동물의 ID를 조회하는 SQL 문을 작성해주세요. 단, ID는 오름차순 정렬되어야 합니다.

  ```sql
  SELECT ANIMAL_ID
  FROM ANIMAL_INS
  WHERE NAME IS NULL;
  ```



### Ex 10) 이름이 있는 동물의 아이디

- 동물 보호소에 들어온 동물 중, 이름이 있는 동물의 ID를 조회하는 SQL 문을 작성해주세요. 단, ID는 오름차순 정렬되어야 합니다.

  ```sql
  SELECT ANIMAL_ID
  FROM ANIMAL_INS
  WHERE NAME IS NOT NULL;
  ```

