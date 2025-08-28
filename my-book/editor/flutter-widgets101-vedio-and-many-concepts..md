---
description: 25/8/28
---

# Flutter Widgets101 vedio and many concepts.

이 영상 시리즈는 개념 이해에 필수적인 것 같다.  공식 문서 초반에는 아예 나오지 않는 element 개념이 나오고, context, key 등의 개념과 더 근본적인 개념에 대해 나온다.

{% embed url="http://bit.ly/FlutterWidgets101" %}

### Element and Widget

* Widget
  * &#x20;dart 코드 안에서 내가 만드는 코드의 class 이다. 위젯은 불변이다. const 를 붙인다.
* Element
  * 요소는 실제로 앱 화면에서 보여지는 것 을 말한다.
  * (render 이라는 게 실제로 이것을 말하지만, element 까지만 알아도 된다고 한다.)
  * 각 Element 는 key로 구분된다. key 가 같거나, 구분을 안하면 구분을 안한다.(다시 만들거나, 지우고 새로 만든다.)

### <mark style="color:orange;">순서</mark>

Widget 생성 ⇒ Element 생성

상태변경 ⇒ Widget 재생성 ⇒ Element의 State에서 didUpdateWidget(oldWidget) 실행 ⇒ oldWidget과 자신을 비교해서 property 다른것 업데이트

### <mark style="color:purple;">클래스 구조</mark>

BuildContext 추상클래스 ⇒ Element 추상클래스 ⇒ (상태유형)Element 클래스\
BuildContext 는 "위치 인터페이스"를 담고 있다. 그 이외의 정보는 위로 올릴 필요가 없으므로 자식 클래스를 넘기지 않는 build(BuildContext context) 가 나온 것이다.(사용자 정의 widget 이외에는  build 메서드가 자동 호출돼서 안 보이는 거다.)

### 위젯의 대표적 3종류

1. StatelessWidget
   1. 상태를 가지지 않는다. 고정이다.
2. StatefullWidget
   1. 상태를 가진다.&#x20;
   2. `class _위젯이름state extend state<위젯이름>` 을 추가로 가진다. 원본 클래스에서 이 클래스를   호출한다.&#x20;
3. InheritedWidget
   1. 어떤 값을 많은 자식위젯에 전달해야 할 때 사용한다. 그 값을 가져야 하는 위젯들의 맨 위에 상속한다.
   2. StatefullWidget 로 상태를 바꾸는 방식은 모든 위젯을 다 build 다시 하지만, 이건 값만 참조 가능하다.

