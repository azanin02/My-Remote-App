import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatefulWidget {
  const MyApp({super.key});

  
  @override
  State<MyApp> createState() => _MyHomePageState();
}


class _MyHomePageState extends State<MyApp> {
  String operation = "Stop";
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData(
        primarySwatch: Colors.grey),
      home: Scaffold(
        appBar: AppBar(title: const Text("MY REMOTE APP")),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Container(
                decoration: BoxDecoration(
                    border: Border.all(color: Colors.blueGrey),
                    borderRadius: BorderRadius.circular(40)),
                height: 200,
                width: 330,
                child: Column(
                    mainAxisAlignment: MainAxisAlignment.center,
                    crossAxisAlignment: CrossAxisAlignment.center,
                    children: [
                      SizedBox(
                        width: 90,
                        child: ElevatedButton(
                            onPressed: () {
                              onPressed("Forward");
                            },
                            child: const Text("FOWARD")),
                      ),
                      Row(
                        mainAxisAlignment: MainAxisAlignment.spaceAround,
                        children: [
                          SizedBox(
                            width: 90,
                            child: ElevatedButton(
                                onPressed: () {
                                  onPressed("Left");
                                },
                                child: const Text("LEFT")),
                          ),
                          SizedBox(
                            width: 90,
                            child: ElevatedButton(
                                onPressed: () {
                                  onPressed("Stop");
                                },
                                child: const Text("STOP")),
                          ),
                          SizedBox(
                            width: 90,
                            child: ElevatedButton(
                                onPressed: () {
                                  onPressed("Right");
                                },
                                child: const Text("RIGHT")),
                          )
                        ],
                      ),
                      SizedBox(
                        width: 90,
                        child: ElevatedButton(
                            onPressed: () {
                              onPressed("Reverse");
                            },
                            child: const Text("REVERSE")),
                      )
                    ]),
              ),
              Text(
                operation,
                style:
                    const TextStyle(fontSize: 30, fontWeight: FontWeight.bold),
              ),
            ],
          ),
        ),
      ),
    );
  }

  void onPressed(String s) {
    operation = s;
    setState(() {});
  }
}