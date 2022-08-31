### withIndex
- 배열에 대해서 for문을 돌릴때 Index와 Value둘다 값을 받아 쓸수 있게 해주는 기능이다
```kotlin
var str = arrayOf("zero","one","two")
for ((index, value) in str.withIndex()) {
        println("index : ${index}, value : ${value}")
    }
}
//출력 결과
//index : 0, value : zero
//index : 1, value : one
//index : 2, value : two
```
- 위 코드처럼 사용하면 된다