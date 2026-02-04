<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Course: Building a Simple Professional Portfolio with Flutter Web

## **Module 3 Continued: Adding Menu Items Line by Line**


***

### **Lesson 3.88: Adding First Menu Item (Home) - Line 1**

**Objective:** Start adding the Home menu item

**Instructions:**

1. Find your drawer's ListView children list
2. You should see:
```dart
children: [
  DrawerHeader(...),
],
```

3. **After** the entire `DrawerHeader(...),` section
4. **Type:**
```dart
ListTile(
```

5. Press Enter after `(`

Your children list should look like:

```dart
children: [
  DrawerHeader(...),
  ListTile(
],
```

**Don't save yet!**

**What this does:**

- `ListTile` = pre-built widget for list items
- Perfect for menu items (has icon, text, tap functionality)
- Material Design widget specifically for lists/menus

***

### **Lesson 3.89: Adding Home Menu Item - Line 2 (leading)**

**Objective:** Start adding the icon on the left

**Instructions:**

1. Inside ListTile, **type:**
```dart
leading: 
```

**Don't save yet!**

**What this does:**

- `leading:` = widget shown on left side of ListTile
- Will contain the home icon (🏠)

***

### **Lesson 3.90: Adding Home Menu Item - Line 3 (Icon)**

**Objective:** Add the home icon

**Instructions:**

1. **After** `leading: ` on same line
2. **Type:**
```dart
Icon(Icons.home),
```

Your code should look like:

```dart
ListTile(
  leading: Icon(Icons.home),
```

**Don't save yet!**

**What this does:**

- `Icon()` = displays an icon
- `Icons.home` = house icon (🏠)
- Will appear on left of "Home" text

***

### **Lesson 3.91: Adding Home Menu Item - Line 4 (title)**

**Objective:** Start adding the menu text

**Instructions:**

1. **After** the Icon line
2. **Type:**
```dart
title: 
```

Your code should look like:

```dart
ListTile(
  leading: Icon(Icons.home),
  title: 
```

**Don't save yet!**

**What this does:**

- `title:` = main text of the ListTile
- Will show "Home" next to the icon

***

### **Lesson 3.92: Adding Home Menu Item - Line 5 (Text)**

**Objective:** Add the word "Home"

**Instructions:**

1. **After** `title: ` on same line
2. **Type:**
```dart
Text('Home'),
```

Your code should look like:

```dart
ListTile(
  leading: Icon(Icons.home),
  title: Text('Home'),
```

**Don't save yet!**

**What this does:**

- `Text('Home')` = displays the word "Home"
- This is what user sees and taps

***

### **Lesson 3.93: Adding Home Menu Item - Line 6 (onTap)**

**Objective:** Start adding tap functionality

**Instructions:**

1. **After** the title line
2. **Type:**
```dart
onTap: () {
```

3. Press Enter after `{`

Your code should look like:

```dart
ListTile(
  leading: Icon(Icons.home),
  title: Text('Home'),
  onTap: () {
```

**Don't save yet!**

**What this does:**

- `onTap:` = function that runs when user taps this item
- `() {` = starts an anonymous function
- Inside we'll add what happens when tapped

***

### **Lesson 3.94: Adding Home Menu Item - Line 7 (Navigator.pop)**

**Objective:** Close the drawer when tapped

**Instructions:**

1. Inside the onTap function, **type:**
```dart
Navigator.pop(context);
```

Your code should look like:

```dart
onTap: () {
  Navigator.pop(context);
```

**Don't save yet!**

**What this does:**

- `Navigator.pop(context)` = closes the drawer
- `Navigator` = Flutter's navigation manager
- `.pop()` = removes top layer (the drawer)
- `context` = current location in widget tree

**Understanding Navigator.pop:**

```
Drawer is open (on top of screen)
        ↓
User taps "Home"
        ↓
Navigator.pop(context) runs
        ↓
Removes drawer layer
        ↓
Drawer slides closed
```


***

### **Lesson 3.95: Adding Home Menu Item - Line 8 (print)**

**Objective:** Add temporary action (for testing)

**Instructions:**

1. **After** Navigator.pop line
2. **Type:**
```dart
print('Home tapped');
```

Your code should look like:

```dart
onTap: () {
  Navigator.pop(context);
  print('Home tapped');
```

**Don't save yet!**

**What this does:**

- `print()` = shows message in console
- Helps us see that tap is working
- Later we'll replace this with actual navigation

***

### **Lesson 3.96: Adding Home Menu Item - Line 9 (Close function)**

**Objective:** Complete the onTap function

**Instructions:**

1. **After** the print line
2. **Type:**
```dart
},
```

Your code should look like:

```dart
onTap: () {
  Navigator.pop(context);
  print('Home tapped');
},
```

**Don't save yet!**

***

### **Lesson 3.97: Adding Home Menu Item - Line 10 (Close ListTile)**

**Objective:** Complete the Home menu item

**Instructions:**

1. **After** the `},` line
2. **Type:**
```dart
),
```

Your complete Home ListTile should now look like:

```dart
ListTile(
  leading: Icon(Icons.home),
  title: Text('Home'),
  onTap: () {
    Navigator.pop(context);
    print('Home tapped');
  },
),
```

3. **NOW save and hot reload!**

**Expected Output:**

- Open drawer → see blue header + "Home" item below!
- House icon (🏠) on left
- "Home" text next to icon
- Tap it → drawer closes + console shows "Home tapped"
- First menu item working! 🎉

***

### **Lesson 3.98: Testing the Home Menu Item**

**Objective:** Verify Home item works

**Testing:**

1. **Open drawer (click ☰)**
2. **Look at menu item:**
    - [ ] See house icon?
    - [ ] See "Home" text?
    - [ ] Icon and text aligned?
3. **Tap "Home":**
    - [ ] Drawer closes?
    - [ ] Smooth animation?
4. **Check console (F12):**
    - [ ] Shows "Home tapped"?

**Expected Output:**

- All checkboxes ✓
- Professional menu item
- Ready to add more items!

***

### **Lesson 3.99: Adding About Menu Item - Line 1**

**Objective:** Start second menu item

**Instructions:**

1. **After** the entire Home ListTile `),` line
2. **Type:**
```dart
ListTile(
```

3. Press Enter after `(`

**Don't save yet!**

***

### **Lesson 3.100: Adding About Menu Item - Line 2**

**Objective:** Add person icon

**Instructions:**

1. **Type:**
```dart
leading: Icon(Icons.person),
```

**Don't save yet!**

**What this does:**

- `Icons.person` = person icon (👤)
- Different icon for About (person represents profile/about)

***

### **Lesson 3.101: Adding About Menu Item - Line 3**

**Objective:** Add "About" text

**Instructions:**

1. **Type:**
```dart
title: Text('About'),
```

**Don't save yet!**

***

### **Lesson 3.102: Adding About Menu Item - Line 4**

**Objective:** Add tap function start

**Instructions:**

1. **Type:**
```dart
onTap: () {
```

2. Press Enter after `{`

**Don't save yet!**

***

### **Lesson 3.103: Adding About Menu Item - Line 5**

**Objective:** Close drawer

**Instructions:**

1. **Type:**
```dart
Navigator.pop(context);
```

**Don't save yet!**

***

### **Lesson 3.104: Adding About Menu Item - Line 6**

**Objective:** Add console message

**Instructions:**

1. **Type:**
```dart
print('About tapped');
```

**Don't save yet!**

***

### **Lesson 3.105: Adding About Menu Item - Line 7**

**Objective:** Close function

**Instructions:**

1. **Type:**
```dart
},
```

**Don't save yet!**

***

### **Lesson 3.106: Adding About Menu Item - Line 8**

**Objective:** Close ListTile

**Instructions:**

1. **Type:**
```dart
),
```

Your complete About item:

```dart
ListTile(
  leading: Icon(Icons.person),
  title: Text('About'),
  onTap: () {
    Navigator.pop(context);
    print('About tapped');
  },
),
```

2. **NOW save and hot reload!**

**Expected Output:**

- Open drawer → see Home AND About items!
- About has person icon (👤)
- Tap About → drawer closes, console shows message

***

### **Lesson 3.107: Adding Skills Menu Item - Line 1**

**Objective:** Start third menu item

**Instructions:**

1. **After** About ListTile, **type:**
```dart
ListTile(
```

2. Press Enter

**Don't save yet!**

***

### **Lesson 3.108: Adding Skills Menu Item - Line 2**

**Objective:** Add lightbulb icon

**Instructions:**

1. **Type:**
```dart
leading: Icon(Icons.lightbulb),
```

**Don't save yet!**

**What this does:**

- `Icons.lightbulb` = lightbulb icon (💡)
- Represents ideas/skills/knowledge

***

### **Lesson 3.109: Adding Skills Menu Item - Line 3**

**Objective:** Add "Skills" text

**Instructions:**

1. **Type:**
```dart
title: Text('Skills'),
```

**Don't save yet!**

***

### **Lesson 3.110: Adding Skills Menu Item - Lines 4-7**

**Objective:** Add complete onTap function

**Instructions:**

1. **Type these 4 lines:**
```dart
onTap: () {
  Navigator.pop(context);
  print('Skills tapped');
},
```

**Don't save yet!**

***

### **Lesson 3.111: Adding Skills Menu Item - Line 8**

**Objective:** Close ListTile

**Instructions:**

1. **Type:**
```dart
),
```

Your complete Skills item:

```dart
ListTile(
  leading: Icon(Icons.lightbulb),
  title: Text('Skills'),
  onTap: () {
    Navigator.pop(context);
    print('Skills tapped');
  },
),
```

2. Save and hot reload!

**Expected Output:**

- Three menu items now: Home, About, Skills
- Each with different icon
- All working

***

### **Lesson 3.112: Adding Contact Menu Item - Line 1**

**Objective:** Start fourth menu item

**Instructions:**

1. **After** Skills ListTile, **type:**
```dart
ListTile(
```

2. Press Enter

***

### **Lesson 3.113: Adding Contact Menu Item - Line 2**

**Objective:** Add email icon

**Instructions:**

1. **Type:**
```dart
leading: Icon(Icons.email),
```

**What this does:**

- `Icons.email` = envelope icon (✉️)
- Represents contact/email

***

### **Lesson 3.114: Adding Contact Menu Item - Lines 3-8**

**Objective:** Complete Contact item quickly

**Instructions:**

1. **Type these lines:**
```dart
title: Text('Contact'),
onTap: () {
  Navigator.pop(context);
  print('Contact tapped');
},
),
```

Your complete Contact item:

```dart
ListTile(
  leading: Icon(Icons.email),
  title: Text('Contact'),
  onTap: () {
    Navigator.pop(context);
    print('Contact tapped');
  },
),
```

2. Save and hot reload!

**Expected Output:**

- Four menu items: Home, About, Skills, Contact
- Each with unique icon
- All functional

***

### **Lesson 3.115: Adding Divider - Line 1**

**Objective:** Add separator before Download Resume

**Instructions:**

1. **After** Contact ListTile
2. **Type:**
```dart
Divider(),
```

3. Save and hot reload

**What this does:**

- `Divider()` = horizontal line
- Separates navigation items from action items
- Professional menu organization

**Expected Output:**

- Horizontal line appears after Contact
- Visual separation
- Ready for Download Resume

***

### **Lesson 3.116: Adding Download Resume Item - Line 1**

**Objective:** Start the download action item

**Instructions:**

1. **After** the Divider line
2. **Type:**
```dart
ListTile(
```

3. Press Enter

***

### **Lesson 3.117: Adding Download Resume Item - Line 2**

**Objective:** Add download icon

**Instructions:**

1. **Type:**
```dart
leading: Icon(Icons.download),
```

**What this does:**

- `Icons.download` = download arrow icon (⬇️)
- Indicates downloadable content

***

### **Lesson 3.118: Adding Download Resume Item - Lines 3-8**

**Objective:** Complete Download Resume item

**Instructions:**

1. **Type these lines:**
```dart
title: Text('Download Resume'),
onTap: () {
  Navigator.pop(context);
  print('Download Resume tapped');
},
),
```

Your complete Download Resume item:

```dart
ListTile(
  leading: Icon(Icons.download),
  title: Text('Download Resume'),
  onTap: () {
    Navigator.pop(context);
    print('Download Resume tapped');
  },
),
```

2. **NOW save and hot reload!**

**Expected Output:**

- Complete menu with 5 items!
- Divider before Download Resume
- All items working
- Professional drawer menu! 🎉

***

### **Lesson 3.119: Styling Menu Icons with Blue Color - Line 1**

**Objective:** Make Home icon blue

**Instructions:**

1. Find your Home ListTile's Icon line:
```dart
leading: Icon(Icons.home),
```

2. **Change to:**
```dart
leading: Icon(Icons.home, color: Colors.blue),
```

3. Save and hot reload

**What this does:**

- `color: Colors.blue` = makes icon blue
- Matches your theme (AppBar, header, name color)

**Expected Output:**

- Home icon is now blue instead of gray
- Matches theme color

***

### **Lesson 3.120: Styling Remaining Icons**

**Objective:** Make all icons blue for consistency

**Instructions:**

Apply same color to each Icon:

**About:**

```dart
leading: Icon(Icons.person, color: Colors.blue),
```

**Skills:**

```dart
leading: Icon(Icons.lightbulb, color: Colors.blue),
```

**Contact:**

```dart
leading: Icon(Icons.email, color: Colors.blue),
```

**Download Resume:**

```dart
leading: Icon(Icons.download, color: Colors.blue),
```

Save and hot reload after each change!

**Expected Output:**

- All 5 icons are blue
- Consistent theme throughout drawer
- Professional, cohesive design

***

### **Lesson 3.121: Final Testing - Complete Drawer**

**Objective:** Test everything works perfectly

**Complete Testing Checklist:**

1. **Visual Check:**
    - [ ] Blue header with your name and title
    - [ ] 5 menu items below header
    - [ ] All icons blue and visible
    - [ ] Divider line before Download Resume
    - [ ] Clean, professional layout
2. **Functionality Check:**
    - [ ] Click ☰ → drawer opens smoothly
    - [ ] Tap "Home" → drawer closes, console message
    - [ ] Tap "About" → drawer closes, console message
    - [ ] Tap "Skills" → drawer closes, console message
    - [ ] Tap "Contact" → drawer closes, console message
    - [ ] Tap "Download Resume" → drawer closes, console message
3. **Close Methods:**
    - [ ] Tap outside drawer → closes
    - [ ] Swipe left → closes
    - [ ] Press ESC → closes

**Expected Output:**

- All checkboxes ✓
- Professional hamburger menu complete!
- Ready for state management in Module 4!

***

## ✅ **Module 3 Complete!**

**What You've Built (Line by Line):**

**Profile Section:** 28 lines

- Circular profile picture
- Your name (Poppins, bold)
- Your title (Roboto, gray)

**Hamburger Menu:** 20 lines

- Hamburger icon in AppBar
- Basic drawer structure

**DrawerHeader:** 32 lines

- Blue header
- Name and title (white text)

**Menu Items:** 50 lines

- Home (🏠)
- About (👤)
- Skills (💡)
- Contact (✉️)
- Divider
- Download Resume (⬇️)
- All with blue icons
- All with tap functionality

**Grand Total: 130+ lines of code you typed one by one!** 🎉

**Your Complete Drawer:**

```
┌─────────────────────┐
│ BLUE HEADER         │
│ Your Name           │
│ Your Title          │
├─────────────────────┤
│ 🏠 Home             │
│ 👤 About            │
│ 💡 Skills           │
│ ✉️  Contact         │
├─────────────────────┤
│ ⬇️  Download Resume │
└─────────────────────┘
```

**Skills Mastered:**

- ✓ Building widgets line by line
- ✓ Understanding each line's purpose
- ✓ Widget nesting (ListTile, Icon, Text)
- ✓ Event handling (onTap)
- ✓ Navigation (Navigator.pop)
- ✓ Theming (consistent blue color)
- ✓ Layout (DrawerHeader, Divider)

***

## **Next Module Preview**

**Module 4: State Management \& dispose() in Action**

In Module 4, you'll:

1. Add state variable: `String selectedPage = 'Home';`
2. Use `setState()` to change pages
3. Show different content based on state
4. Highlight selected menu item
5. Add ScrollController (see dispose() in action!)
6. Clean up resources properly

You'll finally see StatefulWidget and dispose() being USED!

***

**Ready for Module 4?** Reply **"Continue to Module 4"** 🚀

**Incredible Work!**

- ✓ 130+ lines built line by line
- ✓ Complete understanding
- ✓ No copy-pasting
- ✓ Professional portfolio with hamburger menu! 💪🍔✨

