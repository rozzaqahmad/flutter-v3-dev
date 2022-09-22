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
              image: AssetImage("assets/images/banner.jpeg"),
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
                  icon: Icon(Icons.add_circle_outline),
                  text: "Topup",
                ),
                SizedBox(
                  width: 43,
                ),
                Tab(
                  icon: Icon(Icons.currency_exchange_rounded),
                  text: "Transfer",
                ),
                SizedBox(
                  width: 43,
                ),
                Tab(
                  icon: Icon(Icons.add_card),
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
                mainAxisAlignment: MainAxisAlignment.start,
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  // Produk 1
                  Row(
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 0),
                        child: const Icon(Icons.phone_android,
                            color: Colors.lightBlueAccent),
                      ),
                      // Produk 2
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 40),
                        child: const Icon(Icons.four_g_mobiledata_sharp,
                            color: Colors.lightBlueAccent),
                      ),
                      // Produk 3
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.health_and_safety,
                            color: Colors.lightBlueAccent),
                      ),
                      // Produk 4
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.sports_esports,
                            color: Colors.lightBlueAccent),
                      ),
                    ],
                  ),
                  const SizedBox(
                    height: 4,
                  ),
                  // Baris ke dua
                  Row(
                    children: [
                      // Produk ke 5
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.electric_bolt,
                            color: Colors.lightBlueAccent),
                      ),
                      // Produk ke 6
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.crisis_alert,
                            color: Colors.lightBlueAccent),
                      ),
                      // Produk ke 7
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.circle_outlined,
                            color: Colors.lightBlueAccent),
                      ),
                      // Produk ke 8
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.water_drop,
                            color: Colors.lightBlueAccent),
                      ),
                    ],
                  ),
                  const SizedBox(
                    height: 17,
                  ),
                  // Baris ke tiga
                  Row(
                    children: [
                      // Produk ke 9
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.shopify_rounded,
                            color: Colors.lightBlueAccent),
                      ),
                      // Produk ke 10
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.perm_phone_msg_outlined,
                            color: Colors.lightBlueAccent),
                      ),
                      // Produk ke 11
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.sports_motorsports_outlined,
                            color: Colors.lightBlueAccent),
                      ),
                      // Icon lain nya ke 12
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
                                end: Alignment.bottomCenter)),
                        margin: const EdgeInsets.fromLTRB(40, 10, 0, 10),
                        child: const Icon(Icons.dataset_outlined,
                            color: Colors.lightBlueAccent),
                      ),
                    ],
                  ),
                ],
              ),
            ),
          ),
          const Text("Selalu ada di Berkah shop")
        ],
      ),
    );
  }
}


```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/191656833-c392552d-2cb4-454f-be18-d328663e541c.png" width="200" height="400">

[__-->Title Reference<--__]()
