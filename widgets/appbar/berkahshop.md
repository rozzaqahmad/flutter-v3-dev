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
                  width: 45,
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
                children: [
                  const SizedBox(height: 25),
                  // Produk 1
                  Row(
                    children: [
                      Produk(Icons.phone_android),
                      Produk(Icons.four_g_mobiledata_sharp),
                      Produk(Icons.health_and_safety),
                      Produk(Icons.sports_esports),
                    ],
                  ),
                  const SizedBox(height: 25),
                  Row(
                    children: [
                      Produk(Icons.electric_bolt),
                      Produk(Icons.crisis_alert),
                      Produk(Icons.circle_outlined),
                      Produk(Icons.water_drop),
                    ],
                  ),
                  const SizedBox(height: 25),
                  Row(
                    children: [
                      Produk(Icons.shopify_rounded),
                      Produk(Icons.perm_phone_msg_outlined),
                      Produk(Icons.sports_motorsports_outlined),
                      Produk(Icons.dataset_outlined),
                    ],
                  ),
                ],
              ),
            ),
          ),
          // Text selau ada di Berkah shop
          Container(
            margin: const EdgeInsets.only(left: 35.0, top: 645.0),
            child: const Text(
              "Selalu ada di Berkahshop",
              style: TextStyle(fontWeight: FontWeight.bold),
            ),
          ),
          Container(
            margin: const EdgeInsets.only(left: 35.0, top: 670.0),
            child: const Text(
              "Mudah Dapatkan Info Akses Terbaru",
              style: TextStyle(fontSize: 12.0, color: Colors.grey),
            ),
          ),
          // container banner
          Container(
            width: 320,
            height: 130,
            margin: const EdgeInsets.only(left: 30.0, top: 700.0),
            // decoration: BoxDecoration(borderRadius: BorderRadius.circular(20)),
            child: const Image(
              image: AssetImage("assets/images/bannershop.jpg"),
              fit: BoxFit.cover,
            ),
          ),
        ],
      ),
    );
  }
}

// ignore: must_be_immutable
class Produk extends StatefulWidget {
  IconData iconData;

  Produk(this.iconData, {Key? key}) : super(key: key);

  @override
  State<Produk> createState() => _ProdukState();
}

class _ProdukState extends State<Produk> {
  @override
  Widget build(BuildContext context) {
    return Container(
      width: 40,
      height: 40,
      decoration: BoxDecoration(
        borderRadius: BorderRadius.circular(10),
        gradient: const LinearGradient(colors: [
          Color.fromARGB(255, 225, 234, 235),
          Color.fromARGB(255, 236, 242, 244),
        ], begin: Alignment.topCenter, end: Alignment.bottomCenter),
      ),
      margin: const EdgeInsets.fromLTRB(40, 10, 0, 0),
      child: Icon(
        widget.iconData,
        color: Colors.lightBlue,
      ),
    );
  }
}



```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/192685122-3cab12f3-aa7a-4505-bcb9-88df817c1566.png" width="200" height="400">

[__-->Title Reference<--__]()
