# Title

__Sample code:__

```dart
import 'package:flutter/material.dart';

class DrafPage extends StatelessWidget {
  // const DrafPage({Key? key}) : super(key: key);

  final Color backgroundColor;
  final Widget body;

  DrafPage({required this.body, this.backgroundColor = Colors.pink});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: backgroundColor,
        title: const Text(
          "Demo MultiBloc And MultiPage App ",
        ),
      ),
      body: body,
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
