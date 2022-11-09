# Main Dart

__Sample code:__

```dart
import 'package:belajar/model/data_model.dart';
import 'package:flutter/material.dart';
import 'package:belajar/bloc/servcice_api.dart';

class TestPostDataAja extends StatefulWidget {
  const TestPostDataAja({Key? key}) : super(key: key);

  @override
  State<TestPostDataAja> createState() => _MyAppState();
}

class _MyAppState extends State<TestPostDataAja> {
  TextEditingController nameController = TextEditingController();
  TextEditingController idController = TextEditingController();
  TextEditingController pekerjaanController = TextEditingController();

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
          title: const Text("Get, Post, Delete API HTTP"),
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
                              trailing: Text(isiDataAja[index].id),
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
            Container(
              decoration: BoxDecoration(
                  // color: Color.fromARGB(255, 112, 204, 247),
                  border: Border.all(color: Colors.grey),
                  borderRadius: BorderRadius.circular(5)),
              child: TextField(
                keyboardType: TextInputType.number,
                controller: idController,
                decoration: const InputDecoration(
                  hintText: "Input ID to Delete Data",
                ),
              ),
            ),
            Container(
              decoration: BoxDecoration(
                  border: Border.all(color: Colors.grey),
                  borderRadius: BorderRadius.circular(5)),
              child: TextField(
                controller: nameController,
                decoration: const InputDecoration(
                    hintText: "Masukkan Nama To Post Data"),
              ),
            ),
            Container(
              decoration: BoxDecoration(
                  border: Border.all(color: Colors.grey),
                  borderRadius: BorderRadius.circular(5)),
              child: TextField(
                controller: pekerjaanController,
                decoration:
                    const InputDecoration(hintText: "Masukkan Pekerjaan"),
              ),
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                ElevatedButton(
                  onPressed: () {
                    tambahData();
                  },
                  child: const Text("Tambah Data"),
                ),
                ElevatedButton(
                  onPressed: () {
                    deleteData(nameController.text);
                  },
                  child: const Text("Hapus Data"),
                ),
              ],
            )
          ],
        ),
      ),
    );
  }

  void tambahData() async {
    bool response = await serviceAPI.PostDataAja(
        nameController.text, pekerjaanController.text);

    if (response == true) {
      print('SUCCESS TO POST DATA');
      setState(() {
        listData = serviceAPI.getALlDataAja();
      });
    } else {
      print('FAILED TO POST DATA');
    }
  }

  void deleteData(String id) async {
    bool response = await serviceAPI.deleteDataAja(idController.text);

    if (response == true) {
      print('SUCCES TO DELETE DATA');
      setState(() {
        listData = serviceAPI.getALlDataAja();
      });
    } else {
      print('FAILED TO DELETE DATA !');
    }
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/200781289-c8e66be1-b623-42ab-8cf3-cf744e476391.png" width="200" height="400">

[__-->Title Reference<--__]()
