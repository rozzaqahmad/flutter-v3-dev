# Navigator multipage Main Page

__Sample code:__

```dart
import 'package:belajar_flutter/navigator_multipage_secondpage.dart';
import 'package:flutter/material.dart';

class Mainpage extends StatelessWidget {
  const Mainpage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Main Page"),
        centerTitle: true,
      ),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            // Navigator adalah fungsi untuk menjalankan dari page ke page lain
            // push adalah fungsi untuk menaruh atau meletak kan page selanjut nya
            Navigator.push(
              context,
              MaterialPageRoute(
                builder: (context) {
                  return const Secondpage();
                },
              ),
            );
          },
          child: const Text("Go to Second Page"),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189299579-0feb74f9-b873-47a0-88e2-981aaeb2dc99.png" width="250" height="400">

[__-->Title Reference<--__]()
