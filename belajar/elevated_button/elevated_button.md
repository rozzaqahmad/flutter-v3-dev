# Elevated Button Demo

__Sample code:__

```dart
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
