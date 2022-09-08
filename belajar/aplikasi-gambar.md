# Gambar Aplikasi

__Sample code:__

```dart
import 'package:flutter/material.dart';

class Gambar extends StatelessWidget {
  const Gambar({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Latihan gambar"),
        centerTitle: true,
      ),
      body: Center(
        child: Container(
          color: Colors.blue[100],
          width: 200,
          height: 200,
          padding: const EdgeInsets.all(3),
          child: const Image(
            image: NetworkImage(
                "https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cGhvbmV8ZW58MHx8MHx8&auto=format&fit=crop&w=500&q=60"),
            fit: BoxFit.contain,
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189054853-785e5375-d542-4524-bd78-3b9a5d3cd023.png" widht="300" height="400">

[__-->Title Reference<--__]()
