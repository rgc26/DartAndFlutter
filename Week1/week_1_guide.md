# WEEK 1: Introduction & Environment Setup
## Comprehensive Guide with Full Details and Sources

---

## 📋 WEEK 1 OVERVIEW

**Duration:** 5-7 days of study  
**Time Commitment:** 10-15 hours total  
**Difficulty Level:** Beginner (No prior Dart experience needed)

### Learning Outcomes
By the end of Week 1, you will:
- ✅ Understand what Dart is and how it relates to Flutter
- ✅ Successfully install Dart SDK on your operating system
- ✅ Set up an IDE with Dart extensions
- ✅ Run your first Dart program
- ✅ Understand basic Dart syntax and the `main()` function
- ✅ Use the `print()` function
- ✅ Declare variables and understand type inference
- ✅ Verify installation and troubleshoot common issues

---

## PART 1: UNDERSTANDING DART

### 1.1 What is Dart? (Learn the Basics)

#### Definition
**Dart is a client-optimized, general-purpose programming language developed by Google.**[17][23]

Dart is an open-source language that supports application development on both client (mobile, web, desktop) and server sides. However, it is primarily optimized and widely used for the development of:
- 📱 Android apps
- 📱 iOS apps  
- 🌐 Web applications (using Flutter framework)
- 💻 Desktop applications (Windows, macOS, Linux)
- 🏗️ Backend applications
- 🛠️ IoT (Internet of Things) applications[20]

#### Why Dart Was Created (Historical Context)

**Creation Date & Location:** Dart was unveiled on October 10-12, 2011, at the GOTO conference in Aarhus, Denmark by **Lars Bak and Kasper Lund**, both renowned for their work on virtual machines and language design.

**Problem It Solved:**
In the early 2010s, JavaScript had critical limitations for large-scale applications:
- ❌ Poor performance on complex applications
- ❌ Lack of strong typing made large codebases hard to maintain
- ❌ Difficult to optimize for both mobile and web simultaneously
- ❌ Missing modern language features for scalable development

**Dart's Initial Goals:**
- ✅ Improve upon JavaScript's shortcomings
- ✅ Offer optional static typing without losing flexibility
- ✅ Scale from small scripts to massive applications
- ✅ Provide a more advanced virtual machine than existing JavaScript interpreters
- ✅ Support both web and eventually mobile development[1]

#### Evolution of Dart (Timeline)

| Version | Year | Major Changes | Source |
|---------|------|---------------|--------|
| **Dart 1.0** | November 2013 | First stable release; Initial focus on web development | Official Dart Evolution[13] |
| **Dart 1.9** | 2015 | Web VM in Chrome dropped; Focus shifted to JavaScript compilation (dart2js) | Official Dart Evolution[13] |
| **AngularDart** | 2016-2017 | Dart port of Angular framework for web development | Official Dart Evolution[13] |
| **Dart 2.0** | August 2018 | **Major pivot**: Sound type system introduced; Focus shifted to "client-optimized development" | Official Dart Evolution[13] |
| **Dart 2.6** | November 2019 | Native compilation support (Linux, macOS, Windows); Standalone executables | Official Dart Evolution[13] |
| **Dart 3.0** | May 2023 | 100% sound null safety; Records & Patterns; WebAssembly compilation support | Official Dart Evolution[13] |
| **Dart 3.4+** | 2024 | WebAssembly (WASM) support; Continued optimization for cross-platform development | Official Dart SDK[24] |

#### Current Dart Version (January 2026)
- **Latest Stable:** Dart 3.10.3 (as of documentation refresh date)
- **Release Cadence:** New stable release approximately every 3 months[24]

### 1.2 Dart vs Other Languages: Why Choose Dart?

#### Dart vs JavaScript
```
╔═════════════════════════════════════════════════════════════════╗
║ Why Dart is Better than JavaScript for Large Applications[2]    ║
╠═════════════════════════════════════════════════════════════════╣
║ Feature              │ Dart         │ JavaScript              ║
╠──────────────────────┼──────────────┼─────────────────────────╣
║ Type Safety          │ ✅ Strong    │ ❌ Weak (TypeScript)    ║
║ Compilation          │ ✅ Both JIT  │ ❌ Interpreted only     ║
║                      │    & AOT     │                         ║
║ Performance          │ ✅ Fast      │ ⚠️  Variable            ║
║ Null Safety          │ ✅ Built-in  │ ❌ No (prone to errors) ║
║ Tooling              │ ✅ Excellent │ ⚠️  Growing             ║
║ Learning Curve       │ ✅ Moderate  │ ✅ Moderate             ║
╚═════════════════════════════════════════════════════════════════╝
```

#### Dart vs C++/Java
Dart is much simpler than C++ or Java while maintaining type safety:
- 🎯 **Less Verbose:** Dart code is more concise
- ⚡ **Faster Development:** Simpler syntax, less boilerplate
- 📱 **Mobile-Optimized:** Designed from ground up for mobile
- 🔄 **Hot Reload:** Change code without restarting (not in C++/Java)
- 🌐 **Cross-Platform:** One language for multiple platforms

### 1.3 Why Industry Needs Dart Today

#### 1️⃣ One Codebase for Multiple Platforms
```
Traditional Approach:
┌────────────────────────────────────────┐
│ iOS → Swift                            │
│ Android → Java/Kotlin                  │
│ Web → JavaScript/TypeScript            │
│ Desktop → C#/.NET or C++               │
│ Total: 4 different languages/codebases │
└────────────────────────────────────────┘

Dart/Flutter Approach:
┌────────────────────────────────────────┐
│ iOS, Android, Web, Windows,            │
│ macOS, Linux → ALL DART                │
│ Total: 1 language/codebase             │
│ Cost Savings: 40-60% development time  │
└────────────────────────────────────────┘
```

#### 2️⃣ Hot Reload: Sub-Second Development Speed
Dart's Just-In-Time (JIT) compiler enables **instant code reload**:
- 🔄 See code changes in < 1 second without restarting
- 💾 Preserves app state during development
- 🚀 Like "cheetah during development, race car in production"
- 📊 Measured productivity increase: 2-3x faster iteration

#### 3️⃣ Performance & Compilation Options
Dart has multiple compilation modes:
```
JIT (Just-In-Time):
  → Development: Fast compilation, instant hot reload
  → Optimization: Adapts based on runtime usage patterns
  
AOT (Ahead-Of-Time):
  → Production: Pre-compiled to native code
  → Fast Startup: No JIT warm-up time needed
  → Small Size: Optimized for deployment
  
WebAssembly (WASM):
  → Web: Better performance than JavaScript
  → Modern Browsers: 100% browser support
  → Performance: 10-100x faster than JavaScript
```

#### 4️⃣ Type Safety Without Verbosity
```dart
// Best of both worlds
var x = 5;                              // Type inference (int)
int count = 10;                         // Explicit typing
final String name = "John";             // Immutable with type
dynamic data = "anything";              // When needed
String? nullable = null;                // Explicitly nullable
String notNull = "must have value";     // Cannot be null
```

#### 5️⃣ Reactive Programming for Modern UIs
- 📡 Native async/await for asynchronous operations
- 🌊 Stream-based data flow (Futures, Streams)
- ⚡ Perfect for real-time applications
- 🎯 Foundation for reactive state management (BLoC, Provider, Riverpod)

#### 6️⃣ Industry Adoption & Success Stories[4][7]

**Companies Using Dart:**
- 🏢 **Google** - Google Ads, AdSense (critical revenue-generating applications)
- 🛍️ **Alibaba** - Large-scale e-commerce platform
- 🚗 **BMW** - Connected car applications
- 🎮 **Tencent** - QQ, Weixin integrations
- 🎭 **Hamilton Musical** - Official app
- 📊 **Many others** - Growing adoption across industries

**Growth Metrics:**
- 📈 **47% year-over-year growth** in Dart adoption
- 📱 **1 million+** apps developed with Flutter (Dart)
- 💼 **Fortune 500** companies using Dart/Flutter

#### 7️⃣ Unified Skill Set (Career Advantage)
A Dart developer can build:
- ✅ Mobile apps (iOS & Android with single codebase)
- ✅ Web applications (SPA, PWA)
- ✅ Desktop applications (Windows, macOS, Linux)
- ✅ Backend servers (Dart Frog, Aqueduct)
- ✅ Command-line tools
- ✅ IoT applications

**Career Implication:** In a competitive market, mastering Dart means you're not limited to one platform. You become a **full-stack, multi-platform developer**, significantly increasing your market value.

---

## PART 2: INSTALLING DART SDK

### 2.1 System Requirements[24]

**Dart Supports:**

| Platform | x64 | Arm32 | Arm64 | OS Versions |
|----------|-----|-------|-------|------------|
| **Windows** | ✅ | ❌ | ✅ | Windows 11, Windows 10 |
| **Linux** | ✅ | ✅ | ✅ | Debian stable, Ubuntu LTS |
| **macOS** | ✅ | ❌ | ✅ | Latest 3 versions (Tahoe, Sequoia, Sonoma) |

**Your Location:** Metro Manila, Philippines
- 💻 Recommended: Windows 11/10 or Linux (Ubuntu 22.04 LTS or later)
- 🍎 If using Mac: macOS Sequoia (15) or later

### 2.2 Installation Methods

Choose ONE installation method below based on your OS:

---

#### **OPTION A: Windows Installation (Recommended)**[24][18][27][30]

**Method 1: Using Chocolatey (EASIEST)**

**Step 1: Check if Chocolatey is installed**
```powershell
choco --version
```

If you see a version number (e.g., 2.0.0), skip to Step 2.  
If not, install Chocolatey from https://chocolatey.org/install

**Step 2: Install Dart SDK via Chocolatey**

Open PowerShell **as Administrator** and run:
```powershell
PS C:\> choco install dart-sdk
```

Expected output:
```
Chocolatey v2.0.0
Installing the following packages:
dart-sdk
...
Dart SDK has been installed to C:\tools\dart-sdk
```

**Step 3: Verify Installation**

Close and reopen PowerShell, then run:
```powershell
dart --version
```

Expected output:
```
Dart SDK version: 3.10.3 (stable) on "win_x64"
```

✅ **If you see the version, installation is successful!**

---

**Method 2: Manual ZIP Installation (If Chocolatey Doesn't Work)**[21][27][30]

**Step 1: Download Dart SDK**
1. Go to: https://dart.dev/get-dart/archive
2. Click **"Dart SDK"** for Windows 64-Bit
3. Save the ZIP file to your **Downloads** folder

**Step 2: Extract the ZIP file**
1. Right-click the downloaded ZIP file
2. Select **"Extract All..."**
3. Extract to a folder like: `C:\Program Files\dart-sdk`

**Step 3: Add Dart to System PATH**

This allows you to run `dart` from any command prompt.

1. Open **Start Menu** → Search for **"Environment Variables"**
2. Click **"Edit the system environment variables"**
3. Click **"Environment Variables..."** button
4. Under **"System Variables"**, find **"Path"** and click **"Edit..."**
5. Click **"New"** and add: `C:\Program Files\dart-sdk\bin`
6. Click **"OK"** three times to apply

**Step 4: Verify PATH Configuration**

Close all PowerShell windows and open a **new PowerShell window**:
```powershell
dart --version
```

If you see the version, you're done! ✅

---

#### **OPTION B: Linux Installation (Ubuntu/Debian)**[24][18]

**Method 1: Using apt-get (RECOMMENDED)**

**Step 1: Update package index**
```bash
sudo apt-get update && sudo apt-get install apt-transport-https
```

**Step 2: Add Google's GPG key**
```bash
wget -qO- https://dl-ssl.google.com/linux/linux_signing_key.pub \
| sudo gpg --dearmor -o /usr/share/keyrings/dart.gpg
```

**Step 3: Add Dart repository**
```bash
echo 'deb [signed-by=/usr/share/keyrings/dart.gpg arch=amd64] https://storage.googleapis.com/download.dartlang.org/linux/debian stable main' \
| sudo tee /etc/apt/sources.list.d/dart_stable.list
```

**Step 4: Install Dart**
```bash
sudo apt-get update && sudo apt-get install dart
```

**Step 5: Add Dart to PATH (if not automatic)**
```bash
export PATH="$PATH:/usr/lib/dart/bin"
source ~/.bashrc
```

**Step 6: Verify installation**
```bash
dart --version
```

Expected output:
```
Dart SDK version: 3.10.3 (stable) on "linux_x64"
```

---

**Method 2: Using Snap (Simpler Alternative)**

If apt-get method doesn't work:
```bash
sudo snap install dart --classic
dart --version
```

---

#### **OPTION C: macOS Installation**[24]

**Method 1: Using Homebrew (RECOMMENDED)**

**Step 1: Install Homebrew (if not installed)**
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Step 2: Add Dart tap**
```bash
brew tap dart-lang/dart
```

**Step 3: Install Dart**
```bash
brew install dart
```

**Step 4: Verify Homebrew is in PATH**

Add this to your `~/.zprofile` (or `~/.bash_profile` for older Macs):
```bash
export PATH="/usr/local/bin:$PATH"
```

**Step 5: Verify installation**
```bash
dart --version
```

Expected output:
```
Dart SDK version: 3.10.3 (stable) on "macos_x64"
```

---

### 2.3 Troubleshooting Installation Issues

| Problem | Cause | Solution |
|---------|-------|----------|
| ❌ `dart` command not found | PATH not set correctly | Re-run PATH setup (see Step 3 above) and **restart terminal** |
| ❌ Permission denied | Running without admin | Open PowerShell/Terminal **as Administrator** |
| ❌ ZIP won't extract | Corrupted download | Delete file, re-download from https://dart.dev/get-dart/archive |
| ❌ Version mismatch | Multiple Dart installations | Run `where dart` (Windows) or `which dart` (Linux/Mac) to find conflicting installations |
| ❌ Chocolatey not found | Chocolatey not installed | Install from https://chocolatey.org/install or use ZIP method |

---

## PART 3: SETTING UP YOUR IDE

### 3.1 Choosing an IDE

We recommend **Visual Studio Code (VS Code)** because:
- ✅ Lightweight and fast
- ✅ Excellent Dart/Flutter support
- ✅ Free and open-source
- ✅ Easy extension management
- ✅ Popular in the Dart community
- ✅ Integrated terminal

Alternative: **Android Studio** (also works but heavier)

### 3.2 Installing VS Code

1. **Download VS Code:**
   - Go to https://code.visualstudio.com
   - Download for your OS (Windows, Linux, or macOS)
   - Run the installer

2. **Install Dart Extension:**
   - Open VS Code
   - Click the **Extensions icon** on the left sidebar (or press `Ctrl+Shift+X`)
   - Search for **"Dart"**
   - Click **"Install"** on the official Dart extension (by Dart Code)

3. **VS Code will automatically detect your Dart SDK** ✅

### 3.3 Verify IDE Setup

1. Open VS Code
2. Open **View → Command Palette** (or press `Ctrl+Shift+P`)
3. Type: `Dart: Show SDK Info`
4. You should see your Dart SDK path and version

---

## PART 4: YOUR FIRST DART PROGRAM

### 4.1 Understanding the Main Function[29]

Every Dart program starts with a `main()` function:

```dart
void main() {
  // Your code here
}
```

**Breakdown:**
- `void` - Return type (no value is returned)
- `main()` - Function name (special: entry point of your program)
- `{ }` - Function body (code between braces executes)

### 4.2 Creating Your First Program

**Step 1: Create a new file**

In VS Code:
1. Click **File → New Text File**
2. Select **Dart** as the language
3. Or create a file named `hello.dart`

**Step 2: Write the program**

Type this code:

```dart
void main() {
  print('Hello, Dart!');
}
```

**Explanation:**
- `print()` - Built-in function that displays text on console
- `'Hello, Dart!'` - String literal (text in single or double quotes)
- `;` - Semicolon ends the statement (required in Dart)

**Step 3: Save the file**

Press `Ctrl+S` (or Cmd+S on Mac)
- Suggested location: Create a folder called `dart_projects`
- Save as: `hello.dart`

### 4.3 Running Your Program

**Method 1: Using Terminal (Recommended)**[17]

1. Open terminal in VS Code:
   - Press **Ctrl+`** (backtick) on Windows/Linux
   - Or **Cmd+`** on Mac
   
2. Navigate to your file's directory:
   ```bash
   cd ~/dart_projects
   ```

3. Run the program:
   ```bash
   dart run hello.dart
   ```
   
   Or simply:
   ```bash
   dart hello.dart
   ```

4. **Expected Output:**
   ```
   Hello, Dart!
   ```

✅ **Congratulations! You've run your first Dart program!**

---

**Method 2: Using VS Code Run Button (If available)**

If you see a **"Run"** button above the `main()` function:
1. Click **"Run"**
2. Output appears in the bottom panel

---

### 4.4 Your Second Program: Variables and Print

Let's create a more interesting program:

```dart
void main() {
  // Declare a variable
  var name = 'Flutter Developer';
  
  // Print the variable
  print('Welcome to Dart!');
  print('Name: $name');
  
  // Another variable
  int age = 25;
  print('Age: $age');
  
  // Boolean
  bool isStudent = true;
  print('Is Student: $isStudent');
}
```

**Save as:** `variables.dart`

**Run it:**
```bash
dart variables.dart
```

**Expected Output:**
```
Welcome to Dart!
Name: Flutter Developer
Age: 25
Is Student: true
```

---

## PART 5: UNDERSTANDING BASIC SYNTAX

### 5.1 Comments[19][20]

Comments explain your code (ignored by Dart):

```dart
void main() {
  // Single-line comment
  print('Hello'); // Comment on same line
  
  /* Multi-line
     comment
     here */
  
  /// Documentation comment
  /// Used for generating docs
}
```

### 5.2 Variables and Type Inference[22][28]

**Explicit Type Declaration:**
```dart
String name = "John";           // String type
int age = 25;                   // Integer type
double height = 5.9;            // Decimal number
bool isActive = true;           // Boolean (true/false)
```

**Type Inference (var):**
```dart
var name = "John";              // Dart infers: String
var age = 25;                   // Dart infers: int
var price = 19.99;              // Dart infers: double
var isActive = true;            // Dart infers: bool
```

Dart automatically detects the type from the value assigned.[22]

**Benefits of Type Inference:**
- ✅ Less typing
- ✅ Code is cleaner
- ✅ Dart still checks types (type-safe)
- ✅ IDE autocomplete works

---

### 5.3 Output with print()[17][25]

**Basic Output:**
```dart
print('Hello, World!');
```

**String Interpolation (embedding variables in strings):**
```dart
String language = "Dart";
print('I love $language');  // Output: I love Dart

int number = 42;
print('The answer is $number');  // Output: The answer is 42
```

**Expression in Interpolation:**
```dart
int x = 10;
int y = 20;
print('Sum: ${x + y}');  // Output: Sum: 30
// Note: Use ${} for expressions, just $variable for simple variables
```

**Multiple Prints:**
```dart
print('Line 1');
print('Line 2');
print('Line 3');
```

---

## PART 6: HANDS-ON PRACTICE (Week 1)

### Practice 1: Hello World (15 minutes)
✅ Create `hello_world.dart`
✅ Write a program that prints: "Hello, World!"
✅ Run it successfully

### Practice 2: Personal Introduction (30 minutes)
Create `introduction.dart`:

```dart
void main() {
  // TODO: Declare variables for:
  // - Your name
  // - Your age
  // - Your city
  // - Your favorite programming language
  
  // TODO: Print them in a formatted way
  // Example output:
  // Name: John Doe
  // Age: 25
  // City: Manila
  // Favorite Language: Dart
}
```

**Solution:**
```dart
void main() {
  String name = 'Your Name';
  int age = 25;
  String city = 'Manila';
  String language = 'Dart';
  
  print('Name: $name');
  print('Age: $age');
  print('City: $city');
  print('Favorite Language: $language');
}
```

### Practice 3: Simple Calculations (30 minutes)
Create `calculator.dart`:

```dart
void main() {
  int num1 = 15;
  int num2 = 8;
  
  // TODO: Calculate and print:
  // - Addition
  // - Subtraction
  // - Multiplication
  // - Division (use /)
  // - Integer Division (use ~/)
}
```

**Solution:**
```dart
void main() {
  int num1 = 15;
  int num2 = 8;
  
  print('$num1 + $num2 = ${num1 + num2}');
  print('$num1 - $num2 = ${num1 - num2}');
  print('$num1 * $num2 = ${num1 * num2}');
  print('$num1 / $num2 = ${num1 / num2}');
  print('$num1 ~/ $num2 = ${num1 ~/ num2}');  // Integer division
}
```

**Expected Output:**
```
15 + 8 = 23
15 - 8 = 7
15 * 8 = 120
15 / 8 = 1.875
15 ~/ 8 = 1
```

### Practice 4: Data Types Exploration (45 minutes)
Create `data_types.dart`:

```dart
void main() {
  // String
  String greeting = 'Hello Dart';
  print('String: $greeting');
  
  // Integer
  int count = 42;
  print('Integer: $count');
  
  // Double
  double pi = 3.14159;
  print('Double: $pi');
  
  // Boolean
  bool isLearning = true;
  print('Boolean: $isLearning');
  
  // Demonstrate type inference
  var dynamicString = 'Dart';
  var dynamicNumber = 100;
  var dynamicDecimal = 99.99;
  
  print('\nType Inference:');
  print('$dynamicString is a String');
  print('$dynamicNumber is an int');
  print('$dynamicDecimal is a double');
}
```

---

## PART 7: VERIFICATION CHECKLIST

By the end of Week 1, you should be able to:

### ✅ Installation & Setup
- [ ] Dart SDK installed (verified with `dart --version`)
- [ ] VS Code installed with Dart extension
- [ ] Created a `dart_projects` folder on your computer
- [ ] Opened Terminal in VS Code without errors

### ✅ Understanding Concepts
- [ ] Explain what Dart is and why Google created it
- [ ] Describe 3 reasons why industry needs Dart
- [ ] Understand the relationship between Dart and Flutter
- [ ] Explain what `main()` function does

### ✅ Practical Skills
- [ ] Created and ran `hello.dart` program
- [ ] Created and ran `variables.dart` program
- [ ] Used `print()` function with string interpolation
- [ ] Declared variables with explicit types and `var`
- [ ] Performed basic arithmetic operations
- [ ] No errors when running any program

### ✅ Knowledge
- [ ] Know 3 different ways to install Dart
- [ ] Understand difference between `var`, explicit type, and type inference
- [ ] Can explain what a string literal is
- [ ] Understand single-line and multi-line comments

---


## RESOURCES FOR WEEK 1

### Official Documentation
- **Dart SDK Installation Guide:** https://dart.dev/get-dart (Official)[24]
- **Dart Language Tour:** https://dart.dev/language (Official)[17]
- **Dart Variables Documentation:** https://dart.dev/language/variables (Official)[22]

### Community Resources
- **GeeksforGeeks Dart Tutorial:** https://www.geeksforgeeks.org/dart/ (Community)[20]
- **GeeksforGeeks SDK Installation:** https://www.geeksforgeeks.org/dart/dart-sdk-installation/ (Community)[18]
- **Dart Tutorial Site:** https://www.darttutorial.org (Community)[23]
- **Dart Tutorial (dart-tutorial.com):** https://dart-tutorial.com (Community)[28]

### Video Resources
- **How to Install Dart SDK on Windows 11:** YouTube (Recent 2025)[30]
- **Introduction to Dart Variables:** YouTube (Udemy course)[31]

### Online IDEs (No Installation Required)
- **DartPad:** https://dartpad.dev - Write and run Dart code online instantly[1]

---

## FAQ: Week 1

### Q1: Do I need to install Flutter to use Dart?
**A:** No. Dart is a standalone language. You can learn and use Dart without Flutter. Flutter is a framework **built on top of** Dart. Learn Dart first, then Flutter later (Week 7).

### Q2: What's the difference between `dart run file.dart` and `dart file.dart`?
**A:** They do the same thing. `dart run` is the newer, preferred syntax, but both work.

### Q3: Can I use DartPad instead of installing?
**A:** Yes! If installation is difficult, use https://dartpad.dev to write and run code online. However, installing locally is recommended for Week 1+ when we add more complex features.

### Q4: I'm getting "dart command not found" after installation
**A:** Your PATH is not set correctly. Re-run the PATH configuration steps (Section 2.3) and **restart your terminal completely**.

### Q5: Which IDE is best for beginners?
**A:** VS Code with Dart extension is easiest to learn. Android Studio works but is heavier.

### Q6: Can I use Dart on my phone?
**A:** Not directly. Dart compiles to various platforms. For phones, you use Flutter (Dart framework) to create mobile apps.

### Q7: Is Dart similar to Java?
**A:** Dart has some similarities (object-oriented, static typing) but is simpler and more modern. See comparison in Section 1.2.

### Q8: Do I need to know Java/C++ before learning Dart?
**A:** No. Dart is designed to be beginner-friendly. This curriculum assumes no prior programming experience.

---

---

**Total Estimated Time for Week 1: 10-15 hours**

End of Week 1 Document
