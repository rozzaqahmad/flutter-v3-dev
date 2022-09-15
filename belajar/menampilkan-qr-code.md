# QR Code

__Sample code:__

```dart
import 'package:flutter/material.dart';
import 'package:qr_flutter/qr_flutter.dart';

class AplikasiBarcode extends StatelessWidget {
  const AplikasiBarcode({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("MOTOVLOG NINBU QR CODE"),
        centerTitle: true,
      ),
      body: Center(
        child: QrImage(
            version: 6,
            backgroundColor: Colors.grey,
            foregroundColor: Colors.black,
            errorCorrectionLevel: QrErrorCorrectLevel.M,
            padding: const EdgeInsets.all(30),
            data: "https://www.youtube.com/channel/UC9K4Itxv0iVbga3RGirQ8_g"),
      ),
    );
  }
}

```

__Output:__

<img src="https://user-images.githubusercontent.com/88677064/190367231-8d85bc83-5d14-437c-998b-035d0c780b35.png" width="200" height="400">

[__-->Title Reference<--__]()
