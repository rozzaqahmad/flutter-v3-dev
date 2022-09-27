# Main Dart Doc Comment

__Sample code:__

```dart
import 'package:berkahshop/doc_comment.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  final UserProfile profile = const UserProfile(
    name: "Hulk",
    role: "Hulk",
    photoURL:
        "https://images.unsplash.com/photo-1608272841063-67f50df421c3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80",
  );

  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          backgroundColor: Colors.red[900],
          title: const Text("Doc Comment Example"),
          centerTitle: true,
        ),
        body: Center(child: profile),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/192430516-2e8d8c7d-c857-432c-9032-0b62e0800cbc.png" width="200" height="400">

[__-->Title Reference<--__]()
