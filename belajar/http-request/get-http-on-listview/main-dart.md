# Main dart UI

__Sample code:__

```dart
import 'package:belajar/bloc/api_services.dart';
import 'package:flutter/material.dart';
import 'package:belajar/model/data_users.dart';

void main(List<String> args) {
  runApp(const MyApp());
}

class MyApp extends StatefulWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  Service serviceAPI = Service();
  late Future<List<Data>> listData;
  @override
  void initState() {
    // ignore: todo
    // TODO: implement initState
    super.initState();
    listData = serviceAPI.getALlDataAja();
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text("Get API With Listview Builder"),
          centerTitle: true,
        ),
        body: FutureBuilder<List<Data>>(
          future: listData,
          builder: (context, snapshot) {
            if (snapshot.hasData) {
              List<Data> isiDataAja = snapshot.data!;
              return ListView.builder(
                itemCount: isiDataAja.length,
                itemBuilder: (context, index) {
                  return Card(
                    child: ListTile(
                      title: Text(isiDataAja[index].nama),
                      // menampilkan avatar atau gambar nya
                      leading: CircleAvatar(
                        backgroundImage: NetworkImage(isiDataAja[index].avatar),
                      ),
                      subtitle: Text(isiDataAja[index].email),
                    ),
                  );
                },
              );
            } else if (snapshot.hasError) {
              return Text("${snapshot.error}");
            }
            return const CircularProgressIndicator();
          },
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/199396342-ebf03798-9d34-45ed-840c-27084f882831.png" width="200" height="400">

[__-->Title Reference<--__]()
