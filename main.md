          import 'dart:async';
          import 'package:favorite_button/favorite_button.dart';
          import 'package:flutter/material.dart';
          import 'package:google_maps_flutter/google_maps_flutter.dart';

          void main() {
            runApp(
                MaterialApp(
                  home: HomePage(),
                )
            );
          }

          class HomePage extends StatefulWidget {
            @override
            _HomePageState createState() => _HomePageState();
          }

          class _HomePageState extends State<HomePage> {
            bool notification = false;

            @override
            Widget build(BuildContext context) {
              return MaterialApp(
                home: Scaffold(
                  appBar: AppBar(title: Text('Android Smart Traffic'),),
                  body: Container(
                      child: Column(
                        mainAxisAlignment: MainAxisAlignment.center,
                        crossAxisAlignment: CrossAxisAlignment.center,
                        children: <Widget>[
                          Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            crossAxisAlignment: CrossAxisAlignment.center,
                            children: <Widget>[
                              Text('Reach your Destination with us',
                                style: TextStyle(fontSize: 17.0),
                              ),
                            ],
                          ),
                          Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            crossAxisAlignment: CrossAxisAlignment.center,
                            children: <Widget>[
                              SizedBox(width: 10,),
                              Checkbox(
                                value: this.notification,
                                onChanged: (bool value) {
                                  setState(() {
                                    this.notification = value;
                                  });
                                },
                              ),
                              Text(' Get notification',
                                style: TextStyle(fontSize: 17.0),
                              ),
                            ],
                          ),
                          Row(
                            mainAxisAlignment: MainAxisAlignment.center,
                            crossAxisAlignment: CrossAxisAlignment.center,
                            children: <Widget>[
                              ElevatedButton(
                                child: Text('Start'),
                                onPressed: () {
                                  Navigator.push(
                                    context,
                                    MaterialPageRoute(builder: (context) => SettingPage()),
                                  );
                                },
                              ),
                            ],
                          ),
                        ],
                      )
                  ),
                ),
                theme: ThemeData(primarySwatch: Colors.lightGreen),
              );
            }
          }

          class SettingPage extends StatefulWidget {
            @override
            _SettingPageState createState() => _SettingPageState();
          }

          class _SettingPageState extends State<SettingPage> {
            TextEditingController myController1 = TextEditingController();
            TextEditingController myController2 = TextEditingController();
            TextEditingController myController3 = TextEditingController();
            TextEditingController myController4 = TextEditingController();
            TextEditingController myController5 = TextEditingController();
            TextEditingController myController6 = TextEditingController();
            bool star1 = false;
            bool star2 = false;
            bool star3 = false;

            @override
            Widget build(BuildContext context) {
              return MaterialApp(
                  home:Scaffold(
                    appBar: AppBar(
                      title: Text("Setting"),
                    ),
                    body: SingleChildScrollView(
                      padding: EdgeInsets.only(left: 0, right: 0, top: 20, bottom: 20),
                      child: Center(
                        child: Column(
                          children: [
                              Card(
                                color: Colors.white,
                                child: Padding(
                                    padding: const EdgeInsets.all(20.0),
                                    child: Column(
                                      children: [
                                        Row(
                                          children: [
                                            Text('Address: ', style: TextStyle(fontSize: 15,)),
                                            Flexible(
                                              child: TextField(
                                                obscureText: false,
                                                controller: myController1,
                                                decoration: InputDecoration(
                                                  border: OutlineInputBorder(),
                                                  labelText: 'Address',
                                                ),
                                              ),
                                            ),
                                          ],
                                        ),
                                        SizedBox(height: 10,),
                                        Row(
                                          children: [
                                            Text('Set as: ', style: TextStyle(fontSize: 15,)),
                                            Flexible(
                                              child: TextField(
                                                obscureText: false,
                                                controller: myController2,
                                                decoration: InputDecoration(
                                                  border: OutlineInputBorder(),
                                                  labelText: 'Name',
                                                ),
                                              ),
                                            ),
                                            Text('          '),
                                            StarButton(
                                              isStarred: false,
                                              valueChanged: (_isStarred) {
                                                print('Is Starred : $_isStarred');
                                                star1 = _isStarred;
                                              },
                                            )
                                          ],
                                        ),
                                        SizedBox(height: 10,),
                                      ],
                                    ),
                                ),
                              ),
                              SizedBox(height: 10,),
                              Card(
                                color: Colors.white,
                                child: Padding(
                                  padding: const EdgeInsets.all(20.0),
                                  child: Column(
                                    children: [
                                      Row(
                                        children: [
                                          Text('Address: ', style: TextStyle(fontSize: 15,)),
                                          Flexible(
                                            child: TextField(
                                              obscureText: false,
                                              controller: myController3,
                                              decoration: InputDecoration(
                                                border: OutlineInputBorder(),
                                                labelText: 'Address',
                                              ),
                                            ),
                                          ),
                                        ],
                                      ),
                                      SizedBox(height: 10,),
                                      Row(
                                        children: [
                                          Text('Set as: ', style: TextStyle(fontSize: 15,)),
                                          Flexible(
                                            child: TextField(
                                              obscureText: false,
                                              controller: myController4,
                                              decoration: InputDecoration(
                                                border: OutlineInputBorder(),
                                                labelText: 'Name',
                                              ),
                                            ),
                                          ),
                                          Text('          '),
                                          StarButton(
                                            isStarred: false,
                                            valueChanged: (_isStarred) {
                                              print('Is Starred : $_isStarred');
                                              star2 = _isStarred;
                                            },
                                          )
                                        ],
                                      ),
                                      SizedBox(height: 10,),
                                    ],
                                  ),
                                ),
                              ),
                              SizedBox(height: 10,),
                              Card(
                                color: Colors.white,
                                child: Padding(
                                  padding: const EdgeInsets.all(20.0),
                                  child: Column(
                                    children: [
                                      Row(
                                        children: [
                                          Text('Address: ', style: TextStyle(fontSize: 15,)),
                                          Flexible(
                                            child: TextField(
                                              obscureText: false,
                                              controller: myController5,
                                              decoration: InputDecoration(
                                                border: OutlineInputBorder(),
                                                labelText: 'Address',
                                              ),
                                            ),
                                          ),
                                        ],
                                      ),
                                      SizedBox(height: 10,),
                                      Row(
                                        children: [
                                          Text('Set as: ', style: TextStyle(fontSize: 15,)),
                                          Flexible(
                                            child: TextField(
                                              obscureText: false,
                                              controller: myController6,
                                              decoration: InputDecoration(
                                                border: OutlineInputBorder(),
                                                labelText: 'Name',
                                              ),
                                            ),
                                          ),
                                          Text('          '),
                                          StarButton(
                                            isStarred: false,
                                            valueChanged: (_isStarred) {
                                              print('Is Starred : $_isStarred');
                                              star3 = _isStarred;
                                            },
                                          )
                                        ],
                                      ),
                                      SizedBox(height: 10,),
                                    ],
                                  ),
                                ),
                              ),

                            ],
                          ),
                        ),
                    ),
                    bottomNavigationBar: BottomAppBar(
                      child: Row(
                        mainAxisAlignment: MainAxisAlignment.spaceAround,
                        children: <Widget>[
                          TextButton(
                            onPressed: () {
                              Navigator.push(
                                context,
                                MaterialPageRoute(builder: (context) => HomePage()),
                              );
                            },
                            child: Text('<< Back', style: TextStyle(color: Colors.indigo, decoration:TextDecoration.underline,)),
                          ),
                          ElevatedButton(
                            style: ElevatedButton.styleFrom(
                              primary: Colors.grey,
                              onPrimary: Colors.black,
                            ),
                            child: Text('Edit'),
                            onPressed: () { },
                          ),
                          ElevatedButton(
                            child: Text('Save'),
                            onPressed: () {
                              _sendDataToSecondScreen(context);
                            },
                          ),
                          TextButton(
                            onPressed: () {
                              Navigator.push(
                                context,
                                MaterialPageRoute(builder: (context) => DestinationPage()),
                              );
                            },
                            child: Text('Skip >>', style: TextStyle(color: Colors.indigo, decoration:TextDecoration.underline,)),
                          ),
                        ],
                      ),
                    ),
                  ),
                  theme: ThemeData(primarySwatch: Colors.lightGreen),
              );
            }
            void _sendDataToSecondScreen(BuildContext context) {
              String addr1 = myController1.text;
              String set1 = myController2.text;
              String addr2 = myController3.text;
              String set2 = myController4.text;
              String addr3 = myController5.text;
              String set3 = myController6.text;
              bool s1 = star1;
              bool s2 = star2;
              bool s3 = star3;

              Navigator.push(
                  context,
                  MaterialPageRoute(
                    builder: (context) => SaveScreen(text1: addr1, text2: set1, text3: addr2, text4: set2, text5: addr3, text6: set3, st1: s1, st2: s2, st3: s3,),
                  ) ) ;
            }
          }

          class SaveScreen extends StatelessWidget {
            final String text1, text2, text3, text4, text5, text6;
            final bool st1, st2, st3;
            SaveScreen({Key key, @required this.text1, @required this.text2, @required this.text3,
                        @required this.text4, @required this.text5, @required this.text6,
                        @required this.st1, @required this.st2, @required this.st3
            }) : super(key: key);

            @override
            Widget build(BuildContext context) {
              return MaterialApp(
                home:Scaffold(
                  appBar: AppBar(
                    title: Text("Setting"),
                  ),
                  body: SingleChildScrollView(
                    padding: EdgeInsets.only(left: 0, right: 0, top: 20, bottom: 20),
                    child: Center(
                      child: Column(
                        children: [
                          Card(
                            color: Colors.white,
                            child: Padding(
                              padding: const EdgeInsets.all(20.0),
                              child: Column(
                                children: [
                                  Row(
                                    children: [
                                      StarButton(
                                        isStarred: st1,
                                        valueChanged: (_isStarred) {
                                          print('Is Starred : $_isStarred');
                                        },
                                      ),
                                      Text('Address: ', style: TextStyle(fontSize: 15,)),
                                      Text(text1, style: TextStyle(fontSize: 15,)),
                                    ],
                                  ),
                                  SizedBox(height: 10,),
                                  Row(
                                    children: [
                                      Text('Set as: ', style: TextStyle(fontSize: 15,)),
                                      Text(text2, style: TextStyle(fontSize: 15,)),
                                    ],
                                  ),
                                  SizedBox(height: 10,),
                                ],
                              ),
                            ),
                          ),
                          SizedBox(height: 10,),
                          Card(
                            color: Colors.white,
                            child: Padding(
                              padding: const EdgeInsets.all(20.0),
                              child: Column(
                                children: [
                                  Row(
                                    children: [
                                      StarButton(
                                        isStarred: st2,
                                        valueChanged: (_isStarred) {
                                          print('Is Starred : $_isStarred');
                                        },
                                      ),
                                      Text('Address: ', style: TextStyle(fontSize: 15,)),
                                      Text(text3, style: TextStyle(fontSize: 15,)),
                                    ],
                                  ),
                                  SizedBox(height: 10,),
                                  Row(
                                    children: [
                                      Text('Set as: ', style: TextStyle(fontSize: 15,)),
                                      Text(text4, style: TextStyle(fontSize: 15,)),
                                    ],
                                  ),
                                  SizedBox(height: 10,),
                                ],
                              ),
                            ),
                          ),
                          SizedBox(height: 10,),
                          Card(
                            color: Colors.white,
                            child: Padding(
                              padding: const EdgeInsets.all(20.0),
                              child: Column(
                                children: [
                                  Row(
                                    children: [
                                      StarButton(
                                        isStarred: st3,
                                        valueChanged: (_isStarred) {
                                          print('Is Starred : $_isStarred');
                                        },
                                      ),
                                      Text('Address: ', style: TextStyle(fontSize: 15,)),
                                      Text(text5, style: TextStyle(fontSize: 15,)),
                                    ],
                                  ),
                                  SizedBox(height: 10,),
                                  Row(
                                    children: [
                                      Text('Set as: ', style: TextStyle(fontSize: 15,)),
                                      Text(text6, style: TextStyle(fontSize: 15,)),
                                    ],
                                  ),
                                  SizedBox(height: 10,),
                                ],
                              ),
                            ),
                          ),

                        ],
                      ),
                    ),
                  ),
                  bottomNavigationBar: BottomAppBar(
                    child: Row(
                      mainAxisAlignment: MainAxisAlignment.spaceAround,
                      children: <Widget>[
                        TextButton(
                          onPressed: () {
                            Navigator.push(
                              context,
                              MaterialPageRoute(builder: (context) => HomePage()),
                            );
                          },
                          child: Text('<< Back', style: TextStyle(color: Colors.indigo, decoration:TextDecoration.underline,)),
                        ),
                        ElevatedButton(
                          child: Text('Edit'),
                          onPressed: () {
                            Navigator.push(
                              context,
                              MaterialPageRoute(builder: (context) => SettingPage()),
                            );
                          },
                        ),
                        ElevatedButton(
                          style: ElevatedButton.styleFrom(
                            primary: Colors.grey,
                            onPrimary: Colors.black,
                          ),
                          child: Text('Save'),
                          onPressed: () { },
                        ),
                        TextButton(
                          onPressed: () {
                            Navigator.push(
                              context,
                              MaterialPageRoute(builder: (context) => DestinationPage()),
                            );
                          },
                          child: Text('Skip >>', style: TextStyle(color: Colors.indigo, decoration:TextDecoration.underline,)),
                        ),
                      ],
                    ),
                  ),
                ),
                theme: ThemeData(primarySwatch: Colors.lightGreen),
              );
            }
          }

          class DestinationPage extends StatefulWidget {
            @override
            _DestinationPageState createState() => _DestinationPageState();
          }

          class _DestinationPageState extends State<DestinationPage> {
            bool _usefav = false;
            @override
            Widget build(BuildContext context) {
              return MaterialApp(
                home:Scaffold(
                  appBar: AppBar(
                    title: Text("Destination"),
                  ),
                  body: SingleChildScrollView(
                    padding: EdgeInsets.only(left: 0, right: 0, top: 20, bottom: 20),
                    child: Center(
                      child: Column(
                        children: [
                          Card(
                            color: Colors.white,
                              child: Padding(
                                padding: const EdgeInsets.all(20.0),
                                child: Column(
                                  mainAxisAlignment: MainAxisAlignment.center,
                                  crossAxisAlignment: CrossAxisAlignment.center,
                                  children: <Widget>[
                                    Row(
                                      mainAxisAlignment: MainAxisAlignment.center,
                                      crossAxisAlignment: CrossAxisAlignment.center,
                                      children: <Widget>[
                                        Icon(
                                          Icons.location_on,
                                          color: Colors.redAccent,
                                          size: 45.0,
                                        ),
                                        Text(' Destination', style: TextStyle(fontSize: 40.0),),
                                      ],
                                    ),
                                    SizedBox(height: 30,),
                                    Row(
                                      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                      crossAxisAlignment: CrossAxisAlignment.center,
                                      children: <Widget>[
                                        Flexible(
                                          child: TextField(
                                            obscureText: false,
                                            decoration: InputDecoration(
                                              border: OutlineInputBorder(),
                                              labelText: 'Address',
                                            ),
                                          ),
                                        ),
                                      ],
                                    ),
                                    SizedBox(height: 10,),
                                    Row(
                                      mainAxisAlignment: MainAxisAlignment.center,
                                      crossAxisAlignment: CrossAxisAlignment.center,
                                      children: <Widget>[
                                        Checkbox(
                                          value: this._usefav,
                                          onChanged: (bool value) {
                                            setState(() {
                                              this._usefav = value;
                                            });
                                          },
                                        ),
                                        Text(' use my favourite address',
                                          style: TextStyle(fontSize: 17.0),
                                        ),
                                      ],
                                    ),
                                    SizedBox(height: 10,),
                                    Row(
                                      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                      crossAxisAlignment: CrossAxisAlignment.center,
                                      children: [
                                        ElevatedButton(
                                          style: ElevatedButton.styleFrom(
                                            primary: Colors.green,
                                            onPrimary: Colors.white,
                                          ),
                                          child: Text('Find the Route'),
                                          onPressed: () {
                                            Navigator.push(
                                              context,
                                              MaterialPageRoute(builder: (context) => RoutePage()),
                                            );
                                          },
                                        ),
                                        ElevatedButton(
                                          style: ElevatedButton.styleFrom(
                                            primary: Colors.red,
                                            onPrimary: Colors.white,
                                          ),
                                          child: Text('Check the Traffic'),
                                          onPressed: () {
                                            Navigator.push(
                                              context,
                                              MaterialPageRoute(builder: (context) => TrafficPage()),
                                            );
                                          },
                                        ),
                                      ],
                                    ),
                                    SizedBox(height: 10,),
                                    Row(
                                      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                      crossAxisAlignment: CrossAxisAlignment.center,
                                      children: [
                                        ElevatedButton(
                                          style: ElevatedButton.styleFrom(
                                            primary: Colors.green,
                                            onPrimary: Colors.white,
                                          ),
                                          child: Text('Navigate Me'),
                                          onPressed: () {
                                            Navigator.push(
                                              context,
                                              MaterialPageRoute(builder: (context) => NavigatePage()),
                                            );
                                          },
                                        ),
                                      ],
                                    ),
                                  ],
                                ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                  bottomNavigationBar: BottomAppBar(
                    child: Row(
                      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                      children: <Widget>[
                        TextButton(
                          onPressed: () {
                            Navigator.push(
                              context,
                              MaterialPageRoute(builder: (context) => SettingPage()),
                            );
                          },
                          child: Text('<< Back', style: TextStyle(color: Colors.indigo, decoration:TextDecoration.underline,)),
                        ),
                      ],
                    ),
                  ),
                ),
                theme: ThemeData(primarySwatch: Colors.lightGreen),
              );
            }
          }

          class RoutePage extends StatefulWidget {
            @override
            _RoutePageState createState() => _RoutePageState();
          }

          class _RoutePageState extends State<RoutePage> {
            @override
            Widget build(BuildContext context) {
              return MaterialApp(
                home:Scaffold(
                  appBar: AppBar(
                    title: Text("Route"),
                  ),
                  body: SingleChildScrollView(
                    padding: EdgeInsets.only(left: 0, right: 0, top: 20, bottom: 20),
                    child: Center(
                      child: Column(
                        children: [
                          Text('You can use: ', style: TextStyle(fontSize: 20.0),),
                          SizedBox(height: 20,),
                          Card(
                            color: Colors.lime,
                            child: Padding(
                              padding: const EdgeInsets.all(20.0),
                              child: Column(
                                mainAxisAlignment: MainAxisAlignment.center,
                                crossAxisAlignment: CrossAxisAlignment.center,
                                children: <Widget>[
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      Text('1002 Road'),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      Text('Distance: 19.6 km'),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      Text('Time: 33 minutes'),
                                    ],
                                  ),
                                ],
                              ),
                            ),
                          ),
                          SizedBox(height: 30,),
                          Text('Or: ', style: TextStyle(fontSize: 20.0),),
                          SizedBox(height: 20,),
                          Card(
                            color: Colors.lime,
                            child: Padding(
                              padding: const EdgeInsets.all(20.0),
                              child: Column(
                                mainAxisAlignment: MainAxisAlignment.center,
                                crossAxisAlignment: CrossAxisAlignment.center,
                                children: <Widget>[
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      Text('1009 Road'),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      Text('Distance: 20.2 km'),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      Text('Time: 40 minutes'),
                                    ],
                                  ),
                                ],
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                  bottomNavigationBar: BottomAppBar(
                    child: Row(
                      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                      children: <Widget>[
                        TextButton(
                          onPressed: () {
                            Navigator.push(
                              context,
                              MaterialPageRoute(builder: (context) => DestinationPage()),
                            );
                          },
                          child: Text('<< Back', style: TextStyle(color: Colors.indigo, decoration:TextDecoration.underline,)),
                        ),
                      ],
                    ),
                  ),
                ),
                theme: ThemeData(primarySwatch: Colors.lightGreen),
              );
            }
          }

          class TrafficPage extends StatefulWidget {
            @override
            _TrafficPageState createState() => _TrafficPageState();
          }

          class _TrafficPageState extends State<TrafficPage> {
            @override
            Widget build(BuildContext context) {
              return MaterialApp(
                home:Scaffold(
                  appBar: AppBar(
                    title: Text("Traffic Report"),
                  ),
                  body: SingleChildScrollView(
                    padding: EdgeInsets.only(left: 0, right: 0, top: 20, bottom: 20),
                    child: Center(
                      child: Column(
                        children: [
                          Text('Real time: ', style: TextStyle(fontSize: 20.0),),
                          SizedBox(height: 20,),
                          Card(
                            color: Colors.lime,
                            child: Padding(
                              padding: const EdgeInsets.all(20.0),
                              child: Column(
                                mainAxisAlignment: MainAxisAlignment.center,
                                crossAxisAlignment: CrossAxisAlignment.center,
                                children: <Widget>[
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      SizedBox(height: 20,),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      Text('Real time traffic report'),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      SizedBox(height: 20,),
                                    ],
                                  ),
                                ],
                              ),
                            ),
                          ),
                          SizedBox(height: 20,),
                          Text('Traffic news ', style: TextStyle(fontSize: 20.0),),
                          SizedBox(height: 20,),
                          Card(
                            color: Colors.lime,
                            child: Padding(
                              padding: const EdgeInsets.all(20.0),
                              child: Column(
                                mainAxisAlignment: MainAxisAlignment.center,
                                crossAxisAlignment: CrossAxisAlignment.center,
                                children: <Widget>[
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      SizedBox(height: 20,),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      Text('Hot news about traffic condition in Thailand'),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      SizedBox(height: 20,),
                                    ],
                                  ),
                                ],
                              ),
                            ),
                          ),
                          SizedBox(height: 10,),
                          Card(
                            color: Colors.lime,
                            child: Padding(
                              padding: const EdgeInsets.all(20.0),
                              child: Column(
                                mainAxisAlignment: MainAxisAlignment.center,
                                crossAxisAlignment: CrossAxisAlignment.center,
                                children: <Widget>[
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      SizedBox(height: 20,),
                                    ],
                                  ),
                                  Row(
                                    mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                                    crossAxisAlignment: CrossAxisAlignment.center,
                                    children: <Widget>[
                                      SizedBox(height: 20,),
                                    ],
                                  ),
                                ],
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                  bottomNavigationBar: BottomAppBar(
                    child: Row(
                      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                      children: <Widget>[
                        TextButton(
                          onPressed: () {
                            Navigator.push(
                              context,
                              MaterialPageRoute(builder: (context) => DestinationPage()),
                            );
                          },
                          child: Text('<< Back', style: TextStyle(color: Colors.indigo, decoration:TextDecoration.underline,)),
                        ),
                      ],
                    ),
                  ),
                ),
                theme: ThemeData(primarySwatch: Colors.lightGreen),
              );
            }
          }

          class NavigatePage extends StatefulWidget {
            @override
            _NavigatePageState createState() => _NavigatePageState();
          }

          class _NavigatePageState extends State<NavigatePage> {
            Completer<GoogleMapController> _controller = Completer();

            @override
            Widget build(BuildContext context) {
              return MaterialApp(
                  home:Scaffold(
                    appBar: AppBar(
                      title: Text("Navigate"),
                  ),
                    body: GoogleMap(
                      mapType: MapType.terrain,
                      initialCameraPosition: CameraPosition(
                        target: LatLng(13.794216, 100.324731),
                        zoom: 12,
                      ),
                      onMapCreated: (GoogleMapController controller) {
                        _controller.complete(controller);
                      },
                    )
                  ),
                theme: ThemeData(primarySwatch: Colors.lightGreen),
              );
            }
          }
