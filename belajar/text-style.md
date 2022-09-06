# Text Style

__Sample code:__

```dart
import 'package:flutter/material.dart';

class AplikasiTextStyle extends StatelessWidget {
  const AplikasiTextStyle({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Ini adalah Text"),
      ),
      body: const Center(
        child: Text(
          "Ini adalah Text",
          style: TextStyle(
            fontStyle: FontStyle.italic,
            fontSize: 30,
            decoration: TextDecoration.underline,
            decorationColor: Colors.red,
            decorationThickness: 2,
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/188569224-f5ff66ff-2ac6-4187-8e3d-9d5b7ff46930.png" width="200" height="300">


[__-->Title Reference<--__]()
