# Flutter Portfolio App: Complete Beginner's Guide

**Course:** Fundamentals of Mobile Programming  
**Topic:** Building a Professional Portfolio App with Navigation  
**Level:** Beginner  

---

## 📚 Table of Contents

1. [Introduction](#introduction)
2. [What You'll Learn](#what-youll-learn)
3. [Prerequisites](#prerequisites)
4. [Understanding New Concepts](#understanding-new-concepts)
5. [Step-by-Step Build Process](#step-by-step-build-process)
6. [Testing Your App](#testing-your-app)
7. [Common Errors and Solutions](#common-errors-and-solutions)
8. [Next Steps](#next-steps)

---

## Introduction

You'll build a **Professional Portfolio App** that showcases your skills, projects, and contact information. This app introduces navigation concepts that are essential for multi-page applications.

By the end of this guide, you'll understand:
- How to implement Navigation Drawer (sidebar menu)
- How to manage multiple pages in one screen
- How to use external fonts (Google Fonts)
- How to add and display images
- How to create professional-looking layouts

---

## What You'll Learn

### Core Concepts
1. **Navigation Drawer** - Sidebar menu for navigation[1]
2. **Google Fonts Package** - Using custom fonts[2]
3. **Asset Management** - Working with images
4. **ScrollController** - Advanced scroll management[3]
5. **StatefulWidget Navigation** - Page switching without routes
6. **Builder Widget** - Understanding BuildContext

### Skills You'll Develop
- Setting up external packages
- Managing app assets (images, fonts)
- Creating navigation patterns
- Building multi-section apps
- Professional UI design
- Conditional rendering

---

## Understanding New Concepts

### 1. What is a Navigation Drawer?

A **Navigation Drawer** (also called sidebar or hamburger menu) is a panel that slides in from the side of the screen, typically showing navigation options[1].

**Common uses:**
- Main app navigation
- User profile access
- Settings and preferences
- Quick actions

**Visual example:**
```
┌─────────────────────────┐
│ ☰ Portfolio            │ ← App Bar with menu icon
├─────────────────────────┤
│                         │
│   Your content here     │
│                         │
└─────────────────────────┘

When you tap ☰:
┌──────────────┬──────────┐
│              │          │
│ Profile Info │          │
│──────────────│  Content │
│ 🏠 Home      │  (dimmed)│
│ 👤 About     │          │
│ 💡 Skills    │          │
│ ✉️  Contact  │          │
└──────────────┴──────────┘
   Drawer slides in
```

### 2. Understanding Google Fonts Package

**What is it?**
A package that gives you access to 1000+ fonts from Google Fonts directly in your Flutter app[2].

**Why use it?**
- Professional typography
- No manual font file downloads
- Automatic font caching
- Easy to implement

**Traditional way (harder):**
1. Download font files (.ttf)
2. Add to assets folder
3. Update pubspec.yaml
4. Declare font family
5. Use in code

**With google_fonts package (easier):**
1. Add package to pubspec.yaml
2. Use in code: `GoogleFonts.poppins()`

### 3. Asset Management in Flutter

**What are assets?**
Assets are resources bundled with your app (images, fonts, JSON files, etc.).

**Why important?**
- Apps need images (logos, profiles, icons)
- Must be declared in pubspec.yaml
- Flutter bundles them into your app

**Asset structure:**
```
your_project/
├── lib/
│   ├── main.dart
│   └── assets/
│       └── images/
│           └── profile.jpg
└── pubspec.yaml
```

### 4. ScrollController

**What is it?**
A controller that manages scrolling behavior of scrollable widgets[3].

**Why use it?**
- Programmatically scroll to positions
- Listen to scroll events
- Animate scrolling
- Track scroll position

**Analogy:** Like a remote control for a scrollable view.

---

## Step-by-Step Build Process

### 📋 Module 1: Project Setup (20 minutes)

#### Step 1.1: Create a New Flutter Project

#### Step 1.2: Add Google Fonts Package

Open `pubspec.yaml` and add the google_fonts dependency:

```yaml
dependencies:
  flutter:
    sdk: flutter
  google_fonts: ^6.2.1
```

**What this does:** Tells Flutter to download and include the Google Fonts package[2].

**Run this command in terminal:**
```bash
flutter pub get
```

This downloads the package and makes it available in your project.

#### Step 1.3: Set Up Asset Folder Structure

1. Create folders in your project:
   - `lib/assets/`
   - `lib/assets/images/`

2. Add a profile image (any image) and name it `profile.jpg`

**Your structure should look like:**
```
portfolio_app/
├── lib/
│   ├── main.dart
│   └── assets/
│       └── images/
│           └── profile.jpg
└── pubspec.yaml
```

#### Step 1.4: Declare Assets in pubspec.yaml

In `pubspec.yaml`, find the `flutter:` section and add:

```yaml
flutter:
  uses-material-design: true
  
  assets:
    - lib/assets/images/
```

**Important formatting rules:**
- Exact indentation matters (2 spaces)
- The dash `-` must align with `uses-material-design`
- The path ends with `/` to include all files in folder

**Common mistakes:**
```yaml
# ❌ WRONG - incorrect indentation
flutter:
uses-material-design: true
assets:
  - lib/assets/images/

# ❌ WRONG - missing dash
flutter:
  uses-material-design: true
  assets:
    lib/assets/images/

# ✅ CORRECT
flutter:
  uses-material-design: true
  
  assets:
    - lib/assets/images/
```

**Run this command after changes:**
```bash
flutter pub get
```

---

### 📋 Module 2: Basic App Structure (25 minutes)

#### Step 2.1: Import Required Packages

Open `lib/main.dart` and clear everything. Start with imports:

```dart
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
```

**What these do:**
- `flutter/material.dart` → Material Design widgets
- `google_fonts/google_fonts.dart` → Access to Google Fonts

#### Step 2.2: Create Main Function

```dart
void main() {
  runApp(const SimplePortfolioApp());
}
```

**Explanation:** Entry point that launches your app.

#### Step 2.3: Create Root App Widget

```dart
class SimplePortfolioApp extends StatelessWidget {
  const SimplePortfolioApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'Portfolio',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        scaffoldBackgroundColor: Color(0xFFF5F5F5),
      ),
      home: HomePage(),
    );
  }
}
```

**New concept: Color(0xFFF5F5F5)**

This is a **hexadecimal color code**:
- `0xFF` → Opacity (FF = fully opaque)
- `F5F5F5` → RGB color (light grey)

**Color breakdown:**
- `0xFFFFFFFF` → White
- `0xFF000000` → Black
- `0xFFF5F5F5` → Light grey (our background)
- `0xFF2196F3` → Blue

**Why this background color?**
Professional apps use off-white instead of pure white for better visual comfort.

---

### 📋 Module 3: Creating the HomePage Structure (30 minutes)

#### Step 3.1: Create StatefulWidget

```dart
class HomePage extends StatefulWidget {
  const HomePage({Key? key}) : super(key: key);

  @override
  State<HomePage> createState() => _HomePageState();
}
```

**Why StatefulWidget?**
We need to track which page is selected and update the UI accordingly.

#### Step 3.2: Create State Class with Variables

```dart
class _HomePageState extends State<HomePage> {
  String selectedPage = 'Home';
  late ScrollController _scrollController;
  
  // We'll add more code here
}
```

**Understanding these variables:**

1. **`String selectedPage = 'Home';`**
   - Tracks which navigation item is selected
   - Changes when user taps menu items
   - Determines what content to show

2. **`late ScrollController _scrollController;`**
   - `late` means "I'll initialize this before using it"
   - Controls scrolling behavior
   - Must be created in initState()

**Why use 'late'?**

```dart
// ❌ CAN'T do this - context not available yet
ScrollController _scrollController = ScrollController();

// ✅ CORRECT - initialized in initState()
late ScrollController _scrollController;

@override
void initState() {
  super.initState();
  _scrollController = ScrollController();
}
```

#### Step 3.3: Implement initState and dispose

```dart
@override
void initState() {
  super.initState();
  _scrollController = ScrollController();
}

@override
void dispose() {
  _scrollController.dispose();
  super.dispose();
}
```

**Why we need both:**

**initState():**
- Called once when widget is created
- Perfect for creating controllers
- Setup that happens before UI builds

**dispose():**
- Called when widget is removed permanently
- Cleanup to prevent memory leaks
- Release resources (controllers, listeners, etc.)

**Lifecycle flow:**
```
Widget Created
    ↓
initState() called
    ↓
build() called
    ↓
Widget displayed
    ↓
(Widget lives here)
    ↓
Widget removed
    ↓
dispose() called
```

---

### 📋 Module 4: Building the App Bar (25 minutes)

#### Step 4.1: Create the Build Method with Scaffold

```dart
@override
Widget build(BuildContext context) {
  return Scaffold(
    backgroundColor: Color(0xFFF5F5F5),
    appBar: AppBar(
      leading: Builder(
        builder: (BuildContext context) {
          return IconButton(
            icon: Icon(Icons.menu),
            onPressed: () {
              Scaffold.of(context).openDrawer();
            },
          );
        },
      ),
      title: Text(
        'Portfolio',
        style: GoogleFonts.poppins(
          fontSize: 20,
          fontWeight: FontWeight.w600,
        ),
      ),
    ),
    // We'll add drawer and body next
  );
}
```

**Understanding the Builder Widget:**

This is the MOST confusing part for beginners. Let's break it down carefully.

**The Problem:**
```dart
// ❌ THIS DOESN'T WORK:
leading: IconButton(
  icon: Icon(Icons.menu),
  onPressed: () {
    Scaffold.of(context).openDrawer();  // ❌ Wrong context!
  },
),
```

**Why it fails:**
- `context` here refers to `_HomePageState`
- But `Scaffold.of(context)` needs the context of a widget INSIDE the Scaffold
- It's looking "up" the widget tree but can't find Scaffold

**The Solution: Builder Widget**
```dart
// ✅ THIS WORKS:
leading: Builder(
  builder: (BuildContext context) {  // New context!
    return IconButton(
      icon: Icon(Icons.menu),
      onPressed: () {
        Scaffold.of(context).openDrawer();  // ✅ Correct context!
      },
    );
  },
),
```

**Why it works:**
- `Builder` creates a NEW context
- This new context is a child of Scaffold
- Now `Scaffold.of(context)` can find the Scaffold above it

**Visual explanation:**
```
_HomePageState context ← Can't see Scaffold
    ↓
Scaffold
    ↓
AppBar
    ↓
Builder ← Creates new context that CAN see Scaffold
    ↓
IconButton
```

**Analogy:** Imagine you're in a room (IconButton) trying to turn on a light switch (Scaffold) outside the door. Builder is like stepping into the hallway where you can reach the switch.

#### Step 4.2: Understanding GoogleFonts Usage

```dart
Text(
  'Portfolio',
  style: GoogleFonts.poppins(
    fontSize: 20,
    fontWeight: FontWeight.w600,
  ),
),
```

**How GoogleFonts works:**[2]

**Format:** `GoogleFonts.fontName(properties)`

**Available fonts:**
- `GoogleFonts.poppins()` → Modern, clean
- `GoogleFonts.roboto()` → Standard, readable
- `GoogleFonts.montserrat()` → Elegant, professional
- `GoogleFonts.lato()` → Friendly, corporate
- `GoogleFonts.openSans()` → Neutral, versatile

**Font weights:**
- `FontWeight.w300` → Light
- `FontWeight.w400` → Regular (normal)
- `FontWeight.w500` → Medium
- `FontWeight.w600` → Semi-bold (our choice)
- `FontWeight.w700` → Bold
- `FontWeight.w900` → Black (very bold)

**Comparison with regular TextStyle:**
```dart
// Without GoogleFonts (system font)
Text(
  'Portfolio',
  style: TextStyle(
    fontSize: 20,
    fontWeight: FontWeight.w600,
  ),
)

// With GoogleFonts (Poppins font)
Text(
  'Portfolio',
  style: GoogleFonts.poppins(
    fontSize: 20,
    fontWeight: FontWeight.w600,
  ),
)
```

---

### 📋 Module 5: Creating the Navigation Drawer (45 minutes)

#### Step 5.1: Add Drawer Property to Scaffold

In your `build()` method, after `appBar:`, add:

```dart
drawer: Drawer(
  child: ListView(
    padding: EdgeInsets.zero,
    children: [
      // We'll add DrawerHeader and menu items here
    ],
  ),
),
```

**Understanding the structure:**

- **Drawer** → The sliding panel widget[1]
- **ListView** → Makes drawer content scrollable
- **padding: EdgeInsets.zero** → Removes default padding (we want header to touch edges)
- **children** → List of widgets in the drawer

#### Step 5.2: Create the Drawer Header

Inside the `children: [ ]` list, add:

```dart
DrawerHeader(
  decoration: BoxDecoration(
    color: Colors.blue,
  ),
  child: Column(
    crossAxisAlignment: CrossAxisAlignment.start,
    mainAxisAlignment: MainAxisAlignment.end,
    children: [
      Text(
        'Your Name',
        style: GoogleFonts.poppins(
          fontSize: 18,
          fontWeight: FontWeight.bold,
          color: Colors.white,
        ),
      ),
      SizedBox(height: 4),
      Text(
        'Flutter Developer',
        style: GoogleFonts.roboto(
          fontSize: 14,
          color: Colors.white70,
        ),
      ),
    ],
  ),
),
```

**Understanding DrawerHeader:**

**Properties explained:**
- `decoration: BoxDecoration(color: Colors.blue)` → Background color
- `child: Column` → Vertical arrangement of name and title
- `crossAxisAlignment: CrossAxisAlignment.start` → Align left
- `mainAxisAlignment: MainAxisAlignment.end` → Push to bottom

**Visual layout:**
```
┌─────────────────────┐
│                     │
│   (Blue background) │
│                     │
│   Your Name         │ ← Bold, 18px
│   Flutter Developer │ ← Regular, 14px, lighter
└─────────────────────┘
```

**Color variations:**
- `Colors.white` → Full white (#FFFFFF)
- `Colors.white70` → 70% opacity white (semi-transparent)
- `Colors.white54` → 54% opacity
- `Colors.white38` → 38% opacity

**Why white70?** Creates visual hierarchy - main text is prominent, subtitle is subtle.

#### Step 5.3: Add Navigation Menu Items

After the `DrawerHeader,` add these ListTile widgets:

```dart
ListTile(
  leading: Icon(Icons.home, color: Colors.blue),
  title: Text('Home'),
  onTap: () {
    Navigator.pop(context);
    setState(() {
      selectedPage = 'Home';
    });
  },
),
ListTile(
  leading: Icon(Icons.person, color: Colors.blue),
  title: Text('About'),
  onTap: () {
    Navigator.pop(context);
    setState(() {
      selectedPage = 'About';
    });
  },
),
ListTile(
  leading: Icon(Icons.lightbulb, color: Colors.blue),
  title: Text('Skills'),
  onTap: () {
    Navigator.pop(context);
    setState(() {
      selectedPage = 'Skills';
    });
  },
),
ListTile(
  leading: Icon(Icons.email, color: Colors.blue),
  title: Text('Contact'),
  onTap: () {
    Navigator.pop(context);
    setState(() {
      selectedPage = 'Contact';
    });
  },
),
```

**Understanding ListTile:**

**Structure:**
```
┌──────────────────────────┐
│ 🏠  Home             ›   │
└──────────────────────────┘
   ↑     ↑              ↑
leading title        trailing
```

**Properties:**
- `leading` → Widget at the start (usually icon)
- `title` → Main text
- `trailing` → Widget at the end (optional, like arrow)
- `onTap` → Function called when tapped

**Understanding onTap logic:**

```dart
onTap: () {
  Navigator.pop(context);      // Step 1: Close drawer
  setState(() {                // Step 2: Update state
    selectedPage = 'Home';     // Step 3: Change page
  });
},
```

**Step-by-step flow:**
1. User taps "Home"
2. `Navigator.pop(context)` closes the drawer (slides it back)
3. `setState()` tells Flutter to rebuild
4. `selectedPage = 'Home'` changes the page variable
5. Build method runs again
6. New content displays based on `selectedPage`

**Why Navigator.pop()? **
- Without it, drawer stays open after tapping
- `pop()` means "go back" or "close current overlay"
- Makes UX better - drawer auto-closes on selection

#### Step 5.4: Add Divider and Extra Menu Item

After the Contact ListTile, add:

```dart
Divider(),
ListTile(
  leading: Icon(Icons.download, color: Colors.blue),
  title: Text('Download Resume'),
  onTap: () {
    Navigator.pop(context);
    print('Download Resume tapped');
  },
),
```

**Understanding Divider:**
- Creates a horizontal line
- Separates sections visually
- No properties needed for basic use

**Visual result:**
```
Home
About
Skills
Contact
──────────────  ← Divider
Download Resume
```

**The print statement:**
```dart
print('Download Resume tapped');
```

- Outputs to console/debug log
- Useful for testing if tap works
- Later, you'll replace with actual download functionality

---

### 📋 Module 6: Creating the Body with ScrollView (30 minutes)

#### Step 6.1: Add Body to Scaffold

After the `drawer:` property in Scaffold, add:

```dart
body: SingleChildScrollView(
  controller: _scrollController,
  child: Padding(
    padding: EdgeInsets.all(20),
    child: Center(
      child: _buildContent(),
    ),
  ),
),
```

**Understanding SingleChildScrollView:**[3]

**What it does:**
- Makes content scrollable
- Useful when content might exceed screen height
- Single child (unlike ListView which has multiple)

**Why we need it:**
- Different screen sizes (small phones vs tablets)
- Content might be longer than screen
- Prevents overflow errors

**Properties:**
- `controller: _scrollController` → Connects our ScrollController
- `child` → The scrollable content

**Structure visualization:**
```
SingleChildScrollView
    ↓
Padding (20px all sides)
    ↓
Center (centers content horizontally)
    ↓
_buildContent() (the actual page content)
```

#### Step 6.2: Create _buildContent Method

Add this method in your `_HomePageState` class, above the `build()` method:

```dart
Widget _buildContent() {
  if (selectedPage == 'Home') {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        ClipOval(
          child: Image.asset(
            'lib/assets/images/profile.jpg',
            width: 120,
            height: 120,
            fit: BoxFit.cover,
          ),
        ),
        SizedBox(height: 16),
        Text(
          'Your Full Name',
          style: GoogleFonts.poppins(
            fontSize: 24,
            fontWeight: FontWeight.bold,
          ),
        ),
        SizedBox(height: 8),
        Text(
          'Flutter Developer',
          style: GoogleFonts.roboto(
            fontSize: 16,
            color: Colors.grey[600],
          ),
        ),
      ],
    );
  }
  return Text('Coming soon: $selectedPage');
}
```

**Understanding this method:**

**Method structure:**
```dart
Widget _buildContent() {  // Returns a Widget
  if (selectedPage == 'Home') {
    return /* Home page content */;
  }
  return /* Default content for other pages */;
}
```

**Why this pattern?**
- Clean separation of concerns
- Easy to add more pages later
- Keeps build() method clean

**Understanding ClipOval:**

**What it does:** Clips the child widget into a circular shape.

```dart
ClipOval(
  child: Image.asset(
    'lib/assets/images/profile.jpg',
    width: 120,
    height: 120,
    fit: BoxFit.cover,
  ),
),
```

**Without ClipOval:**
```
┌────────────┐
│            │
│   Image    │  ← Square
│            │
└────────────┘
```

**With ClipOval:**
```
    ●●●●
  ●      ●
 ●  Image ●  ← Circle
  ●      ●
    ●●●●
```

**Image.asset properties:**
- `'lib/assets/images/profile.jpg'` → Path to your image
- `width: 120, height: 120` → Size of the image
- `fit: BoxFit.cover` → How image fills the space

**BoxFit options:**
- `BoxFit.cover` → Fills space, may crop (recommended for profiles)
- `BoxFit.contain` → Fits inside, may have empty space
- `BoxFit.fill` → Stretches to fill (distorts image)
- `BoxFit.fitWidth` → Fits width, crops height
- `BoxFit.fitHeight` → Fits height, crops width

**Visual comparison:**
```
BoxFit.cover (crops if needed):
┌──────────┐
│ ████████ │ ← Image fills circle
│ ████████ │    May crop edges
└──────────┘

BoxFit.contain (shows all):
┌──────────┐
│    ██    │ ← Entire image visible
│    ██    │    May have gaps
└──────────┘
```

**Understanding Colors.grey[600]:**

Flutter's material colors come in **shades** from 50 (lightest) to 900 (darkest):

```
Colors.grey[50]  ← Almost white
Colors.grey[100]
Colors.grey[200]
Colors.grey[300]
Colors.grey[400]
Colors.grey[500] ← Medium grey
Colors.grey[600] ← Our choice (slightly darker)
Colors.grey[700]
Colors.grey[800]
Colors.grey[900] ← Almost black
```

**Why [600]?** 
- Dark enough to be readable
- Light enough to look subtle
- Good for secondary text

**Understanding string interpolation:**

```dart
return Text('Coming soon: $selectedPage');
```

The `$selectedPage` inserts the variable value into the string:
- If `selectedPage = 'About'` → "Coming soon: About"
- If `selectedPage = 'Skills'` → "Coming soon: Skills"
- If `selectedPage = 'Contact'` → "Coming soon: Contact"

---

### 📋 Module 7: Complete Page Structure (15 minutes)

#### Step 7.1: Verify Complete Code Structure

Your `_HomePageState` class should now have:

```dart
class _HomePageState extends State<HomePage> {
  String selectedPage = 'Home';
  late ScrollController _scrollController;

  @override
  void initState() {
    super.initState();
    _scrollController = ScrollController();
  }

  Widget _buildContent() {
    // ... your _buildContent code
  }

  @override
  Widget build(BuildContext context) {
    // ... your build code with Scaffold, AppBar, Drawer, Body
  }

  @override
  void dispose() {
    _scrollController.dispose();
    super.dispose();
  }
}
```

**Code organization order:**
1. State variables declaration
2. initState() method
3. Custom methods (_buildContent, etc.)
4. build() method
5. dispose() method

**Why this order?**
- Variables at top → Easy to find
- initState before build → Logical flow
- Custom methods before build → Used by build
- dispose at end → Cleanup last

---

## Testing Your App

### Test Plan

Now let's test your portfolio app systematically:

#### ✅ Test 1: App Launch
1. Run your app
2. **Expected:** 
   - Blue app bar with "Portfolio" title
   - Hamburger menu icon (☰) visible
   - Profile picture, name, and title centered on screen

#### ✅ Test 2: Open Drawer
1. Tap the hamburger menu icon (☰)
2. **Expected:**
   - Drawer slides in from left
   - Blue header with name and title visible
   - Four navigation items visible (Home, About, Skills, Contact)
   - Divider line visible
   - Download Resume option visible

#### ✅ Test 3: Navigate to Different Pages
1. Tap "About" in drawer
2. **Expected:**
   - Drawer closes automatically
   - Content changes to "Coming soon: About"

3. Open drawer again, tap "Skills"
4. **Expected:**
   - Drawer closes
   - Content changes to "Coming soon: Skills"

5. Open drawer again, tap "Contact"
6. **Expected:**
   - Drawer closes
   - Content changes to "Coming soon: Contact"

#### ✅ Test 4: Return to Home
1. Open drawer
2. Tap "Home"
3. **Expected:**
   - Drawer closes
   - Profile picture, name, and title reappear

#### ✅ Test 5: Test Download Resume
1. Open drawer
2. Tap "Download Resume"
3. **Expected:**
   - Drawer closes
   - Check debug console/log for "Download Resume tapped" message

#### ✅ Test 6: Close Drawer Without Selection
1. Open drawer
2. Tap outside drawer area (on the grey dimmed background)
3. **Expected:**
   - Drawer closes
   - Current page stays the same

#### ✅ Test 7: Verify Fonts
1. Look at "Portfolio" text in app bar
2. Look at name on home screen
3. **Expected:**
   - Text should use Poppins font (cleaner, more modern than system font)
   - If fonts look different from default, Google Fonts is working

---

## Common Errors and Solutions

### Error 1: "Unable to load asset: lib/assets/images/profile.jpg"

**Problem:** Flutter can't find your image file.

**Solutions:**
1. **Check file exists:** Verify `profile.jpg` is in `lib/assets/images/` folder
2. **Check filename:** Must be exact (case-sensitive)
   - `Profile.jpg` ≠ `profile.jpg`
   - `profile.JPG` ≠ `profile.jpg`
3. **Check pubspec.yaml:** Assets must be declared
   ```yaml
   flutter:
     assets:
       - lib/assets/images/
   ```
4. **Run pub get:** After changing pubspec.yaml, run:
   ```bash
   flutter pub get
   ```
5. **Hot restart:** Hot reload isn't enough for asset changes:
   - Stop app
   - Run again

---

### Error 2: Google Fonts not loading / Font looks the same

**Problem:** Google Fonts package not working.

**Check:**
1. **Dependency added:** In `pubspec.yaml`:
   ```yaml
   dependencies:
     google_fonts: ^6.2.1
   ```
2. **Package installed:** Run:
   ```bash
   flutter pub get
   ```
3. **Import added:** At top of `main.dart`:
   ```dart
   import 'package:google_fonts/google_fonts.dart';
   ```
4. **Internet connection:** First time loading a font requires internet
5. **Hot restart:** Not hot reload

---

### Error 3: "Scaffold.of() called with a context that does not contain a Scaffold"

**Problem:** Trying to open drawer with wrong context.

**Solution:** Make sure you're using `Builder` widget:

```dart
// ❌ WRONG
leading: IconButton(
  icon: Icon(Icons.menu),
  onPressed: () {
    Scaffold.of(context).openDrawer();
  },
),

// ✅ CORRECT
leading: Builder(
  builder: (BuildContext context) {
    return IconButton(
      icon: Icon(Icons.menu),
      onPressed: () {
        Scaffold.of(context).openDrawer();
      },
    );
  },
),
```

---

### Error 4: "ScrollController not attached to any scroll views"

**Problem:** Trying to use ScrollController before it's initialized or after dispose.

**Check:**
1. **Initialize in initState:**
   ```dart
   @override
   void initState() {
     super.initState();
     _scrollController = ScrollController();
   }
   ```

2. **Attach to SingleChildScrollView:**
   ```dart
   SingleChildScrollView(
     controller: _scrollController,  // ← Must have this
     child: ...
   )
   ```

3. **Dispose properly:**
   ```dart
   @override
   void dispose() {
     _scrollController.dispose();
     super.dispose();
   }
   ```

---

### Error 5: Drawer items not changing content

**Problem:** Tapping menu items but content doesn't change.

**Check:**
1. **setState() is called:**
   ```dart
   onTap: () {
     Navigator.pop(context);
     setState(() {  // ← Must have this
       selectedPage = 'About';
     });
   },
   ```

2. **Variable name is correct:** Check spelling of `selectedPage`

3. **_buildContent() uses correct variable:**
   ```dart
   Widget _buildContent() {
     if (selectedPage == 'Home') {  // ← Check variable name
       return ...
     }
     return Text('Coming soon: $selectedPage');
   }
   ```

---

### Error 6: YAML parsing error in pubspec.yaml

**Problem:** Invalid YAML syntax.

**Common issues:**

```yaml
# ❌ WRONG - incorrect indentation
flutter:
uses-material-design: true

# ❌ WRONG - missing dash before path
flutter:
  assets:
    lib/assets/images/

# ❌ WRONG - mixed tabs and spaces
flutter:
    assets:  ← Tab used here
  - lib/assets/images/  ← Spaces used here

# ✅ CORRECT
flutter:
  uses-material-design: true
  
  assets:
    - lib/assets/images/
```

**Rules:**
- Use spaces, not tabs
- Consistent 2-space indentation
- Dash (-) before each list item
- No extra spaces at line ends

---

## Understanding Key Concepts

### 1. Navigation Patterns: Drawer vs Routes

**This app uses: Drawer with conditional rendering**
```dart
Widget _buildContent() {
  if (selectedPage == 'Home') return HomeContent();
  if (selectedPage == 'About') return AboutContent();
  // ...
}
```

**Alternative: Named Routes**
```dart
Navigator.pushNamed(context, '/about');
```

**When to use each:**

| Use Drawer + Conditional | Use Named Routes |
|--------------------------|------------------|
| Simple apps (2-5 pages) | Complex apps (10+ pages) |
| Shared layout | Different layouts per page |
| Quick page switching | Deep navigation needed |
| Less memory usage | Better for large apps |

**Our app:** Drawer + Conditional is perfect because:
- Only 4 pages
- All pages share same layout (app bar, drawer)
- Fast switching without animation overhead

### 2. Understanding BuildContext

**What is BuildContext?**
A handle to the location of a widget in the widget tree.

**Why it matters:**
Some methods need context to find parent widgets:
- `Scaffold.of(context)` → Find nearest Scaffold
- `Navigator.of(context)` → Find nearest Navigator
- `Theme.of(context)` → Find theme data

**The Builder Problem Explained:**

```dart
Widget build(BuildContext context) {  // Context A (too high)
  return Scaffold(
    appBar: AppBar(
      leading: IconButton(
        onPressed: () {
          Scaffold.of(context);  // ❌ Uses Context A (can't find Scaffold)
        },
      ),
    ),
  );
}
```

**Context A** is from the build method - it's ABOVE Scaffold in the tree, so it can't see Scaffold.

**Solution:**
```dart
Widget build(BuildContext context) {  // Context A
  return Scaffold(
    appBar: AppBar(
      leading: Builder(
        builder: (BuildContext context) {  // Context B (lower)
          return IconButton(
            onPressed: () {
              Scaffold.of(context);  // ✅ Uses Context B (can find Scaffold)
            },
          );
        },
      ),
    ),
  );
}
```

**Context B** is from Builder - it's BELOW Scaffold, so it can see Scaffold above it.

**Visual tree:**
```
build context A
    ↓
Scaffold ← This is what we want to find
    ↓
AppBar
    ↓
Builder
    ↓
builder context B ← This can see Scaffold
    ↓
IconButton
```

### 3. Asset Management Best Practices

**Folder organization:**

**Good structure:**
```
lib/
├── assets/
│   ├── images/
│   │   ├── profile.jpg
│   │   ├── project1.png
│   │   └── logo.png
│   ├── icons/
│   │   ├── skill_flutter.png
│   │   └── skill_dart.png
│   └── fonts/  (if using custom fonts)
│       └── CustomFont.ttf
└── main.dart
```

**Declaration in pubspec.yaml:**
```yaml
flutter:
  assets:
    - lib/assets/images/
    - lib/assets/icons/
```

**Path in code:**
```dart
Image.asset('lib/assets/images/profile.jpg')
```

**Tips:**
- Keep assets organized in folders
- Use descriptive names
- Compress images before adding (reduce file size)
- Support multiple resolutions (2x, 3x) for sharp images

---

## Next Steps

### 🎯 Challenges to Try

#### Beginner Challenges
1. **Change your name and title** in the drawer header and home page
2. **Try different Google Fonts:**
   - Roboto, Montserrat, Lato, OpenSans
3. **Change color scheme:**
   - Try Colors.purple or Colors.green instead of Colors.blue
4. **Add your actual profile picture**

#### Intermediate Challenges
5. **Build the About page content:**
   - Add your bio
   - List your education
   - Show your experience

6. **Build the Skills page:**
   - Create a list of your skills
   - Add icons for each skill
   - Show proficiency levels

7. **Build the Contact page:**
   - Add email, phone, social media links
   - Create a simple contact form
   - Add clickable email/phone buttons

8. **Add more drawer items:**
   - Projects/Portfolio section
   - Certifications
   - Blog or Articles

#### Advanced Challenges
9. **Implement actual navigation:**
   - Convert to named routes
   - Add smooth page transitions
   - Implement back button handling

10. **Add animations:**
    - Animate profile picture on home
    - Fade in content when switching pages
    - Add hero animations

11. **Make it responsive:**
    - Different layouts for tablets
    - Adjust font sizes based on screen
    - Hide/show drawer based on screen width

12. **Add interactivity:**
    - Implement the download resume functionality
    - Add clickable project cards
    - Create an image gallery

---

### 📚 Additional Learning Resources

#### Official Documentation
- [Navigation Drawer Guide](https://docs.flutter.dev/cookbook/design/drawer)[1]
- [Google Fonts Package](https://pub.dev/packages/google_fonts)[2]
- [Asset Management](https://docs.flutter.dev/ui/assets-and-images)


---

## Summary: What You Built

### Architecture Overview

```
SimplePortfolioApp (StatelessWidget)
└── MaterialApp
    └── HomePage (StatefulWidget)
        └── _HomePageState
            ├── State Variables:
            │   ├── selectedPage (String)
            │   └── _scrollController (ScrollController)
            ├── Lifecycle:
            │   ├── initState()
            │   └── dispose()
            ├── Methods:
            │   └── _buildContent()
            └── UI (build method):
                ├── AppBar
                │   ├── leading: Builder → IconButton
                │   └── title: Text (GoogleFonts)
                ├── drawer: Drawer
                │   └── ListView
                │       ├── DrawerHeader
                │       ├── ListTile (Home)
                │       ├── ListTile (About)
                │       ├── ListTile (Skills)
                │       ├── ListTile (Contact)
                │       ├── Divider
                │       └── ListTile (Download)
                └── body: SingleChildScrollView
                    └── _buildContent() result
```

### Key Takeaways

1. ✅ **Navigation Drawer** provides intuitive app navigation[1]
2. ✅ **Google Fonts** makes professional typography easy[2]
3. ✅ **Asset management** requires proper setup in pubspec.yaml
4. ✅ **Builder widget** solves context-related issues
5. ✅ **ScrollController** enables advanced scrolling features[3]
6. ✅ **Conditional rendering** (`if` statements) can manage multiple pages
7. ✅ **setState()** is still the key to updating UI

---

## Troubleshooting Checklist

Before asking for help, check:

- [ ] Did you run `flutter pub get` after adding dependencies?
- [ ] Is your profile.jpg file in the correct folder (lib/assets/images/)?
- [ ] Did you declare assets in pubspec.yaml with correct indentation?
- [ ] Did you import google_fonts package?
- [ ] Is Builder widget wrapping the menu IconButton?
- [ ] Did you initialize ScrollController in initState()?
- [ ] Did you dispose ScrollController in dispose()?
- [ ] Are you using setState() when changing selectedPage?
- [ ] Did you hot restart (not just hot reload) after asset changes?

---

## Conclusion

Excellent work! 🎉 You've built a professional portfolio app with navigation. You now understand:

- Navigation Drawer implementation
- External package usage (Google Fonts)
- Asset management and display
- BuildContext and Builder widget
- ScrollController usage
- Multi-page state management
- Professional UI patterns


You're now ready to build more complex apps with multiple pages and professional styling!

---

## References

[1] Flutter Documentation. (2025). Add a Drawer to a screen. Retrieved from https://docs.flutter.dev/cookbook/design/drawer

[2] Educative. (2024). How to use Google Fonts in Flutter. Retrieved from https://www.educative.io/answers/how-to-use-google-fonts-in-flutter

[3] DhiWise. (2025). How to Integrate a Flutter SingleChildScrollView in Your App. Retrieved from https://www.dhiwise.com/post/how-to-implement-a-flutter-singlechildscrollview-in-your-app

---

**Created by:** Romark Cacho
**Date:** February 11, 2026  
**Course:** Fundamentals of Mobile Programming  
**Version:** 1.0

**Need Help?** Review each module carefully. Type the code yourself. Understanding the 'why' is more important than memorizing the 'how'!

---

## Appendix A: Complete Code Structure Reference

For your reference, here's the complete file structure:

```
1. Imports
   ├── import 'package:flutter/material.dart';
   └── import 'package:google_fonts/google_fonts.dart';

2. Main Function
   └── void main() { runApp(const SimplePortfolioApp()); }

3. SimplePortfolioApp (StatelessWidget)
   └── Returns MaterialApp with theme

4. HomePage (StatefulWidget)
   └── Creates _HomePageState

5. _HomePageState (State<HomePage>)
   ├── State variables
   │   ├── selectedPage
   │   └── _scrollController
   ├── initState()
   ├── _buildContent()
   ├── build()
   │   └── Returns Scaffold
   │       ├── appBar (with Builder)
   │       ├── drawer (with ListView)
   │       └── body (SingleChildScrollView)
   └── dispose()
```

**Remember:** Structure is learned through building, not memorizing!

---

**End of Portfolio App Tutorial**
