# 18-Week Dart & Flutter Curriculum: From Fundamentals to First Application

## HISTORY OF DART: Why Industry Needs This Language

### The Origin Story (2011)

**Dart was unveiled on October 10-12, 2011** at the GOTO conference in Aarhus, Denmark by **Lars Bak and Kasper Lund**, both renowned for their work on virtual machines and language design.

#### Why Google Created Dart

In the early 2010s, **JavaScript was showing critical limitations**:
- Poor performance for large, complex applications
- Lack of strong typing made large codebases hard to maintain
- Difficult to optimize for mobile and web platforms simultaneously
- Missing modern language features for scalable development

**Dart's Initial Mission**: Create a language that could:
- ✅ Improve on JavaScript's shortcomings
- ✅ Offer optional static typing without losing flexibility
- ✅ Scale from small scripts to massive applications
- ✅ Provide a more advanced virtual machine than existing interpreters
- ✅ Support both web and eventually mobile development

### Timeline of Evolution

| Version | Year | Major Changes |
|---------|------|---------------|
| **Dart 1.0** | November 2013 | First stable release; Initial web focus |
| **Dart 1.9** | 2015 | Web VM in Chrome plans dropped; Focus shifted to JavaScript compilation (dart2js) |
| **AngularDart** | 2016-2017 | Dart port of Angular framework for web development |
| **Dart 2.0** | August 2018 | **Major pivot**: Sound type system introduced; Focus shifted to **client-optimized development** |
| **Dart 2.6** | November 2019 | Native compilation support (Linux, macOS, Windows); Standalone executables |
| **Dart 3.0** | May 2023 | 100% sound null safety; Records & Patterns; WebAssembly compilation support |
| **Dart 3.4+** | 2024 | WebAssembly (WASM) support; Continued optimization for cross-platform development |

### Why Web Adoption Failed, Mobile Adoption Succeeded

**The Web Struggle (2011-2018):**
- ❌ Browsers rejected Dart VM in Chrome
- ❌ JavaScript evolved rapidly (ES6, TypeScript)
- ❌ Web community preferred established solutions
- ❌ Even Google's AngularDart couldn't compete

**The Mobile Revolution (2015-Present):**
- ✅ **Flutter introduced in 2015** as a UI toolkit
- ✅ Dart chosen for Flutter due to: fast hot reload, performant VM, excellent tooling
- ✅ Single codebase for iOS, Android, and Web
- ✅ Developer productivity skyrocketed with instant code changes
- ✅ Industry adoption exploded: Google Ads, Alibaba, Hamilton Musical app

### Why Industry Needs Dart Today

#### 1. **Cross-Platform Development (One Codebase, Multiple Platforms)**
```
Traditional Approach:
- Android → Java/Kotlin
- iOS → Swift
- Web → JavaScript/TypeScript
- Desktop → C#/.NET or C++

Dart/Flutter Approach:
- Android, iOS, Web, Windows, macOS, Linux → DART (ONE language!)
```
**Business Impact**: 40-60% reduction in development time, unified team, consistent behavior across platforms

#### 2. **Hot Reload: Development Speed**
Dart's Just-In-Time (JIT) compiler enables **sub-second hot reload**:
- See code changes instantly without restarting the app
- Stateful hot reload preserves app state during development
- Like a "cheetah during development, a race car in production" (JIT vs AOT compilation)

#### 3. **Performance & Compilation**
- **JIT (Just-In-Time)**: Development speed with optimization
- **AOT (Ahead-Of-Time)**: Production efficiency with native code compilation
- **WebAssembly**: Modern browser execution with better performance than JavaScript
- **Native Compilation**: Standalone executables without SDK dependency

#### 4. **Type Safety Without Verbosity**
```dart
// Best of both worlds
var x = 5;                           // Type inference
int count = 10;                      // Explicit typing
final String name = "John";          // Immutable with types
dynamic data = "anything";           // When needed

// Null Safety (Dart 3.0)
String notNull = "must have value";  // Compiler guarantees non-null
String? canBeNull = null;            // Explicitly nullable
```

#### 5. **Reactive Programming for UI**
- Native async/await for asynchronous operations
- Stream-based data flow (Futures, Streams)
- Perfect for real-time applications and responsive UIs
- Foundation for reactive state management (BLoC, Provider, Riverpod)

#### 6. **Industry Adoption & Success Stories**
- **Google**: Powers Google Ads, AdSense, critical revenue-generating applications
- **Alibaba**: Large-scale e-commerce platform
- **BMW**: Connected car applications
- **Tencent**: QQ, Weixin integrations
- **47% growth in Dart adoption** year-over-year

#### 7. **Unified Skill Set**
A Dart developer can build:
- ✅ Mobile apps (iOS & Android)
- ✅ Web applications (SPA, PWA)
- ✅ Desktop applications (Windows, macOS, Linux)
- ✅ Backend servers (Dart Frog, Aqueduct)
- ✅ Command-line tools

**Why This Matters**: In a competitive market, mastering Dart means you're not limited to one platform. You're a **full-stack, multi-platform developer**.

---

## 18-WEEK CURRICULUM: DART TO FLUTTER TO FIRST APPLICATION

### Curriculum Overview by Phase

```
PHASE 1: DART FOUNDATIONS (Weeks 1-6)
    ↓
PHASE 2: FLUTTER BASICS (Weeks 7-12)
    ↓
PHASE 3: ADVANCED CONCEPTS & REAL APP (Weeks 13-18)
```

---

## PHASE 1: DART FUNDAMENTALS (Weeks 1-6)

### **Week 1: Introduction & Environment Setup**

**Learning Objectives:**
- Understand Dart's purpose and relationship to Flutter
- Set up development environment
- Write and run first Dart program
- Understand basic Dart syntax

**Topics:**
1. **What is Dart?**
   - Compiled and interpreted language
   - Type-safe with null safety
   - Optimized for client-side development
   - Powers Flutter framework

2. **Setup & Installation**
   - Install Dart SDK (https://dart.dev/get-dart)
   - Install IDE: VS Code or Android Studio
   - Install Dart extensions
   - Verify installation: `dart --version`

3. **Your First Program**
   ```dart
   void main() {
     print('Hello, Dart!');
     var greeting = 'Welcome to Dart';
     print(greeting);
   }
   ```

4. **Running Dart Code**
   - `dart run` - Run from files
   - `dart compile js` - Compile to JavaScript
   - `dart compile exe` - Compile to native executable

**Hands-On Practice:**
- [ ] Install Dart SDK and verify
- [ ] Create hello_world.dart
- [ ] Run it and modify output
- [ ] Explore Dart documentation
- [ ] Set up your preferred IDE with Dart extensions

**Resources:**
- Official Dart Getting Started: https://dart.dev/guides/get-started
- Dart Playground: https://dartpad.dev (online IDE)

---

### **Week 2: Variables, Data Types & Operators**

**Learning Objectives:**
- Understand all Dart data types
- Master variable declaration patterns
- Learn operators and expressions
- Understand null safety

**Topics:**

1. **Variable Declaration Patterns**
   ```dart
   // Explicit type
   int age = 25;
   String name = "John";
   double height = 5.9;
   bool isStudent = true;
   
   // Type inference (var)
   var count = 10;                    // Inferred as int
   var message = "Hello";             // Inferred as String
   
   // Late initialization
   late String description;           // Declared but not initialized yet
   description = "Dart is awesome";   // Initialize later
   
   // Final & Const
   final String city = "Manila";      // Runtime constant
   const String country = "Philippines"; // Compile-time constant
   ```

2. **Null Safety (Dart 3.0)**
   ```dart
   // Non-nullable (default)
   String name = "John";              // Must always have value
   // name = null;                    // ❌ Compile error!
   
   // Nullable (explicit)
   String? nickname = null;           // Can be null
   if (nickname != null) {
     print(nickname.length);
   }
   
   // Null coalescing operator
   String displayName = nickname ?? "Guest";
   
   // Null-aware member access
   int? length = nickname?.length;    // Returns null if nickname is null
   ```

3. **All Data Types**
   ```dart
   // Numbers
   int count = 42;
   double price = 19.99;
   num dynamicNumber = 10; // Can be int or double
   
   // String
   String name = "Dart";
   String interpolation = "Language: $name";
   String multiline = '''This is
   a multiline
   string''';
   
   // Boolean
   bool isActive = true;
   
   // List (Array)
   List<int> numbers = [1, 2, 3, 4, 5];
   List<String> fruits = ["apple", "banana"];
   
   // Map (Dictionary)
   Map<String, int> ages = {
     "John": 25,
     "Jane": 28,
     "Bob": 30
   };
   
   // Set (Unique items)
   Set<String> colors = {"red", "blue", "green"};
   ```

4. **Operators**
   ```dart
   // Arithmetic
   int result = 10 + 5;    // 15
   int divided = 20 ~/ 3;  // 6 (integer division)
   
   // Comparison
   bool isGreater = 10 > 5;
   bool isEqual = "abc" == "abc";
   
   // Logical
   bool logicalAnd = true && false;   // false
   bool logicalOr = true || false;    // true
   
   // Assignment
   int x = 5;
   x += 3;  // x = x + 3
   
   // Type testing
   if (count is int) { }
   if (name is! null) { }
   ```

**Hands-On Practice:**
- [ ] Create variables with all data types
- [ ] Practice type inference with var
- [ ] Work with null safety: create nullable and non-nullable variables
- [ ] Perform calculations with operators
- [ ] Create a program that calculates BMI (requires taking numbers and computing)

**Small Project: Simple Calculator**
```dart
void main() {
  // Create a calculator that:
  // 1. Accepts two numbers
  // 2. Performs +, -, *, / operations
  // 3. Displays results with null safety
}
```

---

### **Week 3: Control Flow & Functions**

**Learning Objectives:**
- Master conditional statements (if/else, switch)
- Understand loops (for, while, do-while)
- Create and use functions with parameters
- Learn arrow functions and closures

**Topics:**

1. **Conditional Statements**
   ```dart
   // if-else
   int age = 20;
   if (age < 13) {
     print("Child");
   } else if (age < 18) {
     print("Teenager");
   } else {
     print("Adult");
   }
   
   // Ternary operator
   String status = age >= 18 ? "Adult" : "Minor";
   
   // switch-case
   String day = "Monday";
   switch (day) {
     case "Monday":
     case "Tuesday":
     case "Wednesday":
       print("Weekday");
       break;
     case "Saturday":
     case "Sunday":
       print("Weekend");
       break;
     default:
       print("Unknown");
   }
   ```

2. **Loops**
   ```dart
   // for loop
   for (int i = 0; i < 5; i++) {
     print(i);
   }
   
   // for-in loop
   List<String> fruits = ["Apple", "Banana", "Cherry"];
   for (String fruit in fruits) {
     print(fruit);
   }
   
   // forEach with arrow function
   fruits.forEach((fruit) => print(fruit));
   
   // while loop
   int counter = 0;
   while (counter < 5) {
     print(counter);
     counter++;
   }
   
   // do-while
   do {
     print(counter);
   } while (counter < 5);
   ```

3. **Functions**
   ```dart
   // Basic function
   void greet(String name) {
     print("Hello, $name!");
   }
   
   // Function with return type
   int add(int a, int b) {
     return a + b;
   }
   
   // Arrow function (single expression)
   int multiply(int a, int b) => a * b;
   
   // Optional parameters
   void introduce(String name, [String? hobby]) {
     print("$name likes ${hobby ?? "many things"}");
   }
   
   // Named parameters
   void createUser({
     required String name,
     required int age,
     String? email,
   }) {
     print("User: $name, Age: $age, Email: ${email ?? "N/A"}");
   }
   
   // Default values
   void repeatMessage(String message, {int times = 3}) {
     for (int i = 0; i < times; i++) {
       print(message);
     }
   }
   ```

4. **Higher-Order Functions**
   ```dart
   // Function as parameter
   void executeFunction(Function callback) {
     callback();
   }
   
   // Return function
   Function makeMultiplier(int factor) {
     return (int x) => x * factor;
   }
   
   // Map, filter, reduce
   List<int> numbers = [1, 2, 3, 4, 5];
   
   // Map: transform each element
   List<int> doubled = numbers.map((n) => n * 2).toList();
   
   // Where: filter elements
   List<int> evens = numbers.where((n) => n % 2 == 0).toList();
   
   // Reduce: accumulate to single value
   int sum = numbers.reduce((a, b) => a + b);
   ```

**Hands-On Practice:**
- [ ] Write programs using if-else and switch statements
- [ ] Create programs with all loop types
- [ ] Write functions with various parameter styles
- [ ] Use arrow functions and closures
- [ ] Practice map, filter, reduce operations

**Project: Grade Calculator**
```dart
// Input: List of test scores
// Process: Calculate average, letter grade
// Output: Display results with formatted message
```

---

### **Week 4: Object-Oriented Programming Part 1 (Classes & Objects)**

**Learning Objectives:**
- Understand class structure in Dart
- Create objects and work with properties
- Master constructors (including named and factory)
- Learn about access modifiers and encapsulation

**Topics:**

1. **Class Basics**
   ```dart
   class Person {
     // Properties
     String name;
     int age;
     
     // Constructor
     Person(this.name, this.age);
     
     // Method
     void introduce() {
       print("Hi, I'm $name and I'm $age years old.");
     }
   }
   
   // Creating objects
   var person1 = Person("John", 25);
   person1.introduce();
   ```

2. **Advanced Constructors**
   ```dart
   class Student {
     String name;
     int age;
     String grade;
     
     // Default constructor
     Student(this.name, this.age, this.grade);
     
     // Named constructor
     Student.fromJson(Map<String, dynamic> json)
       : name = json['name'],
         age = json['age'],
         grade = json['grade'];
     
     // Factory constructor
     factory Student.guest() {
       return Student("Guest", 0, "N/A");
     }
   }
   
   // Using constructors
   var student1 = Student("Alice", 20, "A");
   var student2 = Student.fromJson({"name": "Bob", "age": 21, "grade": "B"});
     var student3 = Student.guest();
   ```

3. **Properties & Getters/Setters**
   ```dart
   class BankAccount {
     String _accountNumber; // Private property (convention with _)
     double _balance = 0;
     
     BankAccount(this._accountNumber);
     
     // Getter
     double get balance => _balance;
     
     // Setter with validation
     set balance(double amount) {
       if (amount >= 0) {
         _balance = amount;
       }
     }
     
     void deposit(double amount) {
       balance = _balance + amount;
     }
   }
   ```

4. **Late Variables & Lazy Initialization**
   ```dart
   class Config {
     late String apiUrl;
     
     Config() {
       // Initialize later
       apiUrl = "https://api.example.com";
     }
   }
   ```

**Hands-On Practice:**
- [ ] Create a Car class with properties and methods
- [ ] Use named constructors
- [ ] Implement getters and setters
- [ ] Create private properties using underscore convention
- [ ] Build an object-based program (e.g., Library management system)

**Project: Student Management System**
```dart
// Create Student class with:
// - Properties: name, id, grades[]
// - Methods: addGrade(), calculateAverage()
// - Constructors: default, named
// 
// Create and manipulate multiple student objects
```

---

### **Week 5: Object-Oriented Programming Part 2 (Inheritance, Interfaces, Mixins)**

**Learning Objectives:**
- Understand inheritance and method overriding
- Use abstract classes and interfaces
- Apply mixins for code reuse
- Implement polymorphism

**Topics:**

1. **Inheritance**
   ```dart
   // Parent class
   class Animal {
     String name;
     
     Animal(this.name);
     
     void makeSound() {
       print("$name makes a sound");
     }
   }
   
   // Child class
   class Dog extends Animal {
     Dog(String name) : super(name);
     
     @override
     void makeSound() {
       print("$name barks: Woof!");
     }
     
     void fetch() {
       print("$name fetches the ball");
     }
   }
   
   // Usage
   var dog = Dog("Buddy");
   dog.makeSound();  // $name barks: Woof!
   dog.fetch();      // $name fetches the ball
   ```

2. **Abstract Classes**
   ```dart
   abstract class Shape {
     double getArea(); // Abstract method
     
     // Concrete method
     void printArea() {
       print("Area: ${getArea()}");
     }
   }
   
   class Circle extends Shape {
     double radius;
     
     Circle(this.radius);
     
     @override
     double getArea() => 3.14159 * radius * radius;
   }
   
   class Rectangle extends Shape {
     double width, height;
     
     Rectangle(this.width, this.height);
     
     @override
     double getArea() => width * height;
   }
   ```

3. **Interfaces (Implicit Interfaces)**
   ```dart
   class Bird {
     void fly() => print("Flying...");
   }
   
   // Any class can implement Bird's interface
   class Eagle implements Bird {
     @override
     void fly() => print("Eagle soars high!");
   }
   
   class Airplane implements Bird {
     @override
     void fly() => print("Airplane takes off!");
   }
   ```

4. **Mixins (Code Reuse)**
   ```dart
   mixin Flyer {
     void fly() => print("Flying...");
   }
   
   mixin Swimmer {
     void swim() => print("Swimming...");
   }
   
   class Duck with Flyer, Swimmer {
     String name;
     Duck(this.name);
   }
   
   var duck = Duck("Donald");
   duck.fly();      // From Flyer mixin
   duck.swim();     // From Swimmer mixin
   ```

5. **Polymorphism**
   ```dart
   List<Animal> animals = [
     Dog("Buddy"),
     Cat("Whiskers"),
     Parrot("Polly")
   ];
   
   // All animals respond differently
   for (var animal in animals) {
     animal.makeSound();
   }
   ```

**Hands-On Practice:**
- [ ] Create inheritance hierarchy (e.g., Vehicle → Car → SportsCar)
- [ ] Use abstract classes with multiple implementations
- [ ] Practice method overriding
- [ ] Create and use mixins
- [ ] Demonstrate polymorphism with collections

**Project: Zoo Management System**
```dart
// Abstract Animal class
// Concrete classes: Lion, Elephant, Penguin
// Each has unique behaviors
// Mixins: Swimmer, Flyer, Carnivore
// Create zoo with animals and simulate actions
```

---

### **Week 6: Asynchronous Programming & Error Handling**

**Learning Objectives:**
- Understand synchronous vs asynchronous code
- Master Futures and async/await
- Work with Streams
- Implement proper error handling
- Handle exceptions gracefully

**Topics:**

1. **Futures (Promises)**
   ```dart
   // Creating a Future
   Future<String> fetchUserName() {
     return Future.delayed(Duration(seconds: 2), () {
       return "John Doe";
     });
   }
   
   // Using Future.then()
   void getUserName() {
     fetchUserName().then((name) {
       print("Name: $name");
     });
   }
   
   // Chaining Futures
   fetchUserName()
     .then((name) => print("Got: $name"))
     .catchError((error) => print("Error: $error"))
     .whenComplete(() => print("Done!"));
   ```

2. **Async/Await (Modern Syntax)**
   ```dart
   // Making a function async
   Future<void> getUserInfo() async {
     try {
       String name = await fetchUserName();
       int age = await fetchUserAge();
       print("$name is $age years old");
     } catch (e) {
       print("Error: $e");
     } finally {
       print("User info retrieval completed");
     }
   }
   
   // Parallel execution
   Future<void> fetchMultiple() async {
     var results = await Future.wait([
       fetchUserName(),
       fetchUserAge(),
       fetchUserEmail()
     ]);
     print(results);
   }
   ```

3. **Streams (Continuous Async Data)**
   ```dart
   // Creating a Stream
   Stream<int> countStream() async* {
     for (int i = 1; i <= 5; i++) {
       await Future.delayed(Duration(seconds: 1));
       yield i; // Emit value
     }
   }
   
   // Listening to a Stream
   void listenToStream() {
     countStream().listen(
       (value) => print("Got: $value"),
       onError: (error) => print("Error: $error"),
       onDone: () => print("Stream finished")
     );
   }
   
   // Stream transformations
   countStream()
     .where((n) => n % 2 == 0)      // Only even numbers
     .map((n) => n * 2)             // Transform each value
     .listen((n) => print(n));
   ```

4. **Error Handling**
   ```dart
   // try-catch-finally
   void handleError() {
     try {
       String result = riskyOperation();
       print("Success: $result");
     } on FormatException catch (e) {
       print("Format error: $e");
     } on IOException catch (e) {
       print("IO error: $e");
     } catch (e) {
       print("Unknown error: $e");
     } finally {
       print("Cleanup code");
     }
   }
   
   // Custom exceptions
   class InvalidAgeException implements Exception {
     String message;
     InvalidAgeException(this.message);
     
     @override
     String toString() => message;
   }
   
   // Throwing exceptions
   void validateAge(int age) {
     if (age < 0) {
       throw InvalidAgeException("Age cannot be negative");
     }
   }
   ```

5. **Null Safety with Async**
   ```dart
   Future<String?> fetchOptionalValue() async {
     await Future.delayed(Duration(seconds: 1));
     return null; // Can return null
   }
   
   void processValue() async {
     String? value = await fetchOptionalValue();
     
     if (value != null) {
       print("Got: $value");
     } else {
       print("Value was null");
     }
   }
   ```

**Hands-On Practice:**
- [ ] Create and use Futures
- [ ] Convert callbacks to async/await
- [ ] Handle errors with try-catch
- [ ] Create and listen to Streams
- [ ] Implement parallel async operations
- [ ] Create custom exceptions

**Project: Weather App (Simulated)**
```dart
// Simulate fetching weather data (with delay)
// Use async/await to get: temperature, humidity, wind
// Handle errors (network, invalid location)
// Display formatted results
// Practice: Chain multiple async calls
```

---

## PHASE 2: FLUTTER BASICS (Weeks 7-12)

### **Week 7: Flutter Setup & Your First App**

**Learning Objectives:**
- Install Flutter SDK and configure environment
- Understand Flutter project structure
- Create first Flutter app
- Understand widgets and Material Design
- Run app on emulator/device

**Topics:**

1. **Flutter Installation**
   - Download Flutter SDK: https://flutter.dev/docs/get-started/install
   - Add Flutter to PATH
   - Verify: `flutter --version`
   - Install IDE extensions (VS Code or Android Studio)
   - Create emulator or connect device

2. **Flutter Project Structure**
   ```
   my_app/
   ├── android/          # Android native code
   ├── ios/              # iOS native code
   ├── lib/              # Dart code (main app)
   │   └── main.dart     # Entry point
   ├── test/             # Unit & widget tests
   ├── pubspec.yaml      # Dependencies
   └── pubspec.lock      # Locked versions
   ```

3. **First Flutter App**
   ```dart
   import 'package:flutter/material.dart';
   
   void main() {
     runApp(const MyApp());
   }
   
   class MyApp extends StatelessWidget {
     const MyApp({Key? key}) : super(key: key);
     
     @override
     Widget build(BuildContext context) {
       return MaterialApp(
         title: 'My First App',
         home: Scaffold(
           appBar: AppBar(
             title: const Text('Welcome to Flutter'),
           ),
           body: const Center(
             child: Text('Hello, Flutter!'),
           ),
         ),
       );
     }
   }
   ```

4. **Running Your App**
   - `flutter run` - Run on default device
   - `flutter run -d chrome` - Run on web
   - `flutter run -d windows` - Run on Windows desktop
   - Hot reload: Press 'r' in terminal

**Hands-On Practice:**
- [ ] Install Flutter and verify setup
- [ ] Create new Flutter project: `flutter create my_app`
- [ ] Run the default app
- [ ] Modify the app text
- [ ] Use hot reload to see changes instantly
- [ ] Run on multiple devices/platforms

---

### **Week 8: Widgets & Layout (Stateless Widgets)**

**Learning Objectives:**
- Understand Flutter widget hierarchy
- Master layout widgets (Container, Column, Row, Stack)
- Style widgets with properties
- Build responsive layouts
- Understand widget composition

**Topics:**

1. **Widget Fundamentals**
   ```dart
   // Stateless Widget - immutable, no state changes
   class GreetingCard extends StatelessWidget {
     final String name;
     final int age;
     
     const GreetingCard({
       Key? key,
       required this.name,
       required this.age,
     }) : super(key: key);
     
     @override
     Widget build(BuildContext context) {
       return Card(
         child: Padding(
           padding: const EdgeInsets.all(16.0),
           child: Column(
             children: [
               Text(
                 'Hello, $name!',
                 style: const TextStyle(fontSize: 24),
               ),
               Text('Age: $age'),
             ],
           ),
         ),
       );
     }
   }
   ```

2. **Layout Widgets**
   ```dart
   // Container - generic box with styling
   Container(
     width: 100,
     height: 100,
     color: Colors.blue,
     child: const Text('Box'),
   )
   
   // Column - vertical layout
   Column(
     children: [
       const Text('First'),
       const Text('Second'),
       const Text('Third'),
     ],
   )
   
   // Row - horizontal layout
   Row(
     mainAxisAlignment: MainAxisAlignment.spaceEvenly,
     children: const [
       Icon(Icons.home),
       Icon(Icons.settings),
       Icon(Icons.person),
     ],
   )
   
   // Stack - overlapping widgets
   Stack(
     children: [
       Container(color: Colors.blue),
       Positioned(
         top: 10,
         left: 10,
         child: Container(
           width: 50,
           height: 50,
           color: Colors.red,
         ),
       ),
     ],
   )
   ```

3. **Padding & Spacing**
   ```dart
   // Padding
   Padding(
     padding: const EdgeInsets.all(16.0),
     child: const Text('Padded text'),
   )
   
   // EdgeInsets variants
   EdgeInsets.all(8)           // Same on all sides
   EdgeInsets.symmetric(horizontal: 16, vertical: 8)
   EdgeInsets.only(top: 16, bottom: 16)
   
   // SizedBox for spacing
   Column(
     children: const [
       Text('First'),
       SizedBox(height: 16),
       Text('Second'),
     ],
   )
   ```

4. **Text & Typography**
   ```dart
   Text(
     'Hello Flutter',
     style: TextStyle(
       fontSize: 24,
       fontWeight: FontWeight.bold,
       color: Colors.blue,
       letterSpacing: 2.0,
     ),
   )
   ```

**Hands-On Practice:**
- [ ] Create layouts with Column and Row
- [ ] Practice alignment and spacing
- [ ] Build a profile card UI
- [ ] Create a dashboard-like layout
- [ ] Practice responsive design concepts

**Project: Profile Card UI**
```dart
// Display user profile with:
// - Name, email, bio
// - Profile image
// - Follow button
// - Social icons
// Use Column, Row, Container for layout
```

---

### **Week 9: User Input & Interactivity (Stateful Widgets)**

**Learning Objectives:**
- Understand state in Flutter
- Create Stateful widgets
- Handle user input (TextField, buttons)
- Manage state with setState()
- Build interactive UIs

**Topics:**

1. **Stateful Widgets**
   ```dart
   class Counter extends StatefulWidget {
     const Counter({Key? key}) : super(key: key);
     
     @override
     State<Counter> createState() => _CounterState();
   }
   
   class _CounterState extends State<Counter> {
     int count = 0;
     
     void _increment() {
       setState(() {
         count++;  // Notify Flutter to rebuild
       });
     }
     
     @override
     Widget build(BuildContext context) {
       return Column(
         children: [
           Text('Count: $count'),
           ElevatedButton(
             onPressed: _increment,
             child: const Text('Increment'),
           ),
         ],
       );
     }
   }
   ```

2. **Form & TextInput**
   ```dart
   class LoginForm extends StatefulWidget {
     const LoginForm({Key? key}) : super(key: key);
     
     @override
     State<LoginForm> createState() => _LoginFormState();
   }
   
   class _LoginFormState extends State<LoginForm> {
     final TextEditingController emailController = TextEditingController();
     final TextEditingController passwordController = TextEditingController();
     
     @override
     void dispose() {
       emailController.dispose();
       passwordController.dispose();
       super.dispose();
     }
     
     void _login() {
       String email = emailController.text;
       String password = passwordController.text;
       print('Login: $email');
     }
     
     @override
     Widget build(BuildContext context) {
       return Column(
         children: [
           TextField(
             controller: emailController,
             decoration: const InputDecoration(
               label: Text('Email'),
               hintText: 'Enter your email',
             ),
           ),
           TextField(
             controller: passwordController,
             obscureText: true,
             decoration: const InputDecoration(
               label: Text('Password'),
               hintText: 'Enter your password',
             ),
           ),
           ElevatedButton(
             onPressed: _login,
             child: const Text('Login'),
           ),
         ],
       );
     }
   }
   ```

3. **Interactive Widgets**
   ```dart
   // Checkbox
   Checkbox(
     value: isChecked,
     onChanged: (value) {
       setState(() {
         isChecked = value ?? false;
       });
     },
   )
   
   // Switch
   Switch(
     value: isEnabled,
     onChanged: (value) {
       setState(() {
         isEnabled = value;
       });
     },
   )
   
   // Slider
   Slider(
     value: sliderValue.toDouble(),
     min: 0,
     max: 100,
     onChanged: (value) {
       setState(() {
         sliderValue = value.toInt();
       });
     },
   )
   
   // DropdownButton
   DropdownButton<String>(
     value: selectedItem,
     items: ['Option 1', 'Option 2', 'Option 3']
       .map((String item) {
         return DropdownMenuItem(
           value: item,
           child: Text(item),
         );
       })
       .toList(),
     onChanged: (String? value) {
       setState(() {
         selectedItem = value;
       });
     },
   )
   ```

4. **GestureDetector for Custom Interactions**
   ```dart
   GestureDetector(
     onTap: () {
       print('Tapped!');
     },
     onLongPress: () {
       print('Long pressed!');
     },
     onDoubleTap: () {
       print('Double tapped!');
     },
     child: Container(
       width: 100,
       height: 100,
       color: Colors.blue,
     ),
   )
   ```

**Hands-On Practice:**
- [ ] Create a simple counter app with increment/decrement
- [ ] Build a form with multiple inputs
- [ ] Use CheckBox, Switch, Slider
- [ ] Handle button presses and update UI
- [ ] Practice setState() for state management

**Project: Todo List App (Basic)**
```dart
// Stateful widget that:
// - Accepts user input (todo text)
// - Displays list of todos
// - Mark todos as complete/incomplete
// - Delete todos
// - Use setState to update UI
```

---

### **Week 10: Navigation & Routing**

**Learning Objectives:**
- Understand Flutter routing systems
- Navigate between screens
- Pass data between routes
- Use named routes
- Handle back navigation

**Topics:**

1. **Basic Navigation (Push/Pop)**
   ```dart
   class HomeScreen extends StatelessWidget {
     const HomeScreen({Key? key}) : super(key: key);
     
     @override
     Widget build(BuildContext context) {
       return Scaffold(
         appBar: AppBar(title: const Text('Home')),
         body: Center(
           child: ElevatedButton(
             onPressed: () {
               // Navigate to DetailScreen
               Navigator.push(
                 context,
                 MaterialPageRoute(
                   builder: (context) => const DetailScreen(),
                 ),
               );
             },
             child: const Text('Go to Details'),
           ),
         ),
       );
     }
   }
   
   class DetailScreen extends StatelessWidget {
     const DetailScreen({Key? key}) : super(key: key);
     
     @override
     Widget build(BuildContext context) {
       return Scaffold(
         appBar: AppBar(
           title: const Text('Details'),
         ),
         body: Center(
           child: ElevatedButton(
             onPressed: () {
               // Go back
               Navigator.pop(context);
             },
             child: const Text('Back'),
           ),
         ),
       );
     }
   }
   ```

2. **Passing Data Between Screens**
   ```dart
   // Data object
   class Product {
     final int id;
     final String name;
     final double price;
     
     Product({
       required this.id,
       required this.name,
       required this.price,
     });
   }
   
   // Sending data
   Navigator.push(
     context,
     MaterialPageRoute(
       builder: (context) => ProductDetailScreen(
         product: Product(1, 'Laptop', 999.99),
       ),
     ),
   );
   
   // Receiving data
   class ProductDetailScreen extends StatelessWidget {
     final Product product;
     
     const ProductDetailScreen({required this.product});
     
     @override
     Widget build(BuildContext context) {
       return Scaffold(
         appBar: AppBar(title: Text(product.name)),
         body: Text('Price: \$${product.price}'),
       );
     }
   }
   
   // Getting return data
   final result = await Navigator.push<String>(
     context,
     MaterialPageRoute(
       builder: (context) => const SecondScreen(),
     ),
   );
   ```

3. **Named Routes**
   ```dart
   // Configure in main.dart
   MaterialApp(
     home: const HomeScreen(),
     routes: {
       '/details': (context) => const DetailScreen(),
       '/profile': (context) => const ProfileScreen(),
     },
   )
   
   // Navigate using route names
   Navigator.pushNamed(context, '/details');
   
   // With arguments
   Navigator.pushNamed(
     context,
     '/profile',
     arguments: userId,
   );
   
   // Receive arguments
   final userId = ModalRoute.of(context)!.settings.arguments as String;
   ```

**Hands-On Practice:**
- [ ] Create multiple screen apps
- [ ] Navigate between screens using push/pop
- [ ] Pass data to different screens
- [ ] Use named routes
- [ ] Handle back button behavior
- [ ] Create a multi-screen app (e.g., product catalog)

**Project: Multi-Screen Shopping App**
```dart
// Screens:
// 1. HomeScreen - list of products
// 2. ProductDetailScreen - details of selected product
// 3. CartScreen - shopping cart
//
// Navigation:
// - From Home to Details (with product data)
// - From Details to Cart
// - Back navigation
// - Pass selected items through navigation
```

---

### **Week 11: Lists & Data Display**

**Learning Objectives:**
- Display lists of data efficiently
- Use ListView and GridView
- Handle large datasets with lazy loading
- Display complex data with custom widgets
- Implement search and filter

**Topics:**

1. **ListView - Scrollable Lists**
   ```dart
   // Simple list
   ListView(
     children: [
       ListTile(
         title: const Text('Item 1'),
         subtitle: const Text('Subtitle'),
       ),
       ListTile(
         title: const Text('Item 2'),
       ),
     ],
   )
   
   // ListView.builder - for dynamic/large lists
   ListView.builder(
     itemCount: items.length,
     itemBuilder: (context, index) {
       return ListTile(
         title: Text(items[index].title),
         subtitle: Text(items[index].description),
         onTap: () {
           // Handle item tap
         },
       );
     },
   )
   ```

2. **GridView - Grid Layouts**
   ```dart
   // GridView.count
   GridView.count(
     crossAxisCount: 2,  // 2 columns
     childAspectRatio: 1.0,
     children: [
       Card(child: const Text('Item 1')),
       Card(child: const Text('Item 2')),
       Card(child: const Text('Item 3')),
       Card(child: const Text('Item 4')),
     ],
   )
   
   // GridView.builder - for dynamic grids
   GridView.builder(
     gridDelegate: const SliverGridDelegateWithFixedCrossAxisCount(
       crossAxisCount: 3,
     ),
     itemCount: products.length,
     itemBuilder: (context, index) {
       return Card(
         child: Column(
           children: [
             Image.asset(products[index].image),
             Text(products[index].name),
           ],
         ),
       );
     },
   )
   ```

3. **Custom List Items**
   ```dart
   class ProductCard extends StatelessWidget {
     final Product product;
     final VoidCallback onTap;
     
     const ProductCard({
       required this.product,
       required this.onTap,
     });
     
     @override
     Widget build(BuildContext context) {
       return Card(
         child: InkWell(
           onTap: onTap,
           child: Padding(
             padding: const EdgeInsets.all(8.0),
             child: Column(
               crossAxisAlignment: CrossAxisAlignment.start,
               children: [
                 Image.network(product.imageUrl),
                 Text(
                   product.name,
                   style: const TextStyle(
                     fontSize: 18,
                     fontWeight: FontWeight.bold,
                   ),
                 ),
                 Text('\$${product.price}'),
               ],
             ),
           ),
         ),
       );
     }
   }
   ```

4. **Search & Filter**
   ```dart
   class ProductList extends StatefulWidget {
     const ProductList({Key? key}) : super(key: key);
     
     @override
     State<ProductList> createState() => _ProductListState();
   }
   
   class _ProductListState extends State<ProductList> {
     List<Product> allProducts = [...];
     List<Product> filteredProducts = [...];
     
     void _filterProducts(String query) {
       setState(() {
         filteredProducts = allProducts
           .where((product) =>
             product.name.toLowerCase().contains(query.toLowerCase())
           )
           .toList();
       });
     }
     
     @override
     Widget build(BuildContext context) {
       return Column(
         children: [
           TextField(
             onChanged: _filterProducts,
             decoration: const InputDecoration(
               hintText: 'Search products',
               prefixIcon: Icon(Icons.search),
             ),
           ),
           Expanded(
             child: ListView.builder(
               itemCount: filteredProducts.length,
               itemBuilder: (context, index) {
                 return ListTile(
                   title: Text(filteredProducts[index].name),
                 );
               },
             ),
           ),
         ],
       );
     }
   }
   ```

**Hands-On Practice:**
- [ ] Display lists using ListView.builder
- [ ] Create GridView layouts
- [ ] Build custom list item widgets
- [ ] Implement search functionality
- [ ] Handle item tap events
- [ ] Display real-world data (products, users, posts)

**Project: Product Catalog App**
```dart
// Features:
// - ListView of products
// - Search/filter products
// - Tap to view details (navigate)
// - Display prices and images
// - Handle empty states
```

---

### **Week 12: API Integration & Networking**

**Learning Objectives:**
- Fetch data from REST APIs
- Handle JSON parsing
- Manage API responses and errors
- Use http package
- Implement loading states

**Topics:**

1. **HTTP Package Setup**
   ```yaml
   # In pubspec.yaml
   dependencies:
     flutter:
       sdk: flutter
     http: ^1.1.0
   ```

2. **Fetching Data from API**
   ```dart
   import 'package:http/http.dart' as http;
   import 'dart:convert';
   
   // Define model class
   class Post {
     final int id;
     final String title;
     final String body;
     
     Post({
       required this.id,
       required this.title,
       required this.body,
     });
     
     // JSON to Dart object
     factory Post.fromJson(Map<String, dynamic> json) {
       return Post(
         id: json['id'],
         title: json['title'],
         body: json['body'],
       );
     }
   }
   
   // Fetch function
   Future<List<Post>> fetchPosts() async {
     final response = await http.get(
       Uri.parse('https://jsonplaceholder.typicode.com/posts'),
     );
     
     if (response.statusCode == 200) {
       List<dynamic> jsonList = jsonDecode(response.body);
       return jsonList
         .map((json) => Post.fromJson(json))
         .toList();
     } else {
       throw Exception('Failed to load posts');
     }
   }
   ```

3. **Display API Data with FutureBuilder**
   ```dart
   class PostsList extends StatelessWidget {
     const PostsList({Key? key}) : super(key: key);
     
     @override
     Widget build(BuildContext context) {
       return FutureBuilder<List<Post>>(
         future: fetchPosts(),
         builder: (context, snapshot) {
           // Loading state
           if (snapshot.connectionState == ConnectionState.waiting) {
             return const Center(child: CircularProgressIndicator());
           }
           
           // Error state
           if (snapshot.hasError) {
             return Center(child: Text('Error: ${snapshot.error}'));
           }
           
           // Success state
           if (!snapshot.hasData || snapshot.data!.isEmpty) {
             return const Center(child: Text('No posts found'));
           }
           
           return ListView.builder(
             itemCount: snapshot.data!.length,
             itemBuilder: (context, index) {
               Post post = snapshot.data![index];
               return Card(
                 child: ListTile(
                   title: Text(post.title),
                   subtitle: Text(post.body),
                 ),
               );
             },
           );
         },
       );
     }
   }
   ```

4. **POST Requests (Sending Data)**
   ```dart
   Future<void> createPost(String title, String body) async {
     final response = await http.post(
       Uri.parse('https://jsonplaceholder.typicode.com/posts'),
       headers: {'Content-Type': 'application/json'},
       body: jsonEncode({
         'title': title,
         'body': body,
         'userId': 1,
       }),
     );
     
     if (response.statusCode == 201) {
       print('Post created successfully');
     } else {
       throw Exception('Failed to create post');
     }
   }
   ```

5. **Error Handling in Network Requests**
   ```dart
   Future<List<Post>> fetchPostsSafely() async {
     try {
       final response = await http
         .get(Uri.parse('https://jsonplaceholder.typicode.com/posts'))
         .timeout(const Duration(seconds: 10));
       
       if (response.statusCode == 200) {
         List<dynamic> jsonList = jsonDecode(response.body);
         return jsonList
           .map((json) => Post.fromJson(json))
           .toList();
       } else if (response.statusCode == 404) {
         throw Exception('Resource not found');
       } else if (response.statusCode == 500) {
         throw Exception('Server error');
       } else {
         throw Exception('Failed to load posts: ${response.statusCode}');
       }
     } on SocketException catch (_) {
       throw Exception('No internet connection');
     } on TimeoutException catch (_) {
       throw Exception('Request timeout');
     } catch (e) {
       throw Exception('Error: $e');
     }
   }
   ```

**Hands-On Practice:**
- [ ] Fetch data from public API (JSONPlaceholder, OpenWeather, etc.)
- [ ] Parse JSON responses
- [ ] Use FutureBuilder for loading states
- [ ] Handle errors gracefully
- [ ] Send POST requests
- [ ] Implement timeout and retry logic

**Project: News App**
```dart
// Using: https://newsapi.org (free tier)
// Features:
// - Fetch latest news articles
// - Display articles in list
// - Show loading state
// - Handle errors
// - Tap article to view details
// - Implement refresh functionality
```

---

## PHASE 3: ADVANCED CONCEPTS & BUILDING YOUR FIRST APP (Weeks 13-18)

### **Week 13: State Management Fundamentals**

**Learning Objectives:**
- Understand state management challenges
- Learn Provider package (easiest for beginners)
- Implement app-wide state
- Lift state up architecture pattern
- Manage local vs global state

**Topics:**

1. **Understanding State Management Problem**
   ```dart
   // Problem: Passing data through many widgets
   // MyApp → HomeScreen → UserCard → UserName
   // This becomes unmaintainable with complex apps
   ```

2. **Provider Package Setup**
   ```yaml
   # pubspec.yaml
   dependencies:
     provider: ^6.0.0
   ```

3. **Simple ChangeNotifier + Provider**
   ```dart
   // Model class
   class CartModel extends ChangeNotifier {
     List<Product> _items = [];
     
     List<Product> get items => _items;
     
     double get total => _items.fold(
       0,
       (sum, item) => sum + item.price,
     );
     
     void addItem(Product product) {
       _items.add(product);
       notifyListeners();
     }
     
     void removeItem(Product product) {
       _items.remove(product);
       notifyListeners();
     }
   }
   
   // Setup in main.dart
   void main() {
     runApp(
       ChangeNotifierProvider(
         create: (context) => CartModel(),
         child: const MyApp(),
       ),
     );
   }
   
   // Use in widgets
   class CartScreen extends StatelessWidget {
     const CartScreen({Key? key}) : super(key: key);
     
     @override
     Widget build(BuildContext context) {
       // Rebuild only when CartModel changes
       return Consumer<CartModel>(
         builder: (context, cart, child) {
           return Column(
             children: [
               Text('Total: \$${cart.total}'),
               ListView.builder(
                 itemCount: cart.items.length,
                 itemBuilder: (context, index) {
                   return ListTile(
                     title: Text(cart.items[index].name),
                   );
                 },
               ),
             ],
           );
         },
       );
     }
   }
   ```

4. **Multiple Providers**
   ```dart
   MultiProvider(
     providers: [
       ChangeNotifierProvider(create: (_) => CartModel()),
       ChangeNotifierProvider(create: (_) => UserModel()),
       ChangeNotifierProvider(create: (_) => ThemeModel()),
     ],
     child: const MyApp(),
   )
   ```

**Hands-On Practice:**
- [ ] Create a ChangeNotifier model
- [ ] Set up Provider in main.dart
- [ ] Use Consumer to rebuild widgets
- [ ] Manage app-wide state
- [ ] Create multiple providers

---

### **Week 14: Advanced Widgets & Animations**

**Learning Objectives:**
- Use advanced widgets (Hero, AnimatedContainer, etc.)
- Implement animations
- Create smooth transitions
- Use AnimationController
- Build interactive animated UIs

**Topics:**

1. **Hero Animation (Shared Element)**
   ```dart
   // Source screen
   Hero(
     tag: 'product-${product.id}',
     child: GestureDetector(
       onTap: () {
         Navigator.push(context, MaterialPageRoute(
           builder: (context) => ProductDetailScreen(product: product),
         ));
       },
       child: Image.network(product.imageUrl),
     ),
   )
   
   // Destination screen
   Hero(
     tag: 'product-${product.id}',
     child: Image.network(product.imageUrl),
   )
   ```

2. **AnimatedContainer**
   ```dart
   class ColorChangeContainer extends StatefulWidget {
     @override
     State<ColorChangeContainer> createState() => _ColorChangeContainerState();
   }
   
   class _ColorChangeContainerState extends State<ColorChangeContainer> {
     bool isExpanded = false;
     
     @override
     Widget build(BuildContext context) {
       return GestureDetector(
         onTap: () {
           setState(() {
             isExpanded = !isExpanded;
           });
         },
         child: AnimatedContainer(
           duration: const Duration(milliseconds: 300),
           width: isExpanded ? 200 : 100,
           height: isExpanded ? 200 : 100,
           color: isExpanded ? Colors.blue : Colors.red,
         ),
       );
     }
   }
   ```

3. **Custom Animations with AnimationController**
   ```dart
   class FadeInText extends StatefulWidget {
     final String text;
     
     const FadeInText(this.text);
     
     @override
     State<FadeInText> createState() => _FadeInTextState();
   }
   
   class _FadeInTextState extends State<FadeInText>
     with SingleTickerProviderStateMixin {
     late AnimationController _controller;
     late Animation<double> _opacity;
     
     @override
     void initState() {
       super.initState();
       _controller = AnimationController(
         duration: const Duration(seconds: 2),
         vsync: this,
       );
       
       _opacity = Tween<double>(begin: 0, end: 1).animate(_controller);
       _controller.forward();
     }
     
     @override
     void dispose() {
       _controller.dispose();
       super.dispose();
     }
     
     @override
     Widget build(BuildContext context) {
       return FadeTransition(
         opacity: _opacity,
         child: Text(widget.text),
       );
     }
   }
   ```

**Hands-On Practice:**
- [ ] Implement Hero animations
- [ ] Use AnimatedContainer
- [ ] Create custom animations
- [ ] Build animated page transitions
- [ ] Create loading animations

---

### **Week 15: Database & Local Storage**

**Learning Objectives:**
- Persist data locally
- Use SQLite with sqflite package
- Implement CRUD operations
- Manage data locally
- Understand migrations

**Topics:**

1. **SharedPreferences (Simple Key-Value)**
   ```yaml
   # pubspec.yaml
   dependencies:
     shared_preferences: ^2.0.0
   ```

   ```dart
   import 'package:shared_preferences/shared_preferences.dart';
   
   // Save data
   void saveUserName(String name) async {
     final prefs = await SharedPreferences.getInstance();
     await prefs.setString('user_name', name);
   }
   
   // Load data
   Future<String?> loadUserName() async {
     final prefs = await SharedPreferences.getInstance();
     return prefs.getString('user_name');
   }
   ```

2. **SQLite with sqflite**
   ```yaml
   dependencies:
     sqflite: ^2.0.0
   ```

   ```dart
   import 'package:sqflite/sqflite.dart';
   
   class DatabaseHelper {
     static const String tableTodo = 'todos';
     
     Future<Database> initDB() async {
       String path = await getDatabasesPath();
       return openDatabase(
         '$path/app.db',
         version: 1,
         onCreate: (db, version) async {
           await db.execute('''
             CREATE TABLE $tableTodo (
               id INTEGER PRIMARY KEY AUTOINCREMENT,
               title TEXT NOT NULL,
               description TEXT,
               isCompleted INTEGER DEFAULT 0
             )
           ''');
         },
       );
     }
     
     // Create
     Future<int> insertTodo(Todo todo) async {
       final db = await initDB();
       return db.insert(tableTodo, todo.toMap());
     }
     
     // Read
     Future<List<Todo>> getTodos() async {
       final db = await initDB();
       final List<Map<String, dynamic>> maps = 
         await db.query(tableTodo);
       return List.generate(maps.length, (i) {
         return Todo.fromMap(maps[i]);
       });
     }
     
     // Update
     Future<int> updateTodo(Todo todo) async {
       final db = await initDB();
       return db.update(tableTodo, todo.toMap(),
         where: 'id = ?',
         whereArgs: [todo.id],
       );
     }
     
     // Delete
     Future<int> deleteTodo(int id) async {
       final db = await initDB();
       return db.delete(tableTodo, where: 'id = ?', whereArgs: [id]);
     }
   }
   ```

**Hands-On Practice:**
- [ ] Save and load simple data with SharedPreferences
- [ ] Create SQLite database
- [ ] Implement CRUD operations
- [ ] Build a persisted Todo app
- [ ] Handle database queries

---

### **Week 16: Building Your First Complete Application - Todo App (Part 1)**

**Learning Objectives:**
- Combine all learned concepts
- Build a complete, functional application
- Implement user stories
- Handle all CRUD operations
- Create polished UI

**Project: Advanced Todo List Application**

**Features to Implement:**
1. ✅ Add todo items
2. ✅ Display todos in a list
3. ✅ Mark as complete/incomplete
4. ✅ Edit existing todos
5. ✅ Delete todos
6. ✅ Persist to local database
7. ✅ Search/filter todos
8. ✅ Categories for todos
9. ✅ Due dates
10. ✅ Priority levels

**Architecture Plan:**
```
lib/
├── main.dart                 # Entry point
├── models/
│   └── todo.dart            # Todo data model
├── screens/
│   ├── home_screen.dart     # Main todo list
│   └── todo_detail_screen.dart  # Add/edit todo
├── widgets/
│   ├── todo_item.dart       # Reusable todo card
│   └── todo_form.dart       # Add/edit form
├── database/
│   └── database_helper.dart # SQLite operations
└── providers/
    └── todo_provider.dart   # State management
```

**Week 16 Tasks:**
1. [ ] Create data models
2. [ ] Set up database layer
3. [ ] Create home screen UI
4. [ ] Implement add todo functionality
5. [ ] Implement edit todo functionality
6. [ ] Implement delete functionality
7. [ ] Connect UI to database
8. [ ] Test all CRUD operations

**Code Structure (Starter):**

```dart
// models/todo.dart
class Todo {
  final int? id;
  final String title;
  final String description;
  final String category;
  final DateTime dueDate;
  final int priority; // 1-3: low, medium, high
  final bool isCompleted;
  
  Todo({
    this.id,
    required this.title,
    required this.description,
    required this.category,
    required this.dueDate,
    required this.priority,
    this.isCompleted = false,
  });
  
  Map<String, dynamic> toMap() {
    return {
      'id': id,
      'title': title,
      'description': description,
      'category': category,
      'dueDate': dueDate.toIso8601String(),
      'priority': priority,
      'isCompleted': isCompleted ? 1 : 0,
    };
  }
  
  factory Todo.fromMap(Map<String, dynamic> map) {
    return Todo(
      id: map['id'],
      title: map['title'],
      description: map['description'],
      category: map['category'],
      dueDate: DateTime.parse(map['dueDate']),
      priority: map['priority'],
      isCompleted: map['isCompleted'] == 1,
    );
  }
}

// providers/todo_provider.dart
class TodoProvider extends ChangeNotifier {
  List<Todo> _todos = [];
  final DatabaseHelper _db = DatabaseHelper();
  
  List<Todo> get todos => _todos;
  
  Future<void> loadTodos() async {
    _todos = await _db.getTodos();
    notifyListeners();
  }
  
  Future<void> addTodo(Todo todo) async {
    await _db.insertTodo(todo);
    await loadTodos();
  }
  
  Future<void> updateTodo(Todo todo) async {
    await _db.updateTodo(todo);
    await loadTodos();
  }
  
  Future<void> deleteTodo(int id) async {
    await _db.deleteTodo(id);
    await loadTodos();
  }
}

// main.dart
void main() {
  runApp(
    ChangeNotifierProvider(
      create: (_) => TodoProvider(),
      child: const MyApp(),
    ),
  );
}
```

---

### **Week 17: Building Your First Complete Application - Todo App (Part 2)**

**Learning Objectives:**
- Complete the Todo application
- Implement advanced features
- Polish UI/UX
- Add error handling
- Optimize performance

**Week 17 Tasks:**
1. [ ] Implement search/filter functionality
2. [ ] Add category management
3. [ ] Implement sorting (by date, priority)
4. [ ] Add animations and transitions
5. [ ] Implement validation
6. [ ] Add empty state UI
7. [ ] Polish animations and transitions
8. [ ] Test thoroughly

**Additional Features:**
- [ ] Category selector in add/edit form
- [ ] Due date picker
- [ ] Priority selector
- [ ] Filter by category
- [ ] Sort by due date or priority
- [ ] Beautiful empty state
- [ ] Success/error notifications
- [ ] Confirmation dialogs for delete

**UI Polish:**
- [ ] Smooth transitions between screens
- [ ] Loading animations
- [ ] Error messages
- [ ] Success confirmations
- [ ] Responsive layout
- [ ] Dark mode support (if time permits)

---

### **Week 18: Testing, Deployment & Publishing**

**Learning Objectives:**
- Write unit and widget tests
- Debug and optimize app
- Prepare for release
- Handle edge cases
- Package and distribute

**Topics:**

1. **Widget Testing**
   ```dart
   import 'package:flutter_test/flutter_test.dart';
   
   void main() {
     testWidgets('TodoItem displays title', (WidgetTester tester) async {
       // Build app and trigger a frame
       await tester.pumpWidget(
         MaterialApp(
           home: Scaffold(
             body: TodoItem(
               todo: Todo(
                 id: 1,
                 title: 'Test Todo',
                 description: 'Test',
                 category: 'Work',
                 dueDate: DateTime.now(),
                 priority: 1,
               ),
             ),
           ),
         ),
       );
       
       // Verify
       expect(find.text('Test Todo'), findsOneWidget);
     });
   }
   ```

2. **Unit Testing**
   ```dart
   void main() {
     group('Todo Model', () {
       test('Todo.toMap() creates correct map', () {
         final todo = Todo(
           id: 1,
           title: 'Test',
           description: 'Test description',
           category: 'Work',
           dueDate: DateTime(2024, 12, 25),
           priority: 1,
         );
         
         expect(todo.toMap()['title'], 'Test');
         expect(todo.toMap()['priority'], 1);
       });
     });
   }
   ```

3. **Build for Release**
   ```bash
   # Android
   flutter build apk --release
   flutter build appbundle --release
   
   # iOS
   flutter build ios --release
   
   # Web
   flutter build web --release
   
   # Windows/macOS
   flutter build windows --release
   flutter build macos --release
   ```

4. **Publishing Checklist**
   - [ ] Update app version in pubspec.yaml
   - [ ] Update app icon and splash screen
   - [ ] Write app description
   - [ ] Create privacy policy
   - [ ] Add screenshots
   - [ ] Test thoroughly on multiple devices
   - [ ] Handle all edge cases
   - [ ] Optimize for performance
   - [ ] Review code quality
   - [ ] Document code

**Week 18 Tasks:**
1. [ ] Write unit tests
2. [ ] Write widget tests
3. [ ] Debug and fix issues
4. [ ] Optimize performance
5. [ ] Create app icon
6. [ ] Set up app metadata
7. [ ] Build for release
8. [ ] Test release build
9. [ ] Create documentation
10. [ ] Prepare for publication

---

## LEARNING RESOURCES SUMMARY

### Official Documentation
- **Dart**: https://dart.dev/guides
- **Flutter**: https://flutter.dev/docs
- **Provider Package**: https://pub.dev/packages/provider

### Recommended Packages
- `http` - Network requests
- `provider` - State management
- `sqflite` - Local database
- `shared_preferences` - Key-value storage
- `intl` - Internationalization & date formatting
- `connectivity` - Network connectivity
- `image_picker` - Image selection
- `firebase_core` + `cloud_firestore` - Backend (optional)

### Practice Platforms
- **DartPad**: https://dartpad.dev (online Dart IDE)
- **GitHub**: Share and learn from real projects
- **Stack Overflow**: Dart & Flutter community

### Tips for Success
1. **Code Along**: Type code, don't copy-paste
2. **Build Projects**: Theory + practice together
3. **Read Error Messages**: They guide you to solutions
4. **Use Hot Reload**: Experiment quickly
5. **Debug Print**: Use `print()` and Flutter DevTools
6. **Join Communities**: Flutter Discord, Reddit, local meetups
7. **Review Code**: Read others' code on GitHub
8. **Build Incrementally**: Small features → complete app

---

## Conclusion

By completing this 18-week curriculum, you will:

✅ Master Dart fundamentals including OOP, async programming, and null safety
✅ Learn Flutter from basic widgets to advanced patterns
✅ Understand state management and how to structure apps
✅ Build a complete, functional application from scratch
✅ Know how to fetch data from APIs, work with databases, and handle errors
✅ Be ready to publish apps to app stores

**Most importantly**: You'll understand not just *how* to build Flutter apps, but *why* Dart and Flutter matter to the industry. You'll be equipped to build cross-platform applications for millions of users.

The industry needs developers who can:
- Build iOS, Android, Web, and Desktop from one codebase
- Deliver products quickly with hot reload
- Write safe, type-checked code
- Scale from startup prototypes to enterprise applications

This 18-week journey prepares you to be exactly that developer.

---

**Happy Learning! 🚀**
