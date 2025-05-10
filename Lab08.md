```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      initialRoute: '/',
      routes: {
        '/': (context) => LoginPage(),
        '/register': (context) => RegisterPage(),
        '/menu': (context) => MenuPage(),
        '/page1': (context) => Page1(),
        '/page2': (context) => Page2(),
        '/page3': (context) => Page3(),
      },
    );
  }
}

// LOGIN
class LoginPage extends StatelessWidget {
  final TextEditingController userController = TextEditingController();
  final TextEditingController passController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Stack(
        fit: StackFit.expand,
        children: [
          Image.network(
            'https://img.freepik.com/vector-gratis/fondo-abstracto-colorido_23-2148470833.jpg?semt=ais_hybrid&w=740',
            fit: BoxFit.cover,
          ),
          Center(
            child: Container(
              padding: EdgeInsets.all(25),
              width: 350,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.95),
                borderRadius: BorderRadius.circular(15),
                boxShadow: [
                  BoxShadow(
                    color: Colors.black.withOpacity(0.3),
                    blurRadius: 15,
                    offset: Offset(0, 8),
                  ),
                ],
              ),
              child: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  Image.network(
                    'https://images.icon-icons.com/3862/PNG/512/login_icon_240424.png',
                    height: 100,
                  ),
                  Text(
                    'Iniciar Sesión',
                    style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
                  ),
                  SizedBox(height: 25),
                  TextField(
                    controller: userController,
                    decoration: InputDecoration(
                      labelText: 'Usuario',
                      border: OutlineInputBorder(),
                    ),
                  ),
                  SizedBox(height: 15),
                  TextField(
                    controller: passController,
                    obscureText: true,
                    decoration: InputDecoration(
                      labelText: 'Contraseña',
                      border: OutlineInputBorder(),
                    ),
                  ),
                  SizedBox(height: 25),
                  ElevatedButton(
                    onPressed: () {
                      Navigator.pushNamed(context, '/menu');
                    },
                    child: Text('Entrar'),
                  ),
                  SizedBox(height: 15),
                  GestureDetector(
                    onTap: () {
                      Navigator.pushNamed(context, '/register');
                    },
                    child: Text(
                      '¿No tienes cuenta? Regístrate aquí',
                      style: TextStyle(
                        color: Colors.blue,
                        decoration: TextDecoration.underline,
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }
}

class RegisterPage extends StatelessWidget {
  final TextEditingController userController = TextEditingController();
  final TextEditingController passController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Stack(
        fit: StackFit.expand,
        children: [
          Image.network(
            'https://img.freepik.com/vector-gratis/fondo-abstracto-colorido_23-2148470833.jpg?semt=ais_hybrid&w=740',
            fit: BoxFit.cover,
          ),
          Center(
            child: Container(
              padding: EdgeInsets.all(25),
              width: 350,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.95),
                borderRadius: BorderRadius.circular(15),
                boxShadow: [
                  BoxShadow(
                    color: Colors.black.withOpacity(0.3),
                    blurRadius: 15,
                    offset: Offset(0, 8),
                  ),
                ],
              ),
              child: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  Image.network(
                    'https://us.123rf.com/450wm/tuktukdesign/tuktukdesign1608/tuktukdesign160800090/62073387-a%C3%B1adir-icono-de-usuario-hombre-cuenta-nueva-el-perfil-de-ilustraci%C3%B3n-vectorial-glifo.jpg',
                    height: 100,
                  ),
                  SizedBox(height: 15),
                  Text(
                    'Registro de Usuario',
                    style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
                  ),
                  SizedBox(height: 25),
                  TextField(
                    controller: userController,
                    decoration: InputDecoration(
                      labelText: 'Nuevo Usuario',
                      border: OutlineInputBorder(),
                    ),
                  ),
                  SizedBox(height: 15),
                  TextField(
                    controller: passController,
                    obscureText: true,
                    decoration: InputDecoration(
                      labelText: 'Nueva Contraseña',
                      border: OutlineInputBorder(),
                    ),
                  ),
                  SizedBox(height: 25),
                  ElevatedButton(
                    onPressed: () {
                      Navigator.pop(context); 
                    },
                    child: Text('Registrarme'),
                  ),
                  SizedBox(height: 15),
                  GestureDetector(
                    onTap: () {
                      Navigator.pop(context); 
                    },
                    child: Text(
                      '¿Ya tienes cuenta? Inicia sesión aquí',
                      style: TextStyle(
                        color: Colors.blue,
                        decoration: TextDecoration.underline,
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }
}



// MENÚ PRINCIPAL
class MenuPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Stack(
        fit: StackFit.expand,
        children: [
          Image.network(
            'https://img.freepik.com/vector-gratis/fondo-abstracto-circulos-puntos_23-2148458946.jpg?semt=ais_hybrid&w=740', // Fondo del menú
            fit: BoxFit.cover,
          ),
          Center(
            child: Container(
              padding: EdgeInsets.all(25),
              width: 350,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.95),
                borderRadius: BorderRadius.circular(15),
                boxShadow: [
                  BoxShadow(
                    color: Colors.black.withOpacity(0.3),
                    blurRadius: 15,
                    offset: Offset(0, 8),
                  ),
                ],
              ),
              child: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  Image.network(
                    'https://cdn-icons-png.flaticon.com/512/5087/5087579.png', // Icono de bienvenida
                    height: 100,
                  ),
                  SizedBox(height: 15),
                  Text(
                    'Menú Principal',
                    style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
                  ),
                  SizedBox(height: 30),
                  // Botón para navegar a Page 1
                  ElevatedButton.icon(
                    onPressed: () {
                      Navigator.pushNamed(context, '/page1');
                    },
                    icon: Icon(Icons.pageview),
                    label: Text('Ir a Página 1'),
                    style: ElevatedButton.styleFrom(
                      minimumSize: Size(250, 50),
                      backgroundColor: Colors.blue,  // Usando backgroundColor en lugar de primary
                    ),
                  ),
                  SizedBox(height: 20),
                  // Botón para navegar a Page 2
                  ElevatedButton.icon(
                    onPressed: () {
                      Navigator.pushNamed(context, '/page2');
                    },
                    icon: Icon(Icons.pageview),
                    label: Text('Ir a Página 2'),
                    style: ElevatedButton.styleFrom(
                      minimumSize: Size(250, 50),
                      backgroundColor: Colors.green, // Usando backgroundColor
                    ),
                  ),
                  SizedBox(height: 20),
                  // Botón para navegar a Page 3
                  ElevatedButton.icon(
                    onPressed: () {
                      Navigator.pushNamed(context, '/page3');
                    },
                    icon: Icon(Icons.pageview),
                    label: Text('Ir a Página 3'),
                    style: ElevatedButton.styleFrom(
                      minimumSize: Size(250, 50),
                      backgroundColor: Colors.orange, // Usando backgroundColor
                    ),
                  ),
                  SizedBox(height: 30),
                  // Botón para cerrar sesión y regresar al login
                  ElevatedButton(
                    onPressed: () {
                      Navigator.pushNamed(context, '/');
                    },
                    child: Text('Cerrar Sesión'),
                    style: ElevatedButton.styleFrom(
                      minimumSize: Size(250, 50),
                      backgroundColor: Colors.red, // Usando backgroundColor
                    ),
                  ),
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }
}


class FAQItem {
  final String question;
  final String answer;

  FAQItem({required this.question, required this.answer});
}

List<FAQItem> faqList = [
  FAQItem(
    question: '¿Cómo puedo cambiar mi contraseña?',
    answer: 'Para cambiar tu contraseña, ve a la sección de configuración y busca la opción "Cambiar contraseña".',
  ),
  FAQItem(
    question: '¿Cuáles son los métodos de pago aceptados?',
    answer: 'Aceptamos tarjetas de crédito, transferencias bancarias y pagos en efectivo en nuestras sucursales.',
  ),
  FAQItem(
    question: '¿Cómo puedo cambiar mi contraseña?',
    answer: 'Para cambiar tu contraseña, ve a la sección de configuración y busca la opción "Cambiar contraseña".',
  ),
  FAQItem(
    question: '¿Cuáles son los métodos de pago aceptados?',
    answer: 'Aceptamos tarjetas de crédito, transferencias bancarias y pagos en efectivo en nuestras sucursales.',
  ),
  FAQItem(
    question: '¿Cómo puedo cambiar mi contraseña?',
    answer: 'Para cambiar tu contraseña, ve a la sección de configuración y busca la opción "Cambiar contraseña".',
  ),
  FAQItem(
    question: '¿Cuáles son los métodos de pago aceptados?',
    answer: 'Aceptamos tarjetas de crédito, transferencias bancarias y pagos en efectivo en nuestras sucursales.',
  ),
  FAQItem(
    question: '¿Cómo puedo cambiar mi contraseña?',
    answer: 'Para cambiar tu contraseña, ve a la sección de configuración y busca la opción "Cambiar contraseña".',
  ),
  FAQItem(
    question: '¿Cuáles son los métodos de pago aceptados?',
    answer: 'Aceptamos tarjetas de crédito, transferencias bancarias y pagos en efectivo en nuestras sucursales.',
  ),
  FAQItem(
    question: '¿Cómo puedo cambiar mi contraseña?',
    answer: 'Para cambiar tu contraseña, ve a la sección de configuración y busca la opción "Cambiar contraseña".',
  ),
  FAQItem(
    question: '¿Cuáles son los métodos de pago aceptados?',
    answer: 'Aceptamos tarjetas de crédito, transferencias bancarias y pagos en efectivo en nuestras sucursales.',
  ),
  FAQItem(
    question: '¿Cómo puedo cambiar mi contraseña?',
    answer: 'Para cambiar tu contraseña, ve a la sección de configuración y busca la opción "Cambiar contraseña".',
  ),
  FAQItem(
    question: '¿Cuáles son los métodos de pago aceptados?',
    answer: 'Aceptamos tarjetas de crédito, transferencias bancarias y pagos en efectivo en nuestras sucursales.',
  ),
];
// PÁGINAS
class Page1 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Preguntas Frecuentes')),
      body: ListView.builder(
        itemCount: faqList.length,
        itemBuilder: (context, index) {
          final item = faqList[index];
          return ExpansionTile(
            title: Text(item.question),
            children: [
              Padding(
                padding: const EdgeInsets.all(16.0),
                child: Text(item.answer),
              )
            ],
          );
        },
      ),
    );
  }
}

class Page2 extends StatelessWidget {
  final TextEditingController userController = TextEditingController();
  final TextEditingController passController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Stack(
        fit: StackFit.expand,
        children: [
          Image.network(
            'https://img.freepik.com/vector-gratis/fondo-abstracto-colorido_23-2148470833.jpg?semt=ais_hybrid&w=740',
            fit: BoxFit.cover,
          ),
          Center(
            child: Container(
              padding: EdgeInsets.all(25),
              width: 350,
              decoration: BoxDecoration(
                color: Colors.white.withOpacity(0.95),
                borderRadius: BorderRadius.circular(15),
                boxShadow: [
                  BoxShadow(
                    color: Colors.black.withOpacity(0.3),
                    blurRadius: 15,
                    offset: Offset(0, 8),
                  ),
                ],
              ),
              child: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  Image.network(
                    'https://us.123rf.com/450wm/tuktukdesign/tuktukdesign1608/tuktukdesign160800090/62073387-a%C3%B1adir-icono-de-usuario-hombre-cuenta-nueva-el-perfil-de-ilustraci%C3%B3n-vectorial-glifo.jpg',
                    height: 100,
                  ),
                  SizedBox(height: 15),
                  Text(
                    'Registro de Usuario',
                    style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
                  ),
                  SizedBox(height: 25),
                  TextField(
                    controller: userController,
                    decoration: InputDecoration(
                      labelText: 'Nuevo Usuario',
                      border: OutlineInputBorder(),
                    ),
                  ),
                  SizedBox(height: 15),
                  TextField(
                    controller: passController,
                    obscureText: true,
                    decoration: InputDecoration(
                      labelText: 'Nueva Contraseña',
                      border: OutlineInputBorder(),
                    ),
                  ),
                  SizedBox(height: 25),
                  ElevatedButton(
                    onPressed: () {
                      Navigator.pop(context); 
                    },
                    child: Text('Registrarme'),
                  ),
                  SizedBox(height: 15),
                  GestureDetector(
                    onTap: () {
                      Navigator.pop(context); 
                    },
                    child: Text(
                      '¿Ya tienes cuenta? Inicia sesión aquí',
                      style: TextStyle(
                        color: Colors.blue,
                        decoration: TextDecoration.underline,
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }
}

class Page3 extends StatelessWidget {
  const Page3({Key? key}) : super(key: key);

  static const double buttonFontSize = 24.0;
  static const double displayFontSize = 32.0;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: const Color.fromARGB(255, 226, 226, 226),
      appBar: AppBar(
        backgroundColor: Colors.blue,
        title: const Text('Calculadora'),
        leading: IconButton(
          icon: const Icon(Icons.arrow_back),
          onPressed: () {
            Navigator.pop(context);
          },
        ),
      ),
      body: Column(
        children: <Widget>[
          const SizedBox(height: 40.0),
          Container(
            padding: const EdgeInsets.only(right: 20.0),
            alignment: Alignment.centerRight,
            child: const Text(
              "8 x 4",
              style: TextStyle(
                fontSize: displayFontSize,
                fontWeight: FontWeight.bold,
                color: Color.fromARGB(232, 143, 141, 141),
              ),
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
                color: Color.fromARGB(255, 0, 0, 0),
              ),
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
                    fontSize: buttonFontSize,
                    color: Color.fromARGB(255, 0, 0, 0),
                  ),
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
    if (label == "AC" || label == "⌫" || label == "%" || label == "÷" || label == "-" || label == "+") {
      return const Color.fromARGB(255, 211, 211, 211);
    }
    return const Color.fromARGB(255, 247, 246, 246);
  }
}
