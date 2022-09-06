# Aplikasi Row Column

__Sample code:__

```dart

import 'package:flutter/material.dart';

class AplikasiRowColumns extends StatelessWidget {
  const AplikasiRowColumns({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Latihan Row dan Column"),
      ),
      body: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        crossAxisAlignment: CrossAxisAlignment.start,
        children: <Widget>[
          const Text("Text 1"),
          const Text("Text 2"),
          const Text("Text 3"),
          Row(
            children: const <Widget>[
              Text("Text 4"),
              Text("Text 5"),
              Text("Text 6"),
            ],
          )
        ],
      ),
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
