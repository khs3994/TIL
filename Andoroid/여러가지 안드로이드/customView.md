## CustomView
- 말 그대로 개발자가 뷰를 직접 커스텀 해서 사용하는것
### 백문이 불여일견 직접 사용해보자!
#### 1. 뷰로 사용할 파일을 만들자!
```kotlin
class RecordButton(
    context: Context,
    attrs: AttributeSet
) : AppCompatImageButton(context, attrs) {
    fun updateIcon(state: State) {
        when (state) {
            State.BEFORE_RECORDING -> {
                setImageResource(R.drawable.ic_record)
            }
            State.ON_RECORDING -> {
                setImageResource(R.drawable.ic_stop)
            }
            State.AFTER_RECORDING -> {
                setImageResource(R.drawable.ic_play)
            }
            State.ON_PLAYING -> {
                setImageResource(R.drawable.ic_stop)
            }
        }
    }
}
```
- 위 코드처럼 파라미터로 Context,와 AttributeSet을 필수로 받아야한다.
- 그리고 updateIcon처럼 view를 조작할수 있게 함수등을 만들어준다.
#### 2. 만든 파일을 xml에 띄우자!
```xml
<fastcampus.app.part2.chapter07.RecordButton
    android:id="@+id/record_btn"
    android:layout_width="100dp"
    android:layout_height="100dp"
    android:layout_marginBottom="50dp"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent" />
```
- 위 코드와 같이 커스텀 뷰를 띄우고 싶은 뷰의 xml파일에 커스텀뷰를 작성해준다
#### 3. 뷰를 컨트롤 해보자!
```kotlin
private val recordButton: RecordButton by lazy {
    findViewById(R.id.record_btn)
}
```
- 위와 같이 커스텀 뷰를 선언해주고
```kotlin
private fun initViews() {
    recordButton.updateIcon(state)
}
```
- 아래와 같이 메서드를 사용해서 뷰를 컨트롤 해준다
### 느낀점
커스텀 뷰를 사용해보니 생각보다 쉬웠고 이걸 잘만 이용하면 코드를 많이 줄일수 있을것 같다는 생각이 들었다.
