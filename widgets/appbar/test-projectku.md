# Test My Aplikacion

__Sample code:__

```dart
import 'package:flutter/material.dart';

class ProjectKu extends StatelessWidget {
  const ProjectKu({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: const Icon(
          Icons.menu_open,
          color: Colors.white,
        ),
        title: const Text(
          "Berkah Shop",
          style: TextStyle(color: Colors.white),
        ),
        centerTitle: true,
        actions: <Widget>[
          IconButton(
            onPressed: () {},
            icon: const Icon(Icons.notification_add),
          ),
          // IconButton(
          //   onPressed: () {},
          //   icon: const Icon(Icons.settings),
          // ),
        ],
        flexibleSpace: Container(
          decoration: const BoxDecoration(
            gradient: LinearGradient(
                colors: [
                  Color(0xff0096ff),
                  Color(0xff6610f2),
                ],
                begin: FractionalOffset.topLeft,
                end: FractionalOffset.bottomRight),
          ),
        ),
      ),
      // Element Body
      body: Stack(
        children: <Widget>[
          Container(
            height: double.infinity,
            color: const Color(0xfff0f0f0),
          ),
          //  List untuk Text
          ListView(
            children: [
              Title(
                color: Colors.black,
                child: const Text(
                  "Hi, user!",
                  textAlign: TextAlign.start,
                ),
              )
            ],
          ),
          const SizedBox(
            height: 45,
          ),
          // Container
          Container(
            width: 400,
            height: 250,
            margin: const EdgeInsets.fromLTRB(10, 200, 10, 100),
            padding: const EdgeInsets.all(15),
            color: Colors.white,
            child:
                // Column atau kolom
                Column(
              children: [
                // Row atau baris
                Row(
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: [
                    // Column atau baris
                    Column(
                      children: const [
                        Icon(
                          Icons.phone_android,
                          size: 30.0,
                          color: Colors.blue,
                        ),
                        Padding(
                          padding: EdgeInsets.only(top: 5.0),
                          child: Text(
                            "Pulsa",
                            style: TextStyle(fontSize: 11.0),
                          ),
                        ),
                      ],
                    ),
                    // Colom
                    const SizedBox(width: 18),
                    Column(
                      children: [
                        Icon(
                          Icons.games,
                          size: 30.0,
                          color: Colors.blue[400],
                        ),
                        const Padding(
                          padding: EdgeInsets.only(top: 5.0),
                          child: Text(
                            "Game",
                            style: TextStyle(fontSize: 11.0),
                          ),
                        ),
                      ],
                    ),
                    // Colom
                    const SizedBox(width: 18),
                    Column(
                      children: [
                        Icon(
                          Icons.flash_auto,
                          size: 30.0,
                          color: Colors.blue[400],
                        ),
                        const Padding(
                          padding: EdgeInsets.only(top: 5.0),
                          child: Text(
                            "PLN",
                            style: TextStyle(fontSize: 11.0),
                          ),
                        ),
                      ],
                    ),
                    // Colom
                    const SizedBox(width: 45),
                    Column(
                      children: [
                        Icon(
                          Icons.phone_in_talk,
                          size: 30.0,
                          color: Colors.blue[400],
                        ),
                        const Padding(
                          padding: EdgeInsets.only(top: 5.0),
                          child: Text(
                            "Paket Data",
                            style: TextStyle(fontSize: 11.0),
                          ),
                        ),
                      ],
                    ),
                    const SizedBox(width: 18),
                    Column(
                      children: [
                        Icon(
                          Icons.water_drop_rounded,
                          size: 30.0,
                          color: Colors.blue[400],
                        ),
                        const Padding(
                          padding: EdgeInsets.only(top: 5.0),
                          child: Text(
                            "PDAM",
                            style: TextStyle(fontSize: 11.0),
                          ),
                        ),
                      ],
                    ),
                    const SizedBox(width: 18),
                    Column(
                      children: [
                        Icon(
                          Icons.health_and_safety,
                          size: 30.0,
                          color: Colors.blue[400],
                        ),
                        const Padding(
                          padding: EdgeInsets.only(top: 5.0),
                          child: Text(
                            "bpjs",
                            style: TextStyle(fontSize: 11.0),
                          ),
                        ),
                      ],
                    ),
                    // Produk Baris Ke 2
                  ],
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190539632-d65c1943-b2c7-410a-85bf-cc271efa1bdc.png" width="200" height="400">

[__-->Title Reference<--__]()
