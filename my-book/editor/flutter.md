# Flutter에서 위젯과 관련해 자동으로 호출되는 함수

flutter 에서는 위젯을 생성할때 build(context)를 호출한다. 하지만, 그 함수 외에 내부적으로 불려지는 함수들이 있다.&#x20;

`createState()` → `initState()` → `didChangeDependencies()` → `build()` →\
(필요시 `didUpdateWidget()`, `setState()` 시 `build()` 반복) →\
`deactivate()` → `dispose()`

### createState()

* state 객체를 생성할 때 호출한다. 내가 호출한다.

### initState()

* 위젯 트리에 추가될 때 호출

### didChangeDependencies()

* `InheritedWidget` 의 값에 의존할 때 값이 바뀔 때 호출

