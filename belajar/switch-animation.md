# APlikasi Switch Animasi

__Sample code:__

```dart
import 'package:flutter/material.dart';

class TombolAnimasiSwitch extends StatefulWidget {
  const TombolAnimasiSwitch({super.key});

  @override
  State<TombolAnimasiSwitch> createState() => _TombolAnimasiSwitchState();
}

// fungsi bool isON = false untuk mencatat keadaan tombol, dan variable false akan di gunakan di value nya widget Switch
bool isON = false;
// animasi yang akan di ubah ketika tombol di off kan
Widget myWidget = Container(
  width: 200,
  height: 100,
  decoration: BoxDecoration(
    color: Colors.red,
    border: Border.all(color: Colors.black, width: 3),
  ),
);

class _TombolAnimasiSwitchState extends State<TombolAnimasiSwitch> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Animation Tombol"),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: <Widget>[
            // AnimatedSwitcher akan membutuh kan child untuk animasi yang akan di ubah2
            AnimatedSwitcher(
              duration: const Duration(seconds: 1),
            // transitionBuilder adalah untuk perubahan2 animasi, dan membutuh kan animation yang berisi komponen untuk perubahan animasi nya
              transitionBuilder: ((child, animation) => ScaleTransition(scale: animation, child: child,)),
              child: myWidget,
            ),
            // Switch membutuhkan value untuk posisi awal nya, apakah di on atau di off, dan onPress ketika di tekan
            Switch(
              activeColor: Colors.green,
              inactiveThumbColor: Colors.red,
              inactiveTrackColor: Colors.red[200],
              value: isON,
              onChanged: (newValue) {
                isON = newValue;
                setState(
                  () {
                    if (isON)
                      // Text di bungkus Widget SizedBox dan center supaya Text Switch ON tidak naik turun - naik turun ketika tombol di on off kan
                      myWidget = SizedBox(
                        width: 200,
                        height: 100,
                        child: Center(
                          child: Text(
                            "Switch: ON",
                            style: TextStyle(
                                color: Colors.green,
                                fontWeight: FontWeight.w700,
                                fontSize: 20),
                          ),
                        ),
                      );
                    else
                      myWidget = Container(
                        width: 200,
                        height: 100,
                        decoration: BoxDecoration(
                          color: Colors.red,
                          border: Border.all(color: Colors.black, width: 3),
                        ),
                      );
                      // itu adalah contoh Switch animation dari container ke text, jikalau animasi nya dari container ke container maka jangan lupa berikan key: ValueKey(2) di container nya agar animasi container nya terlihat. 
                  },
                );
              },
            )
          ],
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/191415073-bb9627c7-f2a9-49d8-b29a-8ab537173bb4.png" width="200" height="400">

[__-->Title Reference<--__]()
