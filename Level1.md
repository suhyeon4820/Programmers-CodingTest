# Programmers-CodingTest
🐢 프로그래머스 Level별 Swift 풀이 🚀

>지금은 느리지만 알고리즘 문제를 매일 꾸준히 풀어 1년뒤, 3년뒤, 5년뒤 성장하는 개발자가 되자!



### Level 1 - (25/41) ![](https://us-central1-progress-markdown.cloudfunctions.net/progress/51)

---

#### [ 주요내용 ]

- 고차함수 : 매개변수로 함수를 갖는 함수

  ```swift
  /* n까지 해당하는 모든 약수의 합*/
  return n != 0 ? (1...n).filter{n % $0 == 0}.reduce(0){$0 + $1} : 0
  ```

  - map : 컨테이너가 담고 있던 각각의 값을 매개변수를 통해 받은 함수에 적용한 후 새로운 컨테이너를 생성하여 반환 (기존 컨테이너의 값은 변경되지 않음)

  - 배열 내부의 값을 하나씩 mapping(하나의 매개변수와 리턴 타입을 갖는 함수를 대입), 각 요소에 대한 값을 변경하고자 할 때 사용하고 그 결과를 배열로 반환

  - ```swift
    /*
    func map<T>(_ transform: (Element) throws -> T) rethrows -> [T]
    */
    
    let cast = ["Vivien", "Marlon", "Kim", "Karl"]
    let lowercaseNames = cast.map { $0.lowercased() } // ["vivien", "marlon", "kim", "karl"]
    let letterCounts = cast.map { $0.count } // 'letterCounts' == [6, 6, 3, 4]
    
    var string = ["1","2","3","4"]
    string.map { Int($0)! } // [1,2,3,4] 
    
    let array = [0, 1, 2, 3]
    let newArray = array.map { $0 * 5 } //[0, 5, 10, 15]
    ```

    

  - filter : 클로저로 각 항목들을 비교하여 일치하는 결과물을 가진 새로운 배열을 반환합니다.

    - `includeElement`를 지원하는 클로저는 항목이 포함되는지(`true`) 또는 제외되는지(`false`) 나타내기 위해 Boolean 값을 반환해야 합니다.

      다음은 앞의 예제에서 사용한 배열에 홀수 값 항목만 가지는 배열을 얻는 예제입니다.

  - ```swift
    /* func filter(includeElement: (T) -> Bool) -> Array<T> */
    let oddArray = array.filter( { (value: Int) -> Bool in return (value % 2 == 0) } )
    array.filter { $0 % 2 == 0 }
    ```

  - 

  - Reduce

  - ```swift
    let n = 123
    // map :문자열 요소의 타입은 Character형식 -> 요소를 String형식으로 바꿔준 다음, 다시 정수형으로 바꿈
    print(String(n).map { Int(String($0))! }.reduce(0) { $0 + $1 })
    print(String(n).reduce(0, {$0 + Int(String($1))!}))
    ```

  - ```swift
    func reduce<U>(initial: U, combine: (U, T) -> U) -> U
    
    // 배열의 각 항목들을 재귀적으로 클로저를 적용시켜 하나의 값을 만듭니다.
    array.reduce(0, { (s1: Int, s2: Int) -> Int in
        return s1 + s2
    })
    
    // 클로저는 함수의 마지막에 위치하면 다른 인자와 분리하여 작성할 수 있습니다.
    array.reduce(0) { (s1: Int, s2: Int) -> Int in
        return s1 + s2
    }
    
    array.reduce(0) { (s1, s2) in s1 + s2 }
    
    array.reduce(0) { $0 + $1 }
    // 연산자는 중위 연산자로 왼쪽 값이 $0, 오른쪽 값이 $1임을 추론 가능하므로 다음과 같이 생략 가능
    array.reduce( 0, + )
    // {0 + 1}, {1 + 2}, {3 + 3}, {6 + 4}이며, 결과는 10입
    ```

    

- 배열 (Array)

  - 배열 생성 (repeating /prefix)

  - ```swift
  var array =[Int](repeating: 0, count: 5)) // [0, 0, 0, 0, 0]
    ```

  - 

  - Array 문자열 처리 - 문자열(String)은  문자(Character)가 2개 이상 결합한 데이터 타입 

    ```swift
    let s = "abcde"
    Array(s)         // ["a", "b", "c", "d", "e"] String -> Character
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

  - 인덱스 찾기 -> O(*n*)

    ```swift
    /* 하나의 인덱스만 반환 
    func firstIndex(of element: Element) -> Int? */
    let seoul = ["Jane", "Kim"]
    seoul.firstIndex(of: "Kim")!            // 1
    seoul.firstIndex(where: {$0 == "Kim"})  // 1
    ```

- 형변환

  - String : Sorting 가능

    ```swift
  let n = 118372
    String(n).sorted(by: >)         // ["8", "7", "3", "2", "1", "1"]
    String(String(n).sorted(by: >)) // 873211
    ```
    

    
  - 데이터 타입 변경 - 문자열에서 숫자만 있는 데이터 찾기

    ```swift
    let s = "9a99a99"
    print(Int(s)) // nil
    ```

- Character <-> String

  - 

- 수학 공식

  - 두 수 사이의 합

    ```swift
    /* S=(∣a−b∣+1)∗(a+b)/2 */
    return (a + b) * (max(a, b) - min(a, b) + 1) / 2
    ```

    

- Suffix
- 최소공배수, 최대공약수 : https://velog.io/@hhhan0315/Level-1-%EC%B5%9C%EB%8C%80%EA%B3%B5%EC%95%BD%EC%88%98%EC%99%80-%EC%B5%9C%EC%86%8C%EA%B3%B5%EB%B0%B0%EC%88%98-Swift



