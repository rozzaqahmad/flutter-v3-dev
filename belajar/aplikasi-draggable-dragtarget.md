# Aplikasi Draggable dan DragTarget

__Sample code:__

```dart
import 'package:flutter/material.dart';

class AplikasiDraggableTarget extends StatefulWidget {
  const AplikasiDraggableTarget({super.key});

  @override
  State<AplikasiDraggableTarget> createState() =>
      _AplikasiDraggableTargetState();
}

class _AplikasiDraggableTargetState extends State<AplikasiDraggableTarget> {
  Color color1 = Colors.red;
  Color color2 = Colors.amber;
  late Color targetColor;
  // bool untuk mencatat apakah tempat target sudah menerima data yang di Dragg atau belum
  bool isAccepted = false;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Draggable dan Drag Target"),
        centerTitle: true,
      ),
      body: Column(
        mainAxisAlignment: MainAxisAlignment.spaceEvenly,
        children: <Widget>[
          Row(
            mainAxisAlignment: MainAxisAlignment.spaceAround,
            children: <Widget>[
              // Draggable adalah fungsi untuk membawa data komponen atau widget yang akan di dragg ke suatu tempat
              Draggable<Color>(
                data: color1,
                // ChildWhenDRagging adalah fungsi untuk membuat komponen yang di dragg bentuk nya seperti apa
                childWhenDragging: const SizedBox(
                  width: 50,
                  height: 50,
                  child: Material(
                    color: Colors.black26,
                    shape: StadiumBorder(),
                  ),
                ),
                // Feedback adalah fungsi untuk membentuk komponen ketika di Dragg
                feedback: SizedBox(
                  width: 50,
                  height: 50,
                  child: Material(
                    color: color1.withOpacity(0.5),
                    shape: const StadiumBorder(),
                  ),
                ),
                child: SizedBox(
                  width: 50,
                  height: 50,
                  child: Material(
                    color: color1,
                    shape: const StadiumBorder(),
                  ),
                ),
              ),
              Draggable<Color>(
                data: color2,
                // ChildWhenDRagging adalah fungsi untuk membuat komponen yang di dragg bentuk nya seperti apa
                childWhenDragging: const SizedBox(
                  width: 50,
                  height: 50,
                  child: Material(
                    color: Colors.black26,
                    shape: StadiumBorder(),
                  ),
                ),
                // Feedback adalah fungsi untuk membentuk komponen ketika di Dragg
                feedback: SizedBox(
                  width: 50,
                  height: 50,
                  child: Material(
                    color: color1.withOpacity(0.5),
                    shape: const StadiumBorder(),
                  ),
                ),
                child: SizedBox(
                  width: 50,
                  height: 50,
                  child: Material(
                    color: color2,
                    shape: const StadiumBorder(),
                  ),
                ),
              ),
            ],
          ),
          // Dragtarget adalah tempat untuk menaruh komponen yang akan di Dragg
          // onWillAccept adalah untuk fungsi apakah data yang di Dragg akan di terima atau tidak
          // onAccept adalah fungsi yang akan di lakukan ketika telah menerima data yang di Dragg
          // builder adalah sebuah method yang akan di pakai untuk membuat widget DragTarget

          DragTarget<Color>(
              onWillAccept: (value) => true,
              onAccept: (value) {
                isAccepted = true;
                targetColor = value;
              },
              builder: (context, candidates, rejected) {
                return (isAccepted)
                    ? SizedBox(
                        width: 100,
                        height: 100,
                        child: Material(
                          color: targetColor,
                          shape: const StadiumBorder(),
                        ),
                      )
                    : const SizedBox(
                        width: 100,
                        height: 100,
                        child: Material(
                          color: Colors.black26,
                          shape: StadiumBorder(),
                        ),
                      );
              })
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189286122-476da9f4-f8cf-4ccc-adbd-c72e0c7e4b5b.png" width="200" height="400">

[__-->Title Reference<--__]()
