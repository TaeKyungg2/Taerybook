---
icon: rocket-launch
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Flutter/Dart

{% embed url="https://docs.flutter.dev/" %}

공식 문서이다. 내 생각에는 친절하기는 하지만 처음 하는 사람이 보기에는 다른 자료나 ai 를 참조해야 할 것 같다.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key}); 
  //const MyApp({Key? key}) : super(key: key);와 같다.


  // 이 위젯은 너의 애플리케이션의 뿌리야.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        // 이 앱의 테마입니다.
        //
        // 이렇게 해보세요: "flutter run"으로 앱을 실행해 보세요.
        // 앱에 보라색 툴바가 보일 겁니다. 앱을 종료하지 않고,
        // 아래 colorScheme에서 seedColor를 Colors.green으로 변경해 보세요.
        // 그런 다음 "핫 리로드"를 호출합니다(변경 사항을 저장하거나 "핫"을 누르세요)
        // Flutter를 지원하는 IDE에서 "새로고침" 버튼을 누르거나, "r" 키를 누르세요
        // 앱을 시작하는 명령줄).
        //
        // 카운터가 0으로 다시 재설정되지 않았음을 확인하세요. 애플리케이션
        // 상태는 다시 로드하는 동안 손실되지 않습니다. 상태를 재설정하려면 핫
        // 재시작을 대신 사용하세요.
        //
        // 이는 값뿐만 아니라 코드에도 적용됩니다. 대부분의 코드 변경 사항은
        // 핫 리로드만으로 테스트할 수 있습니다.
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  // 이 위젯은 애플리케이션의 홈 페이지입니다. 상태를 가지는 위젯으로,
  // (아래에 정의된) State 객체를 가지고 있으며, 이 객체에는 위젯의
  // 모양에 영향을 미치는 필드가 포함되어 있습니다.

  // 이 클래스는 상태에 대한 구성입니다. 이 클래스는 (이
  // 부모(이 경우 App 위젯)가 제공한 제목을 소문자로 변환하고
  // State의 build 메서드에서 사용됩니다. Widget 서브클래스의 필드는
  // 항상 "final"로 표시됩니다.

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
        // 이 setState 호출은 Flutter 프레임워크에 무언가 변경되었음을 알립니다
        // 이 State에서 변경되었으며, 이로 인해 아래의 build 메서드가 다시 실행됩니다
        // 디스플레이가 업데이트된 값을 반영할 수 있도록. 만약 우리가 변경했다면
        // _counter를 setState() 호출 없이 변경하면 build 메서드가 호출되지 않을 것입니다
        // 다시 호출되면 아무 일도 일어나지 않는 것처럼 보일 것입니다.
        // 리스타트를 대신 사용하세요.
        //
        // 이는 값뿐만 아니라 코드에서도 작동합니다: 대부분의 코드 변경 사항은
        // 핫 리로드만으로 테스트할 수 있습니다.
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    // 이 메서드는 setState가 호출될 때마다 다시 실행됩니다.
    // 예를 들어 위 _incrementCounter 메서드에서처럼요.
    //
    // Flutter 프레임워크는 빌드 메서드가 다시 실행되도록 최적화되었습니다.
    // 빠르므로, 위젯 인스턴스를 개별적으로 변경할 필요 없이 업데이트해야 하는 모든 것을 다시 빌드할 수 있습니다.
    // 개별적으로 위젯 인스턴스를 변경할 필요 없이 업데이트해야 하는 모든 것을 다시 빌드할 수 있습니다.
    return Scaffold(
      appBar: AppBar(
        // 직접 해보기: 여기 색상을 특정 색상(예: Colors.amber)으로 변경해 보고 핫 리로드를 실행해 보세요. 
        //그러면 AppBar의 색상만 변경되고 다른 색상은 그대로 유지되는 것을 확인할 수 있습니다.
        // Colors.amber 같은 색상으로 바꿔 보세요)으로 변경한 후 핫 리로드를 실행하면
        // AppBar 색상만 변하고 다른 색상은 동일하게 유지되는 걸 볼 수 있습니다.
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        // 여기서는 App.build 메서드에 의해 생성된 MyHomePage 객체에서 값을 가져와
        // 앱바 제목을 설정하는 데 사용합니다.
        title: Text(widget.title),
      ),
      body: Center(
        // Center는 레이아웃 위젯입니다. 단일 자식을 받아
        // 부모의 중앙에 배치합니다.
        child: Column(
          // Column은 레이아웃 위젯입니다. 자식 위젯 목록을 받아
          // 수직으로 정렬합니다. 기본적으로 자동으로 크기를 조정하여
          // 자식들을 수평으로 배치하고, 부모와 같은 높이가 되도록 노력합니다.
          //
          // Column은 자신의 크기를 조절하고 제어하기 위한 다양한 속성을 가지고 있습니다
          // 자식 요소들을 배치하는 방법입니다. 여기서는 mainAxisAlignment를 사용하여
          // 자식 요소를 수직으로 중앙 정렬합니다. 여기서 주축은 수직입니다
          // 축은 열이 수직이기 때문입니다(교차 축은
          // 가로 방향).
          //
          // 시도해 보세요: "디버그 페인팅"을 실행해 보세요(IDE에서 "Toggle Debug Paint"를 선택하거나
          // 콘솔에서 "p"를 누르세요), 그러면
          // 각 위젯에 대한 와이어프레임
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text('You have pushed the button this many times:'),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ), // 이 후행 쉼표는 빌드 메서드의 자동 서식을 더 좋게 만듭니다.
    );
  }
}

```

플러터 데모 파일의 main.dart이다.

문법 헷갈리는 것들

* `func({argname})`  : 함수선언에 괄호안에 중괄호가 들어가있다. named argument이다. 호출할 때 `func(argname : value)` 형식으로 호출한다.
* `var func() ⇒ express` 은 함수 선언이다.&#x20;
* `() ⇒ {}` 이건 익명 함수(람다) 이다.
* `const MyApp({super.key});` 는, `const MyApp({Key? key}) : super(key: key);` 와 같다. 부모에 키를 넘겨주는 건데, 같은 위젯을 구분하기 위해서(element 를 새로 만들지, 재사용할지) key 가 있다. key 는 상태관리에서 아주 유용하다.
