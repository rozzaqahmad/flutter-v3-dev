# Widget Widget Tambahan 

__Sample code:__

```dart
import 'package:flutter/material.dart';

class TambahanWidget extends StatelessWidget {
  // const TambahanWidget({Key? key}) : super(key: key);

  // List untuk togglebuttons
  List<bool> isSelected = [true, false, false];
  ColorFilter colorFilter =
      const ColorFilter.mode(Colors.blue, BlendMode.screen);

  @override
  Widget build(BuildContext context) {
    return ColorFiltered(
      colorFilter: colorFilter,
      child: Scaffold(
        appBar: AppBar(
          title: const Text("Widget Tambahan"),
          centerTitle: true,
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              const SelectableText(
                "Ini adalah selec table text, silah kan pilih saya.",
                style: TextStyle(fontSize: 20),
                showCursor: true,
                cursorWidth: 3,
                cursorColor: Colors.red,
              ),
              const SizedBox(
                height: 10,
              ),
              ToggleButtons(
                isSelected: isSelected,
                onPressed: (index) {
                  isSelected[index] = !isSelected[index];
                  if (index == 0)
                    colorFilter =
                        ColorFilter.mode(Colors.blue, BlendMode.screen);
                  else if (index == 1)
                    colorFilter =
                        ColorFilter.mode(Colors.green, BlendMode.softLight);
                  else
                    colorFilter =
                        ColorFilter.mode(Colors.purple, BlendMode.multiply);
                },
                fillColor: Colors.red[50],
                selectedColor: Colors.red,
                selectedBorderColor: Colors.red,
                splashColor: Colors.blue,
                highlightColor: Colors.yellow,
                borderRadius: BorderRadius.circular(15),
                children: const [
                  Icon(Icons.access_alarm),
                  Icon(Icons.adb),
                  Icon(Icons.add_comment)
                ],
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

<img src="https://user-images.githubusercontent.com/88677064/192991890-2d49cc50-038b-47c2-8367-9a8b96921eba.png" width="200" height="400">


[__-->Title Reference<--__]()
