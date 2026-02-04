<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Course: Building a Simple Professional Portfolio with Flutter Web

## **Simplified Version - Essential Features Only**

Welcome, student! This is a streamlined portfolio course focused on the essentials: clean design, hamburger menu navigation, and proper resource management with dispose(). Let's build it step-by-step from scratch.

***

## **Module 1: Project Setup \& Essential Configuration**

### **Lesson 1.1: Creating Your Flutter Web Project**

**Objective:** Initialize a new Flutter web project

**Step-by-Step Instructions:**

1. Open your terminal/command prompt
2. Run: `flutter create simple_portfolio`
3. Navigate into the project: `cd simple_portfolio`
4. Verify web support: `flutter devices`
5. Run the app: `flutter run -d chrome`

**Expected Output:**

- New project folder named `simple_portfolio`
- Default Flutter counter demo app running in Chrome
- Console shows: "✓ Built web\application\flutter_bootstrap.js"
- No errors
- Counter app with + button visible

**What you have now:**

```
simple_portfolio/
├── lib/
│   └── main.dart
├── web/
├── test/
├── android/
├── ios/
└── pubspec.yaml
```


***

### **Lesson 1.2: Understanding What We'll Keep and Delete**

**Objective:** Understand the default code before removing it

**Instructions:**

1. Open `lib/main.dart` in your code editor
2. **DO NOT DELETE YET - just observe**
3. Notice the file has:
    - Line 1: `import 'package:flutter/material.dart';`
    - Lines 3-5: `void main()` function
    - Lines 7-30: `MyApp` class
    - Lines 32-120+: `MyHomePage` class (the counter)

**What we'll KEEP:**

- The import statement (line 1)
- The main() function structure
- MaterialApp concept

**What we'll DELETE:**

- Everything about the counter
- All comments
- MyHomePage class completely

**Expected Understanding:**

- You can see the counter app code
- You know we'll start from scratch
- You understand `main()` is the starting point

***

### **Lesson 1.3: Deleting All Default Code**

**Objective:** Clear the file to start fresh

**Instructions:**

1. In `lib/main.dart`, **select ALL text** (Ctrl+A or Cmd+A)
2. **Press Delete**
3. Your file should now be completely empty
4. Save the file

**Expected Output:**

- Empty `main.dart` file
- Red errors everywhere (expected!)
- App stops running if it was running
- Don't worry - we'll fix this step by step

***

### **Lesson 1.4: Adding the Import Statement**

**Objective:** Add back the essential Flutter import

**Instructions:**

1. In your empty `main.dart` file, type this ONE line:
```dart
import 'package:flutter/material.dart';
```

2. Save the file

**What this does:**

- Imports Flutter's Material Design widgets
- Required for Text, Container, Scaffold, AppBar, etc.
- Without it, Flutter doesn't know what widgets are

**Expected Output:**

- Single line of code at top of file
- Still has errors (expected - we need more code)
- Green/white text (syntax highlighting working)

***

### **Lesson 1.5: Adding the Main Function**

**Objective:** Create the app entry point

**Instructions:**

1. Below the import line, press Enter twice (blank line)
2. Type these 3 lines:
```dart
void main() {
  runApp(const SimplePortfolioApp());
}
```

3. Save the file

**What this does:**

- `void main()` = starting point of every Dart/Flutter app
- `runApp()` = Flutter function that launches your app
- `SimplePortfolioApp()` = your app (we'll create this next)

**Expected Output:**

- New error: "Undefined class 'SimplePortfolioApp'"
- This is expected - we haven't created it yet
- Next lesson will fix this error

***

### **Lesson 1.6: Creating Your Root App Widget**

**Objective:** Create the app configuration widget

**Instructions:**

1. Below the main() function, press Enter twice
2. Type these lines:
```dart
class SimplePortfolioApp extends StatelessWidget {
  const SimplePortfolioApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Portfolio',
      home: Text('Hello'),
    );
  }
}
```

3. Save and run: `flutter run -d chrome`

**What this does:**

- Creates a class named `SimplePortfolioApp`
- `extends StatelessWidget` = doesn't change after building
- `MaterialApp` = root widget that provides app structure
- `debugShowCheckedModeBanner: false` = removes "DEBUG" banner
- `home: Text('Hello')` = shows "Hello" text (temporary)

**Expected Output:**

- App runs without errors!
- Black text "Hello" on white screen
- No AppBar or styling yet
- Very minimal but working

***

### **Lesson 1.7: Installing Google Fonts Package**

**Objective:** Add Google Fonts for professional typography

**Instructions:**

1. **STOP the app** (press Q in terminal or Ctrl+C)
2. Open `pubspec.yaml` file
3. Find the `dependencies:` section (around line 30)
4. Add this line below `cupertino_icons`:
```yaml
dependencies:
  flutter:
    sdk: flutter
  
  cupertino_icons: ^1.0.2
  google_fonts: ^4.0.3
```

**IMPORTANT:** Make sure indentation matches exactly (2 spaces before `google_fonts`)

5. Save the file
6. Run in terminal: `flutter pub get`

**Expected Output:**

- Terminal shows: "Running 'flutter pub get'..."
- Then shows: "Got dependencies!"
- No errors
- Package is now installed

***

### **Lesson 1.8: Creating Assets Folder**

**Objective:** Set up folder for your profile image

**Instructions:**

1. In your project root (same level as `lib/`), create a new folder named `assets`
2. Inside `assets/`, create a subfolder named `images`
3. Place your profile photo in `assets/images/` and name it `profile.jpg`

**Your folder structure should be:**

```
simple_portfolio/
├── lib/
│   └── main.dart
├── assets/           ← NEW
│   └── images/       ← NEW
│       └── profile.jpg  ← YOUR PHOTO HERE
└── pubspec.yaml
```

**Expected Output:**

- `assets/images/` folder exists
- Your profile photo is inside
- Photo is named exactly `profile.jpg` (or `profile.png`)

***

### **Lesson 1.9: Registering Assets in pubspec.yaml**

**Objective:** Tell Flutter about your assets folder

**Instructions:**

1. Open `pubspec.yaml`
2. Scroll down to around line 60 where you see `# assets:`
3. **Uncomment and modify** to look like this:
```yaml
flutter:
  uses-material-design: true
  
  assets:
    - assets/images/
```

**IMPORTANT:**

- `flutter:` has NO spaces before it
- `uses-material-design:` has 2 spaces
- `assets:` has 2 spaces
- `- assets/images/` has 4 spaces and a dash

4. Save the file
5. Run: `flutter pub get`

**Expected Output:**

- No errors
- Assets are now registered
- Flutter knows where to find your images

***

### **Lesson 1.10: Importing Google Fonts in Code**

**Objective:** Make Google Fonts available in your app

**Instructions:**

1. Open `lib/main.dart`
2. At the top, add this second import line:
```dart
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
```

3. Save the file

**What this does:**

- Imports the google_fonts package
- Makes `GoogleFonts` class available
- You can now use `GoogleFonts.poppins()`, `GoogleFonts.roboto()`, etc.

**Expected Output:**

- No errors (if you see error, run `flutter pub get`)
- Two import lines at top
- Ready to use Google Fonts

***

## ✅ **Module 1 Checkpoint**

**What You've Accomplished:**

- ✓ Created new Flutter web project
- ✓ Deleted all default counter code
- ✓ Added import statement
- ✓ Created main() function
- ✓ Built SimplePortfolioApp widget
- ✓ Installed Google Fonts package
- ✓ Created assets folder structure
- ✓ Registered assets in pubspec.yaml
- ✓ Imported Google Fonts in code
- ✓ Have a working (minimal) app

**Your Complete main.dart (so far):**

```dart
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';

void main() {
  runApp(const SimplePortfolioApp());
}

class SimplePortfolioApp extends StatelessWidget {
  const SimplePortfolioApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Portfolio',
      home: Text('Hello'),
    );
  }
}
```

**Your Project Structure:**

```
simple_portfolio/
├── lib/
│   └── main.dart (clean, minimal code)
├── assets/
│   └── images/
│       └── profile.jpg (your photo)
├── pubspec.yaml (with google_fonts and assets)
└── web/
```

**What Works:**

- App runs without errors
- Shows "Hello" text
- Google Fonts installed
- Assets ready to use

***

## **Next Module Preview**

**Module 2: Building the Basic UI Structure**

In Module 2, you'll add (one step at a time):

- Scaffold widget for basic structure
- AppBar at the top
- Centered content area
- Background color
- Better layout foundation

Then Module 3 will add profile picture and text!

***

**Ready for Module 2?** Reply **"Continue to Module 2"** and we'll start building the UI structure step by step! 🚀

**Current Status:** Clean foundation ready ✓
**Next Step:** Add basic UI structure (Scaffold, AppBar) ✓

