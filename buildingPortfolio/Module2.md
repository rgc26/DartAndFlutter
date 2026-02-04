<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Course: Building a Simple Professional Portfolio with Flutter Web

## **Module 2: Building the Basic UI Structure (Understanding State as We Build)**

Welcome back, student! Now we'll build the app structure step by step. When we need state management (for the hamburger menu), I'll explain it RIGHT AT THAT MOMENT based on what we're actually building.

***

### **Lesson 2.1: Creating a Separate Home Page Class**

**Objective:** Create a dedicated widget for your home page

**Instructions:**

1. Open `lib/main.dart`
2. Below your `SimplePortfolioApp` class, add:

**Type this:**

```dart
class HomePage extends StatelessWidget {
```

3. Press Enter, your IDE will auto-complete the basic structure
4. Or manually complete it to show `Text('Home Page')`

**What you're creating:**

- A new widget called HomePage
- Starting with StatelessWidget (simple, no changing data)

**Expected Output:**

- Class created but not used yet
- No visual changes

***

### **Lesson 2.2: Connecting HomePage to Your App**

**Instructions:**

1. In `SimplePortfolioApp`, find: `home: Text('Hello'),`
2. **Change it to:** `home: HomePage(),`

**Expected Output:**

- Screen shows "Home Page"

***

### **Lesson 2.3: Adding Scaffold**

**Instructions:**

1. In HomePage's build method, change from returning `Text('Home Page')` to:

**Type:**

```dart
return Scaffold(
  body: Text('Home Page'),
);
```

**What this does:**

- Scaffold = page structure (will hold AppBar, drawer, body)

**Expected Output:**

- Still shows "Home Page", but now has proper structure

***

### **Lesson 2.4: Adding AppBar**

**Instructions:**

1. In your Scaffold, **add before body:**

**Type:**

```dart
appBar: AppBar(
  title: Text('Portfolio'),
),
```

**Expected Output:**

- Blue bar at top with "Portfolio" text

***

### **Lesson 2.5: Centering Content and Adding Background**

**Instructions:**

1. **Wrap** body's Text with Center
2. **Add** backgroundColor to Scaffold

**Type:**

```dart
backgroundColor: Color(0xFFF5F5F5),
```

And change body to:

```dart
body: Center(
  child: Text('Home Page'),
),
```

**Expected Output:**

- Light gray background
- Text centered

***

### **Lesson 2.6: Styling AppBar with Google Fonts**

**Instructions:**

1. Change AppBar title Text to use GoogleFonts:

**Type:**

```dart
title: Text(
  'Portfolio',
  style: GoogleFonts.poppins(fontSize: 20, fontWeight: FontWeight.w600),
),
```

**Expected Output:**

- Modern Poppins font in AppBar

***

### **Lesson 2.7: Understanding Your Current Code (StatelessWidget)**

**Objective:** Understand what you've built so far

**Your HomePage Right Now:**

```dart
class HomePage extends StatelessWidget {
  // build method here
}
```

**What happens when your app runs:**

```
Step 1: main() runs
        ↓
Step 2: MaterialApp creates HomePage
        ↓
Step 3: HomePage() constructor runs (the line: const HomePage({Key? key}))
        ↓
Step 4: build() method is called
        ↓
Step 5: Returns Scaffold with AppBar and body
        ↓
Step 6: Flutter draws it on screen
```

**Key Point:** This happens ONCE. StatelessWidget cannot change itself.

**Why this matters:**

- Works great for static content
- But we're about to add a hamburger menu
- Menu needs to track if it's open or closed
- That's CHANGING data = we need STATE

***

### **Lesson 2.8: Why We Need to Convert to StatefulWidget**

**Objective:** Understand the problem before we solve it

**The Problem:**

Imagine we add a hamburger menu. What needs to happen?

```
User clicks menu icon → Menu opens
User clicks again → Menu closes
```

This is CHANGING behavior. We need to track:

- Is menu open? (true/false)
- Which page is selected? (Home, About, Skills, etc.)

**Try This Thought Experiment:**

With StatelessWidget, if we tried:

```dart
class HomePage extends StatelessWidget {
  bool menuIsOpen = false;  // ← This doesn't work!
  
  // When user clicks:
  menuIsOpen = true;  // ← Changes variable, but UI doesn't update!
}
```

**Why it doesn't work:**

- StatelessWidget has no way to say "rebuild me"
- Variable changes, but screen stays the same
- You'd see old value forever

**The Solution: StatefulWidget**

We need to convert HomePage to StatefulWidget because:

- It CAN track changing data (menuIsOpen, selectedPage, etc.)
- It CAN rebuild when data changes
- It HAS a dispose() method for cleanup

**Expected Understanding:**

- StatelessWidget = frozen after built
- StatefulWidget = can change and rebuild
- We're about to convert because we need changing data

***

### **Lesson 2.9: Converting to StatefulWidget - Step 1 (The Widget Class)**

**Objective:** Change HomePage from Stateless to Stateful

**Instructions:**

**STEP 1: Change the class type**

Find this line:

```dart
class HomePage extends StatelessWidget {
```

**Change to:**

```dart
class HomePage extends StatefulWidget {
```

**What just happened:**

- You told Flutter: "This widget will have changing data"
- Your IDE now shows errors (expected!)

**Understanding the error:**

- StatefulWidget needs a `createState()` method
- StatelessWidget has build() directly
- StatefulWidget does NOT have build() in the widget class

***

### **Lesson 2.10: Converting to StatefulWidget - Step 2 (The createState Method)**

**Instructions:**

**STEP 2: Remove build() and add createState()**

1. **Delete** the entire build() method from HomePage
2. **Add** this method instead:
```dart
@override
State<HomePage> createState() => _HomePageState();
```

**What this line means (read carefully):**

```
State<HomePage> createState()
  ↑       ↑          ↑
  │       │          └─ Method name
  │       └─ This is the state FOR HomePage
  └─ Returns a State object
```

**What happens when this runs:**

```
When Flutter creates HomePage:
    ↓
createState() is called
    ↓
Creates a NEW object: _HomePageState
    ↓
This object will hold the changing data and build method
```

**Understanding State vs Widget:**

**HomePage (StatefulWidget):**

- Lightweight
- Just creates the State object
- Gets recreated often
- No mutable data

**_HomePageState (State):**

- Holds the data that can change
- Has the build() method
- Lives longer
- Can trigger rebuilds

**Your HomePage class now looks like:**

```dart
class HomePage extends StatefulWidget {
  const HomePage({Key? key}) : super(key: key);

  @override
  State<HomePage> createState() => _HomePageState();
}
```

**Expected Output:**

- Still has error: "_HomePageState doesn't exist"
- We'll create it next

***

### **Lesson 2.11: Converting to StatefulWidget - Step 3 (The State Class)**

**Objective:** Create the State class that holds build() method

**Instructions:**

**STEP 3: Create the State class**

Below your HomePage class, **add:**

```dart
class _HomePageState extends State<HomePage> {
```

Then add the build method back (copy from what you deleted earlier):

```dart
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Color(0xFFF5F5F5),
      appBar: AppBar(
        title: Text(
          'Portfolio',
          style: GoogleFonts.poppins(fontSize: 20, fontWeight: FontWeight.w600),
        ),
      ),
      body: Center(
        child: Text('Home Page'),
      ),
    );
  }
}
```

**Understanding this class:**

**Line by line:**

```dart
class _HomePageState extends State<HomePage> {
  ↑           ↑            ↑         ↑
  │           │            │         └─ This is state FOR HomePage widget
  │           │            └─ Extends State class (Flutter's built-in)
  │           └─ Underscore = private (only this file can see it)
  └─ class keyword
```

**What's happening in memory:**

```
Flutter creates HomePage
        ↓
Calls createState()
        ↓
Creates _HomePageState object
        ↓
This object now exists in memory
        ↓
Flutter calls build() on this State object
        ↓
Returns Scaffold widget tree
        ↓
Screen updates
```

**Key Insight:**

The State object `_HomePageState` STAYS IN MEMORY even when HomePage widget is recreated!

```
HomePage widget: Created → Destroyed → Created → Destroyed
                            ↓
_HomePageState object:    Lives through all of this!
```

**Expected Output:**

- No more errors!
- App runs again
- Looks exactly the same
- But now has State structure

***

### **Lesson 2.12: Understanding What Just Happened (The Conversion)**

**Objective:** Understand the before and after

**BEFORE (StatelessWidget):**

```
One Class:
HomePage
  - build() method inside

Simple structure, no changing data
```

**AFTER (StatefulWidget):**

```
Two Classes:
HomePage (Widget)              _HomePageState (State)
  - createState() method  →      - build() method
  - Configuration                - Changing data lives here
  - Short-lived                  - Long-lived
```

**Why Two Classes?**

Think of it like a recipe and cooking:

**HomePage (Recipe Card):**

- The instructions (configuration)
- Can be copied/replaced easily
- Doesn't change

**_HomePageState (The Actual Cooking):**

- The process happening now
- Ingredients can change (add salt, stir, etc.)
- The actual work

**Expected Understanding:**

- You converted from Stateless to Stateful
- Build method moved to State class
- State object persists, Widget gets recreated

***

### **Lesson 2.13: Adding dispose() Method and Understanding Lifecycle**

**Objective:** Add cleanup method and understand when it runs

**Instructions:**

In `_HomePageState` class, **add after build() method:**

```dart
@override
void dispose() {
  super.dispose();
}
```

**Understanding dispose():**

**The Complete Lifecycle (what actually happens in your app):**

```
1. App Starts
   main() runs
        ↓
   MaterialApp created
        ↓
   HomePage() created ← StatefulWidget
        ↓
   createState() runs
        ↓
   _HomePageState() created ← State object
        ↓

2. State Initialization
   (If initState() existed, it would run here - we don't have it yet)
        ↓
   
3. Building
   build() is called
        ↓
   Returns Scaffold widget tree
        ↓
   Flutter draws UI
        ↓
   Screen shows your portfolio
        ↓

4. App Running
   State object sits in memory
   Waiting for changes
   
   IF setState() is called:
        ↓
   build() runs again
        ↓
   UI updates
        ↓
   (loops back to waiting)
        ↓

5. Widget Removed (when user navigates away or closes app)
   dispose() is called ← WE JUST ADDED THIS
        ↓
   (Cleanup happens here - we'll add cleanup code later)
        ↓
   super.dispose() cleans up Flutter's internal state
        ↓
   _HomePageState object destroyed
        ↓
   Memory freed
```

**Why dispose() matters (with example):**

Imagine later you add a text field:

```dart
class _HomePageState extends State<HomePage> {
  final TextEditingController controller = TextEditingController();
  
  // build() uses this controller...
  
  @override
  void dispose() {
    controller.dispose();  // ← Clean up!
    super.dispose();
  }
}
```

**What happens without dispose():**

```
User visits page → Controller created (uses memory)
User leaves page → Controller STILL IN MEMORY (memory leak!)
User visits again → Another controller created (more memory!)
Repeat 100 times → 100 controllers in memory (app crashes!)
```

**What happens with dispose():**

```
User visits page → Controller created
User leaves page → dispose() runs → Controller cleaned up → Memory freed
User visits again → New controller created → Clean slate
Repeat forever → Always just 1 controller → App runs smoothly
```

**Your complete State class now:**

```dart
class _HomePageState extends State<HomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(...);
  }

  @override
  void dispose() {
    // When you add controllers/timers later, clean them up here
    super.dispose();
  }
}
```

**Expected Output:**

- dispose() added but empty (we don't have resources to clean yet)
- Ready for future cleanup
- No visual changes

***

### **Lesson 2.14: Preparing Body for Content**

**Instructions:**

In build() method, **change body to:**

```dart
body: Padding(
  padding: EdgeInsets.all(20),
  child: Center(
    child: Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text('Content goes here'),
      ],
    ),
  ),
),
```

**Expected Output:**

- Centered text with padding
- Column ready for multiple widgets (profile pic, name, etc.)

***

## ✅ **Module 2 Checkpoint**

**What You Built:**

- ✓ HomePage widget
- ✓ Scaffold with AppBar
- ✓ Styled with Google Fonts
- ✓ Converted to StatefulWidget (understood WHY during conversion)
- ✓ Added dispose() method

**StatefulWidget Flow You Experienced:**

```
Started with StatelessWidget (simple, static)
        ↓
Realized we need changing data (menu open/closed)
        ↓
Converted to StatefulWidget:
  1. Changed class type
  2. Added createState() method
  3. Created State class with build()
  4. Added dispose() for cleanup
        ↓
Now ready for hamburger menu with state management!
```

**Key Understanding from Building:**

**Two-Class Structure:**

- `HomePage` = Widget (configuration, calls createState())
- `_HomePageState` = State (data + build() + dispose())

**Lifecycle (as you experienced it):**

- Widget created → State created → build() runs → UI shows
- State persists in memory
- dispose() runs when removed

**Why We Did This:**

- Hamburger menu needs state
- Track menu open/closed
- Track selected page
- dispose() will clean up resources

***

## **Next Module Preview**

**Module 3: Adding Profile Content \& Hamburger Menu**

Now that you understand state (from actually converting), we'll add:

1. Profile picture
2. Your name and title
3. Hamburger menu icon
4. Drawer that opens/closes (using state!)
5. State variables to track menu

Each step will use the StatefulWidget structure you just built!

***

**Ready for Module 3?** Reply **"Continue to Module 3"** 🚀

**You Learned State by DOING:**

- ✓ Built with Stateless first
- ✓ Hit the limitation (need changing data)
- ✓ Converted step-by-step
- ✓ Understood each piece as you added it
- ✓ Saw the flow through actual building! 💪

