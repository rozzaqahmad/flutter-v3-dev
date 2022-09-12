# Aplikasi AppBar Gradasi

__Sample code:__

```dart
import 'package:flutter/material.dart';

class AppBarGradasi extends StatelessWidget {
  const AppBarGradasi({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: const Icon(
          Icons.adb,
          color: Colors.white,
        ),
        title: const Text(
          "AppBar Example",
          style: TextStyle(color: Colors.white),
        ),
        centerTitle: true,
        actions: <Widget>[
          IconButton(
            onPressed: () {},
            icon: const Icon(Icons.settings),
          ),
          IconButton(
            onPressed: () {},
            icon: const Icon(Icons.exit_to_app),
          ),
        ],
        flexibleSpace: Container(
          decoration: const BoxDecoration(
            gradient: LinearGradient(
                colors: [
                  Color(0xff0096ff),
                  Color(0xff6610f2),
                ],
                begin: FractionalOffset.topLeft,
                end: FractionalOffset.bottomRight),
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189565769-9fa9e851-edba-4ef0-b998-38290e5cec5d.png" width="200" height="400">

[__-->Title Reference<--__]()
