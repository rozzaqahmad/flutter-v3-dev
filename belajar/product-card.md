# Aplikasi Product Card

__Sample code:__

```dart
import 'package:flutter/material.dart';

const Color firstColor = Color(0xffF44336);
const Color secondColor = Color(0xff4CAF50);

class ProductCard extends StatelessWidget {
  final String imageURL;
  final String name;
  final String price;
  final int quantity;
  final String notification;
  // VoidCallBack adalah final void function yg di tugaskan untuk memanggil sebuah void function (The argument type 'Function' can't be assigned to the parameter type 'void Function()?'.)
  final VoidCallback onAddCardTap;
  final VoidCallback onIncTap;
  final VoidCallback onDecTap;

  final TextStyle textStyle = TextStyle(
    fontSize: 14,
    fontWeight: FontWeight.bold,
    color: Colors.grey[800],
  );

  ProductCard({
    Key? key,
    this.imageURL = "",
    this.name = "",
    this.price = "",
    this.quantity = 0,
    this.notification = "",
    // required di gunakan agar tidak error ketika parameter nya berdefault null di flutter null safety
    required this.onAddCardTap,
    required this.onIncTap,
    required this.onDecTap,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Stack(
      children: [
        // Container notifikasi
        AnimatedContainer(
          padding: const EdgeInsets.all(5),
          // di beri margin agar tidak miring dan lurus sejajar pada kotak card dari kiri 10 dan kanan nya juga 10
          margin: const EdgeInsets.only(left: 10, right: 10),
          duration: const Duration(milliseconds: 300),
          width: 130,
          // ignore: unnecessary_null_comparison
          height: (notification != null) ? 270 : 250,
          decoration: BoxDecoration(
            boxShadow: [
              BoxShadow(
                  blurRadius: 3,
                  offset: const Offset(1, 1),
                  color: Colors.black.withOpacity(0.3)),
            ],
            borderRadius: const BorderRadius.only(
              bottomLeft: Radius.circular(8),
              bottomRight: Radius.circular(8),
            ),
            color: secondColor,
          ),
          child: Align(
            alignment: Alignment.bottomCenter,
            child: Text(
              // ignore: unnecessary_null_comparison
              (notification != null) ? notification : "",
              style: textStyle.copyWith(color: Colors.white, fontSize: 12),
            ),
          ),
        ),
        // Container card
        Container(
          width: 150,
          height: 250,
          decoration: BoxDecoration(
            color: Colors.white,
            borderRadius: BorderRadius.circular(16),
            boxShadow: [
              BoxShadow(
                color: Colors.black.withOpacity(0.2),
                blurRadius: 6,
                offset: const Offset(1, 1),
              ),
            ],
          ),
          // kolom gambar produk dan nama produk dan harga
          child: Column(
            // MainAxisAlignment.spaceBetween adalah supaya container nya terbagi menjadi 2 kolom yaitu atas bawah, atau supaya space kosong nya di taruh di tengah2 widget
            mainAxisAlignment: MainAxisAlignment.spaceBetween,
            children: [
              // kolom atas
              Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  Container(
                    width: 150,
                    height: 100,
                    decoration: BoxDecoration(
                      borderRadius: const BorderRadius.only(
                          topLeft: Radius.circular(16),
                          topRight: Radius.circular(16)),
                      image: DecorationImage(
                          image: NetworkImage(imageURL), fit: BoxFit.cover),
                    ),
                  ),
                  Container(
                    margin: const EdgeInsets.all(5),
                    child: Text(
                      name,
                      style: textStyle,
                    ),
                  ),
                  Container(
                    margin: const EdgeInsets.only(left: 5, right: 5),
                    child: Text(
                      price,
                      style:
                          textStyle.copyWith(fontSize: 12, color: firstColor),
                    ),
                  ),
                ],
              ),
              // kolom bawah
              Column(
                children: [
                  const SizedBox(height: 30),
                  //     // Tombol + dan -
                  Container(
                    width: 140,
                    height: 30,
                    decoration: BoxDecoration(
                      border: Border.all(color: firstColor),
                    ),
                    child: Row(
                      // spaceBetween fungsi nya adalah jika ada space kosong antara 3 buah button, maka akan di taruh di antara 3 button tersebut
                      mainAxisAlignment: MainAxisAlignment.spaceBetween,
                      children: [
                        GestureDetector(
                          onTap: onDecTap,
                          child: Container(
                              width: 30,
                              height: 30,
                              color: firstColor,
                              child: const Icon(
                                Icons.remove,
                                size: 18,
                                color: Colors.white,
                              )),
                        ),
                        Text(quantity.toString(), style: textStyle),
                        GestureDetector(
                          onTap: onIncTap,
                          child: Container(
                            width: 30,
                            height: 30,
                            color: firstColor,
                            child: const Icon(
                              Icons.add,
                              size: 18,
                              color: Colors.white,
                            ),
                          ),
                        ),
                      ],
                    ),
                  ),
                ],
              ),

              // Tombol Keranjang
              SizedBox(
                width: 140,
                child: ElevatedButton(
                  onPressed: onAddCardTap,
                  // color: firstColor,
                  child: const Icon(
                    Icons.add_shopping_cart,
                    size: 18,
                    color: Colors.white,
                  ),
                ),
              ),
            ],
          ),
        ),
      ],
    );
  }
}


```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/192973055-a5a02413-ca1b-426c-be33-6d780ce6ccf3.png" width="200" height="400">

[__-->Title Reference<--__]()
