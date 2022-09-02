# AppBar Widgets

__Sample code:__

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
          title: const Text("AppBar Widget"),
          leading: const Icon(Icons.menu_open),
          actions: const [
            Icon(Icons.notification_add),
            SizedBox(width: 8.0),
            Icon(Icons.shopping_cart),
            SizedBox(width: 5.0),
          ],
        ),
        body: const Center(
          child: Text("Hello World"),
        ),
      ),
    );
  }
}

```


__Output:__


[__-->AppBar Reference<--__](https://api.flutter.dev/flutter/material/AppBar-class.html)
