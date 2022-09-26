# Aplikasi Bloc State Management

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'dart:async';

class AplikasiPerubahanWarna extends StatefulWidget {
  const AplikasiPerubahanWarna({Key? key}) : super(key: key);

  @override
  State<AplikasiPerubahanWarna> createState() => _AplikasiPerubahanWarnaState();
}

class _AplikasiPerubahanWarnaState extends State<AplikasiPerubahanWarna> {
  ColorBloc bloc = ColorBloc();
  @override
  void dispose() {
    bloc.dispose;
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      // floatingActionBUtton untuk dua buah tombol lingkaran di kanan bawah
      floatingActionButton: Row(
        mainAxisAlignment: MainAxisAlignment.end,
        children: [
          FloatingActionButton(
              backgroundColor: Colors.amber,
              onPressed: () {
                bloc.eventSink.add(ColorEvent.to_amber);
              }),
          const SizedBox(width: 10),
          FloatingActionButton(
              backgroundColor: Colors.lightBlue,
              onPressed: () {
                bloc.eventSink.add(ColorEvent.to_light_blue);
              })
        ],
      ),
      appBar: AppBar(
        title: const Text("Block Tanpa Library"),
        centerTitle: true,
      ),
      body: Center(
          child: StreamBuilder(
        stream: bloc.stateStream,
        initialData: Colors.amber,
        builder: (context, snapshot) {
          return AnimatedContainer(
            duration: const Duration(microseconds: 500),
            width: 100,
            height: 100,
            color: snapshot.data,
          );
        },
      )),
    );
  }
}

enum ColorEvent { to_amber, to_light_blue }

class ColorBloc {
  Color _color = Colors.amber;

  StreamController<ColorEvent> _eventController =
      StreamController<ColorEvent>();
  StreamSink<ColorEvent> get eventSink => _eventController.sink;
  StreamController<Color> _stateController = StreamController<Color>();
  StreamSink<Color> get _stateSink => _stateController.sink;
  Stream<Color> get stateStream => _stateController.stream;

  void _mapEventToState(ColorEvent colorEvent) {
    if (colorEvent == ColorEvent.to_amber) {
      _color = Colors.amber;
    } else {
      _color = Colors.lightBlue;
    }

    _stateSink.add(_color);
  }

  ColorBloc() {
    _eventController.stream.listen(_mapEventToState);
  }
  void dispose() {
    _eventController.close();
    _stateController.close();
  }
}

```

__Output:__


[__-->Title Reference<--__]()
