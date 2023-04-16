아래의 코드는 MaterialApp 위젯은 앱의 기본적인 디자인 요소를 설정하는 데 사용됩니다. 이 위젯은 home 프로퍼티를 갖고 있으며, 이 프로퍼티에는 Scaffold 위젯이 지정되어 있습니다.

Scaffold 위젯은 앱의 뼈대를 구성하는 위젯입니다. 이 위젯은 상단 앱바와 본문 내용으로 구성됩니다.

상단 앱바는 AppBar 위젯으로 구현되어 있습니다. 이 위젯은 두 개의 자식 위젯을 가지고 있습니다. 하나는 상단 왼쪽에 위치한 아이콘으로 Icon 위젯을 사용하였고, 다른 하나는 상단 중앙에 위치한 제목으로 Text 위젯을 사용하였습니다.

본문 내용은 Column 위젯으로 구성되어 있습니다. 이 위젯은 여러 개의 자식 위젯을 가질 수 있으며, 위에서부터 아래 방향으로 자식 위젯들을 배치합니다.

Column 위젯의 자식 위젯 중 하나는 Row 위젯입니다. 이 위젯은 가로 방향으로 자식 위젯들을 배치합니다. 이 Row 위젯은 상단 본문 내용의 첫 번째 줄에 위치하며, Icon 위젯과 Column 위젯을 자식 위젯으로 가지고 있습니다.

Column 위젯의 다른 자식 위젯은 Container 위젯입니다. 이 위젯은 앱의 본문 내용 중간에 위치하며, 계좌 상태를 나타내는 컨테이너입니다. 이 Container 위젯은 다시 Padding 위젯과 Row 위젯, Column 위젯을 자식 위젯으로 가집니다.

마지막으로, MaterialApp 위젯과 Scaffold 위젯을 종료하는 닫는 괄호())가 나타납니다.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          backgroundColor: Colors.teal,
          title: Row(
            mainAxisAlignment: MainAxisAlignment.spaceAround,
            crossAxisAlignment: CrossAxisAlignment.center,
            children: [
              Icon(Icons.ac_unit_outlined, 
              color: Colors.orange, 
              size: 60,
              ), // Icon
              Text('Welcome My Friend', style: TextStyle(fontSize: 25,),),
            ]
          ),  //Row
        ), //AppBar
				
        body: Column(
          children: [
            Row(
              children: [
                Icon(Icons.abc, size: 100,),
                Column(
                  children: [
                    Text("강정묵", style: TextStyle(fontSize : 20, fontWeight: FontWeight.bold,),),
                    Text("성일", style: TextStyle(fontSize: 10)),
                  ],
                ) //Column
              ],
            ), //Row
						
						// 여백을 위한 공백이다.
            SizedBox(height: 10,),
            Container(
              decoration: BoxDecoration(
                color: Colors.amber,
                borderRadius: BorderRadius.circular(10)
              ), // BoxDecoration
              width: 400,
              height: 200,
              child: Padding(
                padding: const EdgeInsets.all(20.0),
                child: Row(
                  children: [
                    Text('성일'), // 
                    Column(
                      mainAxisSize: MainAxisSize.max,
                      mainAxisAlignment: MainAxisAlignment.center,
                      crossAxisAlignment: CrossAxisAlignment.end,
                      children: [
                        Text("잔고"),
                        Text("1,000,000,000원"),
                      ],
                    ), // Column
                  ],
                ), // Row
              ), //Padding
            ), // Container
          ]
        ), //Column
      ), //Scaffold
    ); //MaterialApp

  }
}
```
