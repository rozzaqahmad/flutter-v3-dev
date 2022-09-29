# main.dart 

__Sample code:__

```dart
import 'package:berkahshop/test.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
          // Kotak 3
          child: Container(
            width: 400,
            height: 400,
            decoration: BoxDecoration(
              color: Colors.white,
              borderRadius: BorderRadius.circular(10),
            ),
            margin: const EdgeInsets.fromLTRB(15, 300, 15, 200),
            child: Column(
              children: [
                const SizedBox(height: 25),
                Row(
                  children: [
                    TestAja(Icons.phone_android),
                    TestAja(Icons.four_g_mobiledata_sharp),
                    TestAja(Icons.health_and_safety),
                    TestAja(Icons.sports_esports),
                  ],
                ),
                const SizedBox(height: 25),
                Row(
                  children: [
                    TestAja(Icons.electric_bolt),
                    TestAja(Icons.crisis_alert),
                    TestAja(Icons.circle_outlined),
                    TestAja(Icons.water_drop),
                  ],
                ),
                const SizedBox(height: 25),
                Row(
                  children: [
                    TestAja(Icons.shopify_rounded),
                    TestAja(Icons.perm_phone_msg_outlined),
                    TestAja(Icons.sports_motorsports_outlined),
                    TestAja(Icons.dataset_outlined),
                  ],
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
