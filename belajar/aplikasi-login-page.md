# Aplikasi LOgin Page

__Sample code:__

```dart
import 'package:flutter/material.dart';

class LoginPage extends StatelessWidget {
  const LoginPage({super.key});

// Fungsi atau Method untuk menhgembalikan diameter lingkaran kecil dan lingkaran besar
  double getSmallDiameter(BuildContext context) =>
      MediaQuery.of(context).size.width * 2 / 3;
  double getBigDiameter(BuildContext context) =>
      MediaQuery.of(context).size.width * 7 / 8;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: const Color(0xFFEEEEEE),
      body: Stack(
        children: <Widget>[
          // Positioned adalah untuk mengatur tata letak lingkaran
          Positioned(
            // dari kanan lingkaran nya akan mundur 1/3 lingkaran
            right: -getSmallDiameter(context) / 3,
            // dan dari atas lingkaran nya juga akan mundur 1/3 lingkaran juga
            top: -getSmallDiameter(context) / 3,
            child: Container(
              width: (getSmallDiameter(context)),
              height: getSmallDiameter(context),
              decoration: const BoxDecoration(
                shape: BoxShape.circle,
                gradient: LinearGradient(
                  colors: [
                    Color(0xFFB226B2),
                    Color(0xFFFF6DA7),
                  ],
                  begin: Alignment.topCenter,
                  end: Alignment.bottomCenter,
                ),
              ),
            ),
          ),
          // Positioned adalah untuk mengatur tata letak lingkaran
          Positioned(
            // dari kiri lingkaran nya akan mundur 1/4 lingkaran
            left: -getBigDiameter(context) / 4,
            // dan dari atas lingkaran nya juga akan mundur 1/4 lingkaran juga
            top: -getBigDiameter(context) / 4,
            child: Container(
              width: (getBigDiameter(context)),
              height: getBigDiameter(context),
              decoration: const BoxDecoration(
                shape: BoxShape.circle,
                gradient: LinearGradient(
                  colors: [
                    Color(0xFFB226B2),
                    Color(0xFFFF4891),
                  ],
                  begin: Alignment.topCenter,
                  end: Alignment.bottomCenter,
                ),
              ),
              child: const Center(
                child: Text(
                  "BerkahShop",
                  style: TextStyle(
                      fontFamily: "Pacifico",
                      fontSize: 30,
                      color: Colors.white),
                ),
              ),
            ),
          ),
          // Positioned adalah untuk mengatur tata letak lingkaran
          Positioned(
            // dari kanan lingkaran nya akan mundur 1/2 lingkaran
            right: -getBigDiameter(context) / 2,
            // dan dari bawah lingkaran nya juga akan mundur 1/2 lingkaran juga
            bottom: -getBigDiameter(context) / 2,
            child: Container(
              width: (getBigDiameter(context)),
              height: getBigDiameter(context),
              decoration: const BoxDecoration(
                shape: BoxShape.circle,
                color: Color(0xFFF3E9EE),
              ),
            ),
          ),
          // Align adalah fungsi supaya list View nya ke bawah
          Align(
            alignment: Alignment.bottomCenter,
            child: ListView(
              children: [
                // Container
                Container(
                  decoration: BoxDecoration(
                    color: Colors.white,
                    border: Border.all(
                      color: Colors.grey,
                    ),
                    borderRadius: BorderRadius.circular(5),
                  ),
                  margin: const EdgeInsets.fromLTRB(20, 300, 20, 10),
                  // padding supaya komponen text Field nya gak terlalu mepet dengan Container nya
                  padding: const EdgeInsets.fromLTRB(10, 0, 10, 25),
                  child: Column(
                    children: const <Widget>[
                      TextField(
                        decoration: InputDecoration(
                            icon: Icon(
                              Icons.email,
                              color: Color(0xFFFF4891),
                            ),
                            focusedBorder: UnderlineInputBorder(
                              borderSide: BorderSide(
                                color: Color(0xFFFF4891),
                              ),
                            ),
                            labelText: "Email:",
                            labelStyle: TextStyle(color: Color(0xFFFF4891))),
                      ),
                      TextField(
                        obscureText: true,
                        decoration: InputDecoration(
                            icon: Icon(
                              Icons.key,
                              color: Color(0xFFFF4891),
                            ),
                            focusedBorder: UnderlineInputBorder(
                              borderSide: BorderSide(
                                color: Color(0xFFFF4891),
                              ),
                            ),
                            labelText: "Password:",
                            labelStyle: TextStyle(color: Color(0xFFFF4891))),
                      ),
                    ],
                  ),
                ),
                // Text "FORGOT PASSWORD"
                Align(
                  alignment: Alignment.centerRight,
                  child: Container(
                    margin: const EdgeInsets.fromLTRB(0, 0, 20, 20),
                    child:
                        // Text FORGOT PASSWORD? di bungkus COntainer supaya bisa di beri margin
                        const Text(
                      "FORGOT PASSWORD?",
                      style: TextStyle(color: Color(0xFFFF4891), fontSize: 11),
                    ),
                  ),
                ),
                Container(
                  margin: const EdgeInsets.fromLTRB(20, 0, 20, 30),
                  child: Row(
                    // spaceBetween fungsi nya adalah jika ada space kosong antara 3 buah button, maka akan di taruh di antara 3 button tersebut
                    mainAxisAlignment: MainAxisAlignment.spaceBetween,
                    children: <Widget>[
                      SizedBox(
                        width: MediaQuery.of(context).size.width * 0.5,
                        height: 40,
                        child: Container(
                          decoration: BoxDecoration(
                            borderRadius: BorderRadius.circular(20),
                            gradient: const LinearGradient(
                              colors: [
                                Color(0xFFB226B2),
                                Color(0xFFFF4891),
                              ],
                              begin: Alignment.topCenter,
                              end: Alignment.bottomCenter,
                            ),
                          ),
                          child: Material(
                            borderRadius: BorderRadius.circular(20),
                            color: Colors.transparent,
                            child: InkWell(
                              borderRadius: BorderRadius.circular(20),
                              splashColor: Colors.amber,
                              onTap: () {},
                              child: const Center(
                                child: Text(
                                  "SIGN IN",
                                  style: TextStyle(
                                      color: Colors.white,
                                      fontWeight: FontWeight.w700),
                                ),
                              ),
                            ),
                          ),
                        ),
                      ),
                      // Floating Action Button adalah fungsi untuk membuat tombol lingkaran
                      FloatingActionButton(
                        onPressed: () {},
                        mini: true,
                        elevation: 0,
                        child: const Image(
                            image:
                                AssetImage("assets/images/logo-facebook2.png")),
                      ),
                      FloatingActionButton(
                        onPressed: () {},
                        mini: true,
                        elevation: 0,
                        child: const Image(
                            image:
                                AssetImage("assets/images/logo-twitter.png")),
                      ),
                    ],
                  ),
                ),
                Row(
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: const <Widget>[
                    Text(
                      "DON'T HAVE AN ACCOUNT?",
                      style: TextStyle(
                          fontSize: 11,
                          color: Colors.grey,
                          fontWeight: FontWeight.w500),
                    ),
                    // SizedBox adalah fungsi yang bisa mengatur jarak antar text
                    SizedBox(
                      width: 1,
                    ),
                    Text(
                      "SIGN UP",
                      style: TextStyle(
                          fontSize: 11,
                          color: Color(0xFFFF4891),
                          fontWeight: FontWeight.w700),
                    ),
                  ],
                )
              ],
            ),
          )
        ],
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190297854-6deffc75-f05c-4d77-909c-51f715824e07.png" width="200" height="400">

[__-->Title Reference<--__]()
