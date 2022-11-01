# Elevated Button Demo

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:belajar/model/user_model.dart';

void main(List<String> args) {
  runApp(const MyApp());
}

// class MyApp extends StatefulWidget {
//   const MyApp({Key? key}) : super(key: key);

//   @override
//   State<MyApp> createState() => _MyAppState();
// }

// class _MyAppState extends State<MyApp> {
//   User user = null;
//   @override
//   Widget build(BuildContext context) {
//     return MaterialApp(
//       home: Scaffold(
//         appBar: AppBar(
//           title: const Text("GET DATA USER"),
//         ),
//         body: Center(
//           child: Column(
//             mainAxisAlignment: MainAxisAlignment.spaceEvenly,
//             children: [
//               Text((User != null)
//                   ? user.id + " | " + user.name
//                   : "Tidak ada data"),
//               ElevatedButton(
//                   onPressed: () {
//                     User.connectToAPI("3").then((value) {
//                       user = value;
//                       setState(() {});
//                     });
//                   },
//                   child: const Text("GET"))
//             ],
//           ),
//         ),
//       ),
//     );
//   }
// }

// import 'package:belajar/ui/main_page.dart';
// import 'package:flutter/material.dart';
// import 'package:flutter_bloc/flutter_bloc.dart';
// import 'bloc/user_bloc.dart';
// import 'package:belajar/ui/main_page.dart';
// void main(List<String> args) {
//   runApp(const MyApp());
// }

// class MyApp extends StatelessWidget {
//   const MyApp({Key? key}) : super(key: key);

//   @override
//   Widget build(BuildContext context) {
//     return MaterialApp(
//       debugShowCheckedModeBanner: false,
//       home: BlocProvider(create: (context) => UserBloc(), child: MainPage(),),
//     );
//   }
// }

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text("Elevated Button Demo"),
          centerTitle: true,
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              ElevatedButton(
                onPressed: () {},
                style: ElevatedButton.styleFrom(
                  primary: Colors.red,
                  onPrimary: Colors.yellow,
                  onSurface: Colors.red,
                  shadowColor: Colors.green,
                  minimumSize: const Size(200, 40),
                  alignment: Alignment.center,
                  animationDuration: const Duration(microseconds: 200),
                  elevation: 2,
                  shape: const StadiumBorder(),
                  side: BorderSide(color: Colors.red.shade900, width: 2),
                  visualDensity: VisualDensity.compact,
                ),
                child: const Text("Tombol 1"),
              ),
              ElevatedButton.icon(
                onPressed: () {},
                icon: const Icon(Icons.ac_unit),
                label: const Text("Tombol 2"),
                style: ButtonStyle(
                  foregroundColor: MaterialStateProperty.all(Colors.yellow),
                  backgroundColor: MaterialStateProperty.resolveWith((states) =>
                      states.any((element) => element == MaterialState.pressed)
                          ? Colors.purple
                          : Colors.red),
                  overlayColor: MaterialStateProperty.all(Colors.green),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/199191269-92e8b85e-583c-49f6-9770-031c1cc2d3cb.png" width="200" height="400">

[__-->Title Reference<--__]()
