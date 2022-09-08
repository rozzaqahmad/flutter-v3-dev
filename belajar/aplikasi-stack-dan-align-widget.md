# Aplikasi Stack dan Align Widget

__Sample code:__

```dart
import 'package:flutter/material.dart';

// Stack dan Align Widget adalah untuk membuat komponen background menjadi terpisah

class StackAplikasi extends StatelessWidget {
  const StackAplikasi({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Latihan Stack_Align Widget"),
        centerTitle: true,
      ),
      body: Stack(
        children: <Widget>[
          Column(
            children: <Widget>[
              Flexible(
                flex: 1,
                child: Row(
                  children: <Widget>[
                    Flexible(
                      flex: 1,
                      child: Container(
                        color: Colors.white,
                      ),
                    ),
                    Flexible(
                      flex: 1,
                      child: Container(
                        color: Colors.black12,
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
                      child: Container(
                        color: Colors.black12,
                      ),
                    ),
                    Flexible(
                      flex: 1,
                      child: Container(
                        color: Colors.white,
                      ),
                    ),
                  ],
                ),
              )
            ],
          ),
          ListView(
            children: <Widget>[
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
              Container(
                margin: const EdgeInsets.all(10),
                child: const Text(
                  "Ini adalah Text yang ada di lapisan tengah dari Stack.",
                  style: TextStyle(
                    fontSize: (30),
                  ),
                ),
              ),
            ],
          ),

          // Fungsi align adalah untuk meletakan tombol di mana saja yg kita inginkan !

          Align(
            alignment: Alignment.bottomCenter,
            child: ElevatedButton(
              style:
                  ElevatedButton.styleFrom(backgroundColor: Colors.amber[700]),
              onPressed: () {},
              child: const Text("Tombol saya"),
            ),
          )
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189026075-067cb93c-fc6e-4cd7-bf42-14074c7c6c74.png" width="250" height="400">

[__-->Title Reference<--__]()
