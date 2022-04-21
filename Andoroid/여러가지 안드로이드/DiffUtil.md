# DiffUtil
---
## 등장 배경
안드로이드 개발에 거의 필수적인 `recyclerview` 사용에 있어서, 데이터가 동적으로 변경되는 경우 `notifyDataSetChanged()` 를 통해 리사이 클러뷰를 갱신하는 과정을 거친다.<br><br>
하지만 아이템이 딱 하나만 바뀌어도 `notifyDataSetChanged()`는 리사이클러뷰를 싹다 밀고 다시 처음부터 끝까지 객체를 하나하나 생성하는 과정을 거치기 때문에 성능에 치명적인 악영향을 미친다.<br><br>
이러한 이유로 `DiffUtil` 클래스가 등장했다.<br>
`DiffUtil`는 이전 데이터 상태와 현재 데이터간의 상태 차이를 계산하고, 반드시 업데이트해야 할 최소한의 데이터에 대해서만 갱신하게 된다. 데이터 업데이트 횟수를 최소한으로 가져가는 것이다.
## AsyncListDiffer
- `DiffUtil`은 아이템 갯수가 많을 경우 비교연산에 필요한 시간이 길어질수 있기 때문에 백그라운드 스레드에서 처리되어야 한다
- `AsyncListDiffer`는 `DiffUtil`을 편하게 쓰기 위해서 만들어진 클래스로 `DiffUtil`에 대해 자체적으로 스레드 처리를 해주는 클래스이다
## ListAdapter
- `AsyncListDiffer`를 더 쓰기 편하도록 랩핑한 클래스
- 리사이클러뷰 어댑터가 `ListAdapter`를 상속하게 하고 초기화시 `DiffUtil`콜백 객체를 넘겨준다, 이렇게 하면 `currentList`로 현재 데이터를 불러올수 있고 `submitList`로 데이터를 갱신할수 있다
- `submitList()`로 전체 데이터를 넘겨주면 어댑터가 백그라운드 스레드를 이용해 리스트 차이를 계산하여 화면을 갱신시켜준다
## 사용 방법 
`DiffUtil`가 원래 목록과 새로 들어온 목록간의 차이를 계산한 후에 `DiffUtil.Callback` 이라는 추상 클래스를 콜백으로 활용한다, `DiffUtil.Callback`는 4개의 추상 메서드와 1개의 일반 메서드로 이루어져 있는데, 이러한 메서드를 오버라이딩하여 사용한다.<br><br>
> ***1. getOldListSize()***
> - 기존에 있던 목록의 크기를 반환한다.

> ***2. getNewListSize()***
> - 새로 들어온 목록의 크기를 반환한다.

> ***3. areItemsTheSame(int oldItemPosition, int newItemPosition)***
> - 두 아이템이 같은 객체인지 여부를 반환함

>***4. areContentsTheSame(int oldItemPosition, int newItemPosition)***
> - 두 아이템이 같은 데이터를 갖고 있는지 여부를 반환함, `areItemsTheSame()` 이 `true`를 반환할 때만 호출됨, 애초에 객체가 다르다면 데이터를 비교하는 것은 의미가 없기 때문

> ***5. getChangePayload(int oldItemPosition, int newItemPosition)***
> - 만약 `areItemTheSame()`가 `true` 를 반환하고, `areContentsTheSame()`이 `false`를 반환하면 새로운 아이템이 들어온 것으로 간주하고 해당 메소드가 호출되어 변경 내용에 대한 페이로드를 가져온다.
> 
> - 이 매서드는 추상 메서드가 아니기 때문에 꼭 오버라이드 할필요는 없다.