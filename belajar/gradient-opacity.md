# Gradient Opacity atau Transparansi Bergradasi

__Sample code:__

```dart
import 'package:flutter/material.dart';

class TransparantBergradasi extends StatelessWidget {
  const TransparantBergradasi({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Gradient Opacity"),
        centerTitle: true,
      ),
      body: Center(
        // image di bungkus ShaderMask agar image bisa di berikan gradien opacity atau transparansi bergradasi
        child: ShaderMask(
          // shaderCallback membutuh kan sebuah fungsi atau method untuk di panggil si Masking (penyamaran) nya, dan parameter nya adalah rectangle
          shaderCallback: (rectangle) {
            return const LinearGradient(
                    colors: [Colors.black, Colors.transparent],
                    begin: Alignment.topCenter,
                    end: Alignment.bottomCenter)
                // createShader akan meminta rectangle untuk di pakai masking (penyamaran) di image nya, jadi rectangle nya harus sesuai dengan ukuran image nya
                .createShader(
                    Rect.fromLTRB(0, 0, rectangle.width, rectangle.height));
          },
          // BlendMode.dstIn akan menunjukkan destination image ketika ada dua image saling overlap (tumpang tindih), dan gradient nya tidak akan di tampil kan dan hanya di pakai untuk masking(penyamaran), begitu pun juga warna apapun akan di abaikan, yang di pakai hanya opacity nya saja
          blendMode: BlendMode.dstIn,
          child: const Image(
            width: 300,
            image: NetworkImage(
                "https://images.unsplash.com/photo-1654154988309-eeae489508dd?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1631&q=80"),
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190966765-f79871bc-d4df-42ce-abd5-3dc78392a436.png" width="200" height="400">

[__-->Title Reference<--__]()
