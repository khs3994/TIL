## LazyColumn?
#### LazyColumn 이란?
- 리스트를 그릴때 사용하는것이다
- item,items를 이용해서 리스트 안에 아이템들을 넣을수 있다.
```kotlin
LazyColumn(
    modifier = Modifier
        .background(color = Color.Green)
        .fillMaxWidth(),
    contentPadding = PaddingValues(16.dp),
    verticalArrangement = Arrangement.spacedBy(8.dp),
) {
    item {
        Text("헤더")
    }
    items(50){ index ->
        Text("강민제 $index")
    }
    item {
        Text("못생김")
    }
}
```