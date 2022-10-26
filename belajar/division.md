# Division

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:division/division.dart';

class CustomBUtton extends StatelessWidget {
  const CustomBUtton({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Division Example"),
        backgroundColor: Colors.red[900],
      ),
      backgroundColor: Colors.grey[900],
      body: Center(
        child: Parent(
          // AngleFormat.degree untuk rotate
          style: ParentStyle(angleFormat: AngleFormat.degree)
            ..background.color(Colors.lightBlue)
            ..borderRadius(all: 60)
            ..border(all: 3, color: Colors.lightBlue)
            ..elevation(5)
            ..rotate(-5),
          child: Container(
            child: Txt(
              "division",
              style: TxtStyle()
                ..fontSize(30)
                ..bold()
                ..textColor(Colors.white),
            ),
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/197975081-e40b7394-2645-44b8-a4d9-969982e610a9.png" width="200" height="400">

[__-->Title Reference<--__]()
