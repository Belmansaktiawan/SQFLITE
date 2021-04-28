# SQFLITE
import 'package:flutter/material.dart';
void main() => runApp(App());

class App extends StatelessWidget {
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter penyimpanan data',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Leonardo/6SIA10'),
        ),
        body: Customer(),
      ),
    );
  }
}

class DataCustomer{
  
  String ID;
  String nama;
  String alamat;
  String nohp;
  
  
  DataCustomer({ this.ID, this.nama, this.alamat, this.nohp});
  
}

// class Customer
class Customer extends StatefulWidget {
  _MyappState createState() => _MyappState();
}

class _MyappState extends State<Siswa> {
  //deklarasi variabel
  final txtidcustomer = TextEditingController();
  final txtnamacustomer = TextEditingController();
  final txtalamat = TextEditingController();
  final txtnohp = TextEditingController();

  List<Widget> data = [];

  onTambah() {
    setState(() {
      data.add(ListTile(
        leading: Text(txtidcustomer.text),
        title: Text(txtnamacustomer.text),
        subtitle: Text(txtalamat.text),
        trailing: Text(txtnohp.text),
      ));
      txtidcustomer.clear();
      txtnamacustomer.clear();
      txtalamat.clear();
      txtnohp.clear();
    });
  }

  Widget build(BuildContext context) {
    return ListView(
      children: <Widget>[
        new Container(
          padding: EdgeInsets.all(10.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.spaceEvenly,
            children: <Widget>[
           
              TextField(
                controller: txtidcustomer,
                decoration: InputDecoration(hintText: 'ID Customer'),
              ),
              TextField(
                controller: txtnamacustomer,
                decoration: InputDecoration(hintText: 'Nama Customer'),
              ),
              TextField(
                controller: txtalamat,
                decoration: InputDecoration(hintText: 'Alamat'),
              ),
               TextField(
                controller: txtnohp,
                decoration: InputDecoration(hintText: 'No Hp'),
              ),
              Divider(height: 5.0),
              ElevatedButton(child: Text("Tambah"), onPressed: onTambah),
            ],
          ),
        ),
        new Column(
          children: data,
        )
      ],
    );
  }
}
