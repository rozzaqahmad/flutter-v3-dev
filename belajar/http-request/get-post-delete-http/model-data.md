# Data Model

__Sample code:__

```dart
class Data {
  String id;
  String avatar;
  String nama;
  String alamat;
  String email;
  String pekerjaan;
  String quote;

  Data(
      {required this.id,
      required this.avatar,
      required this.nama,
      required this.alamat,
      required this.email,
      required this.pekerjaan,
      required this.quote});

  factory Data.fromJson(Map<String, dynamic> json) => Data(
      id: json['id'],
      avatar: json['avatar'],
      nama: json['nama'],
      alamat: json['alamat'],
      email: json['email'],
      pekerjaan: json['pekerjaan'],
      quote: json['quote']);
}

```

__Output:__


[__-->Title Reference<--__]()
