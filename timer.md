# Aplikasi Stop Watch

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'dart:async';

class Stopwacth extends StatefulWidget {
  const Stopwacth({Key? key}) : super(key: key);

  @override
  State<Stopwacth> createState() => _StopwacthState();
}

bool isStop = true;
bool isBlack = true;
// method angka untuk stop watch
int counter = 0;

class _StopwacthState extends State<Stopwacth> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Timer Demo"),
        centerTitle: true,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              counter.toString(),
              style: TextStyle(
                  color: (isBlack) ? Colors.black : Colors.red,
                  fontSize: 40,
                  fontWeight: FontWeight.bold),
            ),
            const SizedBox(
              height: 10,
            ),
            ElevatedButton(
              onPressed: () {
                Timer(const Duration(seconds: 5), () {
                  setState(() {
                    isBlack = !isBlack;
                  });
                });
              },
              child: const Text("Ubah warna 5 detik kemudian"),
            ),
            const SizedBox(
              height: 10,
            ),
            ElevatedButton(
              onPressed: () {
                Timer(const Duration(seconds: 0), () {
                  setState(() {
                    isBlack = !isBlack;
                  });
                });
              },
              child: const Text("Ubah warna secara langsung"),
            ),
            const SizedBox(
              height: 10,
            ),
            ElevatedButton(
              onPressed: () {
                counter = 0;
                isStop = false;
                Timer.periodic(const Duration(seconds: 1), (timer) {
                  if (isStop) timer.cancel();
                  setState(() {
                    counter++;
                  });
                });
              },
              child: const Text("Start Timer"),
            ),
            const SizedBox(
              height: 10,
            ),
            ElevatedButton(
              onPressed: () {
                isStop = true;
              },
              child: const Text("Stop Timer"),
            ),
          ],
        ),
      ),
    );
  }
}

```

__Output:__

<img src = "https://user-images.githubusercontent.com/88677064/192680381-1fefa8ff-7fab-4e38-a691-774333f4e914.png" width="200" height="400">

[__-->Title Reference<--__]()
