<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Course: Building a Simple Professional Portfolio with Flutter Web

## **Module 3 Continued: Building the Hamburger Menu Line by Line**


***

### **Lesson 3.31: Adding Hamburger Icon - Line 1 (Find AppBar)**

**Objective:** Locate where to add the hamburger icon

**Instructions:**

1. Scroll up in your `_HomePageState` class
2. Find your `appBar: AppBar(` section
3. Look at the current structure:
```dart
appBar: AppBar(
  title: Text(
    'Portfolio',
    style: GoogleFonts.poppins(...),
  ),
),
```

**Understanding AppBar structure:**

Right now your AppBar only has `title`. We'll add `leading` (left side icon).

**Expected Understanding:**

- AppBar can have multiple properties
- `leading:` goes on the left side
- `title:` is in the center (what you have)
- We'll add leading before title

***

### **Lesson 3.32: Adding Hamburger Icon - Line 2 (leading)**

**Objective:** Start adding the left side icon

**Instructions:**

1. **After** `appBar: AppBar(` line
2. **Before** the `title:` line
3. **Type:**
```dart
leading: 
```

Your AppBar should now look like:

```dart
appBar: AppBar(
  leading: 
  title: Text(
```

**Don't save yet! You'll get an error.**

**What this does:**

- `leading:` = left side of AppBar
- This is where hamburger icon will go
- Needs a widget after it (we'll add IconButton next)

***

### **Lesson 3.33: Adding Hamburger Icon - Line 3 (IconButton start)**

**Objective:** Start creating the icon button

**Instructions:**

1. **After** `leading: ` on the same line
2. **Type:**
```dart
IconButton(
```

3. Press Enter after the `(`

Your code should look like:

```dart
appBar: AppBar(
  leading: IconButton(
  title: Text(
```

**Don't save yet!**

**What this does:**

- `IconButton` = tappable icon widget
- Opening `(` means we'll add parameters
- Parameters will be: icon (what icon) and onPressed (what happens when clicked)

***

### **Lesson 3.34: Adding Hamburger Icon - Line 4 (icon parameter)**

**Objective:** Specify which icon to show

**Instructions:**

1. Inside IconButton, **type:**
```dart
icon: 
```

Your code should look like:

```dart
leading: IconButton(
  icon: 
```

**Don't save yet!**

**What this does:**

- `icon:` = parameter that specifies which icon to display
- Needs an Icon widget next

***

### **Lesson 3.35: Adding Hamburger Icon - Line 5 (Icon widget)**

**Objective:** Add the hamburger menu icon

**Instructions:**

1. **After** `icon: ` on the same line
2. **Type:**
```dart
Icon(Icons.menu),
```

Your code should look like:

```dart
leading: IconButton(
  icon: Icon(Icons.menu),
```

**Don't save yet!**

**What this does:**

- `Icon()` = widget that displays an icon
- `Icons.menu` = the hamburger icon (☰)
- `Icons` is Flutter's built-in icon collection
- `.menu` is the specific icon (three horizontal lines)

**Understanding Icons.menu:**

```
Icons.menu = ☰ (hamburger icon)
Icons.home = 🏠 (house icon)
Icons.person = 👤 (person icon)
Icons.email = ✉️ (email icon)
```


***

### **Lesson 3.36: Adding Hamburger Icon - Line 6 (onPressed)**

**Objective:** Define what happens when icon is tapped

**Instructions:**

1. **After** the `Icon(Icons.menu),` line
2. Press Enter to create new line
3. **Type:**
```dart
onPressed: () {
```

4. Press Enter after the `{`

Your code should look like:

```dart
leading: IconButton(
  icon: Icon(Icons.menu),
  onPressed: () {
```

**Don't save yet!**

**What this does:**

- `onPressed:` = function that runs when button is clicked
- `() {` = starts an anonymous function (function without a name)
- Inside `{}` we'll put what happens when clicked

**Understanding () {}:**

```
onPressed: () {
  ↑      ↑  ↑
  │      │  └─ Opening brace (function body starts)
  │      └─ Empty parentheses (function takes no parameters)
  └─ Parameter name
```


***

### **Lesson 3.37: Adding Hamburger Icon - Line 7 (print statement)**

**Objective:** Add temporary action (print to console)

**Instructions:**

1. Inside the `onPressed: () {` function
2. **Type:**
```dart
print('Menu clicked');
```

Your code should look like:

```dart
onPressed: () {
  print('Menu clicked');
```

**Don't save yet!**

**What this does:**

- `print()` = shows message in console
- Temporary - we'll replace this when we add the drawer
- Good for testing that button works

***

### **Lesson 3.38: Adding Hamburger Icon - Line 8 (Close function)**

**Objective:** Close the onPressed function

**Instructions:**

1. **After** the print line
2. **Type:**
```dart
},
```

Your code should look like:

```dart
onPressed: () {
  print('Menu clicked');
},
```

**Don't save yet!**

**What this does:**

- `}` closes the function opening `{`
- `,` comma required by Flutter formatting
- Function is now complete

***

### **Lesson 3.39: Adding Hamburger Icon - Line 9 (Close IconButton)**

**Objective:** Complete the IconButton widget

**Instructions:**

1. **After** the `},` line
2. **Type:**
```dart
),
```

Your complete IconButton should now look like:

```dart
leading: IconButton(
  icon: Icon(Icons.menu),
  onPressed: () {
    print('Menu clicked');
  },
),
```

3. **NOW save and hot reload**

**Expected Output:**

- Hamburger icon (☰) appears on LEFT side of AppBar
- "Portfolio" title moves to center
- Blue AppBar with white hamburger icon
- Click icon → console shows "Menu clicked"

***

### **Lesson 3.40: Testing the Hamburger Icon**

**Objective:** Verify the icon works

**Testing:**

1. **Look at your AppBar:**
    - [ ] Do you see ☰ icon on left?
    - [ ] Is "Portfolio" title in center?
    - [ ] Is icon white on blue background?
2. **Click the hamburger icon**
3. **Open DevTools console** (F12, then Console tab)
4. **Check:**
    - [ ] Does console show "Menu clicked"?
5. **Click multiple times:**
    - [ ] Each click prints a new message?

**Expected Output:**

- All checkboxes ✓
- Icon is tappable
- Console shows messages
- Ready to add actual drawer next!

***

### **Lesson 3.41: Understanding What You Built**

**Line-by-line recap:**

```dart
leading:              ← Line 1: Left side of AppBar
  IconButton(         ← Line 2: Tappable icon button
    icon:             ← Line 3: Specify which icon
      Icon(Icons.menu), ← Line 4: Hamburger icon (☰)
    onPressed: () {   ← Line 5: Function when clicked
      print('Menu clicked'); ← Line 6: Temporary action
    },                ← Line 7: Close function
  ),                  ← Line 8: Close IconButton
```

**Total: 8 lines added!**

**What each part does:**

**IconButton:** Makes icon tappable
**Icon(Icons.menu):** Shows ☰ symbol
**onPressed:** Defines click behavior
**print():** Shows console message (temporary)

**Next:** We'll replace `print('Menu clicked')` with code to open the drawer!

***

### **Lesson 3.42: Creating Drawer - Line 1 (Find Scaffold)**

**Objective:** Locate where to add the drawer

**Instructions:**

1. Scroll down in your code
2. Find your `Scaffold` widget
3. Currently looks like:
```dart
return Scaffold(
  backgroundColor: Color(0xFFF5F5F5),
  appBar: AppBar(...),
  body: Padding(...),
);
```

**Understanding Scaffold properties:**

Scaffold can have:

- `backgroundColor` ✓ (you have this)
- `appBar` ✓ (you have this)
- `drawer` ← (we'll add this)
- `body` ✓ (you have this)

**Expected Understanding:**

- drawer property goes BETWEEN appBar and body
- It defines the side menu panel

***

### **Lesson 3.43: Creating Drawer - Line 2 (drawer property)**

**Objective:** Start adding the drawer

**Instructions:**

1. **After** the entire `appBar: AppBar(...),` section
2. **Before** the `body: Padding(...)` line
3. **Type:**
```dart
drawer: 
```

Your Scaffold should look like:

```dart
return Scaffold(
  backgroundColor: Color(0xFFF5F5F5),
  appBar: AppBar(...),
  drawer: 
  body: Padding(...),
);
```

**Don't save yet!**

**What this does:**

- `drawer:` = defines a side panel (drawer)
- Will slide in from left when hamburger is clicked
- Needs a Drawer widget next

***

### **Lesson 3.44: Creating Drawer - Line 3 (Drawer widget)**

**Objective:** Create the Drawer widget

**Instructions:**

1. **After** `drawer: ` on the same line
2. **Type:**
```dart
Drawer(
```

3. Press Enter after `(`

Your code should look like:

```dart
drawer: Drawer(
```

**Don't save yet!**

**What this does:**

- `Drawer()` = Material Design side panel widget
- Opening `(` means we'll add parameters
- Main parameter will be `child` (what's inside drawer)

***

### **Lesson 3.45: Creating Drawer - Line 4 (child)**

**Objective:** Start defining drawer contents

**Instructions:**

1. Inside Drawer, **type:**
```dart
child: 
```

Your code should look like:

```dart
drawer: Drawer(
  child: 
```

**Don't save yet!**

**What this does:**

- `child:` = what widget goes inside the drawer
- We'll add ListView next (to hold menu items)

***

### **Lesson 3.46: Creating Drawer - Line 5 (ListView)**

**Objective:** Add scrollable list for menu items

**Instructions:**

1. **After** `child: ` on the same line
2. **Type:**
```dart
ListView(
```

3. Press Enter after `(`

Your code should look like:

```dart
drawer: Drawer(
  child: ListView(
```

**Don't save yet!**

**What this does:**

- `ListView` = scrollable list widget
- Perfect for menus (can hold multiple items)
- Automatically scrolls if content is too long

***

### **Lesson 3.47: Creating Drawer - Line 6 (padding)**

**Objective:** Remove default padding from ListView

**Instructions:**

1. Inside ListView, **type:**
```dart
padding: EdgeInsets.zero,
```

Your code should look like:

```dart
drawer: Drawer(
  child: ListView(
    padding: EdgeInsets.zero,
```

**Don't save yet!**

**What this does:**

- `padding: EdgeInsets.zero` = no padding (0 on all sides)
- ListView has default padding
- We want our drawer header to touch the edges
- `EdgeInsets.zero` = top:0, right:0, bottom:0, left:0

**Understanding EdgeInsets:**

```
EdgeInsets.zero = no padding
EdgeInsets.all(20) = 20px padding on all sides
EdgeInsets.only(top: 10) = 10px only on top
```


***

### **Lesson 3.48: Creating Drawer - Line 7 (children)**

**Objective:** Start the list of menu items

**Instructions:**

1. **After** the padding line
2. **Type:**
```dart
children: [
```

Your code should look like:

```dart
drawer: Drawer(
  child: ListView(
    padding: EdgeInsets.zero,
    children: [
```

**Don't save yet!**

**What this does:**

- `children: [` = list of widgets to show in ListView
- `[` opens the list
- We'll add DrawerHeader and menu items inside
- Each item separated by comma

***

### **Lesson 3.49: Creating Drawer - Line 8 (Placeholder text)**

**Objective:** Add temporary content to see drawer working

**Instructions:**

1. Inside the `children: [` list
2. **Type:**
```dart
Text('Menu'),
```

Your code should look like:

```dart
children: [
  Text('Menu'),
```

**Don't save yet!**

**What this does:**

- Temporary text to test drawer
- We'll replace with DrawerHeader soon
- Helps us see that drawer works

***

### **Lesson 3.50: Creating Drawer - Line 9 (Close children)**

**Objective:** Close the children list

**Instructions:**

1. **After** the `Text('Menu'),` line
2. **Type:**
```dart
],
```

Your code should look like:

```dart
children: [
  Text('Menu'),
],
```

**Don't save yet!**

**What this does:**

- `]` closes the opening `[` from children
- `,` comma after for Flutter formatting

***

### **Lesson 3.51: Creating Drawer - Line 10 (Close ListView)**

**Objective:** Complete the ListView widget

**Instructions:**

1. **After** the `],` line
2. **Type:**
```dart
),
```

Your code should look like:

```dart
child: ListView(
  padding: EdgeInsets.zero,
  children: [
    Text('Menu'),
  ],
),
```

**Don't save yet!**

**What this does:**

- Closes the `ListView(` opening parenthesis

***

### **Lesson 3.52: Creating Drawer - Line 11 (Close Drawer)**

**Objective:** Complete the Drawer widget

**Instructions:**

1. **After** the previous `),` line
2. **Type:**
```dart
),
```

Your complete drawer should now look like:

```dart
drawer: Drawer(
  child: ListView(
    padding: EdgeInsets.zero,
    children: [
      Text('Menu'),
    ],
  ),
),
```

3. **NOW save and hot reload**

**Expected Output:**

- Click hamburger icon → drawer slides in from left!
- White panel appears
- Shows "Menu" text at top
- Tap outside drawer (gray area) → drawer closes
- Drawer working! 🎉

**But wait!** The drawer opens, but clicking the icon still prints to console instead of opening drawer. Let's fix that!

***

### **Lesson 3.53: Connecting Icon to Drawer - Line 1 (Change onPressed)**

**Objective:** Make hamburger icon actually open the drawer

**Instructions:**

1. Scroll up to your IconButton
2. Find this line inside onPressed:
```dart
print('Menu clicked');
```

3. **Delete that line completely**
4. **Replace with:**
```dart
Scaffold.of(context).openDrawer();
```

Your IconButton should now look like:

```dart
leading: IconButton(
  icon: Icon(Icons.menu),
  onPressed: () {
    Scaffold.of(context).openDrawer();
  },
),
```

5. Save and hot reload

**What this does:**

- `Scaffold.of(context)` = finds the nearest Scaffold widget
- `.openDrawer()` = tells that Scaffold to open its drawer
- Replaces the temporary print statement

**Understanding Scaffold.of(context):**

```
Scaffold.of(context).openDrawer();
    ↑         ↑           ↑
    │         │           └─ Open the drawer
    │         └─ Find Scaffold above this point
    └─ Scaffold class
```

**Expected Output:**

- Click hamburger icon → drawer slides in smoothly!
- No more console messages
- Drawer has "Menu" text
- Tap outside → drawer closes
- Swipe left → drawer closes
- Working hamburger menu! 🍔

***

### **Lesson 3.54: Testing the Drawer**

**Objective:** Verify drawer works correctly

**Testing:**

1. **Click hamburger icon (☰):**
    - [ ] Drawer slides in from left?
    - [ ] Smooth animation?
    - [ ] Shows "Menu" text?
2. **Close by tapping outside:**
    - [ ] Tap gray area (outside drawer)
    - [ ] Drawer slides closed?
3. **Close by swiping:**
    - [ ] Open drawer
    - [ ] Swipe left
    - [ ] Drawer closes?
4. **Open multiple times:**
    - [ ] Click icon again
    - [ ] Opens every time?

**Expected Output:**

- All checkboxes ✓
- Professional drawer behavior
- Ready to add header and menu items!

***

## ✅ **Checkpoint: Basic Drawer Complete!**

**What You've Built (Line by Line):**

**Hamburger Icon (9 lines):**

```dart
leading: IconButton(
  icon: Icon(Icons.menu),
  onPressed: () {
    Scaffold.of(context).openDrawer();
  },
),
```

**Drawer Structure (11 lines):**

```dart
drawer: Drawer(
  child: ListView(
    padding: EdgeInsets.zero,
    children: [
      Text('Menu'),
    ],
  ),
),
```

**Total: 20 lines added (one at a time)!**

**What Works:**

- ✓ Hamburger icon in AppBar
- ✓ Drawer slides in when clicked
- ✓ Drawer closes when tapped outside
- ✓ Professional behavior

**Next:**

- Add DrawerHeader (blue header with your name)
- Add menu items (Home, About, Skills, Contact)
- Style with icons and colors

***

**Ready to add the drawer header?** Reply **"Continue"** and we'll build it line by line! 🚀

**Lines Built So Far:**

- Profile section: 28 lines
- Hamburger + Drawer: 20 lines
- **Total: 48 lines of understood code!** 💪

