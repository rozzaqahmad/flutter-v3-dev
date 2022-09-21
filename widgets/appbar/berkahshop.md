# Berkah Shop

__Sample code:__

```dart
import 'package:flutter/material.dart';

class BerkahShop extends StatelessWidget {
  const BerkahShop({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: const Color(0xFFEEEEEE),
      body: Stack(
        children: <Widget>[
          // Kotak 1
          Container(
            width: 400,
            height: 220,
            color: Colors.white,
            padding: const EdgeInsets.fromLTRB(0, 0, 0, 0),
            child: const Image(
              image: AssetImage("assets/images/banner.jpg"),
            ),
          ),
          // Kotak 2
          Container(
            width: 400,
            height: 90,
            decoration: BoxDecoration(
              color: Colors.white,
              border: Border.all(color: Colors.transparent),
              borderRadius: BorderRadius.circular(10),
            ),
            margin: const EdgeInsets.fromLTRB(0, 220, 0, 300),
            child: Row(
              children: const <Widget>[
                SizedBox(
                  width: 40,
                ),
                Tab(
                  icon: Icon(Icons.qr_code_2),
                  text: "Scan",
                ),
                SizedBox(
                  width: 43,
                ),
                Tab(
                  icon: Icon(Icons.money),
                  text: "Topup",
                ),
                SizedBox(
                  width: 43,
                ),
                Tab(
                  icon: Icon(Icons.card_giftcard_outlined),
                  text: "Transfer",
                ),
                SizedBox(
                  width: 43,
                ),
                Tab(
                  icon: Icon(Icons.card_giftcard),
                  text: "Terima",
                ),
              ],
            ),
          ),
          Center(
            // Kotak 3
            child: Container(
              width: 400,
              height: 400,
              decoration: BoxDecoration(
                color: Colors.white,
                borderRadius: BorderRadius.circular(10),
              ),
              margin: const EdgeInsets.fromLTRB(15, 340, 15, 250),
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: <Widget>[
                  // Stack Kotak Produk 1
                  Stack(
                    children: [
                      Container(
                        width: 40,
                        height: 40,
                        decoration: BoxDecoration(
                            borderRadius: BorderRadius.circular(10),
                            gradient: const LinearGradient(
                                colors: [
                                  Color.fromARGB(255, 225, 234, 235),
                                  Color.fromARGB(255, 236, 242, 244),
                                ],
                                begin: Alignment.topCenter,
                                end: Alignment.bottomCenter)
                            // color: Colors.lightBlue.withOpacity(0.2),
                            ),
                        margin: const EdgeInsets.fromLTRB(40, 10, 40, 10),
                        child: const Icon(Icons.phone_android,
                            color: Colors.lightBlueAccent),
                      ),
                    ],
                  ),
                  const Text("Pulsa")
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/191440140-2d1c999b-5242-4bbc-b081-71d2c9f2881f.png" width="200" height="400">

[__-->Title Reference<--__]()
