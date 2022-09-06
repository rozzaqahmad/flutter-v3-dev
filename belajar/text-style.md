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
            decorationThickness: 5,
            decorationStyle: TextDecorationStyle.wavy),
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/188572985-7eaa03a9-911c-440a-9b0c-acdd65b0748b.png" width="200" height="300">


[__-->Title Reference<--__]
