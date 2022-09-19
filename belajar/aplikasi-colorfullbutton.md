# APlikasi Color Full Button

__Sample code:__

```dart
import 'package:flutter/material.dart';
// import 'dart:math' untuk pi radiant
import 'dart:math';

class ColorfullButton extends StatefulWidget {
  Color mainColor, secondColor;
  IconData iconData;

  @override
  State<ColorfullButton> createState() =>
      _ColorfullButtonState(mainColor, secondColor, iconData);
  ColorfullButton(this.mainColor, this.secondColor, this.iconData);
}

class _ColorfullButtonState extends State<ColorfullButton> {
  bool isPressed = false;
  Color mainColor, secondColor;
  IconData iconData;

  _ColorfullButtonState(this.mainColor, this.secondColor, this.iconData);

  @override
  Widget build(BuildContext context) {
    // Di bungkus lagi dengan TRansform.rotate agar tombol bisa terguling beberapa derajat, dan satuan derajat nya menggunakan pi radiant (pi = 3,14 adalah sama dengan 180 %)
    return Transform.rotate(
      // pi = 3,14 di bagi 4
      angle: pi / 4,
      // Di bungkus lagi dengan GestureDetector agar supaya komponen elevation atau bayangan bisa berubah2 sesuai warna yang di berikan ketika tombol di tekan
      child: GestureDetector(
        // onTapDown untuk fungsi ketika tombol di tekan akan menjalankan fungsi isPressed
        onTapDown: (details) => setState(() {
          isPressed = !isPressed;
        }),
        // onTapUp untuk fungsi ketika tombol di lepas akan menjalankan fungsi isPressed
        onTapUp: (details) => setState(() {
          isPressed = !isPressed;
        }),
        // onTapCancel adalah fungsi untuk menjalankan fungsi isPressed ketika tombol di tekan lalu tangan kita menggeser keluar dari tombol maka akan meng cancel isPressed nya
        onTapCancel: () {
          setState(() {
            isPressed = !isPressed;
          });
        },
        // Di bungkus material agar supaya tombol bisa di berikan komponen bayangan atau elevation
        child: Material(
          borderRadius: BorderRadius.circular(15),
          // jika tombol di tekan, maka bayangan nya 5, dan jika tidak di tekan maka bayangan nya menjadi 10
          elevation: (isPressed) ? 5 : 10,
          // jika tombol di tekan, maka warna bayangan nya secondColor, dan jika tidak di tekan maka warna bayangan nya mainColor
          shadowColor: (isPressed) ? secondColor : mainColor,
          // ClipRRect adalah fungsi untuk memotong komponer lingkaran
          child: ClipRRect(
            borderRadius: BorderRadius.circular(15),
            child: Stack(
              children: <Widget>[
                SizedBox(
                  width: 50,
                  height: 50,
                  child: Material(
                    borderRadius: BorderRadius.circular(15),
                    // (isPressed) ? mainColor : secondColor, cara membacanya adalah jika tombol di tekan, maka warna tombol yang di pakai adalah secondColor, dan jika tidak maka warna tombol yang di pakai akan mainColor
                    color: (isPressed) ? secondColor : mainColor,
                    // Icon di bungkus juga dengan trensform.Rotate supaya lambang android nya bisa di atur rotasi perputaran nya juga supaya tidak ikut memutar ketika tombol di putar
                    child: Transform.rotate(
                      angle: -pi / 4,
                      child: Icon(
                        iconData,
                        color: Colors.white,
                      ),
                    ),
                  ),
                ),
                // Membuat sizeBox lagi untuk membuat lingkaran - lingkaran putih di dalam tombol atau sizeBox sebelumnya
                // Widget Transform.translate adalah untuk menggeser lingkaran atau sizeBox sejauh offset nya (x-samping, y-bawah)
                Transform.translate(
                  offset: const Offset(30, 30),
                  child: SizedBox(
                    width: 50,
                    height: 50,
                    child: Material(
                        borderRadius: BorderRadius.circular(25),
                        color: Colors.white.withOpacity(0.5)),
                  ),
                ),
                // Membuat sizeBox lagi untuk membuat lingkaran - lingkaran putih di dalam tombol atau sizeBox sebelumnya
                // Widget Transform.translate adalah untuk menggeser lingkaran atau sizeBox sejauh offset nya (samping, bawah)
                Transform.translate(
                  offset: const Offset(-30, 30),
                  child: SizedBox(
                    width: 50,
                    height: 50,
                    child: Material(
                        borderRadius: BorderRadius.circular(25),
                        color: Colors.white.withOpacity(0.5)),
                  ),
                ),
                // Membuat sizeBox lagi untuk membuat lingkaran - lingkaran putih di dalam tombol atau sizeBox sebelumnya
                // Widget Transform.translate adalah untuk menggeser lingkaran atau sizeBox sejauh offset nya (samping, bawah)
                Transform.translate(
                  offset: const Offset(-30, -30),
                  child: SizedBox(
                    width: 50,
                    height: 50,
                    child: Material(
                        borderRadius: BorderRadius.circular(25),
                        color: Colors.white.withOpacity(0.5)),
                  ),
                ),
                // Membuat sizeBox lagi untuk membuat lingkaran - lingkaran putih di dalam tombol atau sizeBox sebelumnya
                // Widget Transform.translate adalah untuk menggeser lingkaran atau sizeBox sejauh offset nya (samping, bawah)
                Transform.translate(
                  offset: const Offset(30, -30),
                  child: SizedBox(
                    width: 50,
                    height: 50,
                    child: Material(
                        borderRadius: BorderRadius.circular(25),
                        color: Colors.white.withOpacity(0.5)),
                  ),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190949392-45c31a96-7581-402b-b3d0-6b9c51662eb2.png" width="200" height="400">

[__-->Title Reference<--__]()
