# Main Dart

__Sample code:__

```dart
import 'dart:developer';

import 'package:belajar/bloc/api_services.dart';
import 'package:belajar/model/model_get_post.dart';
import 'package:flutter/material.dart';

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
        body: Column(
          children: [
            Expanded(
              child: Container(
                child: FutureBuilder<List<Data>>(
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
                                backgroundImage:
                                    NetworkImage(isiDataAja[index].avatar),
                              ),
                              subtitle: Text(isiDataAja[index].pekerjaan),
                              // menampilkan hasil get data ke log console
                              onTap: () {
                                showDataAja(isiDataAja[index].id);
                              },
                              // fungsi delete data
                              onLongPress: () {
                                deleteDataAja(isiDataAja[index].id);
                              },
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
            ),
            ElevatedButton(
                onPressed: () {
                  tambahData();
                },
                child: const Text("Tambah Data"))
          ],
        ),
      ),
    );
  }

  void tambahData() async {
    bool response = await serviceAPI.PostDataAja(
        // paramater di body postDataAja yang mau di tambahkan
        "Dani",
        "avatar",
        "alamat",
        "DaniAja@gmail.com",
        "UI/UX Developer",
        "quote");

    if (response == true) {
      setState(() {
        listData = serviceAPI.getALlDataAja();
      });
    }
  }

  void showDataAja(String id) async {
    Data response = await serviceAPI.getSingleDataAja(id);
    // log harus import'dart:developer';
    log("data = ${response.nama} - ${response.email}");
  }

  // fungsi delete
  void deleteDataAja(String id) async {
    bool response = await serviceAPI.deleteDataAja(id);
    if (response == true) {
      setState(() {
        listData = serviceAPI.getALlDataAja();
      });
    } else {
      log('error = data tidak di hapus!');
    }
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/199925583-ec396ba8-8058-4b07-b824-058368b9d8ba.png" width="200" height="400">

[__-->Title Reference<--__]()
