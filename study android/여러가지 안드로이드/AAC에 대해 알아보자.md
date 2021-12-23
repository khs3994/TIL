## AAC
---
### ViewModel?
```
- 기존의 Lifecycle에 영향을 받지 않는다
- 원래 라면 Lifecycle에 따라 메모리 관리를 따로 해야하지만 viewmodel은 그럴 필요가 없다
- 예를 들어 화면을 회전할때 뷰를 지웠다 가로 모양으로 다시그려야 하지만 viewmodel은 데이터가 사라지지 않기 때문에 그럴 필요가 없다
- viewmodel안에 livedata가 있다
```
이해를 돕기위한 그림
![ex_screenshot](/study%20android/imgfile/viewmodel.png)

### LiveData?
```
- viewmodel과 세트로 묶여 다님
- 데이터가 변경되는걸 관찰함
- viewmodel의 변수를 livedata가 감싸고 있다가 변수의 값이 변경되면 그걸 인지해서 데이터를 처리함 (이런걸 옵저빙 이라고 한대요) 
```
### LiveData를 사용하면 좋은점
1. UI와 데이터 상태의 일치 보장
2. 메모리 누수가 없다
3. 비정상 종료가 없다
4. 수명주기를 수동으로 처리하지 않는다
5. 최신 데이터를 유지한다
6. 적절한 구성 변경
7. 리소스 공유