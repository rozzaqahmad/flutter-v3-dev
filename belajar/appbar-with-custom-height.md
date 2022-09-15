# AppBar Dengan Custom Height

__Sample code:__

```dart
import 'package:flutter/material.dart';

class AppbarCustomHeight extends StatelessWidget {
  const AppbarCustomHeight({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      // PreferedSize adalah fungsi untuk mengubah ukuran AppBar
      appBar: PreferredSize(
        preferredSize: const Size.fromHeight(200),
        child: AppBar(
          backgroundColor: Colors.amber,
          // flexibleSpace adalah fungsi untuk mengatur posisi judul pada AppBar
          flexibleSpace: Positioned(
            left: 30,
            top: 50,
            bottom: 0,
            right: 0,
            // supaya tidak terlalu mepet maka text di bungkus lagi dengan Container supaya bisa di kasih margin untuk mengatur jarak Text
            child: Container(
              margin: const EdgeInsets.fromLTRB(132, 200, 0, 0),
              child: const Text(
                "AppBar With Custom Height",
                style: TextStyle(
                    fontSize: 20,
                    color: Colors.white,
                    fontWeight: FontWeight.w700),
              ),
            ),
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190312113-276875f0-3010-408d-b192-093f6c0c869a.png" width="200" height="400">

[__-->Title Reference<--__]()
