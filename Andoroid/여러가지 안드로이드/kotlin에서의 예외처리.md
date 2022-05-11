## kotlin에서 예외처리하기
코틀린에서 예외를 처리하는 방식은 `java`와 비슷하다. 예외를 처리하는 방식에는 총 2가지 방식이 있는데 1번째는 예외를 던져서 처리하는 `throw`와 예외를 잡아서 처리하는 `try,catch` 방식이 있다.
### 1. throw
- 함수 실행중 오류가 발생하면 예외를 던질(throw) 수 있고 함수를 호출하는 쪽에서는 그 예외를 잡아(catch) 처리할수 있다.
- 예외에 대해 처리를 하지 않는 경우 함수 호출 스택을 거슬러 올라가면서 예외를 처리하는 부분이 나올 때까지 예외를 다시 던진다.(rethrow)
##### 예제
```kotlin
fun main() {
    //Exception 던지기
    val percentage = 200
    if (percentage !in 0..100) {
        //예외 인스턴스를 만들 때, new를 사용 할 필요가 없다
        throw IllegalArgumentException("A percentage value must be between 0 and 100: ${percentage}"
    } else {
        println(percentage)
    }
}
```
- throw로 예외를 던지는 예제
    - 퍼센트에서 0부터100까지 표현이 가능하다. 만약 0에서 100사이가 아닌 값이 들어오면 예외를 던지는 예제
```
실행결과
Exception in thread "main" java.lang.IllegalArgumentException: A percentage value must be between 0 and 100: 200

 at exam02.ThrowExceptionKt.main(ThrowException.kt:11)

 at exam02.ThrowExceptionKt.main(ThrowException.kt)
```
### 2. try, catch
- `try{}`안에서 실행한 코드중에 오류가 발생하면 `catch{}`에서 오류를 처리한다
- `finally{}`라는 것도 있는데 이건 있어도 되고 없어도 된다. 이구문은 코드가 정상작동이 되던 오류가 나던 무조건 실행된다.
```kotlin
try {
    코드
} catch (e: 여러Exception) {
    에러 발생시 실행할 구문
} finally { //선택
    오류가 나던 안나던 무조건 실행할 구문
}
```
#### try를 식으로 사용하기
```kotlin
fun main() {
    val num  = try {
        Integer.parseInt(BufferedReader(StringReader("not a number")).readLIne())
    } catch(e: NumberFormatException) {
        return
    }

    println(num) 
}
```
- 오류가 발생하면 `catch`에서 예외를 잡아서 아무런 값도 출력하지 않는다. 
- `"not a number"` 숫자가 아니가 때문에 오류가 발생한다