# Aplikasi Hero Animation dan ClipRRect Widget

__Sample code:__

```dart
import 'package:flutter/material.dart';

// Hero Animation adalah fungsi untuk memberikan animasi saat pindah dari page ke page yang lain

class HeroAnimation extends StatelessWidget {
  const HeroAnimation({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.lightBlue[50],
      appBar: AppBar(
        backgroundColor: Colors.black,
        title: const Text(
          "Latihan Hero Animation",
          style: TextStyle(color: Colors.white),
        ),
        centerTitle: true,
      ),

      // GestureDetector adalah fungsi agar widget bisa di berikan on tap
      body: GestureDetector(
        onTap: () {
          Navigator.push(
            context,
            MaterialPageRoute(
              builder: (context) {
                return SecondPage();
              },
            ),
          );
        },
        child: Hero(
          // tag adalah sebagai penanda bahwa si tag akan di animasi kan di Second page dan sebalik nya, dan tag page 1 dan pag2 dua harus sama
          tag: "pp",
          // ClipRRect adalah fungsi yang bisa membuat gambar yang bentuk nya kotak menjadi bundar
          child: ClipRRect(
            borderRadius: BorderRadius.circular(50),
            child: Container(
              width: 100,
              height: 100,
              child: const Image(
                fit: BoxFit.cover,
                image: NetworkImage(
                    "https://images.unsplash.com/photo-1576403587258-33453da1ace3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=735&q=80"),
              ),
            ),
          ),
        ),
      ),
    );
  }
}

class SecondPage extends StatelessWidget {
  const SecondPage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.pink[50],
      appBar: AppBar(
        backgroundColor: Colors.black,
        title: const Text(
          "Latihan Hero Animation",
          style: TextStyle(color: Colors.white),
        ),
        centerTitle: true,
      ),

      // GestureDetector adalah fungsi agar widget bisa di berikan on tap
      body: Center(
        child: Hero(
          // tag adalah sebagai penanda bahwa si tag akan di animasi kan di Second page dan sebalik nya, dan tag page 1 dan pag2 dua harus sama
          tag: "pp",
          child: ClipRRect(
            borderRadius: BorderRadius.circular(100),
            child: GestureDetector(
              child: Container(
                width: 200,
                height: 200,
                child: const Image(
                  fit: BoxFit.cover,
                  image: NetworkImage(
                      "https://images.unsplash.com/photo-1576403587258-33453da1ace3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=735&q=80"),
                ),
              ),
            ),
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190306191-6e1cf251-9beb-48fc-b595-7fda8c195e9e.png" width="200" height="400">

[__-->Title Reference<--__]()
