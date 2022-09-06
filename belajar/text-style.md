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
            decorationStyle: TextDecorationStyle.wavy),
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/188572227-fa75b6aa-085d-492b-a5dd-031f4f6caba0.png" width="200" height="300">


[__-->Title Reference<--__]
