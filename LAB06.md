```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  static const double buttonFontSize = 24.0;
  static const double displayFontSize = 32.0;

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Calculadora',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        scaffoldBackgroundColor: const Color.fromARGB(255, 226, 226, 226),
      ),
      debugShowCheckedModeBanner: false,
      home: SafeArea(
        child: Scaffold(
          body: Column(
            children: <Widget>[
              const SizedBox(height: 210.0),
              Container(
                padding: const EdgeInsets.only(right: 20.0),
                alignment: Alignment.centerRight,
                child: const Text(
                  "8 x 4",
                  style: TextStyle(
                      fontSize: displayFontSize,
                      fontWeight: FontWeight.bold,
                      color: Color.fromARGB(232, 143, 141, 141)),
                ),
              ),
              Container(
                padding: const EdgeInsets.only(right: 20.0),
                alignment: Alignment.centerRight,
                child: const Text(
                  "32",
                  style: TextStyle(
                      fontSize: displayFontSize,
                      fontWeight: FontWeight.bold,
                      color: Color.fromARGB(255, 0, 0, 0)),
                ),
              ),
              const Divider(color: Colors.white24),
              // Botones
              Expanded(
                child: Column(
                  children: [
                    buttonRow(["AC", "%", "⌫", "÷"]),
                    buttonRow(["7", "8", "9", "×"]),
                    buttonRow(["4", "5", "6", "-"]),
                    buttonRow(["1", "2", "3", "+"]),
                    buttonRow(["00", "0", ".", "="]),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }

  Widget buttonRow(List<String> labels) {
    return Expanded(
      child: Row(
        children: labels.map((label) {
          return Expanded(
            child: Container(
              margin: const EdgeInsets.all(4.0),
              decoration: BoxDecoration(
                color: _getButtonColor(label),
                borderRadius: BorderRadius.circular(100.0),
              ),
              child: Center(
                child: Text(
                  label,
                  style: const TextStyle(
                      fontSize: buttonFontSize, color: Color.fromARGB(255, 0, 0, 0)),
                ),
              ),
            ),
          );
        }).toList(),
      ),
    );
  }

  Color _getButtonColor(String label) {
    if (label == "=") return Colors.orange;
    if (label == "8") return Colors.orange;
    if (label == "4") return Colors.orange;
    if (label == "×") return Colors.orange;
    if (label == "AC" || label == "⌫" || label == "%" || label == "÷" || label == "-" || label == "+") return const Color.fromARGB(255, 211, 211, 211);
    return const Color.fromARGB(255, 247, 246, 246);
  }
}
