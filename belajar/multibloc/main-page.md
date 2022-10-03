# Title

__Sample code:__

```dart
import 'package:berkahshop/bloc/color_block.dart';
import 'package:berkahshop/second_page.dart';
import 'package:flutter_bloc/flutter_bloc.dart';
import 'draf_page.dart';
import 'package:flutter/material.dart';


class MainPage extends StatelessWidget {
  const MainPage({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return BlocBuilder<ColorBloc, Color>(
      builder: (context, color) => DrafPage(
        backgroundColor: color,
        body: Center(
          child: Column(
            mainAxisSize: MainAxisSize.min,
            children: [
              BlocBuilder<CounterBloc, int>(
                builder: (context, number) => Text(
                  number.toString(),
                  style: const TextStyle(fontSize: 40, fontWeight: FontWeight.bold),
                ),
              ),
              ElevatedButton(
                  onPressed: () {
                    Navigator.push(
                        context,
                        MaterialPageRoute(
                            builder: (context) => const SecondPage()));
                  },
                  child: Text(
                    "Click To Change",
                    style: TextStyle(color: color),
                  ))
            ],
          ),
        ),
      ),
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
