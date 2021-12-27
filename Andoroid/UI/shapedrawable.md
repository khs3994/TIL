## Shape drawable
---
#### Shape drawable?
- 여러가지 뷰의 모양을 정할수 있는것
#### 사용법
* res -> drawable 안에 파일을 생성하여 만든다.
  
```xml
  <shape
    xmlns:android="http://schemas.android.com/apk/res/android">
</shape>
```
* shape 태그(?)를 사용한다.
```xml
android:shape="oval"
```
* shape 태그 안에서 모양을 지정할수 있다.
```xml
<solid 
    android:color="#D7C400"/> <!--색깔 지정 -->

<size
    android:width="44dp"
    android:height="44dp"/> <!-- 가로 세로 높이지정 -->
```
* solid 와 size로 모양을 잡는다.
```xml
android:background="@drawable/파일이름"
```
```kotlin
뷰아이디.background = ContextCompat.getDrawable(this,R.drawable.circlr_blue)
//이런식으로도 사용 가능
```
* 모양을 다 만들었으면 위의 형식으로 여러가지 뷰의 모양을 지정할수 있다.
