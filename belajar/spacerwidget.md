# Spacer Widget

__Sample code:__

```dart
import 'package:flutter/material.dart';

// SpacerWidget adalah fungsi untuk mengatur spasi antar widget dengan widget yang

class Spacerspasi extends StatelessWidget {
  const Spacerspasi({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Spacer Widget"),
        centerTitle: true,
      ),
      body: Center(
        child: Row(
          children: <Widget>[
            const Spacer(
              flex: 1,
            ),
            Container(
              width: 80,
              height: 80,
              color: Colors.red,
            ),
            const Spacer(
              flex: 1,
            ),
            Container(
              width: 80,
              height: 80,
              color: Colors.green,
            ),
            const Spacer(
              flex: 1,
            ),
            Container(
              width: 80,
              height: 80,
              color: Colors.blue,
            ),
            const Spacer(
              flex: 1,
            ),
          ],
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189258825-7e2b5aa5-a44d-4402-ba1a-9f741f076228.png" width="250" height="400">

[__-->Title Reference<--__]()
