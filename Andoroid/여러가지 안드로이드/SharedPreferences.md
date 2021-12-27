## SharedPreferences
---
#### SharedPreferences?
- 간단한 데이터를 저장할 때 사용하는것
- SharedPreferences는 앱 내부에 파일을 만들고, 그 파일안에서 데이터를 저장하거나 불러올수 있게함
- 실제 개발시에는SharedPreferences의 저장/복원 메서드를 호출함
- key - value 형식으로 저장함
  
```kotlin
val detail = getSharedPreferences("키 이름", Context.모드)
```
* 위의 코드와 같이 선언해준다
  
```kotlin
binding.에딧텍스트아이디.setText(detail.getString("detail", ""))
```
* 연결해준다
```kotlin
val runnable = Runnable { //Thread기능 이용
            getSharedPreferences("diary", Context.MODE_PRIVATE).edit {
                putString("detail", binding.diaryEdtx.text.toString())
            }

            Log.d( TAG,"SAVE!!!! ${binding.diaryEdtx.text.toString()}")
        }

        binding.diaryEdtx.addTextChangedListener {
            Log.d( TAG,"TextChanged :: $it")
            handler.removeCallbacks(runnable)//이전에 실행된 콜백이 있다면 삭제 없으면 그대로 놔둠
            handler.postDelayed(runnable, 500) //딜레이 시간마다 한번씩 저장
        }
```
* 이런식으로 수정하는 코드를 작성할수 있다


