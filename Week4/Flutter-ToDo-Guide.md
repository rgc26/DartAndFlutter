# Flutter To-Do List App: Complete Beginner's Guide

**Course:** Fundamentals of Mobile Programming  
**Topic:** Building Your First Interactive Flutter App  
**Level:** Beginner  
**Estimated Time:** 4-6 hours

---

## 📚 Table of Contents

1. [Introduction](#introduction)
2. [What You'll Learn](#what-youll-learn)
3. [Prerequisites](#prerequisites)
4. [Understanding Flutter Basics](#understanding-flutter-basics)
5. [Step-by-Step Build Process](#step-by-step-build-process)
6. [Testing Your App](#testing-your-app)
7. [Common Errors and Solutions](#common-errors-and-solutions)
8. [Next Steps](#next-steps)

---

## Introduction

Welcome to your first interactive Flutter app! In this tutorial, you'll build a **Simple To-Do List** application from scratch. Don't worry—we won't dump all the code on you at once. Instead, we'll build it step by step, explaining every concept along the way.

By the end of this guide, you'll understand:
- How Flutter widgets work
- The difference between Stateless and Stateful widgets
- How to handle user input
- How to manage lists dynamically
- How to update your UI when data changes

---

## What You'll Learn

### Core Concepts
1. **StatelessWidget vs StatefulWidget**
2. **TextEditingController** for managing text input
3. **ListView.builder** for efficient list rendering
4. **State management** with `setState()`
5. **Widget composition** and layout

### Skills You'll Develop
- Creating custom data models
- Handling user interactions
- Managing app state
- Building responsive UIs
- Debugging Flutter apps

---

## Prerequisites

Before starting, make sure you have:

- ✅ Flutter SDK installed
- ✅ Android Studio or VS Code with Flutter extensions
- ✅ An emulator or physical device for testing
- ✅ Basic understanding of Dart syntax (variables, functions, classes)

**Quick check:** Can you run `flutter doctor` in your terminal without major errors?

---

## Understanding Flutter Basics

### What Are Widgets?

In Flutter, **everything is a widget**. A widget is a building block of your UI. Think of widgets as LEGO pieces—you combine them to create your app.

**Two main types:**

1. **StatelessWidget** - Doesn't change once built (static content)
2. **StatefulWidget** - Can change over time (dynamic content)

### When to Use Each?

| Use StatelessWidget when: | Use StatefulWidget when: |
|---------------------------|--------------------------|
| Displaying static text | Content changes based on user actions |
| Showing images that don't change | Forms with user input |
| Building layout structures | Lists that can be modified |
| Creating reusable components | Animations or timers |

**Example:**
- Your app's title → StatelessWidget (never changes)
- The list of tasks → StatefulWidget (users add/remove tasks)

### Understanding State

**State** is any data that can change while your app is running[1]. When state changes, Flutter rebuilds the affected widgets to show the new data.

Think of it like a whiteboard:
- **Stateless** = Permanent marker (can't change)
- **Stateful** = Dry-erase marker (can change and redraw)

---

## Step-by-Step Build Process

### 📋 Module 1: Project Setup (15 minutes)

#### Step 1.1: Create a New Flutter Project

```bash
flutter create todo_list_app
cd todo_list_app
```

#### Step 1.2: Open `lib/main.dart` and Clear Everything

Delete all the default code. Start with a blank file.

#### Step 1.3: Import Flutter Material Package

```dart
import 'package:flutter/material.dart';
```

**What this does:** Imports Flutter's Material Design widgets (buttons, text fields, etc.)

#### Step 1.4: Create the Main Function

```dart
void main() {
  runApp(const MyApp());
}
```

**Explanation:**
- `main()` is the entry point of every Dart program
- `runApp()` tells Flutter which widget to display first
- `const` means this widget won't change (optimization)

---

### 📋 Module 2: Creating the App Structure (20 minutes)

#### Step 2.1: Build the MyApp Widget (StatelessWidget)

```dart
class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Simple To-Do List',
      debugShowCheckedModeBanner: false,
      theme: ThemeData(
        primarySwatch: Colors.blue,
        useMaterial3: true,
      ),
      home: const TodoListScreen(),
    );
  }
}
```

**Line-by-line breakdown:**

- `class MyApp extends StatelessWidget` → Creates a widget that doesn't change
- `const MyApp({Key? key}) : super(key: key)` → Constructor (boilerplate for now)
- `@override Widget build(BuildContext context)` → This method builds your UI
- `return MaterialApp(...)` → Root widget of your app
- `title` → App name (shows in task switcher)
- `debugShowCheckedModeBanner: false` → Removes "DEBUG" banner
- `theme` → Sets app colors and style
- `home` → The first screen users see

**🎯 Try it:** Run your app now. You'll get an error because `TodoListScreen` doesn't exist yet. That's okay—we'll create it next!

---

### 📋 Module 3: Creating the Data Model (15 minutes)

Before building the UI, let's define what a "task" looks like.

#### Step 3.1: Create the TodoItem Class

At the bottom of your `main.dart` file (after all other code), add:

```dart
class TodoItem {
  String title;
  bool isCompleted;

  TodoItem({
    required this.title,
    this.isCompleted = false,
  });
}
```

**What this does:**
- Creates a blueprint for a to-do task
- Each task has a `title` (text description)
- Each task has an `isCompleted` status (checked or not)
- `required` means you must provide a title when creating a task
- `isCompleted = false` means tasks start unchecked by default

**Example usage:**
```dart
// Creating a new task
TodoItem task1 = TodoItem(title: "Buy groceries");
// task1.title → "Buy groceries"
// task1.isCompleted → false

// Creating a completed task
TodoItem task2 = TodoItem(title: "Study Flutter", isCompleted: true);
```

---

### 📋 Module 4: Creating the Main Screen Structure (25 minutes)

Now let's build the screen that will display our to-do list.

#### Step 4.1: Create the TodoListScreen Widget (StatefulWidget)

Add this code between `MyApp` and `TodoItem`:

```dart
class TodoListScreen extends StatefulWidget {
  const TodoListScreen({Key? key}) : super(key: key);

  @override
  State<TodoListScreen> createState() => _TodoListScreenState();
}
```

**Why StatefulWidget?** Because this screen will change when users:
- Add new tasks
- Check/uncheck tasks
- Delete tasks

#### Step 4.2: Create the State Class

```dart
class _TodoListScreenState extends State<TodoListScreen> {
  // We'll add code here in the next steps
}
```

**Understanding the naming:**
- `_TodoListScreenState` → The underscore `_` makes it private
- It holds all the changeable data (state) for `TodoListScreen`

#### Step 4.3: Declare State Variables

Inside `_TodoListScreenState`, add:

```dart
final List<TodoItem> _tasks = [];
final TextEditingController _controller = TextEditingController();
```

**What are these?**

1. **`_tasks`** → A list that holds all your to-do items
   - Starts empty (`[]`)
   - Will grow as users add tasks
   
2. **`_controller`** → Manages the text input field[2]
   - Tracks what the user types
   - Allows you to read and clear the text

**Analogy:** Think of `_controller` as a secretary who:
- Listens to what you type
- Can tell you what's been typed
- Can erase the text when asked

---

### 📋 Module 5: Building the UI Layout (30 minutes)

#### Step 5.1: Create the Build Method Scaffold

Still inside `_TodoListScreenState`, add:

```dart
@override
Widget build(BuildContext context) {
  return Scaffold(
    appBar: AppBar(
      title: const Text('Simple To-Do List'),
      elevation: 2,
    ),
    body: Column(
      children: [
        // We'll add input section here
        // We'll add task list here
      ],
    ),
  );
}
```

**Understanding the structure:**
- **Scaffold** → Provides basic app structure (app bar, body, etc.)
- **AppBar** → The top bar with your title
- **Body: Column** → Arranges children vertically (top to bottom)

**Visual layout:**
```
┌────────────────────────────┐
│   Simple To-Do List        │ ← AppBar
├────────────────────────────┤
│                            │
│   [Input section]          │ ← First child of Column
│                            │
├────────────────────────────┤
│   [Task list]              │ ← Second child of Column
│                            │
└────────────────────────────┘
```

---

### 📋 Module 6: Creating the Input Section (35 minutes)

#### Step 6.1: Add Input Field and Button

Replace `// We'll add input section here` with:

```dart
Padding(
  padding: const EdgeInsets.all(16.0),
  child: Row(
    children: [
      Expanded(
        child: TextField(
          controller: _controller,
          decoration: const InputDecoration(
            hintText: 'Enter a new task',
            border: OutlineInputBorder(),
          ),
          onSubmitted: (_) => _addTask(),
        ),
      ),
      const SizedBox(width: 8),
      IconButton(
        icon: const Icon(Icons.add_circle, size: 40),
        color: Colors.blue,
        onPressed: _addTask,
      ),
    ],
  ),
),
const Divider(height: 1),
```

**Line-by-line breakdown:**

- **`Padding`** → Adds space around the input section (16 pixels on all sides)
- **`Row`** → Arranges children horizontally (left to right)
- **`Expanded`** → Makes the TextField take all available width
- **`TextField`** → The input box where users type
  - `controller: _controller` → Connects to our TextEditingController
  - `decoration` → How it looks (border, hint text)
  - `onSubmitted: (_) => _addTask()` → Calls `_addTask()` when user presses Enter
- **`SizedBox(width: 8)`** → Small gap between text field and button
- **`IconButton`** → The "+" button
  - `onPressed: _addTask` → Calls `_addTask()` when tapped
- **`Divider`** → A horizontal line separating sections

**Visual layout:**
```
┌──────────────────────────────────────┐
│  [Enter a new task...    ] [+]       │
└──────────────────────────────────────┘
       TextField           IconButton
```

---

### 📋 Module 7: Implementing Add Task Function (20 minutes)

#### Step 7.1: Create the _addTask Method

Above the `build()` method but still inside `_TodoListScreenState`, add:

```dart
void _addTask() {
  final task = _controller.text.trim();
  if (task.isNotEmpty) {
    setState(() {
      _tasks.add(TodoItem(title: task));
    });
    _controller.clear();
  }
}
```

**Step-by-step explanation:**

1. **`final task = _controller.text.trim();`**
   - Gets the text from the input field
   - `trim()` removes extra spaces at the beginning and end
   - Example: "  Buy milk  " → "Buy milk"

2. **`if (task.isNotEmpty)`**
   - Only adds task if there's actual text
   - Prevents adding empty tasks

3. **`setState(() { ... });`**
   - **MOST IMPORTANT PART!**
   - Tells Flutter: "Hey, something changed, please rebuild the UI!"
   - Without this, the UI won't update[3]

4. **`_tasks.add(TodoItem(title: task));`**
   - Creates a new TodoItem with the typed text
   - Adds it to the `_tasks` list

5. **`_controller.clear();`**
   - Erases the text field
   - Ready for the next task

**What happens when you type "Study Flutter" and press Enter:**
1. `_controller.text` → "Study Flutter"
2. Check: is it empty? → No
3. Create new `TodoItem(title: "Study Flutter")`
4. Add to `_tasks` list
5. Call `setState()` → Flutter rebuilds UI → Task appears!
6. Clear text field → Ready for next task

---

### 📋 Module 8: Displaying the Task List (40 minutes)

#### Step 8.1: Add the ListView.builder

Replace `// We'll add task list here` with:

```dart
Expanded(
  child: _tasks.isEmpty
      ? const Center(
          child: Text(
            'No tasks yet. Add one above!',
            style: TextStyle(fontSize: 16, color: Colors.grey),
          ),
        )
      : ListView.builder(
          itemCount: _tasks.length,
          itemBuilder: (context, index) {
            final task = _tasks[index];
            return Card(
              margin: const EdgeInsets.symmetric(
                horizontal: 16,
                vertical: 4,
              ),
              child: ListTile(
                leading: Checkbox(
                  value: task.isCompleted,
                  onChanged: (_) => _toggleTask(index),
                ),
                title: Text(
                  task.title,
                  style: TextStyle(
                    decoration: task.isCompleted
                        ? TextDecoration.lineThrough
                        : null,
                    color: task.isCompleted
                        ? Colors.grey
                        : Colors.black,
                  ),
                ),
                trailing: IconButton(
                  icon: const Icon(Icons.delete, color: Colors.red),
                  onPressed: () => _removeTask(index),
                ),
              ),
            );
          },
        ),
),
```

**This looks complex, but let's break it down:**

#### Understanding ListView.builder

**Why ListView.builder?**[4]
- Efficient for lists of any size
- Only builds items that are visible on screen
- Automatically handles scrolling

**Key parameters:**
- `itemCount: _tasks.length` → How many items in total
- `itemBuilder: (context, index) { ... }` → Function that builds each item

**How it works:**
```
If you have 3 tasks:
- itemBuilder is called with index = 0 → builds first task
- itemBuilder is called with index = 1 → builds second task
- itemBuilder is called with index = 2 → builds third task
```

#### Understanding the Conditional Display

```dart
_tasks.isEmpty ? ShowEmptyMessage : ShowTaskList
```

This is called a **ternary operator**. It means:
- If `_tasks` is empty → Show "No tasks yet" message
- Otherwise → Show the list of tasks

#### Understanding Each Task Card

Let's look at one task item:

```dart
Card(                              // White card background
  child: ListTile(                 // Pre-styled list item
    leading: Checkbox(...),        // Left side: checkbox
    title: Text(...),              // Middle: task text
    trailing: IconButton(...),     // Right side: delete button
  ),
)
```

**Visual layout of one task:**
```
┌──────────────────────────────────────┐
│ [✓] Buy groceries           [🗑]    │
└──────────────────────────────────────┘
  ^         ^                    ^
 leading   title              trailing
```

#### Understanding Task Styling

```dart
style: TextStyle(
  decoration: task.isCompleted ? TextDecoration.lineThrough : null,
  color: task.isCompleted ? Colors.grey : Colors.black,
)
```

**What this does:**
- If completed → Strike through the text + grey color
- If not completed → Normal text + black color

**Example:**
- Not completed: "Buy groceries"
- Completed: ~~"Buy groceries"~~ (grey, strikethrough)

---

### 📋 Module 9: Toggle Task Function (15 minutes)

#### Step 9.1: Create the _toggleTask Method

Add this above the `build()` method:

```dart
void _toggleTask(int index) {
  setState(() {
    _tasks[index].isCompleted = !_tasks[index].isCompleted;
  });
}
```

**What this does:**

1. Takes the task position (`index`)
2. Flips the `isCompleted` status:
   - If `false` → becomes `true`
   - If `true` → becomes `false`
3. Calls `setState()` to update UI

**The `!` operator means "NOT":**
```dart
bool value = true;
bool opposite = !value;  // opposite is now false

// In our case:
task.isCompleted = false;
task.isCompleted = !false;  // becomes true (task checked)
```

**What happens when you tap a checkbox:**
1. User taps checkbox
2. `_toggleTask(index)` is called
3. Find the task at that position
4. Flip its `isCompleted` status
5. `setState()` triggers UI rebuild
6. Task appearance changes (strikethrough + grey)

---

### 📋 Module 10: Delete Task Function (15 minutes)

#### Step 10.1: Create the _removeTask Method

Add this above the `build()` method:

```dart
void _removeTask(int index) {
  setState(() {
    _tasks.removeAt(index);
  });
}
```

**What this does:**

1. Takes the task position (`index`)
2. Removes the task at that position from the list
3. Calls `setState()` to update UI

**Understanding `removeAt()`:**
```dart
List<String> fruits = ["Apple", "Banana", "Orange"];
fruits.removeAt(1);  // Removes "Banana" (index 1)
// fruits is now ["Apple", "Orange"]
```

**What happens when you tap the delete button:**
1. User taps 🗑 button
2. `_removeTask(index)` is called
3. Remove task from `_tasks` list
4. `setState()` triggers UI rebuild
5. Task disappears from screen

---

### 📋 Module 11: Clean Up Resources (10 minutes)

#### Step 11.1: Add the dispose Method

Add this method after `_removeTask()`:

```dart
@override
void dispose() {
  _controller.dispose();
  super.dispose();
}
```

**Why is this important?**

TextEditingController uses system resources (memory). When your widget is removed, you must clean up to prevent **memory leaks**.

**Analogy:** It's like turning off the lights when you leave a room.

**The `dispose()` method:**
- Called automatically when the widget is removed permanently
- Perfect place to clean up resources
- `_controller.dispose()` → Release the controller's resources
- `super.dispose()` → Let Flutter do its cleanup too

**Without this:** Your app will slowly consume more and more memory, eventually becoming slow or crashing.

---

## Testing Your App

### Test Plan

Now that your app is complete, let's test it systematically:

#### ✅ Test 1: Add a Task
1. Type "Buy groceries" in the input field
2. Press Enter or tap the + button
3. **Expected:** Task appears in the list below

#### ✅ Test 2: Add Multiple Tasks
1. Add "Study Flutter"
2. Add "Exercise"
3. Add "Call mom"
4. **Expected:** All three tasks appear in order

#### ✅ Test 3: Check a Task
1. Tap the checkbox next to "Buy groceries"
2. **Expected:** 
   - Checkbox is checked
   - Text has strikethrough
   - Text color turns grey

#### ✅ Test 4: Uncheck a Task
1. Tap the checkbox again
2. **Expected:**
   - Checkbox is unchecked
   - Strikethrough disappears
   - Text color returns to black

#### ✅ Test 5: Delete a Task
1. Tap the 🗑 button next to any task
2. **Expected:** Task disappears immediately

#### ✅ Test 6: Empty Input Prevention
1. Try to add an empty task (just spaces or nothing)
2. **Expected:** Nothing happens (no empty task added)

#### ✅ Test 7: Empty State
1. Delete all tasks
2. **Expected:** "No tasks yet. Add one above!" message appears

---

## Common Errors and Solutions

### Error 1: "setState() called after dispose()"

**Problem:** You're trying to update the UI after the widget is removed.

**Solution:**
```dart
void _addTask() {
  if (!mounted) return;  // Add this check
  final task = _controller.text.trim();
  // rest of code...
}
```

---

### Error 2: Tasks Not Appearing

**Problem:** Forgot to call `setState()`.

**Check:**
- Every time you modify `_tasks`, it must be inside `setState(() { ... })`
- Example: `setState(() { _tasks.add(...); });`

---

### Error 3: Text Field Not Clearing

**Problem:** Forgot to call `_controller.clear()`.

**Solution:**
```dart
void _addTask() {
  // ... add task code ...
  _controller.clear();  // Add this line
}
```

---

### Error 4: Checkbox Not Changing

**Problem:** `_toggleTask()` not wrapped in `setState()`.

**Check:**
```dart
void _toggleTask(int index) {
  setState(() {  // Must have this!
    _tasks[index].isCompleted = !_tasks[index].isCompleted;
  });
}
```

---

### Error 5: "RangeError: Invalid value"

**Problem:** Trying to access an index that doesn't exist.

**Common cause:** Deleting a task but not using the correct index.

**Solution:** Always use the `index` parameter from `ListView.builder`:
```dart
onPressed: () => _removeTask(index),  // ✅ Correct
// NOT: () => _removeTask(0)          // ❌ Wrong (always deletes first)
```

---

## Understanding Key Concepts

### 1. The setState() Rule

**Golden Rule:** Any time you change data that affects the UI, wrap it in `setState()`.

```dart
// ❌ WRONG - UI won't update
void _addTask() {
  _tasks.add(TodoItem(title: "Test"));
}

// ✅ CORRECT - UI updates
void _addTask() {
  setState(() {
    _tasks.add(TodoItem(title: "Test"));
  });
}
```

---

### 2. Why Use TextEditingController?

**Option 1: Without controller (harder)**
```dart
String userInput = "";
TextField(
  onChanged: (value) {
    userInput = value;  // Manually track changes
  },
)
```

**Option 2: With controller (easier)**[2]
```dart
final controller = TextEditingController();
TextField(controller: controller)
// Later: String userInput = controller.text;
```

**Benefits:**
- Automatically tracks text changes
- Can read current value anytime
- Can clear the field easily: `controller.clear()`
- Can set value programmatically: `controller.text = "Hello"`

---

### 3. Understanding ListView.builder Efficiency

**Regular ListView (inefficient for large lists):**
```dart
ListView(
  children: [
    TaskCard(task: task1),
    TaskCard(task: task2),
    // ... creates ALL widgets at once
    TaskCard(task: task1000),
  ],
)
```

**ListView.builder (efficient):**[4]
```dart
ListView.builder(
  itemCount: 1000,
  itemBuilder: (context, index) {
    return TaskCard(task: tasks[index]);
  },
)
// Only creates widgets for visible items
```

**Why it matters:**
- If you have 1000 tasks, regular ListView builds all 1000 widgets immediately
- ListView.builder only builds ~10 widgets (ones visible on screen)
- As you scroll, it builds more as needed
- **Result:** Faster performance, less memory usage

---

## Next Steps

### 🎯 Challenges to Try

#### Beginner Challenges
1. **Add a task counter:** Show "You have X tasks" at the top
2. **Change app colors:** Try different color schemes
3. **Add more text styles:** Make the title bigger or bold

#### Intermediate Challenges
4. **Add priority levels:** High, Medium, Low (with different colors)
5. **Add due dates:** Let users set when a task is due
6. **Add categories:** Work, Personal, Shopping, etc.
7. **Persist data:** Save tasks so they survive app restarts (use SharedPreferences)

#### Advanced Challenges
8. **Add search functionality:** Filter tasks by keywords
9. **Add sorting:** Sort by date, priority, or alphabetically
10. **Add edit functionality:** Long-press to edit a task
11. **Add animations:** Animate task additions and deletions

---

### 📚 Additional Learning Resources

#### Official Documentation
- [Flutter Widget Catalog](https://docs.flutter.dev/ui/widgets)
- [State Management](https://docs.flutter.dev/data-and-backend/state-mgmt/intro)
- [Layout Widgets](https://docs.flutter.dev/ui/layout)

#### Recommended Next Topics
1. **Navigation:** Moving between screens
2. **Forms:** Building more complex input forms
3. **Async/Await:** Working with APIs and databases
4. **State Management:** Provider, Riverpod, or Bloc
5. **Firebase Integration:** Cloud database and authentication

---

## Summary: What You Built

### Architecture Overview

```
MyApp (StatelessWidget)
└── MaterialApp
    └── TodoListScreen (StatefulWidget)
        └── _TodoListScreenState
            ├── State Variables:
            │   ├── _tasks (List<TodoItem>)
            │   └── _controller (TextEditingController)
            ├── Methods:
            │   ├── _addTask()
            │   ├── _removeTask(index)
            │   ├── _toggleTask(index)
            │   └── dispose()
            └── UI (build method):
                ├── AppBar
                └── Column
                    ├── Input Section (Row)
                    │   ├── TextField
                    │   └── IconButton
                    └── Task List (ListView.builder)
                        └── Card > ListTile
                            ├── Checkbox
                            ├── Text
                            └── IconButton (delete)

TodoItem (Data Model)
├── title (String)
└── isCompleted (bool)
```

### Key Takeaways

1. ✅ **StatefulWidget** is used when UI needs to change based on user actions
2. ✅ **setState()** tells Flutter to rebuild the UI
3. ✅ **TextEditingController** manages text input
4. ✅ **ListView.builder** efficiently displays dynamic lists
5. ✅ **dispose()** prevents memory leaks
6. ✅ **Data models** (TodoItem) organize your data structure

---

## Assessment Questions

Test your understanding:

### Conceptual Questions
1. What's the main difference between StatelessWidget and StatefulWidget?
2. Why do we need to call `setState()` when modifying `_tasks`?
3. What happens if you forget to call `_controller.dispose()`?
4. Why is `ListView.builder` better than regular `ListView` for long lists?

### Practical Questions
5. How would you add a "Clear All" button that removes all tasks?
6. How would you show the total number of completed tasks?
7. What code would you add to prevent adding duplicate tasks?

### Challenge Question
8. How would you modify the app to show completed tasks in a separate list at the bottom?

**Hint for #8:** You'll need to filter `_tasks` into two lists: completed and incomplete.

---

## Troubleshooting Checklist

Before asking for help, check:

- [ ] Did you import `package:flutter/material.dart`?
- [ ] Is your `main()` function calling `runApp()`?
- [ ] Are all your methods inside `_TodoListScreenState`?
- [ ] Did you add `setState()` around state modifications?
- [ ] Did you add the `dispose()` method?
- [ ] Are you using the correct variable names (case-sensitive)?
- [ ] Did you save the file and hot-reload the app?

---

## Conclusion

Congratulations! 🎉 You've built a fully functional Flutter app from scratch. You now understand:

- Widget composition and layout
- State management fundamentals
- User input handling
- Dynamic list rendering
- Resource cleanup

This knowledge forms the foundation for more complex Flutter apps. Keep practicing, experiment with modifications, and don't be afraid to break things—that's how you learn!

---

## References

[1] Flutter Documentation. (2025). Add interactivity to your Flutter app. Retrieved from https://docs.flutter.dev/ui/interactivity

[2] Scaler Topics. (2024). TextEditingController in Flutter. Retrieved from https://www.scaler.com/topics/texteditingcontroller-flutter/

[3] Flutter Clutter. (2020). StatelessWidget vs. StatefulWidget. Retrieved from https://www.flutterclutter.dev/flutter/basics/statelesswidget-vs-statefulwidget/2020/1195/

[4] Flutter Documentation. (2025). Use ListView.builder to implement a long or infinite list. Retrieved from https://docs.flutter.dev/cookbook/lists/long-lists

---

**Created by:** Your IT Instructor  
**Date:** February 11, 2026  
**Course:** Fundamentals of Mobile Programming  
**Version:** 1.0

**Need Help?** Review each module slowly. Practice typing the code yourself instead of copying. Understanding comes from doing!

---

## Appendix A: Complete Code Structure

For reference, here's how your `main.dart` file should be organized:

```
1. Imports
   └── import 'package:flutter/material.dart';

2. Main Function
   └── void main() { runApp(const MyApp()); }

3. MyApp (StatelessWidget)
   └── Returns MaterialApp with theme and home

4. TodoListScreen (StatefulWidget)
   └── Creates _TodoListScreenState

5. _TodoListScreenState (State<TodoListScreen>)
   ├── State variables (_tasks, _controller)
   ├── _addTask() method
   ├── _removeTask(int index) method
   ├── _toggleTask(int index) method
   ├── dispose() method
   └── build(BuildContext context) method
       └── Returns Scaffold with AppBar and body

6. TodoItem (Data Model)
   └── Properties and constructor
```

Don't try to memorize this structure—understand what each part does and why it's there!

---

**End of Tutorial**