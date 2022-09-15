# Aplikasi Tab Bar

__Sample code:__

```dart
import 'package:flutter/material.dart';

class AplikasiTabBar extends StatelessWidget {
  const AplikasiTabBar({super.key});

  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      // length adalah jumlah Tab Bar yang akan di buat
      length: 4,
      child: Scaffold(
        appBar: AppBar(
          title: const Text("Contoh Tab Bar"),
          centerTitle: true,
          // lalu di bagian bawah nya atau bottom nya baru di kasih Tab Bar yang ada kumpulan tabs nya
          bottom: const TabBar(
            tabs: <Widget>[
              Tab(
                icon: Icon(Icons.comment),
                text: "Comments",
              ),
              Tab(
                child:
                    Image(image: AssetImage("assets/images/logo-payuni.png")),
              ),
              Tab(
                child: Icon(Icons.computer),
              ),
              Tab(
                text: "News",
              ),
            ],
          ),
        ),
        body: const TabBarView(
          // children nya adalah kumpulan tampilan untuk tiap Tab nya
          children: <Widget>[
            Center(
              child: Text("Tab 1"),
            ),
            Center(
              child: Text("Tab 2"),
            ),
            Center(
              child: Text("Tab 3"),
            ),
            Center(
              child: Text("Tab 4"),
            ),
          ],
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190317563-a5a8c1b8-ee31-48f0-91d5-23ae70e46a75.png" width="200" height="400">

[__-->Title Reference<--__]()
