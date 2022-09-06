# Aplikasi Text Widget

__Sample code:__

```dart

import 'package:flutter/material.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Aplikasi Hello World"),
        leading: const Icon(Icons.menu_open),
        actions: const [
          Icon(Icons.notification_add),
          SizedBox(width: 8.0),
          Icon(Icons.shopping_cart),
          SizedBox(width: 5.0),
        ],
        backgroundColor: Colors.blue[400],
        centerTitle: true,
        elevation: 0,
      ),
      body: Center(
        child: Container(
          color: Colors.lightBlue[300],
          width: 150,
          height: 100,
          child: const Text(
            "Saya sedang melatih kemampuan flutter saya.",
            // property tetx
            style: TextStyle(
                color: Colors.white,
                fontStyle: FontStyle.italic,
                fontWeight: FontWeight.w700,
                fontSize: 20),
          ),
        ),
      ),
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
