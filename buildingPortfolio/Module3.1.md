<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Course: Building a Simple Professional Portfolio with Flutter Web

## **Module 3 Continued: Adding Your Title Line by Line**


***

### **Lesson 3.20: Adding Your Title - Line 1 (Spacing)**

**Objective:** Add space between name and title

**Instructions:**

1. Find where your name Text widget ends (the last `),`)
2. **After** that closing bracket, press Enter
3. **Type:**
```dart
SizedBox(height: 8),
```

Your Column's children should now have:

```dart
children: [
  ClipOval(...),
  SizedBox(height: 16),
  Text('Your Name'...),
  SizedBox(height: 8),
],
```

4. Save and hot reload

**What this does:**

- `SizedBox(height: 8)` = 8 pixels of space
- Smaller than previous (16px) because name and title are related
- Creates visual grouping

**Expected Output:**

- Looks the same for now
- Space reserved below name
- Ready for title text

***

### **Lesson 3.21: Adding Your Title - Line 2 (Start Text)**

**Objective:** Begin the title text widget

**Instructions:**

1. **After** the `SizedBox(height: 8),` line
2. **Type:**
```dart
Text(
```

3. Press Enter after the `(`

**Don't save yet!**

**What you started:**

- Starting a new Text widget
- This will show your title/role

***

### **Lesson 3.22: Adding Your Title - Line 3 (The Title Content)**

**Objective:** Add your actual title text

**Instructions:**

1. On the line after `Text(`
2. **Type your title** (choose what fits you):
```dart
'3rd Year IT Student',
```

OR

```dart
'Flutter Developer',
```

OR

```dart
'Computer Science Student',
```

**Pick YOUR title and type it!**

**Don't save yet!**

**What this is:**

- Your professional title or student status
- Will appear below your name
- Use what describes you best

**Action Required:**

- Replace with YOUR actual title
- Keep the single quotes `'...'`
- Keep the comma `,` at the end

***

### **Lesson 3.23: Adding Your Title - Line 4 (style)**

**Objective:** Start styling the title

**Instructions:**

1. **After** your title line (with comma)
2. **Type:**
```dart
style: 
```

Your code should look like:

```dart
Text(
  '3rd Year IT Student',
  style: 
```

**Don't save yet!**

**What this does:**

- `style:` = parameter for text styling
- Title will have different style than name (smaller, different color)

***

### **Lesson 3.24: Adding Your Title - Line 5 (GoogleFonts.roboto)**

**Objective:** Use Roboto font (different from name)

**Instructions:**

1. **After** `style: ` on same line
2. **Type:**
```dart
GoogleFonts.roboto(
```

3. Press Enter after `(`

Your code should look like:

```dart
Text(
  '3rd Year IT Student',
  style: GoogleFonts.roboto(
```

**Don't save yet!**

**What this does:**

- `GoogleFonts.roboto(` = different font from Poppins
- Roboto = body text font (more neutral)
- Poppins was for heading (your name)
- Professional portfolios use 2 fonts: heading + body

**Understanding font pairing:**

```
Name (Poppins) = Display font, personality
Title (Roboto) = Body font, readable
```


***

### **Lesson 3.25: Adding Your Title - Line 6 (fontSize)**

**Objective:** Make title smaller than name

**Instructions:**

1. Inside GoogleFonts.roboto, **type:**
```dart
fontSize: 16,
```

**Don't save yet!**

**What this does:**

- `fontSize: 16` = 16 pixels tall
- Name was 24px (large)
- Title is 16px (medium)
- Creates hierarchy: name > title

**Visual hierarchy:**

```
Name:  24px (most prominent)
Title: 16px (secondary)
```


***

### **Lesson 3.26: Adding Your Title - Line 7 (color)**

**Objective:** Make title gray instead of black

**Instructions:**

1. **After** the `fontSize: 16,` line
2. **Type:**
```dart
color: Colors.grey[600],
```

**Don't save yet!**

**What this does:**

- `color:` = text color
- `Colors.grey[600]` = medium gray (not too light, not too dark)
- `[600]` = shade of gray (100=lightest, 900=darkest)
- Gray = less prominent than black name

**Understanding Colors.grey:**

```
Colors.grey[100] = very light gray (almost white)
Colors.grey[600] = medium gray ← we use this
Colors.grey[900] = very dark gray (almost black)
```


***

### **Lesson 3.27: Adding Your Title - Line 8 (Close GoogleFonts)**

**Objective:** Close the GoogleFonts.roboto

**Instructions:**

1. **After** the color line
2. **Type:**
```dart
),
```

Your code should now look like:

```dart
Text(
  '3rd Year IT Student',
  style: GoogleFonts.roboto(
    fontSize: 16,
    color: Colors.grey[600],
  ),
```

**Don't save yet!**

**What this does:**

- Closes the `GoogleFonts.roboto(` opening parenthesis
- Comma after for Flutter formatting

***

### **Lesson 3.28: Adding Your Title - Line 9 (Close Text)**

**Objective:** Complete the title Text widget

**Instructions:**

1. **After** the previous `),` line
2. **Type:**
```dart
),
```

Your complete title section should now look like:

```dart
Text(
  '3rd Year IT Student',
  style: GoogleFonts.roboto(
    fontSize: 16,
    color: Colors.grey[600],
  ),
),
```

3. **NOW save and hot reload**

**Expected Output:**

- Profile picture (circular)
- Your name (large, bold, black)
- 8px space
- Your title (medium, normal, gray)
- Everything centered
- Clear visual hierarchy! 🎉

***

### **Lesson 3.29: Testing Your Profile Section**

**Objective:** Verify the complete profile looks good

**Visual Check:**

Look at your screen. You should see:

1. **Profile Picture:**
    - [ ] Circular shape
    - [ ] 120 pixels size
    - [ ] Centered
    - [ ] No distortion
2. **Name:**
    - [ ] Large text (24px)
    - [ ] Bold weight
    - [ ] Black color
    - [ ] Poppins font (modern look)
3. **Title:**
    - [ ] Medium text (16px)
    - [ ] Normal weight (not bold)
    - [ ] Gray color (less prominent)
    - [ ] Roboto font (readable)
4. **Spacing:**
    - [ ] 16px between picture and name
    - [ ] 8px between name and title
    - [ ] Balanced appearance

**Expected Output:**

- All checkboxes ✓
- Professional profile section
- Clear hierarchy (picture > name > title)
- Ready for hamburger menu next!

***

### **Lesson 3.30: Understanding Your Complete Profile Code**

**Let's trace what you've built:**

```dart
children: [
  // SECTION 1: Profile Picture (9 lines)
  ClipOval(
    child: Image.asset(
      'assets/images/profile.jpg',
      width: 120,
      height: 120,
      fit: BoxFit.cover,
    ),
  ),
  
  // SECTION 2: Space (1 line)
  SizedBox(height: 16),
  
  // SECTION 3: Name (8 lines)
  Text(
    'Your Name',
    style: GoogleFonts.poppins(
      fontSize: 24,
      fontWeight: FontWeight.bold,
    ),
  ),
  
  // SECTION 4: Space (1 line)
  SizedBox(height: 8),
  
  // SECTION 5: Title (9 lines)
  Text(
    '3rd Year IT Student',
    style: GoogleFonts.roboto(
      fontSize: 16,
      color: Colors.grey[600],
    ),
  ),
],
```

**Total: 28 lines built line by line!**

**The Visual Hierarchy:**

```
       [Profile Photo]    ← Circular, 120px
            ↓ 16px
      YOUR NAME HERE      ← 24px, bold, black, Poppins
            ↓ 8px
   3rd Year IT Student    ← 16px, normal, gray, Roboto
```

**Font Pairing:**

- **Poppins** (name) = Geometric, modern, attention-grabbing
- **Roboto** (title) = Neutral, readable, professional

**Color Hierarchy:**

- **Black** (name) = Most important
- **Gray** (title) = Secondary information

***

## ✅ **Module 3 Profile Section Complete!**

**What You've Accomplished:**

**Lines of Code:** 28 lines (typed one by one!)

**Widgets Used:**

1. ClipOval (makes circular shape)
2. Image.asset (loads image)
3. SizedBox (creates spacing)
4. Text (shows text)
5. GoogleFonts (professional typography)

**Concepts Mastered:**

- ✓ Widget nesting (ClipOval wraps Image)
- ✓ Image parameters (width, height, fit)
- ✓ Text styling (font, size, weight, color)
- ✓ Visual hierarchy (size + weight + color)
- ✓ Font pairing (Poppins + Roboto)
- ✓ Spacing (SizedBox for layout)

***

## **Next Section: Building the Hamburger Menu**

Now we'll add the hamburger menu, line by line:

**Lesson 3.31:** Add hamburger icon to AppBar (3 lines)
**Lesson 3.32:** Add IconButton properties (5 lines)
**Lesson 3.33:** Create empty Drawer (3 lines)
**Lesson 3.34:** Add ListView structure (4 lines)
**Lesson 3.35:** Add DrawerHeader (12 lines)
**Lesson 3.36:** Add menu items one at a time (each item = 6 lines)

Same careful approach - no copy-pasting!

***

**Ready to build the menu?** Reply **"Continue"** and we'll add the hamburger icon line by line! 🍔

**You're Building Real Skills:**

- ✓ Understanding each line
- ✓ No copy-paste
- ✓ Building muscle memory
- ✓ Deep learning! 💪

