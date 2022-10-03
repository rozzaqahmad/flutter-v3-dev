# Title

__Sample code:__

```dart
import 'package:berkahshop/bloc/color_block.dart';
import 'package:berkahshop/bloc/counter_block.dart';
import 'package:flutter_bloc/flutter_bloc.dart';

import 'main_page.dart';
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';

void main(List<String> args) {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MultiBlocProvider(
      providers: [
        BlocProvider<ColorBlock>(create: (context) => ColorBlock()),
        BlocProvider<CounterBlock>(create: (context) => CounterBlock()),
      ],
      child: const MaterialApp(
        debugShowCheckedModeBanner: false,
        home: MainPage(),
      ),
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
