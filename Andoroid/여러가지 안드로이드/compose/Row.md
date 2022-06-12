## Row?
#### Row 란?
- Row안에 있는 아이템들을 가로로 나열해주는 역할이다.
#### arrangement
- Row, Column 같은 요소들이 들어가는 컨테이너 성격의 콤포저블에서 요소들의 아이템을 정렬할때 사용한다
<br>
>`Arrangement.SpaceBetween` : 공간 모두 차지<br>
>`Arrangement.Start` : 왼쪽으로<br>
>`Arrangement.End` : 오른쪽으로<br>
>`Arrangement.SpaceAround` : 빈공간을 남겨두기<br>
>`Arrangement.Center` : 요소들에 넣기<br>
>`Arrangement.SpaceEvenly` : 요소들 사이에 공간을 똑같이 하기

#### aligment
- aligment 해당 컨테이너 안에 들어있는 요소들의 위치를 어떠한 방향으로 놓을지 결정
- 리니어 레이아웃의 gravity 속성과 동일하다고 볼수 있다
<br>
>`Aligment.Bottom` : 컨테이너를 아래에 두기<br>
>`Aligment.Top` : 컨테이너의 위에 두기<br>
>`Aligment.CenterVertically` : 컨테이너의 수직방향으로 중앙에 두기