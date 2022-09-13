# Tombol inkWell

__Sample code:__

```dart
import 'package:flutter/material.dart';

// inkWell adalah fungsi untuk memberikan efek pada button saat di tekan lama

class ButtonGradasi extends StatelessWidget {
  const ButtonGradasi({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Tombol Gradasi"),
        centerTitle: true,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceAround,
          children: <Widget>[
            ElevatedButton(
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.amber,
                shape: const StadiumBorder(),
              ),
              onPressed: () {},
              child: const Text("Raised Button"),
            ),
            Material(
              borderRadius: BorderRadius.circular(20),
              elevation: 3,
              child: Container(
                width: 150,
                height: 40,
                decoration: BoxDecoration(
                  borderRadius: BorderRadius.circular(20),
                  gradient: const LinearGradient(
                    colors: [Colors.purple, Colors.pink],
                    begin: Alignment.topCenter,
                    end: Alignment.bottomCenter,
                  ),
                ),
                child: Material(
                  borderRadius: BorderRadius.circular(20),
                  color: Colors.transparent,
                  child: InkWell(
                    borderRadius: BorderRadius.circular(20),
                    onTap: () {},
                    splashColor: Colors.amber,
                    child: const Center(
                      child: Text(
                        "My Button",
                        style: TextStyle(
                            color: Colors.white, fontWeight: FontWeight.w600),
                      ),
                    ),
                  ),
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/189811091-a314f2da-4bca-4cc4-8532-f51072d2209c.png" width="200" height="400">

[__-->Title Reference<--__]()
