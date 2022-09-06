# Aplikasi Anonymous Method

__Sample code:__

```dart
import 'package:flutter/material.dart';

// anonymous adalah untuk mengembalikan nilai fungsi

class AplikasiAnonymous extends StatefulWidget {
  const AplikasiAnonymous({super.key});

  @override
  State<AplikasiAnonymous> createState() => _AplikasiAnonymousState();
}

class _AplikasiAnonymousState extends State<AplikasiAnonymous> {
  String pesan = "Ini adalah Text";

  void tekanTombol() {
    setState(() {
      pesan = "Tombol sudah di tekan !";
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Anonymous Method"),
        centerTitle: true,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(pesan),
            ElevatedButton(
              onPressed: tekanTombol,
              child: const Text("Tekan saya"),
            ),
          ],
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/188541116-c40aa0f3-33b7-472e-bd33-5f1d68da9b90.png" widht="500" height="500"/> 
