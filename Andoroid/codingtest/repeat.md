### repeat
- repeat는 특정 문자열이나 함수를 반복하게 해주는 기능이다
```kotlin
fun main() {
    println("A".repeat(5)) // A라는 문자열을 5번 반복

    repeat(5) { // B를 출력 하는 함수를 5번 반복
        print("B")
    }
}


-- Result
AAAAA
BBBBB
```
- 위의 코드처럼 사용할수 있다.

