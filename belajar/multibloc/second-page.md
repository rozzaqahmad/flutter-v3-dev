# Title

__Sample code:__

```dart
import 'package:berkahshop/bloc/color_block.dart';
import 'package:berkahshop/bloc/counter_block.dart';
import 'package:berkahshop/draf_page.dart';
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';

class SecondPage extends StatelessWidget {
  const SecondPage({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    ColorBlock colorBloc = BlocProvider.of<ColorBloc>(context);
    CounterBloc counterBloc = BlocProvider.of<CounterBloc>(context);
    return BlocBuilder<ColorBlock, Color>(
      builder: (context, Color) => DrafPage(
        backgroundColor: Color,
        body: Center(
          child: Column(
            mainAxisSize: MainAxisSize.min,
            children: [
              BlocBuilder<CounterBlock, int>(
                builder: (context, number) => GestureDetector(
                  onTap: () {
                    CounterBlock.dispatch(number + 1);
                  },
                  child: Text(
                    number.toString(),
                    style: const TextStyle(
                        fontSize: 40, fontWeight: FontWeight.bold),
                  ),
                ),
              ),
              Row(
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                  Material(
                    color: Colors.pink,
                    shape: (Color == Colors.pink)
                        ? const CircleBorder(
                            side: BorderSide(color: Colors.black, width: 3))
                        : const CircleBorder(),
                    child: ElevatedButton(
                        onPressed: () {
                          ColorBloc.dispatch(ColorEvent.toPink);
                        },
                        child: const Text("Pink")),
                  ),
                  Material(
                    color: Colors.amber,
                    shape: (Color == Colors.amber)
                        ? const CircleBorder(
                            side: BorderSide(color: Colors.black, width: 3))
                        : const CircleBorder(),
                    child: ElevatedButton(
                        onPressed: () {
                          ColorBloc.dispatch(ColorEvent.toAmber);
                        },
                        child: const Text("amber")),
                  ),
                  Material(
                    color: Colors.purple,
                    shape: (Color == Colors.purple)
                        ? const CircleBorder(
                            side: BorderSide(color: Colors.black, width: 3))
                        : const CircleBorder(),
                    child: ElevatedButton(
                        onPressed: () {
                          ColorBloc.dispatch(ColorEvent.toPurple);
                        },
                        child: const Text("purple")),
                  ),
                ],
              )
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
