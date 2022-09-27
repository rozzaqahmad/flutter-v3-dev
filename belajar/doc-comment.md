# Doc Comment

<!-- Untuk menjelaskan atau dokumentasi suatu method atau class -->

__Sample code:__

```dart
import 'package:flutter/material.dart';

/// Class UserProfil di gunakan untuk menampilkan profil dengan indah
class UserProfile extends StatelessWidget {
  /// Field ini di gunakan untuk menyimpan nama user
  final String name;

  /// Field ini di gunakan untuk menyimpan nama peran/jabatan
  final String role;

  /// Field ini di gunakan untuk menyimpan profil photo
  final String photoURL;

  /// * [name] berisi *nama user*. Nilai default nya adalah `No Name`.
  ///
  /// * [role] berisi peran/jabatan dari user. Nilai default nya adalah `No Role`.
  ///
  /// * [photoURL] berisi link **foto user**. Nilai default nya adalah `null`.
  ///
  /// contoh:
  ///
  /// ```
  ///  final UserProfile profil = UserProfile(
  ///  name: "nama user",
  ///  role: "peran user",
  ///  photoURL: "https://lalala.com/foto.png",
  /// );
  ///```

  const UserProfile(
      {Key? key,
      this.name = "No Name",
      this.role = "No Role",
      this.photoURL = "null"})
      : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      crossAxisAlignment: CrossAxisAlignment.center,
      children: [
        Image(
          // ignore: unnecessary_null_comparison
          image: NetworkImage((photoURL != null)
              ? photoURL
              : "https://cdn4.iconfinder.com/data/icons/web-ui-color/128/Account-512.png"),
          fit: BoxFit.cover,
          width: 200,
          height: 200,
        ),
        const SizedBox(
          height: 10,
        ),
        Text(
          name,
          style: const TextStyle(fontWeight: FontWeight.bold, fontSize: 20),
        ),
        const SizedBox(height: 5),
        Text(
          "[$role]",
          style: const TextStyle(fontWeight: FontWeight.bold),
        )
      ],
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/192430799-8226ee89-8c67-49f4-bf17-14f962a01fda.png" width="200" height="400">

[__-->Title Reference<--__]()
