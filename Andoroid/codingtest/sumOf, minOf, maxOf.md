### sumOf
- sumOf는 말 그대로 sumOf 스코프 안에 있는 값의 합을 반환 해준다
```kotlin
val arr = intArrayOf(1,2,3,4)
print(arr.sumOf { it }.toString())//출력 결과: 10
```
### minOf
- minOf도 말 그대로 minOf 스코프 안에 들어가는 값중 최솟값을 반환한다
```kotlin
val arr = intArrayOf(1,2,3,4)
print(arr.minOf { it }.toString())//출력 결과: 1
```
### maxOf
- maxOf 이친구도 이름 그대로 maxOf 스코프 안에 들어가는 값중 최대값을 반환한다
```kotlin
val arr = intArrayOf(1,2,3,4)
print(arr.maxOf { it }.toString())//출력 결과: 4
```