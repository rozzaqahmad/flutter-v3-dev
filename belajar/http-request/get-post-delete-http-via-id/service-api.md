# Service API

__Sample code:__

```dart
import 'dart:convert';
import 'package:belajar/model/data_model.dart';
import 'package:http/http.dart' as http;

class Service {
  Future<List<Data>> getALlDataAja() async {
    final response = await http.get(
        Uri.parse('https://6283762138279cef71d77f41.mockapi.io/api/v1/data2'));
    if (response.statusCode == 200) {
      List jsonResponse = json.decode(response.body);
      return jsonResponse.map((data) => Data.fromJson(data)).toList();
    } else {
      throw Exception('Failed to load Data');
    }
  }

  Future PostDataAja(String nama, String pekerjaan) async {
    final response = await http.post(
      Uri.parse(
        ('https://6283762138279cef71d77f41.mockapi.io/api/v1/data2'),
      ),
      // Menambahkan paramater body yang mau di tambah kan
      body: {
        "nama": nama,
        "pekerjaan": pekerjaan,
        // "email": email,
        // "avatar": avatar,
        // "alamat": alamat,
        // "quote": quote
      },
    );

    if (response.statusCode == 201) {
      return true;
    } else {
      throw Exception('Failed to load Data');
    }
  }

  // fungsi untuk delate data
  Future<bool> deleteDataAja(String id) async {
    final response = await http.delete(Uri.parse(
        'https://6283762138279cef71d77f41.mockapi.io/api/v1/data2/$id'));

    if (response.statusCode == 200) {
      return true;
    } else {
      throw Exception('Failed to Delete');
    }
  }
}
```

__Output:__


[__-->Title Reference<--__]()
