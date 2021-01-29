# Programmers-CodingTest

🐢 프로그래머스 Level별 Swift 풀이 🚀

>지금은 느리지만 알고리즘 문제를 매일 꾸준히 풀어 1년뒤, 3년뒤, 5년뒤 성장하는 개발자가 되자!



### MySQL Level2 - (2/11) ![45%](https://progress-bar.dev/20) 

---

### 1) SUM, MAX, MIN 집계함수

>집계함수(SUM , MAX, MIN, AVG, COUNT)는 계산을 수행하고 단일 값을 반환

- count 함수를 제외한 집계함수는 Null값을 무시
- SELECT문 또는 HAVING 절에만 사용 가능



### Ex 1) 최솟값 구하기

- 동물 보호소에 가장 먼저 들어온 동물은 언제 들어왔는지 조회하는 SQL 문을 작성해주세요.

  ```sql
  SELECT MIN(DATETIME)
  FROM ANIMAL_INS;
  ```



### Ex 2) 동물 수 구하기

- 동물 보호소에 동물이 몇 마리 들어왔는지 조회하는 SQL 문을 작성해주세요.

  ```sql
  SELECT COUNT(ANIMAL_ID)
  FROM ANIMAL_INS
  ```

