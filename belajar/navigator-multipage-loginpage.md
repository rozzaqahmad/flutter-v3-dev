# Navigator Login Page

__Sample code:__

```dart
import 'package:belajar_flutter/navigator_multipage_mainpage.dart';
import 'package:flutter/material.dart';

class Loginpage extends StatelessWidget {
  const Loginpage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            // Navigator adalah fungsi untuk menjalankan dari page ke page lain
            // pushReplacement adalah fungsi untuk menimpah page dengan page selanjut nya
            Navigator.pushReplacement(
              context,
              MaterialPageRoute(
                builder: (context) {
                  return const Mainpage();
                },
              ),
            );
          },
          child: const Text("LOGIN"),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189299046-a8694ba1-9f34-4311-9c20-9b73b94b386d.png" width="250" height="400">

[__-->Title Reference<--__]()
