# Aplikasi Animated Padding Widget

__Sample code:__

```dart
import 'dart:ffi';

import 'package:flutter/material.dart';

class AnimasiPaddingWidget extends StatefulWidget {
  const AnimasiPaddingWidget({Key? key}) : super(key: key);

  @override
  State<AnimasiPaddingWidget> createState() => _AnimasiPaddingWidgetState();
}

class _AnimasiPaddingWidgetState extends State<AnimasiPaddingWidget> {
  // Untuk Padding
  double myPadding = 5;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Animasi Padding Widget"),
        centerTitle: true,
      ),
      body: Column(
        children: <Widget>[
          Flexible(
            flex: 1,
            child: Row(
              children: <Widget>[
                Flexible(
                  flex: 1,
                  child: AnimatedPadding(
                    duration: const Duration(seconds: 1),
                    padding: EdgeInsets.all(myPadding),
                    child: GestureDetector(
                      onTap: () {
                        setState(() {
                          myPadding = 20;
                        });
                      },
                      child: Container(
                        color: Colors.red,
                      ),
                    ),
                  ),
                ),
                Flexible(
                  flex: 1,
                  child: AnimatedPadding(
                    duration: const Duration(seconds: 1),
                    padding: EdgeInsets.all(myPadding),
                    child: Container(
                      color: Colors.green,
                    ),
                  ),
                ),
              ],
            ),
          ),
          Flexible(
            flex: 1,
            child: Row(
              children: <Widget>[
                Flexible(
                  flex: 1,
                  child: AnimatedPadding(
                    duration: const Duration(seconds: 1),
                    padding: EdgeInsets.all(myPadding),
                    child: Container(
                      color: Colors.blue,
                    ),
                  ),
                ),
                Flexible(
                  flex: 1,
                  child: AnimatedPadding(
                    duration: const Duration(seconds: 1),
                    padding: EdgeInsets.all(myPadding),
                    child: Container(
                      color: Colors.yellow,
                    ),
                  ),
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/191660595-72d92693-538b-4642-afec-8f69cf8d50e0.png" width="200" height="400">

[__-->Title Reference<--__]()
