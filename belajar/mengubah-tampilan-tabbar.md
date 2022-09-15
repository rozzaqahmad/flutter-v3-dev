# Mengubah Tampilan Tabbar

__Sample code:__

```dart
import 'package:flutter/material.dart';

class AplikasiTabbarDesain extends StatelessWidget {
  AplikasiTabbarDesain({super.key});

// TabBar

  TabBar myTabBar = const TabBar(
    // untuk memberikan warna pada tiap2 tab Bar yang di pilih
    indicator: BoxDecoration(
      color: Colors.red,
      border: Border(
        //untuk memberikan garis berwarna purple di atas tab Bar
        top: BorderSide(color: Colors.purple, width: 5),
      ),
    ),
    tabs: <Widget>[
      Tab(
        icon: Icon(Icons.comment),
        text: "Comments",
      ),
      Tab(
        icon: Icon(Icons.computer),
        text: "Computer",
      ),
    ],
  );

  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      // length adalah jumlah Tab Bar yang akan di buat
      length: 2,
      child: Scaffold(
        appBar: AppBar(
          centerTitle: true,
          title: const Text("Contoh Tab Bar"),
          bottom: PreferredSize(
            preferredSize: Size.fromHeight(myTabBar.preferredSize.height),
            child: Container(color: Colors.amber, child: myTabBar),
          ),
        ),
        body: const TabBarView(
          // children nya adalah kumpulan tampilan untuk tiap Tab nya
          children: <Widget>[
            Center(
              child: Text("Tab 1"),
            ),
            Center(
              child: Text("Tab 2"),
            ),
          ],
        ),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190340266-0e46151d-bd16-4879-af15-dd841d3ed064.png" width="200" height="400">

[__-->Title Reference<--__]()
