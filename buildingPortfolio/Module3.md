<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Course: Building a Simple Professional Portfolio with Flutter Web

## **Module 3: Adding Profile Content \& Hamburger Menu (Line by Line)**

Welcome back, student! Now we'll build everything ONE LINE AT A TIME. You'll type each line, understand it, see the result, then move to the next. No copy-pasting entire blocks!

***

### **Lesson 3.1: Adding Profile Picture - Line 1 (Remove Placeholder)**

**Objective:** Remove the placeholder text

**Instructions:**

1. Open `lib/main.dart`
2. Find this line in your Column's children:
```dart
Text('Content goes here'),
```

3. **Delete that entire line**
4. Save and hot reload

**Expected Output:**

- Empty centered space (Column has no children now)
- No errors
- Ready to add image

***

### **Lesson 3.2: Adding Profile Picture - Line 2 (Image.asset)**

**Objective:** Add the image loading line

**Instructions:**

1. Where you deleted the Text, **type this ONE line:**
```dart
Image.asset('assets/images/profile.jpg'),
```

2. Make sure:
    - It's inside the `children: [...]` brackets
    - It ends with a comma `,`
    - The path matches your image filename exactly
3. Save and hot reload

**What this line does:**

- `Image.asset()` = Flutter widget that loads images from assets
- `'assets/images/profile.jpg'` = path to your image
- Must match EXACTLY what's in your assets folder

**Expected Output:**

- Your profile picture appears!
- Might be HUGE (original file size)
- Centered on screen
- Next, we'll control the size

**Common Error:**

- Red error "Unable to load asset" → filename doesn't match
- Check: Is it profile.jpg or profile.png?
- Check: Capital letters? (Profile.jpg vs profile.jpg)

***

### **Lesson 3.3: Making Picture Circular - Line 1 (Add ClipOval Start)**

**Objective:** Start wrapping the image with ClipOval

**Instructions:**

1. **Place your cursor** at the very start of the line `Image.asset`
2. **Type:**
```dart
ClipOval(
```

3. Press Enter after the `(`

Your code should now look like:

```dart
ClipOval(
Image.asset('assets/images/profile.jpg'),
```

**Don't save yet! Code is incomplete.**

**What you're doing:**

- `ClipOval(` = starts a widget that clips its child into oval/circle shape
- `(` = opening parenthesis for ClipOval's parameters
- We need to tell it what to clip (the child)

***

### **Lesson 3.4: Making Picture Circular - Line 2 (Add child: )**

**Objective:** Tell ClipOval that Image is its child

**Instructions:**

1. **Before** the word `Image`, **type:**
```dart
child: 
```

Your code should now look like:

```dart
ClipOval(
child: Image.asset('assets/images/profile.jpg'),
```

**Don't save yet! Still incomplete.**

**What this does:**

- `child:` = parameter name (tells ClipOval what widget to wrap)
- Image.asset is now the child of ClipOval
- ClipOval will clip this image into circle

***

### **Lesson 3.5: Making Picture Circular - Line 3 (Close ClipOval)**

**Objective:** Close the ClipOval widget properly

**Instructions:**

1. **At the end** of the Image.asset line, **after** `'assets/images/profile.jpg'),`
2. Press Enter to create new line
3. **Type:**
```dart
),
```

Your code should now look like:

```dart
ClipOval(
  child: Image.asset('assets/images/profile.jpg'),
),
```

4. Save and hot reload

**What this does:**

- `)` = closes the ClipOval's opening `(`
- `,` = required comma for Flutter formatting

**Expected Output:**

- Image is now CIRCULAR! 🎉
- Still very large
- But it's a circle now, not a square
- Next we'll add size

***

### **Lesson 3.6: Adding Image Size - Line 1 (width)**

**Objective:** Add width parameter to control size

**Instructions:**

1. Find your `Image.asset('assets/images/profile.jpg'),` line
2. **After** `'assets/images/profile.jpg'` but **before** the closing `),`
3. Press Enter to create a new line
4. **Type:**
```dart
width: 120,
```

Your Image.asset should now look like:

```dart
Image.asset(
  'assets/images/profile.jpg',
  width: 120,
),
```

**Don't save yet!**

**What this does:**

- `width: 120,` = sets image width to 120 pixels
- But height is still original (image will be stretched/squished)
- Need to add height too

***

### **Lesson 3.7: Adding Image Size - Line 2 (height)**

**Objective:** Add height parameter to match width

**Instructions:**

1. **After** the `width: 120,` line
2. **Type:**
```dart
height: 120,
```

Your Image.asset should now look like:

```dart
Image.asset(
  'assets/images/profile.jpg',
  width: 120,
  height: 120,
),
```

**Don't save yet! One more line needed.**

**What this does:**

- `height: 120,` = sets image height to 120 pixels
- Now image is 120×120 (square dimensions)
- But might still look stretched...

***

### **Lesson 3.8: Adding Image Size - Line 3 (fit)**

**Objective:** Control how image fills the space

**Instructions:**

1. **After** the `height: 120,` line
2. **Type:**
```dart
fit: BoxFit.cover,
```

Your complete Image.asset should now look like:

```dart
Image.asset(
  'assets/images/profile.jpg',
  width: 120,
  height: 120,
  fit: BoxFit.cover,
),
```

3. Save and hot reload

**What this does:**

- `fit: BoxFit.cover` = fills the space while maintaining aspect ratio
- Crops image if needed (doesn't stretch)
- Ensures image always looks good

**Understanding BoxFit.cover:**

```
Your photo might be 800×600
          ↓ (BoxFit.cover)
Scaled to fill 120×120
          ↓
Excess is cropped
          ↓
Result: Perfect circular photo, no stretching
```

**Expected Output:**

- Circular profile picture
- Exactly 120×120 pixels
- Perfectly centered
- No stretching or distortion
- Professional appearance!

***

### **Lesson 3.9: Adding Spacing - Line 1 (SizedBox)**

**Objective:** Add space between picture and your name (which we'll add next)

**Instructions:**

1. **After** the entire `ClipOval(...)` section
2. Press Enter to create new line
3. **Type:**
```dart
SizedBox(height: 16),
```

Your Column's children should now look like:

```dart
children: [
  ClipOval(...),
  SizedBox(height: 16),
],
```

4. Save and hot reload

**What this does:**

- `SizedBox` = invisible box (used for spacing)
- `height: 16` = 16 pixels of vertical space
- Like pressing Enter 16 times, but precise

**Expected Output:**

- Looks the same (we haven't added anything below yet)
- Space is reserved for your name text (coming next)

***

### **Lesson 3.10: Adding Your Name - Line 1 (Text widget)**

**Objective:** Start adding your name text

**Instructions:**

1. **After** the `SizedBox(height: 16),` line
2. **Type:**
```dart
Text(
```

3. Press Enter after the `(`

**Don't save yet!**

**What you started:**

- `Text(` = starts a Text widget
- Needs the actual text content next

***

### **Lesson 3.11: Adding Your Name - Line 2 (The actual name)**

**Objective:** Add your name as text content

**Instructions:**

1. On the line after `Text(`
2. **Type** (replace with YOUR name):
```dart
'Juan Dela Cruz',
```

Your code should look like:

```dart
Text(
  'Juan Dela Cruz',
```

**Don't save yet!**

**What this is:**

- Single quotes `'...'` = text string in Dart
- Your name inside the quotes
- This is what will display
- Comma at end `,` = required

**Action Required:**

- Replace 'Juan Dela Cruz' with YOUR actual name
- Keep the single quotes
- Keep the comma

***

### **Lesson 3.12: Adding Your Name - Line 3 (style: )**

**Objective:** Start styling your name text

**Instructions:**

1. **After** your name line (with the comma)
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

**What this does:**

- `style:` = parameter for Text styling (font, size, color, etc.)
- Needs a TextStyle or GoogleFonts after it

***

### **Lesson 3.13: Adding Your Name - Line 4 (GoogleFonts.poppins)**

**Objective:** Specify Poppins font

**Instructions:**

1. **After** `style: ` on the same line
2. **Type:**
```dart
GoogleFonts.poppins(
```

Your code should look like:

```dart
Text(
  'Juan Dela Cruz',
  style: GoogleFonts.poppins(
```

3. Press Enter after the `(`

**Don't save yet!**

**What this does:**

- `GoogleFonts.poppins(` = uses Poppins font from Google Fonts
- Opening `(` = will contain font properties (size, weight, color)

***

### **Lesson 3.14: Adding Your Name - Line 5 (fontSize)**

**Objective:** Make the name text large

**Instructions:**

1. On the new line inside GoogleFonts.poppins
2. **Type:**
```dart
fontSize: 24,
```

**Don't save yet!**

**What this does:**

- `fontSize: 24` = text will be 24 pixels tall
- Large enough to be prominent
- Not too large to look unprofessional

***

### **Lesson 3.15: Adding Your Name - Line 6 (fontWeight)**

**Objective:** Make the name bold

**Instructions:**

1. **After** the `fontSize: 24,` line
2. **Type:**
```dart
fontWeight: FontWeight.bold,
```

**Don't save yet!**

**What this does:**

- `fontWeight:` = how thick/thin the text is
- `FontWeight.bold` = makes it thick/heavy (700 weight)
- Makes name stand out

***

### **Lesson 3.16: Adding Your Name - Line 7 (Close GoogleFonts)**

**Objective:** Close the GoogleFonts.poppins

**Instructions:**

1. **After** the fontWeight line
2. **Type:**
```dart
),
```

Your code should now look like:

```dart
Text(
  'Juan Dela Cruz',
  style: GoogleFonts.poppins(
    fontSize: 24,
    fontWeight: FontWeight.bold,
  ),
```

**Don't save yet! Need to close Text widget.**

**What this does:**

- Closes the `GoogleFonts.poppins(` opening parenthesis
- Comma after = Flutter formatting style

***

### **Lesson 3.17: Adding Your Name - Line 8 (Close Text)**

**Objective:** Complete the Text widget

**Instructions:**

1. **After** the previous `),` line
2. **Type:**
```dart
),
```

Your complete name Text should now look like:

```dart
Text(
  'Juan Dela Cruz',
  style: GoogleFonts.poppins(
    fontSize: 24,
    fontWeight: FontWeight.bold,
  ),
),
```

3. **NOW save and hot reload**

**Expected Output:**

- Profile picture (circular, 120px)
- 16 pixels space
- YOUR NAME in large, bold Poppins font
- Centered on screen
- Professional appearance! 🎉

***

### **Lesson 3.18: Testing What You've Built**

**Objective:** Verify everything works

**Testing:**

1. **Look at your screen** - Do you see:
    - [ ] Circular profile picture?
    - [ ] Your name below it?
    - [ ] Name is large and bold?
    - [ ] Everything centered?
2. **Check the spacing:**
    - [ ] Is there visible gap between picture and name?
    - [ ] Does it look balanced?
3. **Check the console:**
    - [ ] Any errors? (should be none)
    - [ ] Any warnings?

**Expected Output:**

- All checkboxes ✓
- No errors
- Professional profile section started

***

### **Lesson 3.19: Understanding What You Built (Recap)**

**Let's trace what you typed:**

```dart
ClipOval(              ← Line 1: Start circle clipper
  child:               ← Line 2: This will be clipped
    Image.asset(       ← Line 3: Load image
      'assets/...',    ← Line 4: Image path
      width: 120,      ← Line 5: Set width
      height: 120,     ← Line 6: Set height
      fit: BoxFit.cover, ← Line 7: Fill without stretch
    ),                 ← Line 8: Close Image
),                     ← Line 9: Close ClipOval

SizedBox(height: 16),  ← Line 10: Add space

Text(                  ← Line 11: Start text widget
  'Your Name',         ← Line 12: The text content
  style:               ← Line 13: Start styling
    GoogleFonts.poppins( ← Line 14: Use Poppins font
      fontSize: 24,    ← Line 15: Large size
      fontWeight: FontWeight.bold, ← Line 16: Make bold
    ),                 ← Line 17: Close font styling
),                     ← Line 18: Close Text
```

**Total: 18 lines built one at a time!**

**What each section does:**

**ClipOval Section (Lines 1-9):**

- Creates circular profile picture
- 120×120 pixels
- Filled properly without distortion

**SizedBox (Line 10):**

- Creates vertical space
- Separates picture from name

**Text Section (Lines 11-18):**

- Shows your name
- Poppins font (professional)
- 24 pixels size (prominent)
- Bold weight (stands out)

***

## ✅ **Lesson 3.19 Checkpoint**

**What You Built (Line by Line):**

- ✓ Circular profile picture (9 lines)
- ✓ Spacing (1 line)
- ✓ Your name styled professionally (8 lines)
- ✓ Total: 18 lines of code you typed and understood

**Skills Practiced:**

- ✓ Widget wrapping (ClipOval wraps Image)
- ✓ Widget parameters (width, height, fit)
- ✓ Text styling (GoogleFonts, fontSize, fontWeight)
- ✓ Proper syntax (commas, parentheses, brackets)
- ✓ Understanding what each line does

***

## **Next Lesson Preview**

**Lesson 3.20: Adding Your Title (One Line at a Time)**

Next, you'll add your title/role below your name:

- Spacing line
- Text widget line
- Title content line
- Style line
- GoogleFonts line
- Size line
- Color line
- Close lines

Same careful, line-by-line approach!

***

**Ready to continue?** Reply **"Continue"** and we'll add your title line by line! 🚀

**You're Learning the RIGHT Way:**

- ✓ Not copy-pasting
- ✓ Understanding each line
- ✓ Building muscle memory
- ✓ Real understanding! 💪📚

