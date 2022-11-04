# Service API

__Sample code:__

```dart
import 'dart:convert';
import 'package:belajar/model/model_get_post.dart';
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

  Future PostDataAja(String nama, String avatar, String alamat, String email,
      String pekerjaan, String quote) async {
    final response = await http.post(
      Uri.parse(
        ('https://6283762138279cef71d77f41.mockapi.io/api/v1/data2'),
      ),
      // Menambahkan paramater body yang mau di tambah kan
      body: {
        "nama": nama,
        "avatar": avatar,
        "alamat": alamat,
        "email": email,
        "pekerjaan": pekerjaan,
        "quote": quote
      },
    );

    if (response.statusCode == 201) {
      return true;
    } else {
      throw Exception('Failed to load Data');
    }
  }

  // fungsi untuk menampilkan data di log yang tidak di tampil kan di UI ketika menekan data users di UI
  Future<Data> getSingleDataAja(String id) async {
    final response = await http.get(
      Uri.parse('https://6283762138279cef71d77f41.mockapi.io/api/v1/data2/$id'),
    );

    if (response.statusCode == 200) {
      Data jsonResponse = Data.fromJson(jsonDecode(response.body));
      return jsonResponse;
    } else {
      throw Exception('Failed to get data!');
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
