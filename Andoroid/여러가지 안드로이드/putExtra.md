## putExtra 
#### putExtra란?
- 액티비티 to 프라그먼트, 프라그먼트 to 액티비티, 프라그먼트 to 프라그먼트, 액티비티 to 액티비티 등에서 데이터를 전송할때 사용하는 것이다.
#### 사용법
- 인텐트를 생성한 후에 `인텐트.putExtra("키",데이터)` 형식의 키벨류 형태로 데이터를 저장한다.
```kotlin
val intent = Intent(context, 액티비티::class.java)
intent.putExtra("키",벨류)
```
- 저장한 데이터는 `intent(getIntent())`에 참조한후 `get자료형Extra()`로 데이터를 빼올수 있다.
```kotlin
val result = intent.get자료형Extra("키")
```
#### 특별한 경우
- `putExtra()`로 데이터를 전달할때 만약 사용자가 커스텀한 데이터클래스 형태로 데이터를 전송하고 싶다면 어떻게 할까?<br> 단순히 데이터를 넣기만 하면 맞는 자료형이 없기 때문에 오류가 발생한다.<br>
이럴때 사용할수 있는것이 `serializable`이다.
- 이 키워드를 사용하는 데이터 클래스 밑에 붙여주면 `putExtra()`로 사용자가 만든 데이터 클래스 형태의 데이터를 전송할수 있다.
```kotlin
data class ex(
    val name: String,
    val num: String,
    val high: String
) : Serializable
```
- 이 형태의 데이터를 꺼낼때는 `getSerializableExtra()`를 사용하면 된다.

