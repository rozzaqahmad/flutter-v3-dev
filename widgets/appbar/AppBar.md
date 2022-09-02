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
        body: const Center(
          child: Text("Hello World"),
        ),
      ),
    );
  }
}
```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/188051015-b239c7aa-85fa-47a9-b275-2cef43fc619d.png" widht="500" height="500"/> 

[__-->AppBar Reference<--__](https://api.flutter.dev/flutter/material/AppBar-class.html)
