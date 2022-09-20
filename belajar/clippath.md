# Clip Path 

__Sample code:__

```dart
import 'package:flutter/material.dart';

class PemotongGambar extends StatelessWidget {
  const PemotongGambar({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Custom Clipper"),
        centerTitle: true,
      ),
      body: Center(
        child: ClipPath(
          clipper: MyClipper(),
          child: const Image(
            width: 300,
            image: NetworkImage(
                "https://images.unsplash.com/photo-1637801649256-d5e41e5f1f98?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"),
          ),
        ),
      ),
    );
  }
}

// class untuk memanggil fungsi pemotongan gambar

class MyClipper extends CustomClipper<Path> {
  // method getClip adalah method untuk mendapat kan clipper nya
  // Dan size adalah ukuran gambar nya yang akan di potong
  @override
  Path getClip(Size size)
  // fungsi untuk membentuk pola pemotongan gambar, x = titik awal koordinat 0,0 dan y = tinggi untuk pemotongan gambar nya
  {
    Path path = Path();
    // lineTo adalah titik koordinat awal 0,0 pada gambar
    path.lineTo(0, size.height);
    // quadraticBezierTo adalah method untuk mengatur pemotongan gambar
    // x1 dan y1 adalah titik kontrol di tengah pola yang akan di buat
    path.quadraticBezierTo(
        size.width / 2, size.height * 0.75, size.width, size.height);
    path.lineTo(size.width, 0);
    path.close();

    return path;
  }

// shouldReclip adalah method untuk apakah gambar nya perlu di clip ulang atau di potong ulang
  @override
  bool shouldReclip(covariant CustomClipper<Path> oldClipper) => false;
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/191167991-b5690672-20c0-48f6-8327-dc17bf723185.png" width="200" height="400">

[__-->Title Reference<--__]()
