# Bloc State Management Package

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';

class AplikasiPerubahanWarna extends StatelessWidget {
  const AplikasiPerubahanWarna({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    ColorBloc bloc = BlocProvider.of<ColorBloc>(context);
    return BlocProvider(
      builder: (context) => ColorBloc(),
      child: Scaffold(
        floatingActionButton: Row(
          mainAxisAlignment: MainAxisAlignment.end,
          children: [
            FloatingActionButton(
              backgroundColor: Colors.amber,
              onPressed: () {
                bloc.dispatch(ColorEvent.to_amber);
              },
            ),
            const SizedBox(width: 10),
            FloatingActionButton(
              backgroundColor: Colors.lightBlue,
              onPressed: () {
              bloc.dispatch(ColorEvent.to_light_blue);
              },
            ),
          ],
        ),
        appBar: AppBar(
          title: const Text("Color Bloc Package"),
          centerTitle: true,
        ),
        body: Center(
          child: BlocBuilder<ColorBloc, Color>(
            builder: (context, currentColor) => AnimatedContainer(
              duration: const Duration(microseconds: 500),
              width: 100,
              height: 100,
              color: currentColor,
            ),
          ),
        ),
      ),
    );
  }
}

enum ColorEvent { to_amber, to_light_blue }

class ColorBloc extends Bloc<ColorEvent, Color> {
  Color _color = Colors.amber;

  @override
  Color get initialState => Colors.amber;

  @override
  Stream<Color> mapEventToState(ColorEvent event) async* {
    _color = (event == ColorEvent.to_amber) ? Colors.amber : Colors.lightBlue;
    yield _color;
  }
}

```

__Output:__


[__-->Title Reference<--__]()
