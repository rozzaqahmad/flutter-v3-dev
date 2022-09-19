# main.dart Aplikasi Color Full Button

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'aplikasi_colorfull_button.dart';

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
          title: const Text("Colorfull Button"),
          centerTitle: true;
        ),
        body: Center(
          child: Row(
            mainAxisAlignment: MainAxisAlignment.spaceEvenly,
            children: <Widget>[
              ColorfullButton(Colors.pink, Colors.blue, Icons.adb),
              ColorfullButton(Colors.amber, Colors.red, Icons.comment),
              ColorfullButton(Colors.green, Colors.purple, Icons.computer),
              ColorfullButton(Colors.blue, Colors.yellow, Icons.contact_phone),
            ],
          ),
        ),
      ),
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
