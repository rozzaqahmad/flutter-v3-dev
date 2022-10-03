# Title

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:bloc/bloc.dart';

class CounterBlock extends Bloc<int, int> {
  CounterBlock(super.initialState);

  @override
  int get initialState => 0;

  @override
  Stream<int> mapEventToState(int event) async* {
    yield event;
  }
}

```

__Output:__


[__-->Title Reference<--__]()
