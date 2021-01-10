# Programmers-CodingTest
🐢 프로그래머스 Level별 Swift 풀이 🚀

>지금은 느리지만 알고리즘 문제를 매일 꾸준히 풀어 1년뒤, 3년뒤, 5년뒤 성장하는 개발자가 되자!



### Level 1 - (19/41) ![](https://us-central1-progress-markdown.cloudfunctions.net/progress/46)

---

#### [ 주요내용 ]

- Map, filter, reduce 

  ```swift
  /* n까지 해당하는 모든 약수의 합*/
  return n != 0 ? (1...n).filter{n % $0 == 0}.reduce(0){$0 + $1} : 0
  ```

  

- 배열 (Array)

  - Array 문자열 처리 - 문자열(String)은  문자(Character)가 2개 이상 결합한 데이터 타입 

    ```swift
    let s = "abcde"
    Array(s)         // ["a", "b", "c", "d", "e"]
    Array(s)[0]      // a
    Array(s)[0...2]  // ["a", "b", "c"]
    ```

  - 배열 추가

    ```swift
    /* sequence 추가 */
    var numbers = [1, 2, 3, 4, 5]
    numbers.append(contentsOf: 10...15) 
    numbers // "[1, 2, 3, 4, 5, 10, 11, 12, 13, 14, 15]"
    ```

    

- 배열 기초 

  - 데이터 타입 변경 - 문자열에서 숫자만 있는 데이터 찾기

    ```swift
    let s = "9a99a99"
    print(Int(s)) // nil
    ```

    

- 수학 공식

  - 두 수 사이의 합

    ```swift
    /* S=(∣a−b∣+1)∗(a+b)/2 */
    return (a + b) * (max(a, b) - min(a, b) + 1) / 2
    ```

    

  

