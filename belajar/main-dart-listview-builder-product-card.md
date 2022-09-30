# main.dart List View Builder Product Card

__Sample code:__

```dart
import 'dart:math';

import 'product_card.dart';
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';

void main(List<String> args) {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home:
          BlocProvider(create: (context) => ProductBloc([]), child: MainPage()),
    );
  }
}

class MainPage extends StatelessWidget {
  MainPage({Key? key}) : super(key: key);

  // Random r = Random(); fungsinya adalah untuk membuat bilangan random
  final Random r = Random();

  @override
  Widget build(BuildContext context) {
    ProductBloc bloc = BlocProvider.of<ProductBloc>(context);
    return Scaffold(
      appBar: AppBar(
        title: const Text("Demo ListView Builder"),
      ),
      body: Column(
        children: [
          ElevatedButton(
            onPressed: () {
              bloc.dispatch(r.nextInt(4) + 2);
            },
            child: const Text("Create Product"),
          ),
          BlocBuilder<ProductBloc, List<Product>>(
            builder: (context, products) => Expanded(
              child: Expanded(
                child: ListView.builder(
                  // products.length adalah panjang nya si produk
                  itemCount: products.length,
                  itemBuilder: (context, index) {
                    return ProductCard(
                      imageURL: products[index].imageURL,
                      name: products[index].name,
                      price: products[index].price.toString(),
                      onAddCardTap: () {},
                      onDecTap: () {},
                      onIncTap: () {},
                    );
                  },
                ),
              ),
            ),
          ),
        ],
      ),
    );
  }
}

class Product {
  String imageURL;
  String name;
  int price;

  Product({this.imageURL = "", this.name = "", this.price = 0});
}

class ProductBloc extends Bloc<int, List<Product>> {
  ProductBloc(super.initialState);

  List<Product> get initialState => [];

  Stream<List<Product>> mapEventToState(int event) async* {
    List<Product> products = [];
    for (int i = 0; i < event; i++) {
      products.add(Product(
          imageURL:
              "https://images.unsplash.com/photo-1612927601601-6638404737ce?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80",
          name: "Indomie Telor Spesial$i",
          price: (i + 1) * 5000));
    }
    yield products;
  }

  void dispatch(int i) {}
}

```

__Output:__


[__-->Title Reference<--__]()
