# Programmers-CodingTest

🐢 프로그래머스 Level별 Swift 풀이 🚀

>지금은 느리지만 알고리즘 문제를 매일 꾸준히 풀어 1년뒤, 3년뒤, 5년뒤 성장하는 개발자가 되자!



### MySQL Level2 - (7/11) ![45%](https://progress-bar.dev/60) 

---

### 1) SUM, MAX, MIN 집계함수

>집계함수(SUM , MAX, MIN, AVG, COUNT)는 계산을 수행하고 단일 값을 반환

- COUNT 함수를 제외한 집계함수는 Null값을 무시
- SELECT문 또는 HAVING 절에만 사용 가능
- DISTINCT : 중복 데이터를 제거
- IN : "OR"의 이미를 가지고 있어서 하나의 조건만 만족해도 조회가 가능

<br>

### 2) IS NULL

- `IS NULL` : NULL값을 조회
- `IS NOT NULL` : NULL 값이 아닌 것을 비교

- `IFNULL`: 필드의 값이 NULL을 반환할 때 다른 값으로 대체 -> **IFNULL(필드명, "대체할 값")**

<br>

### 3) GROUP 연산

>GROUP BY는 테이블에서 소규모 행을 그룹화하여 합계, 평균, 최댓값, 최솟값 등 계산 가능

- `HAVING` : 조건문 기능

- `ORDER BY` : 정렬 기능 

- 집계합수

  - COUNT(*) : NULL값 포함 모든 행 수
  - COUNT(칼럼명) : NULL값 제외한 행 수

  | 집계함수      | 설명                   |
  | ------------- | :--------------------- |
  | COUNT()       | 행 수를 계산           |
  | SUM()         | 합계를 계산            |
  | AVG()         | 평균을 계산            |
  | MAX() / MIN() | 최댓값과 최솟값을 계산 |
  | STDDEV()      | 표준편차를 계산        |
  | VARIAN()      | 분산을 계산            |

- `HOUR` : 시간 추출

<br>

### Ex 1) 최솟값 구하기

- 동물 보호소에 가장 먼저 들어온 동물은 언제 들어왔는지 조회하는 SQL 문을 작성해주세요.

  ```sql
  SELECT MIN(DATETIME)
  FROM ANIMAL_INS;
  ```

<br>

### Ex 2) 동물 수 구하기

- 동물 보호소에 동물이 몇 마리 들어왔는지 조회하는 SQL 문을 작성해주세요.

  ```sql
  SELECT COUNT(ANIMAL_ID)
  FROM ANIMAL_INS;
  ```

<br>

### Ex 3) 중복 제거하기

- 동물 보호소에 들어온 동물의 이름은 몇 개인지 조회하는 SQL 문을 작성해주세요. 이때 <u>이름이 NULL인 경우는 집계하지 않으며</u> **중복되는 이름은 하나**로 칩니다.

  ```sql
  SELECT COUNT(DISTINCT NAME)
  FROM ANIMAL_INS
  WHERE NAME IS NOT NULL;
  ```


<br>

### 4) 고양이와 개는 몇 마리 있을까

- 동물 보호소에 들어온 동물 중 <u>고양이와 개가 각각 몇 마리인지 조회</u>하는 SQL문을 작성해주세요. 이때 고양이를 개보다 먼저 조회해주세요.

  ```sql
  SELECT ANIMAL_TYPE, COUNT(ANIMAL_ID) AS count 
  FROM ANIMAL_INS
  WHERE ANIMAL_TYPE IN ("Cat", "Dog")
  GROUP BY ANIMAL_TYPE
  ORDER BY ANIMAL_TYPE ASC;
  ```

<br>

### 5) 동명 동물 수 찾기

- 동물 보호소에 들어온 동물 <u>이름 중 두 번 이상 쓰인 이름</u>과 <u>해당 이름이 쓰인 횟수를 조회</u>하는 SQL문을 작성해주세요. 이때 결과는 이름이 없는 동물은 집계에서 제외하며, 결과는 이름 순으로 조회해주세요.

  ```sql
  SELECT NAME, COUNT(ANIMAL_ID) AS COUNT
  FROM ANIMAL_INS
  GROUP BY NAME
  HAVING COUNT(NAME) >= 2
  ORDER BY NAME ASC;
  ```

<br>

### 6) 입양 시각 구하기(1)*

- 보호소에서는 몇 시에 입양이 가장 활발하게 일어나는지 알아보려 합니다. <u>09:00부터 19:59까지, 각 시간대별</u>로 입양이 몇 건이나 발생했는지 조회하는 SQL문을 작성해주세요. 이때 결과는 **시간대 순으로 정렬**해야 합니다.

  ```sql
  SELECT HOUR(DATETIME) as HOUR, COUNT(ANIMAL_ID) as COUNT
  FROM ANIMAL_OUTS
  WHERE HOUR(DATETIME) BETWEEN '09' AND '19'
  GROUP BY HOUR
  ORDER BY HOUR ASC;
  ```

<br>

### 7) 입양 시각 구하기(2)**

- 보호소에서는 몇 시에 입양이 가장 활발하게 일어나는지 알아보려 합니다. <u>0시부터 23시까지, 각 시간대별</u>로 입양이 몇 건이나 발생했는지 조회하는 SQL문을 작성해주세요. 이때 결과는 **시간대 순으로 정렬**해야 합니다.

  ```
  
  ```

<br>

### 8) NULL 처리하기*

- 입양 게시판에 동물 정보를 게시하려 합니다. <u>동물의 생물 종, 이름, 성별 및 중성화 여부</u>를 아이디 순으로 조회하는 SQL문을 작성해주세요. 이때 프로그래밍을 모르는 사람들은 NULL이라는 기호를 모르기 때문에, **이름이 없는 동물의 이름은 No name으로 표시**해 주세요.

  ```sql
  SELECT ANIMAL_TYPE, IFNULL(NAME, 'No name'), SEX_UPON_INTAKE
  FROM ANIMAL_INS
  ORDER BY ANIMAL_ID ASC;
  ```

  

<br>

### 9) 

<br>

### 10)



<br>

 

### 11)