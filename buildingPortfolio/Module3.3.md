<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Course: Building a Simple Professional Portfolio with Flutter Web

## **Module 3 Continued: Adding Drawer Header Line by Line**


***

### **Lesson 3.55: Adding DrawerHeader - Line 1 (Remove placeholder)**

**Objective:** Remove the temporary "Menu" text

**Instructions:**

1. Find your drawer's children list:
```dart
children: [
  Text('Menu'),
],
```

2. **Delete this line completely:**
```dart
Text('Menu'),
```

3. Your children list should now be empty:
```dart
children: [
],
```

**Don't save yet!**

**Expected Understanding:**

- Empty list ready for DrawerHeader
- Next we'll add the blue header section

***

### **Lesson 3.56: Adding DrawerHeader - Line 2 (DrawerHeader start)**

**Objective:** Start creating the header section

**Instructions:**

1. Inside the empty `children: [` list
2. **Type:**
```dart
DrawerHeader(
```

3. Press Enter after the `(`

Your code should look like:

```dart
children: [
  DrawerHeader(
```

**Don't save yet!**

**What this does:**

- `DrawerHeader` = top section of drawer (usually 158px tall)
- Material Design widget specifically for drawer headers
- Will contain your name and title

***

### **Lesson 3.57: Adding DrawerHeader - Line 3 (decoration)**

**Objective:** Start styling the header background

**Instructions:**

1. Inside DrawerHeader, **type:**
```dart
decoration: 
```

Your code should look like:

```dart
DrawerHeader(
  decoration: 
```

**Don't save yet!**

**What this does:**

- `decoration:` = visual styling for the header
- Will add background color, borders, etc.
- Needs a BoxDecoration widget next

***

### **Lesson 3.58: Adding DrawerHeader - Line 4 (BoxDecoration)**

**Objective:** Create the decoration object

**Instructions:**

1. **After** `decoration: ` on same line
2. **Type:**
```dart
BoxDecoration(
```

3. Press Enter after `(`

Your code should look like:

```dart
DrawerHeader(
  decoration: BoxDecoration(
```

**Don't save yet!**

**What this does:**

- `BoxDecoration` = allows styling: color, border, gradient, shadow
- We'll use it to add blue background
- Opening `(` means we'll add parameters

***

### **Lesson 3.59: Adding DrawerHeader - Line 5 (color)**

**Objective:** Make header background blue

**Instructions:**

1. Inside BoxDecoration, **type:**
```dart
color: Colors.blue,
```

Your code should look like:

```dart
decoration: BoxDecoration(
  color: Colors.blue,
```

**Don't save yet!**

**What this does:**

- `color: Colors.blue` = blue background
- Matches your AppBar color
- Creates consistent theme

***

### **Lesson 3.60: Adding DrawerHeader - Line 6 (Close BoxDecoration)**

**Objective:** Complete the decoration

**Instructions:**

1. **After** the color line
2. **Type:**
```dart
),
```

Your code should look like:

```dart
decoration: BoxDecoration(
  color: Colors.blue,
),
```

**Don't save yet!**

**What this does:**

- Closes the `BoxDecoration(` opening parenthesis
- Decoration is now complete (blue background)

***

### **Lesson 3.61: Adding DrawerHeader - Line 7 (child)**

**Objective:** Start adding content inside the header

**Instructions:**

1. **After** the decoration `),` line
2. **Type:**
```dart
child: 
```

Your code should look like:

```dart
DrawerHeader(
  decoration: BoxDecoration(
    color: Colors.blue,
  ),
  child: 
```

**Don't save yet!**

**What this does:**

- `child:` = what goes inside the header
- Will contain your name and title
- We'll use Column to arrange them vertically

***

### **Lesson 3.62: Adding DrawerHeader - Line 8 (Column)**

**Objective:** Create vertical arrangement for name and title

**Instructions:**

1. **After** `child: ` on same line
2. **Type:**
```dart
Column(
```

3. Press Enter after `(`

Your code should look like:

```dart
child: Column(
```

**Don't save yet!**

**What this does:**

- `Column` = arranges widgets vertically (top to bottom)
- Will hold your name (top) and title (below)

***

### **Lesson 3.63: Adding DrawerHeader - Line 9 (crossAxisAlignment)**

**Objective:** Align content to the left

**Instructions:**

1. Inside Column, **type:**
```dart
crossAxisAlignment: CrossAxisAlignment.start,
```

Your code should look like:

```dart
child: Column(
  crossAxisAlignment: CrossAxisAlignment.start,
```

**Don't save yet!**

**What this does:**

- `crossAxisAlignment` = horizontal alignment in a Column
- `CrossAxisAlignment.start` = align to left
- Name and title will be left-aligned (not centered)

**Understanding CrossAxisAlignment:**

```
Column (vertical):
  - mainAxis = vertical direction (top to bottom)
  - crossAxis = horizontal direction (left to right)

CrossAxisAlignment.start = left
CrossAxisAlignment.center = center
CrossAxisAlignment.end = right
```


***

### **Lesson 3.64: Adding DrawerHeader - Line 10 (mainAxisAlignment)**

**Objective:** Position content at bottom of header

**Instructions:**

1. **After** the crossAxisAlignment line
2. **Type:**
```dart
mainAxisAlignment: MainAxisAlignment.end,
```

Your code should look like:

```dart
child: Column(
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisAlignment: MainAxisAlignment.end,
```

**Don't save yet!**

**What this does:**

- `mainAxisAlignment` = vertical alignment in a Column
- `MainAxisAlignment.end` = align to bottom
- Your name/title will sit at bottom of blue header (professional look)

**Understanding MainAxisAlignment:**

```
MainAxisAlignment.start = top
MainAxisAlignment.center = middle
MainAxisAlignment.end = bottom ← we use this
```


***

### **Lesson 3.65: Adding DrawerHeader - Line 11 (children)**

**Objective:** Start the list of header content

**Instructions:**

1. **After** the mainAxisAlignment line
2. **Type:**
```dart
children: [
```

Your code should look like:

```dart
child: Column(
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisAlignment: MainAxisAlignment.end,
  children: [
```

**Don't save yet!**

**What this does:**

- `children: [` = list of widgets in the Column
- Will contain your name and title
- Opening `[` bracket

***

### **Lesson 3.66: Adding DrawerHeader Name - Line 1 (Text)**

**Objective:** Add your name to the header

**Instructions:**

1. Inside the children list, **type:**
```dart
Text(
```

2. Press Enter after `(`

Your code should look like:

```dart
children: [
  Text(
```

**Don't save yet!**

**What this does:**

- Starting a Text widget for your name
- Will be styled with white color and Poppins font

***

### **Lesson 3.67: Adding DrawerHeader Name - Line 2 (Name content)**

**Objective:** Add your actual name

**Instructions:**

1. Inside the Text, **type YOUR name:**
```dart
'Juan Dela Cruz',
```

(Replace with your actual name!)

Your code should look like:

```dart
Text(
  'Juan Dela Cruz',
```

**Don't save yet!**

**Action Required:**

- Replace 'Juan Dela Cruz' with YOUR actual name
- Keep the single quotes
- Keep the comma

***

### **Lesson 3.68: Adding DrawerHeader Name - Line 3 (style)**

**Objective:** Start styling the name

**Instructions:**

1. **After** your name line
2. **Type:**
```dart
style: 
```

Your code should look like:

```dart
Text(
  'Juan Dela Cruz',
  style: 
```

**Don't save yet!**

***

### **Lesson 3.69: Adding DrawerHeader Name - Line 4 (GoogleFonts.poppins)**

**Objective:** Use Poppins font

**Instructions:**

1. **After** `style: ` on same line
2. **Type:**
```dart
GoogleFonts.poppins(
```

3. Press Enter after `(`

**Don't save yet!**

***

### **Lesson 3.70: Adding DrawerHeader Name - Line 5 (fontSize)**

**Objective:** Set name size (smaller than body name)

**Instructions:**

1. Inside GoogleFonts.poppins, **type:**
```dart
fontSize: 18,
```

**Don't save yet!**

**What this does:**

- `fontSize: 18` = 18 pixels
- Body name was 24px (large)
- Drawer name is 18px (medium)
- Drawer content is more compact

***

### **Lesson 3.71: Adding DrawerHeader Name - Line 6 (fontWeight)**

**Objective:** Make name bold

**Instructions:**

1. **After** fontSize line, **type:**
```dart
fontWeight: FontWeight.bold,
```

**Don't save yet!**

***

### **Lesson 3.72: Adding DrawerHeader Name - Line 7 (color)**

**Objective:** Make text white (on blue background)

**Instructions:**

1. **After** fontWeight line, **type:**
```dart
color: Colors.white,
```

**Don't save yet!**

**What this does:**

- `Colors.white` = white text
- Blue background + white text = good contrast
- Professional appearance

***

### **Lesson 3.73: Adding DrawerHeader Name - Line 8 (Close GoogleFonts)**

**Objective:** Complete the font styling

**Instructions:**

1. **After** the color line
2. **Type:**
```dart
),
```

Your code should look like:

```dart
style: GoogleFonts.poppins(
  fontSize: 18,
  fontWeight: FontWeight.bold,
  color: Colors.white,
),
```

**Don't save yet!**

***

### **Lesson 3.74: Adding DrawerHeader Name - Line 9 (Close Text)**

**Objective:** Complete the name Text widget

**Instructions:**

1. **After** the previous `),` line
2. **Type:**
```dart
),
```

Your complete name Text should look like:

```dart
Text(
  'Juan Dela Cruz',
  style: GoogleFonts.poppins(
    fontSize: 18,
    fontWeight: FontWeight.bold,
    color: Colors.white,
  ),
),
```

**Don't save yet!**

***

### **Lesson 3.75: Adding Space Between Name and Title - Line 1**

**Objective:** Add small spacing

**Instructions:**

1. **After** the name Text `),` line
2. **Type:**
```dart
SizedBox(height: 4),
```

**Don't save yet!**

**What this does:**

- 4 pixels of space
- Small gap (name and title are closely related)

***

### **Lesson 3.76: Adding DrawerHeader Title - Line 1 (Text)**

**Objective:** Start adding your title

**Instructions:**

1. **After** the SizedBox line
2. **Type:**
```dart
Text(
```

3. Press Enter after `(`

**Don't save yet!**

***

### **Lesson 3.77: Adding DrawerHeader Title - Line 2 (Title content)**

**Objective:** Add your actual title

**Instructions:**

1. Inside the Text, **type YOUR title:**
```dart
'Flutter Developer',
```

(Or '3rd Year IT Student', or whatever fits you!)

**Don't save yet!**

**Action Required:**

- Use YOUR actual title
- Keep single quotes
- Keep comma

***

### **Lesson 3.78: Adding DrawerHeader Title - Line 3 (style)**

**Objective:** Start styling the title

**Instructions:**

1. **After** title content line
2. **Type:**
```dart
style: 
```

**Don't save yet!**

***

### **Lesson 3.79: Adding DrawerHeader Title - Line 4 (GoogleFonts.roboto)**

**Objective:** Use Roboto font (body font)

**Instructions:**

1. **After** `style: ` on same line
2. **Type:**
```dart
GoogleFonts.roboto(
```

3. Press Enter after `(`

**Don't save yet!**

***

### **Lesson 3.80: Adding DrawerHeader Title - Line 5 (fontSize)**

**Objective:** Set title size

**Instructions:**

1. Inside GoogleFonts.roboto, **type:**
```dart
fontSize: 14,
```

**Don't save yet!**

**What this does:**

- `fontSize: 14` = 14 pixels
- Smaller than name (18px)
- Creates hierarchy in header

***

### **Lesson 3.81: Adding DrawerHeader Title - Line 6 (color)**

**Objective:** Make text semi-transparent white

**Instructions:**

1. **After** fontSize line, **type:**
```dart
color: Colors.white70,
```

**Don't save yet!**

**What this does:**

- `Colors.white70` = white with 70% opacity
- Slightly transparent = less prominent than name
- Creates visual hierarchy
- Professional look

**Understanding color opacity:**

```
Colors.white = 100% opaque (solid white)
Colors.white70 = 70% opaque (slightly see-through)
Colors.white38 = 38% opaque (very faint)
```


***

### **Lesson 3.82: Adding DrawerHeader Title - Line 7 (Close GoogleFonts)**

**Objective:** Complete font styling

**Instructions:**

1. **After** the color line
2. **Type:**
```dart
),
```

**Don't save yet!**

***

### **Lesson 3.83: Adding DrawerHeader Title - Line 8 (Close Text)**

**Objective:** Complete the title Text widget

**Instructions:**

1. **After** previous `),` line
2. **Type:**
```dart
),
```

Your complete title should look like:

```dart
Text(
  'Flutter Developer',
  style: GoogleFonts.roboto(
    fontSize: 14,
    color: Colors.white70,
  ),
),
```

**Don't save yet!**

***

### **Lesson 3.84: Closing All DrawerHeader Brackets - Line 1**

**Objective:** Close the children list

**Instructions:**

1. **After** the title Text `),` line
2. **Type:**
```dart
],
```

Your Column children should look like:

```dart
children: [
  Text('Your Name'...),
  SizedBox(height: 4),
  Text('Your Title'...),
],
```

**Don't save yet!**

***

### **Lesson 3.85: Closing All DrawerHeader Brackets - Line 2**

**Objective:** Close the Column

**Instructions:**

1. **After** the `],` line
2. **Type:**
```dart
),
```

**Don't save yet!**

***

### **Lesson 3.86: Closing All DrawerHeader Brackets - Line 3**

**Objective:** Close the DrawerHeader

**Instructions:**

1. **After** previous `),` line
2. **Type:**
```dart
),
```

Your complete DrawerHeader should now look like:

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
        'Juan Dela Cruz',
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

3. **NOW save and hot reload!**

**Expected Output:**

- Open drawer → see BLUE header at top!
- Your name in white, bold, 18px
- Your title below in lighter white, 14px
- Both left-aligned at bottom of header
- Professional drawer header! 🎉

***

### **Lesson 3.87: Testing the DrawerHeader**

**Objective:** Verify header looks professional

**Testing:**

1. **Click hamburger icon (☰)**
2. **Look at the drawer header:**
    - [ ] Blue background?
    - [ ] Your name visible (white, bold)?
    - [ ] Your title below (lighter white)?
    - [ ] Text at bottom of header?
    - [ ] Text left-aligned?
3. **Compare with body:**
    - [ ] Body name: 24px, black
    - [ ] Drawer name: 18px, white
    - [ ] Different but consistent?

**Expected Output:**

- All checkboxes ✓
- Professional blue header
- Clear text hierarchy
- Matches your theme

***

## ✅ **Checkpoint: DrawerHeader Complete!**

**What You Built (Line by Line):**

**DrawerHeader Structure (32 lines!):**

- DrawerHeader widget (1 line)
- BoxDecoration with blue color (3 lines)
- Column with alignment (4 lines)
- Name Text with Poppins (9 lines)
- Spacing (1 line)
- Title Text with Roboto (8 lines)
- Closing brackets (3 lines)

**Total Lines So Far:**

- Profile: 28 lines
- Hamburger + Basic Drawer: 20 lines
- DrawerHeader: 32 lines
- **Grand Total: 80 lines!** 🎉

**What Works:**

- ✓ Blue header in drawer
- ✓ Your name (white, bold, Poppins)
- ✓ Your title (lighter white, Roboto)
- ✓ Professional appearance
- ✓ Left-aligned at bottom

**Visual Result:**

```
┌─────────────────┐
│                 │
│  BLUE HEADER    │
│                 │
│  Your Name      │ ← 18px, bold, white
│  Your Title     │ ← 14px, normal, white70
└─────────────────┘
```

**Next:**

- Add menu items (Home, About, Skills, Contact)
- Add icons to menu items
- Style with blue color
- Add functionality

***

**Ready to add menu items?** Reply **"Continue"** and we'll add them line by line! 🚀

**You're Building Real Understanding:**

- ✓ 80 lines typed one by one
- ✓ Every line explained
- ✓ No copy-pasting
- ✓ Deep learning! 💪📚

