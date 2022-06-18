## coil
#### coil이란??
- `Coil`은 `Coroutine Image Loader`의 약자이며 코루틴으로 만들어진 가벼운 이미지 로딩 라이브러리 이다.
#### Glide와의 차이점
- 많은 안드로이드 공부하시는 분들이 이미지 처리 라이브러리는 `Glide`로 알고 계실것이다, 그런데 `Coil`을 사용하는 이유가 무엇일까?
>장점
> - `Glide`, `Fresco` 보다 상대적으로 가볍다.
> - 사용하기 간편하다.
> - 처리속도가 빠르다.<br>

이렇게 되면 무조건 코일쓰면 좋은거 아니야? 라고 생각할수 있는데 코일또한 명확한 단점이 존재한다.

>단점
> - 아직 정식버전이라 할수 없기때문에 신뢰성이 낮아 실무에서 사용하는 기업이 많이 없다.
> - Android SDK 최신버전에서 사용 하는 것을 권장한다.
> - Kotlin을 모른다면 사용하기 어렵다.
> - 일부 기능사용을 위해 `Coroutines` 가 무엇인지 어느정도 알아야 한다.
#### 사용법
1. 먼저 gradle에 Coil 라이브러리를 추가해준다.
```kotlin
implementation("io.coil-kt:coil:0.10.0")
```
2. ImageView에 이미지를 로딩하기 위해 `load` 라는 메서드를 사용한다.
```kotlin
// URL사용시
imageView.load("https://www.example.com/image.jpg")
// Resource사용시
imageView.load(R.drawable.image)
// File 사용시
imageView.load(File("/path/to/image.jpg"))
```
3. 추가로 이미지를 핸들링 하고싶다면 `lamda` 식을 이용하여 설정할수 있다
```kotlin
//예시 (원형으로 자르기)
imageView.load("https://www.example.com/image.jpg") {
    transformations(CircleCropTransformation())
}
```
4가지의 Image Transformations
1. BlurTransformation<br>
이미지를 흐릿하게 보이게하는것
2. CircleCropTransformation<br>
이미지의 중심을 기준으로 원형으로 이미지를 자릅니다. (동그랗게 만드는것)
3. GrayscaleTransformation<br>
음영처리를 적용합니다.
4. RoundedCornersTransformation<br>
사이즈에 맞도록 이미지를 자르고 이미지 모서리를 둥글게 라운드를 적용합니다.
#### 사용 후기
직접 사용해본 결과 사용하기가 정말 편하다, 이미지를 핸들링 하기도 편해서 한번쯤 공부해서 사용해 보는것도 좋을것 같다!