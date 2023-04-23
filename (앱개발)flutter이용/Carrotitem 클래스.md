title, addr, price는 모두 해당 상품의 제목, 주소, 가격 정보를 담고 있습니다.
Carrotitem 클래스는 StatelessWidget으로 정의되어 있으며, build 메소드에서는 Row와 Column 위젯을 사용하여 UI를 구성하고 있습니다.
Row 위젯 내부에는 해당 상품의 이미지와 정보가 표시되도록 구성되어 있습니다. Container 위젯을 사용하여 이미지를 표시하고, Flexible 위젯 내부에 Column을 두어 상품 정보를 표시하고 있습니다.
Text 위젯을 사용하여 상품의 제목, 주소, 가격 정보를 표시하고 있습니다. style 속성을 사용하여 해당 Text 위젯의 스타일을 설정할 수 있습니다.
Row 위젯 내부에는 하트 아이콘과 그 아이콘 옆에 표시될 하트 개수를 표시하는 Text 위젯이 함께 사용되어 있습니다.

```dart
import 'package:flutter/material.dart';

class Carrotitem extends StatelessWidget {
  String title, addr;
  int price;

  Carrotitem({
    required this.title,
    required this.addr,
    required this.price,
    super.key,
  });

  @override
  Widget build(BuildContext context) {
    return Row(
      crossAxisAlignment: CrossAxisAlignment.start,
      children: [
        Container(
          width: 150,
          height: 150,
          decoration: BoxDecoration(
            borderRadius: BorderRadius.circular(10),
            image: const DecorationImage(image: AssetImage('img/iphone.jpg')),
          ),
        ),
        const SizedBox(
          width: 20,
        ),
        Flexible(
          flex: 1,
          child: SizedBox(
            height: 150,
            width: double.infinity,
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(
                  title,
                  style: const TextStyle(
                      fontSize: 20, fontWeight: FontWeight.bold),
                ),
                Text(
                  addr,
                  style: const TextStyle(decoration: TextDecoration.underline),
                ),
                Text("$price"),
                Row(
                  mainAxisAlignment: MainAxisAlignment.end,
                  children: const [Icon(Icons.favorite), Text("12개")],
                )
              ],
            ),
          ),
        )
      ],
    );
  }
}

```
