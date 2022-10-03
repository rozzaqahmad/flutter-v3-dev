# Title

__Sample code:__

```dart
import 'package:flutter/material.dart';

void main(List<String> args) {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: MainPage(),
    );
  }
}

class MainPage extends StatefulWidget {
  const MainPage({Key? key}) : super(key: key);

  @override
  State<MainPage> createState() => _MainPageState();
}

class _MainPageState extends State<MainPage> {
 late Person selectedPerson;
  List<Person> persons = [
    Person("Joni"),
    Person("Eka"),
  ];

  List<DropdownMenuItem> generateItems(List<Person> persons) {
    List<DropdownMenuItem> items = [];
    for (var item in persons) {
      items.add(DropdownMenuItem(
        value: item,
        child: Text(item.name),
      ));
    }
    return items;
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Demo Dropdown Button"),
      ),
      body: Column(
        children: [
          Container(
            margin: const EdgeInsets.all(20),
            child: DropdownButton(
              isExpanded: true,
              style: const TextStyle(fontSize: 20, color: Colors.purple),
              value: selectedPerson,
              items: generateItems(persons),
              onChanged: (item) {
                setState(() {
                  selectedPerson = item;
                });
              },
            ),
          ),
          Text((selectedPerson != null) ? selectedPerson.name : "Belum ada yang terpilih", style: const TextStyle(fontSize: 18, fontWeight: FontWeight.bold),),
        ],
      ),
    );
  }
}

class Person {
  String name;
  Person(this.name);
}

```

__Output:__


[__-->Title Reference<--__]()
