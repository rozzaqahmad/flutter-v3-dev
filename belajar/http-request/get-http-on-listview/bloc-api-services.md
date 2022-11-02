# Bloc Services API

__Sample code:__

```dart
import 'dart:convert';
import 'package:belajar/model/data_users.dart';

import 'package:http/http.dart' as http;

class Service {
  Future<List<Data>> getALlDataAja() async {
    final response = await http.get(
        Uri.parse('https://6283762138279cef71d77f41.mockapi.io/api/v1/Data'));
    if (response.statusCode == 200) {
      List jsonResponse = json.decode(response.body);
      return jsonResponse.map((data) => Data.fromJson(data)).toList();
    } else {
      throw Exception('Failed to load Data');
    }
  }
}

```

__Output:__


[__-->Title Reference<--__]()
