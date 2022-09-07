# Aplikasi Flexible Layout

__Sample code:__

```dart
import 'package:flutter/material.dart';

//flexibel layout adalah fungsi untuk agar supaya tampilan widget tidak error saat mengikuti layar

class AplikasiFlexibleLayout extends StatelessWidget {
  const AplikasiFlexibleLayout({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Flexible Layout"),
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
                    child: Container(
                      color: Colors.red[100],
                    )),
                Flexible(
                    flex: 1,
                    child: Container(
                      color: Colors.green[100],
                    )),
                Flexible(
                    flex: 1,
                    child: Container(
                      color: Colors.purple[100],
                    )),
              ],
            ),
          ),
          Flexible(
            flex: 2,
            child: Container(
              color: Colors.amber[100],
            ),
          ),
          Flexible(
            flex: 1,
            child: Container(
              color: Colors.blue[100],
            ),
          ),
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/188830523-988a8a5d-fb8e-469f-a4a1-d759c58602de.png" width="230" height="400">

[__-->Title Reference<--__]()
