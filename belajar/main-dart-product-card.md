# main.dart Product Card

__Sample code:__

```dart
import 'product_card.dart';
import 'package:flutter/material.dart';
// ignore: import_of_legacy_library_into_null_safe, unused_import
import 'package:provider/provider.dart';

void main(List<String> args) {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          backgroundColor: firstColor,
          title: const Text("Product Card"),
          centerTitle: true,
        ),
        body:
            // Container di bungkus Change Notifier Provider untuk menerima saat ada perubahan dari fungsi Change Notifier
            ChangeNotifierProvider<ProductState>(
          create: (context) => ProductState(),
          child: Container(
            margin: const EdgeInsets.all(20),
            child: Align(
              alignment: Alignment.topCenter,
              child:
                  // ProductCard di bungkus dengan Consumer untuk menerima perubahan2 widget yang akan di rubah
                  Consumer<ProductState>(
                builder: (context, productState, _) => ProductCard(
                  imageURL:
                      "https://images.unsplash.com/photo-1612927601601-6638404737ce?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80",
                  name: "Indomie Telor Spesial",
                  price: "Rp.12.000",
                  notification: (productState.quantity > 5) ? "Diskon 10%" : "",
                  quantity: productState.quantity,
                  onAddCardTap: () {},
                  onIncTap: () {
                    productState.quantity++;
                  },
                  onDecTap: () {
                    productState.quantity--;
                  },
                ),
              ),
            ),
          ),
        ),
      ),
    );
  }
}

class ProductState with ChangeNotifier {
  int _quantity = 0;

  int get quantity => _quantity;
  set quantity(int newValue) {
    _quantity = newValue;
    notifyListeners();
  }
}
```

__Output:__

<img src ="https://user-images.githubusercontent.com/88677064/192972468-e51eb558-5c68-4410-877c-133ff9e824a4.png" width="200" height="400">

[__-->Title Reference<--__]()
