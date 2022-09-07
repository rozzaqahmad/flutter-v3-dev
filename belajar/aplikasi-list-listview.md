# Title

__Sample code:__

```dart
import 'package:flutter/material.dart';

// list view agar bisa di scroll ke bawah widget aplikasi nya

class AplikasiBerkas extends StatefulWidget {
  const AplikasiBerkas({super.key});

  @override
  State<AplikasiBerkas> createState() => AplikasiBerkasState();
}

class AplikasiBerkasState extends State<AplikasiBerkas> {
  List<Widget> widgets = [];
  int counter = 1;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Aplikasi Data"),
        centerTitle: true,
      ),
      body: ListView(
        children: <Widget>[
          Row(
            mainAxisAlignment: MainAxisAlignment.spaceAround,
            children: <Widget>[
              ElevatedButton(
                onPressed: () {
                  setState(() {
                    widgets.removeLast();
                    counter--;
                  });
                },
                child: const Text("Hapus Data"),
              ),
              ElevatedButton(
                onPressed: () {
                  setState(() {
                    widgets.add(
                      Text(
                        "Data ke $counter",
                        style: const TextStyle(fontSize: 15),
                      ),
                    );
                    counter++;
                  });
                },
                child: const Text("Tambah Data"),
              ),
            ],
          ),
          Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: widgets,
          ),
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/188789559-91812a61-c59d-4842-b12e-83f457ebe090.png" width="170" height="340">


[__-->Title Reference<--__]()
