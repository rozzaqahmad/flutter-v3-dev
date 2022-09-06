# Aplikasi Container Widge

__Sample code:__

```dart
import 'package:belajar_flutter/main.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class ContainerWidget extends StatelessWidget {
  const ContainerWidget({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text("Latihan Container"),
        ),
        body: Container(
          color: Colors.red[100],
          margin: const EdgeInsets.fromLTRB(10, 15, 20, 25),
          padding: const EdgeInsets.only(bottom: 20, top: 20),
          child: Container(
            margin: const EdgeInsets.all(10),
            decoration: BoxDecoration(
              borderRadius: BorderRadius.circular(20),
              gradient: const LinearGradient(
                  begin: Alignment.topLeft,
                  end: Alignment.bottomRight,
                  colors: [Colors.blue, Colors.white]),
            ),
          ),
        ),
      ),
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
