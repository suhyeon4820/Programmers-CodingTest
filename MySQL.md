# Programmers-CodingTest

🐢 프로그래머스 Level별 Swift 풀이 🚀

>지금은 느리지만 알고리즘 문제를 매일 꾸준히 풀어 1년뒤, 3년뒤, 5년뒤 성장하는 개발자가 되자!



### MySQL Level1 - (5/10) ![](https://us-central1-progress-markdown.cloudfunctions.net/progress/50)

---

### 1) SELECT

- 테이블에 입력된 데이터를 조회(특정 칼럼/행)하기 위해 SELECT문 사용
  - `SELECT` : 특정 칼럼 조회 - 모든 칼럼 조회 `SELECT *`
  - `FROM`: 테이블명
  - `WHERE` : 조건
  - `ORDER BY` : 오른차순 정렬 - 내림차순  `DESC` 
    - 정렬은 모든 실행이 끝난 후 데이터를 출력해주기 바로 전에 실행



###  Ex 1) 모든 레코드 조회하기

- 동물 보호소에 들어온 모든 동물의 정보를 ANIMAL_ID순으로 조회하는 SQL문을 작성해주세요.

  ```sql
  SELECT 
  * FROM ANIMAL_INS
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
  ORDER BY ANIMAL_ID
  ```



### Ex 4) 어린 동물 찾기

- 동물 보호소에 들어온 동물 중 젊은 동물[1](https://programmers.co.kr/learn/courses/30/lessons/59037#fn1)의 아이디와 이름을 조회하는 SQL 문을 작성해주세요. 이때 결과는 아이디 순으로 조회해주세요.

  ```sql
  SELECT ANIMAL_ID, NAME
  FROM ANIMAL_INS
  WHERE INTAKE_CONDITION != "Aged"
  ORDER BY ANIMAL_ID
  ```



### Ex 5) 동물의 아이디와 이름

- 동물 보호소에 들어온 모든 동물의 아이디와 이름을 ANIMAL_ID순으로 조회하는 SQL문을 작성해주세요.

  ```sql
  SELECT ANIMAL_ID, NAME
  FROM ANIMAL_INS
  ORDER BY ANIMAL_ID
  ```



### Ex 6) 여러 기준으로 정렬하기 

- 동물 보호소에 들어온 모든 동물의 아이디와 이름, 보호 시작일을 이름 순으로 조회하는 SQL문을 작성해주세요. 단, 이름이 같은 동물 중에서는 보호를 나중에 시작한 동물을 먼저 보여줘야 합니다.

  ```sql
  
  ```

