# Title

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:bloc/bloc.dart';

enum ColorEvent { toPink, toAmber, toPurple }

class ColorBlock extends Bloc<ColorEvent, Color> {
  @override
  Color get initialState => Colors.pink;

  @override
  Stream<Color> mapEventToState(ColorEvent event) async* {
    yield (event == ColorEvent.toPink)
        ? Colors.pink
        : (event == ColorEvent.toAmber)
            ? Colors.amber
            : Colors.purple;
  }
}

```

__Output:__


[__-->Title Reference<--__]()
