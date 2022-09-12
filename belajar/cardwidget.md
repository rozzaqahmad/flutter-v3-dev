# Aplikasi Card Widget

__Sample code:__

```dart
import 'package:flutter/material.dart';

class APlikasiCard extends StatelessWidget {
  const APlikasiCard({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.blue[400],
      body: Container(
        margin: const EdgeInsets.all(10),
        child: ListView(
          children: <Widget>[
            buildCard(Icons.account_box, "Account Box"),
            buildCard(Icons.adb, "Serangga Android")
          ],
        ),
      ),
    );
  }

// Extract Method dari build Card
  Card buildCard(IconData iconData, String text) {
    return Card(
      elevation: 5,
      child: Row(
        children: <Widget>[
          Container(margin: const EdgeInsets.all(5), child: Icon(iconData)),
          Text(text),
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189570488-6e2ef4ba-9310-4253-be19-624d349b6a24.png" width="200" height="400">

[__-->Title Reference<--__]()
