<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Course: Building a Simple Professional Portfolio with Flutter Web

## **Module 4: State Management \& dispose() in Action**

Welcome to Module 4, student! Now you'll see WHY we converted to StatefulWidget. You'll add a state variable, use setState() to change it, and see dispose() actually clean up resources. Everything line by line!

***

### **Lesson 4.1: Understanding What We'll Build**

**Objective:** Understand state management before implementing it

**What We'll Add:**

**1. State Variable (to track current page):**

```dart
String selectedPage = 'Home';  // Stores which page is active
```

**2. setState() Usage (to change pages):**

```dart
setState(() {
  selectedPage = 'About';  // Changes variable AND rebuilds
});
```

**3. Conditional Display (show different content):**

```dart
if (selectedPage == 'Home') {
  // Show profile
} else if (selectedPage == 'About') {
  // Show about content
}
```

**The Flow:**

```
User taps "About" in menu
        ↓
onTap() runs
        ↓
setState(() { selectedPage = 'About'; })
        ↓
State variable changes
        ↓
Flutter calls build() again
        ↓
build() checks: if (selectedPage == 'About')
        ↓
Shows About content instead of Home
        ↓
Screen updates!
```

**Expected Understanding:**

- State variable holds current page name
- setState() changes it AND triggers rebuild
- build() uses state variable to decide what to show
- This is the POWER of StatefulWidget!

***

### **Lesson 4.2: Adding State Variable - Line 1 (Find the right place)**

**Objective:** Locate where to add the state variable

**Instructions:**

1. Scroll to your `_HomePageState` class
2. Find the class declaration:
```dart
class _HomePageState extends State<HomePage> {
  @override
  Widget build(BuildContext context) {
```

**Understanding where variables go:**

```dart
class _HomePageState extends State<HomePage> {
  // ← State variables go HERE (before build method)
  
  @override
  Widget build(BuildContext context) {
    // ← NOT here (build runs multiple times)
  }
}
```

**Why BEFORE build()?**

- Variables before build() persist across rebuilds
- Variables inside build() get recreated each time
- State variables need to persist!

**Expected Understanding:**

- You found the right location
- Between class opening `{` and `@override`
- Ready to add state variable

***

### **Lesson 4.3: Adding State Variable - Line 2 (The variable)**

**Objective:** Add the selectedPage variable

**Instructions:**

1. **After** `class _HomePageState extends State<HomePage> {`
2. **Before** `@override`
3. **Type:**
```dart
String selectedPage = 'Home';
```

Your class should now look like:

```dart
class _HomePageState extends State<HomePage> {
  String selectedPage = 'Home';
  
  @override
  Widget build(BuildContext context) {
```

4. Save and hot reload

**What this does:**

- `String` = text data type
- `selectedPage` = variable name
- `= 'Home'` = initial value (starts on Home page)
- `;` = end of statement

**Understanding this line:**

```
String selectedPage = 'Home';
  ↑         ↑          ↑
  │         │          └─ Initial value
  │         └─ Variable name
  └─ Data type (text)
```

**Expected Output:**

- No visual changes yet
- Variable exists in memory
- Currently holds 'Home'
- Ready to be used in menu items

***

### **Lesson 4.4: Using setState() in Home Menu - Line 1 (Find Home onTap)**

**Objective:** Locate Home menu item's onTap function

**Instructions:**

1. Scroll down to your Home ListTile
2. Find the onTap section:
```dart
onTap: () {
  Navigator.pop(context);
  print('Home tapped');
},
```

**Understanding current behavior:**

- Closes drawer
- Prints message
- Does NOT change state
- Does NOT update screen

**Expected Understanding:**

- You found the Home menu's onTap
- Currently just closes drawer and prints
- We'll add setState() to change page

***

### **Lesson 4.5: Using setState() in Home Menu - Line 2 (Add setState)**

**Objective:** Add state change when Home is tapped

**Instructions:**

1. **After** the `Navigator.pop(context);` line
2. **Before** the `print('Home tapped');` line
3. **Type:**
```dart
setState(() {
```

4. Press Enter after `{`

Your onTap should look like:

```dart
onTap: () {
  Navigator.pop(context);
  setState(() {
  print('Home tapped');
},
```

**Don't save yet!**

**What this does:**

- `setState()` = tells Flutter "state is changing, rebuild UI"
- `() {` = anonymous function (what changes go inside)
- Everything inside `{}` will change state

***

### **Lesson 4.6: Using setState() in Home Menu - Line 3 (Change variable)**

**Objective:** Actually change the selectedPage variable

**Instructions:**

1. **Inside** the setState function (after the `{`)
2. **Before** the print line
3. **Type:**
```dart
selectedPage = 'Home';
```

Your code should look like:

```dart
onTap: () {
  Navigator.pop(context);
  setState(() {
    selectedPage = 'Home';
  print('Home tapped');
},
```

**Don't save yet!**

**What this does:**

- Changes `selectedPage` variable to 'Home'
- Inside setState, so Flutter knows to rebuild
- Variable change + rebuild = screen updates!

**Understanding setState():**

```
setState(() {
  selectedPage = 'Home';  // ← Change happens here
});
        ↓
Flutter detects change
        ↓
Calls build() again
        ↓
build() sees selectedPage = 'Home'
        ↓
Shows Home content
```


***

### **Lesson 4.7: Using setState() in Home Menu - Line 4 (Close setState)**

**Objective:** Properly close the setState function

**Instructions:**

1. Find the `print('Home tapped');` line
2. **Move it** OUTSIDE (after) the setState function
3. **Add closing** for setState:

Your onTap should look like:

```dart
onTap: () {
  Navigator.pop(context);
  setState(() {
    selectedPage = 'Home';
  });
  print('Home tapped');
},
```

4. Save and hot reload

**What you did:**

- Moved print OUTSIDE setState (print doesn't need to be inside)
- Added `});` to close setState

**Understanding the structure:**

```dart
setState(() {
  selectedPage = 'Home';  // ← Only state changes inside
});
print('Home tapped');  // ← Other code outside
```

**Expected Output:**

- No visual changes yet
- No errors
- State changes when Home is tapped
- Ready to add to other menu items

***

### **Lesson 4.8: Adding setState() to About Menu - Line 1**

**Objective:** Update About menu to use state

**Instructions:**

1. Find your About ListTile's onTap
2. **After** `Navigator.pop(context);`
3. **Type these lines:**
```dart
setState(() {
  selectedPage = 'About';
});
```

Your About onTap should look like:

```dart
onTap: () {
  Navigator.pop(context);
  setState(() {
    selectedPage = 'About';
  });
  print('About tapped');
},
```

4. Save and hot reload

**What this does:**

- Changes selectedPage to 'About'
- Triggers rebuild
- Prepares to show About content (we'll add that next)

***

### **Lesson 4.9: Adding setState() to Skills Menu**

**Objective:** Update Skills menu to use state

**Instructions:**

1. Find Skills ListTile's onTap
2. **Add after** `Navigator.pop(context);`:
```dart
setState(() {
  selectedPage = 'Skills';
});
```

Your Skills onTap:

```dart
onTap: () {
  Navigator.pop(context);
  setState(() {
    selectedPage = 'Skills';
  });
  print('Skills tapped');
},
```

4. Save and hot reload

***

### **Lesson 4.10: Adding setState() to Contact Menu**

**Objective:** Update Contact menu to use state

**Instructions:**

1. Find Contact ListTile's onTap
2. **Add after** `Navigator.pop(context);`:
```dart
setState(() {
  selectedPage = 'Contact';
});
```

Your Contact onTap:

```dart
onTap: () {
  Navigator.pop(context);
  setState(() {
    selectedPage = 'Contact';
  });
  print('Contact tapped');
},
```

4. Save and hot reload

**Expected Output:**

- All 4 menu items now use setState()
- Each changes selectedPage to different value
- State is being tracked!
- Next: use state to show different content

***

### **Lesson 4.11: Testing State Changes - Console Check**

**Objective:** Verify state is actually changing

**Instructions:**

1. **Add a debug print** in your build method to see state
2. Find the start of your build method:
```dart
@override
Widget build(BuildContext context) {
```

3. **Right after that line, add:**
```dart
print('Building with selectedPage: $selectedPage');
```

4. Save and hot reload

**Testing:**

1. Open console (F12)
2. Click Home in menu
3. Click About in menu
4. Click Skills in menu
5. Look at console

**Expected Output:**

- Each menu click prints:
    - "Building with selectedPage: Home"
    - "Building with selectedPage: About"
    - "Building with selectedPage: Skills"
- Proves state is changing!
- Proves build() runs each time!
- setState() is working! 🎉

**Remove the debug print after testing** (it was just for learning)

***

### **Lesson 4.12: Creating Content Widget Method - Line 1**

**Objective:** Prepare to show different content based on state

**Instructions:**

1. Scroll to the bottom of your `_HomePageState` class
2. **After** the `build()` method's closing `}`
3. **Before** the `dispose()` method
4. **Type:**
```dart
Widget _buildContent() {
```

5. Press Enter after `{`

**Don't save yet!**

**What this does:**

- Creates a helper method to build content
- `Widget` = returns a widget
- `_buildContent` = method name (underscore = private)
- `()` = no parameters needed

**Understanding helper methods:**

```
build() {
  return Scaffold(
    body: _buildContent(),  ← Calls this method
  );
}

Widget _buildContent() {
  // Returns different content based on selectedPage
}
```


***

### **Lesson 4.13: Creating Content Widget Method - Line 2 (if statement)**

**Objective:** Check which page is selected

**Instructions:**

1. Inside `_buildContent()`, **type:**
```dart
if (selectedPage == 'Home') {
```

2. Press Enter after `{`

**Don't save yet!**

**What this does:**

- `if` = conditional statement
- `selectedPage == 'Home'` = checks if variable equals 'Home'
- `==` = comparison (double equals tests equality)
- If true, code inside `{}` runs

***

### **Lesson 4.14: Creating Content Widget Method - Line 3 (return Home content)**

**Objective:** Return profile content when Home is selected

**Instructions:**

1. Inside the if block, **type:**
```dart
return Column(
```

2. Press Enter

**Don't save yet!**

**What this does:**

- `return` = gives back this widget to whoever called the method
- `Column` = the profile content (picture, name, title)
- We'll move your existing profile Column here

***

### **Lesson 4.15: Understanding What We Need to Move**

**Objective:** Understand the structure change

**Current Structure:**

```dart
body: Padding(
  child: Center(
    child: Column(  ← Your profile content is here
      children: [
        ClipOval(...),  // Picture
        Text(...),      // Name
        Text(...),      // Title
      ],
    ),
  ),
),
```

**New Structure:**

```dart
body: Padding(
  child: Center(
    child: _buildContent(),  ← Calls method
  ),
),

Widget _buildContent() {
  if (selectedPage == 'Home') {
    return Column(...);  ← Profile content moves here
  } else if (selectedPage == 'About') {
    return Text('About content');  ← New content
  }
  // etc.
}
```

**Why This Helps:**

- Clean separation of concerns
- Easy to add new pages
- build() method stays simple
- Content logic in one place

**Expected Understanding:**

- We're reorganizing, not adding new features yet
- Profile content will move to _buildContent method
- Next lessons will do this move carefully

***

### **Lesson 4.16: Moving Profile Content - Step 1 (Copy Column properties)**

**Objective:** Start moving the Column to _buildContent

**Instructions:**

1. Find your current Column in the body:
```dart
child: Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
```

2. In your `_buildContent()` method, complete the Column:
```dart
return Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
```

**Don't save yet!**

***

### **Lesson 4.17: Moving Profile Content - Step 2 (Copy children)**

**Objective:** Copy all profile widgets to _buildContent

**Instructions:**

This is a bigger step. You need to copy your profile content:

1. **Copy** these lines from your body's Column:
    - ClipOval with profile picture
    - SizedBox(height: 16)
    - Text with your name
    - SizedBox(height: 8)
    - Text with your title
2. **Paste** them inside the `children: [` in _buildContent
3. **Close** the Column:
```dart
],
);
```

4. **Close** the if block:
```dart
}
```

Your `_buildContent` method should now look like:

```dart
Widget _buildContent() {
  if (selectedPage == 'Home') {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        ClipOval(...),  // Your profile picture
        SizedBox(height: 16),
        Text(...),  // Your name
        SizedBox(height: 8),
        Text(...),  // Your title
      ],
    );
  }
}
```

**Don't save yet! Need to add else case.**

***

### **Lesson 4.18: Adding Default Return - Line 1**

**Objective:** Handle other pages (About, Skills, Contact)

**Instructions:**

1. **After** the closing `}` of the if block
2. **Type:**
```dart
return Text('Coming soon: $selectedPage');
```

3. **Close** the method:
```dart
}
```

Your complete `_buildContent()`:

```dart
Widget _buildContent() {
  if (selectedPage == 'Home') {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        ClipOval(...),
        SizedBox(height: 16),
        Text(...),
        SizedBox(height: 8),
        Text(...),
      ],
    );
  }
  return Text('Coming soon: $selectedPage');
}
```

**Don't save yet!**

**What this does:**

- If selectedPage is NOT 'Home', shows temporary message
- `$selectedPage` = inserts variable value into text
- So if About is selected: "Coming soon: About"

***

### **Lesson 4.19: Using _buildContent in build() Method**

**Objective:** Replace body Column with method call

**Instructions:**

1. Scroll up to your build() method
2. Find the body section:
```dart
body: Padding(
  padding: EdgeInsets.all(20),
  child: Center(
    child: Column(  ← Find this
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        // All your profile content
      ],
    ),
  ),
),
```

3. **Replace** the entire Column (from `Column(` to its closing `)`) with:
```dart
child: _buildContent(),
```

Your body should now look like:

```dart
body: Padding(
  padding: EdgeInsets.all(20),
  child: Center(
    child: _buildContent(),
  ),
),
```

4. **NOW save and hot reload!**

**Expected Output:**

- Home page looks EXACTLY the same (profile, name, title)
- Click menu items and test:
    - Home → shows profile
    - About → shows "Coming soon: About"
    - Skills → shows "Coming soon: Skills"
    - Contact → shows "Coming soon: Contact"
- State-based content switching works! 🎉

***

### **Lesson 4.20: Testing State-Based Navigation**

**Objective:** Verify everything works with state

**Complete Testing:**

1. **Start on Home:**
    - [ ] Profile picture visible?
    - [ ] Name and title visible?
2. **Switch to About:**
    - [ ] Click About in menu
    - [ ] Shows "Coming soon: About"?
    - [ ] Profile content gone?
3. **Switch to Skills:**
    - [ ] Click Skills
    - [ ] Shows "Coming soon: Skills"?
4. **Switch back to Home:**
    - [ ] Click Home
    - [ ] Profile comes back?
    - [ ] Everything restored?
5. **Try all menu items:**
    - [ ] Each shows different content?
    - [ ] Smooth transitions?

**Expected Output:**

- All checkboxes ✓
- State management working!
- Content changes based on menu selection
- This is StatefulWidget in action!

***

## ✅ **Mid-Module Checkpoint**

**What You've Accomplished:**

**State Management:**

- ✓ Added state variable: `String selectedPage = 'Home'`
- ✓ Used setState() in all menu items
- ✓ State changes trigger rebuilds
- ✓ Content changes based on state

**Code Organization:**

- ✓ Created `_buildContent()` helper method
- ✓ Moved profile content to method
- ✓ Clean separation of concerns

**Lines Added:** ~30 lines

**Total Project Lines:** ~160 lines!

**What Works:**

- Click Home → shows profile
- Click About/Skills/Contact → shows "Coming soon" message
- State-based navigation working perfectly

***

## **Next: dispose() in Action**

Now we'll add a ScrollController (for future scrolling features) and see dispose() actually clean it up!

**Lesson 4.21:** Add ScrollController variable
**Lesson 4.22:** Initialize it (see why we need it)
**Lesson 4.23:** Use it in body
**Lesson 4.24:** Dispose it properly
**Lesson 4.25:** Test dispose() is actually called

***

**Ready to see dispose() in action?** Reply **"Continue"** 🚀

**You're Mastering State:**

- ✓ State variables
- ✓ setState() usage
- ✓ Conditional rendering
- ✓ Real state management! 💪⚡

