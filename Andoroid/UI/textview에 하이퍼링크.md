## TextView에 하이퍼링크?
- 개발을 하다 보면 어떠한 url을 받는 경우가 있다, 이럴때 url을 클릭해서 바로 링크로 들어가게 할수 있다.
#### 방법
원하는 `TextView`에 
```
android:linksClickable="true"
android:autoLink="web"
```
위의 두 속성을 적용해준다. <br>
이러면 스트링 형식의 url이 하이퍼링크로 바뀐다.
#### 하이퍼 링크 색깔
하이퍼 링크의 색깔을 `App`의 `color Accent` 색깔을 따라간다.
<br>
만약 별도로 색을 지정하고 싶다면 `style`을 별도로 만들어서 적용시켜야 한다.