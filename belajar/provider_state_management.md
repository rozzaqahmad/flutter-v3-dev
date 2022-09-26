# Provider State Management

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:flutter/foundation.dart';
import 'package:provider/provider.dart';
// provider state management multi provider adalah untuk fungsi performa aplikasi jika widget yang tampilan nya berubah lebih dari satu

class MultiProvider extends StatelessWidget {
  const MultiProvider({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    // Multi provider adalah fungsi untuk menampung material perubahan widget yang lebih dari satu, berbeda dengan changed notifyer provider
    return MultiProvider(
      providers: [
        ChangeNotifierProvider<Money>(
          create: (context) => Money(),
        ),
        ChangeNotifierProvider<Cart>(
          create: (context) => Cart(),
        ),
      ],
      child: Scaffold(
        floatingActionButton: Consumer<Money>(
          builder: (context, money, _) => Consumer<Cart>(
            builder: (context, cart, _) => FloatingActionButton(
              onPressed: () {
                if (money.balance >= 500) {
                  cart.quantity += 1;
                  money.balance -= 500;
                }
              },
              child: const Icon(
                Icons.add_shopping_cart,
                color: Colors.purple,
              ),
            ),
          ),
        ),
        appBar: AppBar(
          backgroundColor: Colors.purple,
          title: const Text("Multi Provider"),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Row(
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                  const Text("balance"),
                  Container(
                    height: 30,
                    width: 150,
                    margin: const EdgeInsets.all(5),
                    decoration: BoxDecoration(
                      borderRadius: BorderRadius.circular(5),
                      color: Colors.purple[100],
                      border: Border.all(color: Colors.purple, width: 2),
                    ),
                    child: Align(
                      alignment: Alignment.centerRight,
                      child: Consumer<Money>(
                        builder: (context, money, _) => Text(
                          money.balance.toString(),
                          style: const TextStyle(
                            color: Colors.purple,
                            fontWeight: FontWeight.w700,
                          ),
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Container(
                height: 30,
                margin: const EdgeInsets.all(5),
                decoration: BoxDecoration(
                  borderRadius: BorderRadius.circular(5),
                  color: Colors.purple[100],
                  border: Border.all(color: Colors.black, width: 2),
                ),
                child: Align(
                  alignment: Alignment.centerRight,
                  child: Consumer<Cart>(
                    builder: (context, cart, _) => Row(
                      mainAxisAlignment: MainAxisAlignment.spaceBetween,
                      children: [
                        Text(
                          "Apel (500) x" + cart.quantity.toString(),
                          style: TextStyle(
                            fontWeight: FontWeight.w700,
                            color: Colors.black,
                          ),
                        ),
                        Text(
                          (500 * cart.quantity).toString(),
                          style: const TextStyle(
                            fontWeight: FontWeight.w700,
                            color: Colors.black,
                          ),
                        ),
                      ],
                    ),
                  ),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

// fungsi class shared state nya
// fungsi untuk keranjang belanja nya

class Cart with ChangeNotifier {
  int _quantity = 0;

  int get quantity => _quantity;
  set quantity(int value) {
    _quantity = value;
    notifyListeners();
  }
}

// fungsi untuk uang nya nya

class Money with ChangeNotifier {
  int _balance = 10000;

  int get balance => _balance;
  set balance(int value) {
    _balance = value;
    notifyListeners();
  }
}

```

__Output:__


[__-->Title Reference<--__]()
