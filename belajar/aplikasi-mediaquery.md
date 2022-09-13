# Aplikasi Media Query

__Sample code:__

```dart
import 'package:flutter/material.dart';

// MediaQuery adalah fungsi untuk membuat layout yang bisa menyesuaikan layar nya

class AplikasiMediaQuery extends StatelessWidget {
  const AplikasiMediaQuery({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Latihan Media Query"),
        centerTitle: true,
      ),
      body:
      
          // Fungsi untuk menyesuaikan layout Column agar menjadi Row saat layar di lanscape agar gambar tidak error
          (MediaQuery.of(context).orientation == Orientation.portrait)
              ? Column(
                  children: generateContainers,
                )
              : Row(
                  children: generateContainers,
                ),
    );
  }

  List<Widget> get generateContainers {
    return <Widget>[
      Container(
        color: Colors.red,
        width: 100,
        height: 100,
      ),
      Container(
        color: Colors.green,
        width: 100,
        height: 100,
      ),
      Container(
        color: Colors.blue,
        width: 100,
        height: 100,
      ),
    ];
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189798177-71c66889-1a97-4660-8a9c-31a4941d69fb.png" width="400" height="200">

[__-->Title Reference<--__]()
