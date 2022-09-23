# Provider State Management

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'package:flutter/foundation.dart';

<!-- Provider State Management adalah untuk membantu aplikasi agar performa nya tidak berkurang saat menggunakan statefulWidget(widget yang berubah2) -->

class StateManagement extends StatelessWidget {
  const StateManagement({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    // Scaffold di bungkus dengan Change Notifier Provider untuk
    return ChangeNotifierProvider<AplicationColor>(
      builder: (context) => AplicationColor(),
      child: Scaffold(
        appBar: AppBar(
          backgroundColor: Colors.black,
          title: Consumer<AplicationColor>(
            builder: (context, aplicationColor, _) => Text(
              "Provider State Management",
              style: TextStyle(color: aplicationColor.color),
            ),
          ),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Consumer<AplicationColor>(
                builder: (context, aplicationColor, _) => AnimatedContainer(
                  duration: const Duration(milliseconds: 500),
                  margin: const EdgeInsets.all(5),
                  width: 100,
                  height: 100,
                  color: aplicationColor.color,
                ),
              ),
              Row(
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                  Container(
                      margin: const EdgeInsets.all(5), child: const Text("AB")),
                  Consumer<AplicationColor>(
                    builder: (context, aplicationColor, _) => Switch(
                      value: aplicationColor.isLightBlue,
                      onChanged: (newValue) {
                        // manggil si setter
                        aplicationColor.isLightBlue = newValue;
                      },
                    ),
                  ),
                  Container(
                      margin: const EdgeInsets.all(5), child: const Text("LB"))
                ],
              )
            ],
          ),
        ),
      ),
    );
  }
}

class AplicationColor with ChangeNotifier {
  bool _isLightBlue = true;

  bool get isLightBlue => _isLightBlue;
  set isLightBlue(bool value) {
    isLightBlue = value;
    // notifyLIsteners adalah fungsi untuk memberitahukan widget2 yang sedang menunggu yang widget nya akan di ubah, yaitu si consumer
    notifyListeners();
  }

  // fungsi untuk mengembalikan warna dari lightblue nya (true atau false)
  Color get color => (isLightBlue) ? Colors.lightBlue : Colors.amber;
}

```

__Output:__


[__-->Title Reference<--__]()
