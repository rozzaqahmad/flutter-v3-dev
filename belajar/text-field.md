# Aplikasi Text Field

__Sample code:__

```dart
import 'package:flutter/material.dart';

class AplikasiTextField extends StatefulWidget {
  const AplikasiTextField({super.key});

  @override
  State<AplikasiTextField> createState() => _AplikasiTextFieldState();
}

class _AplikasiTextFieldState extends State<AplikasiTextField> {
  TextEditingController controller = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Latihan Text Field"),
      ),
      body: Container(
        margin: const EdgeInsets.all(20),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceAround,
          children: <Widget>[
            TextField(
              onChanged: (value) {
                setState(
                  () {},
                );
              },
              controller: controller,
            ),
            Text(controller.text)
          ],
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189658211-401e17e2-4419-47cc-898b-82a5baa64b4c.png" width="200" height="400">

[__-->Title Reference<--__]()
