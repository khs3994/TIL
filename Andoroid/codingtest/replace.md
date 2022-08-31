### replace
- replace는 특정 문자열을 변경할때 사용한다
- `replace("바뀔 문자열","바뀌게 될 문자열")` 이런식으로 사용한다
```kotlin
var str = "Hello World"
var str2 = "Hello World"

str = str.replace(" ","")
print(str)// 출력 결과 : HelloWorld
str2 = str2.replace("World","kotlin")
print(str2)// 출력 결과 : Hello Kotlin
```
- 위의 코드를 예로 들수 있다