# Aplikasi Penyimpanan Data di Aplikasi

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:shared_preferences/shared_preferences.dart';

// SharedPreferences adalah untuk menyimpan data - data  simpel di aplikasi kita

class AplikasiPenyimpananData extends StatefulWidget {
  const AplikasiPenyimpananData({Key? key}) : super(key: key);

  @override
  State<AplikasiPenyimpananData> createState() =>
      _AplikasiPenyimpananDataState();
}

class _AplikasiPenyimpananDataState extends State<AplikasiPenyimpananData> {
  TextEditingController controller = TextEditingController(text: "No Name");
  bool isON = false;

// Method untuk save data nya, dan pref adalah fungsi save
  void saveData() async {
    SharedPreferences pref = await SharedPreferences.getInstance();
    pref.setString("nama", controller.text);
    pref.setBool("isON", isON);
  }

// fungsi untuk nge load
  Future<String> getNama() async {
    SharedPreferences pref = await SharedPreferences.getInstance();
    return pref.getString("nama") ?? "No Name";
  }

// fungsi untuk load boolean
  Future<bool> getON() async {
    SharedPreferences pref = await SharedPreferences.getInstance();
    return pref.getBool("isON") ?? false;
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Text Preference Example"),
        centerTitle: true,
      ),
      body: Center(
        child: (Column(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: <Widget>[
            TextField(
              controller: controller,
            ),
            Switch(
              value: isON,
              onChanged: (newValue) {
                setState(() {
                  isON = newValue;
                });
              },
            ),
            ElevatedButton(
                onPressed: () {
                  saveData();
                },
                child: const Text("Save")),
            ElevatedButton(
                onPressed: () {
                  getNama().then((s) {
                    controller.text = s;
                    setState(() {});
                  });

                  getON().then(
                    (b) {
                      isON = b;
                      setState(() {});
                    },
                  );
                },
                child: const Text("Load"))
          ],
        )),
      ),
    );
  }
}

```

__Output:__


[__-->Title Reference<--__]()
