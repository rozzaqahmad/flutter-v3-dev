# Navigator Multipage SecondPage

__Sample code:__

```dart
import 'package:belajar_flutter/navigator_multipage_mainpage.dart';
import 'package:flutter/material.dart';

class Secondpage extends StatelessWidget {
  const Secondpage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Second Page"),
        centerTitle: true,
      ),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            // Navigator adalah fungsi untuk menjalankan dari page ke page lain
            // pop adalah fungsi untuk mengangkat page saat ini untuk kembali ke page sebelum nya
            Navigator.pop(context);
          },
          child: const Text("Back"),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189300251-464d3a07-f17b-461d-8f92-48d8653f5813.png" width="200" height="400">

[__-->Title Reference<--__]()
