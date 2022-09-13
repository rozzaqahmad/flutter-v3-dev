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
        centerTitle: true,
      ),
      body: Container(
        margin: const EdgeInsets.all(20),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceAround,
          children: <Widget>[
            // TextField dan Text Decoration
            TextField(
              decoration: InputDecoration(
                fillColor: Colors.lightBlue[50],
                filled: true,
                icon: const Icon(Icons.adb),
                suffix: Container(
                  width: 5,
                  height: 5,
                  color: Colors.red,
                ),
                prefixIcon: const Icon(Icons.person),
                prefixText: "Name:",
                prefixStyle: const TextStyle(
                    color: Colors.blue, fontWeight: FontWeight.w600),
                labelText: "Nama Lengkap:",
                hintText: "Nama Lengkap nya..",
                hintStyle: const TextStyle(fontSize: 12),
                border: OutlineInputBorder(
                  borderRadius: BorderRadius.circular(10),
                ),
              ),
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

<img src="https://user-images.githubusercontent.com/88677064/189790299-310eaf2d-9d53-404d-b741-2a2d0279bd02.png"
width="200" height="400">

[__-->Title Reference<--__]()
