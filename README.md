# Lab 9: Persisting Data in Flutter

## Author
Asqarjon Anvarov (220050)

## Project Structure
```
lab-8/
├── lib/
│   └── main.dart          # Main application file with all tasks
├── pubspec.yaml           # Dependencies configuration
└── README.md              # This file
```

## Dependencies
- `shared_preferences: ^2.2.2` - For storing key-value pairs
- `sqflite: ^2.3.0` - SQLite database for Flutter
- `path_provider: ^2.1.1` - Finding common file system paths
- `path: ^1.8.3` - Path manipulation utilities

## Tasks Implementation

### Part A: Shared Preferences (25 points)
- ✅ **Task 1**: Saving Simple Data
  - TextField with "Save" button
  - Store input text in SharedPreferences with key 'username'
  - Display saved username when reopening the app
  
- ✅ **Task 2**: Counter Persistence
  - Counter app that remembers its value after restarting
  - Uses SharedPreferences.setInt() and getInt()
  
- ✅ **Task 3**: Dark Mode Toggle
  - Theme switch saves user preference (true/false) in SharedPreferences
  - Restores theme preference on launch

### Part B: SQLite Basics (35 points)
- ✅ **Task 4**: Database Setup
  - Added sqflite and path_provider packages
  - Created notes.db database with notes table
  - Table structure: id (INTEGER PRIMARY KEY), title (TEXT), content (TEXT)
  
- ✅ **Task 5**: Insert and Read Records
  - "Add Note" button inserts dummy records
  - "View Notes" shows list of all notes from SQLite
  
- ✅ **Task 6**: Update and Delete Records
  - Edit individual notes from the list
  - Delete notes with confirmation dialog box

### Part C: CRUD UI Integration (25 points)
- ✅ **Task 7**: Full CRUD Note App
  - Combined Tasks 4-6 into a single Flutter app
  - Users can add, read, edit, delete notes using SQLite
  - All notes displayed in a scrollable list
  
- ✅ **Task 8**: Data Passing Between Screens
  - Uses Navigator.pushNamed() to open Detail Screen
  - Passes note details as arguments
  - Handles updates in the detail screen

### Part D: Advanced Persistence (15 points)
- ✅ **Task 9**: File Storage Demo
  - Uses path_provider to store user_data.txt
  - Implements write and read operations via buttons
  - Shows file content on screen
  
- ✅ **Task 10**: Hybrid Storage App
  - Uses SharedPreferences for settings (font size, theme)
  - Uses SQLite for structured data (notes, tasks)
  - Demonstrates both working together

## Features

### Home Screen
- Navigation hub to access all parts (A, B/C, D)

### Part A Features
- **Username Screen**: Save and retrieve username
- **Counter Screen**: Persistent counter with increment/decrement/reset
- **Dark Mode Screen**: Theme toggle with preference persistence

### Part B & C Features
- **Full CRUD Note App**:
  - Add new notes
  - View all notes in a list
  - Edit existing notes
  - Delete notes with confirmation
  - Navigate to detail screen on tap

### Part D Features
- **File Storage**: Read/write operations on user_data.txt
- **Hybrid App**: Settings in SharedPreferences, tasks in SQLite

## How to Run

1. Install dependencies:
   ```bash
   flutter pub get
   ```

2. Run the app:
   ```bash
   flutter run
   ```

## Database Schema

### Notes Table
```sql
CREATE TABLE notes (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  title TEXT NOT NULL,
  content TEXT NOT NULL
)
```

## File Locations

- **Database**: Stored in app's documents directory as `notes.db`
- **Text File**: Stored as `user_data.txt` in application documents directory

## Notes

- All SharedPreferences keys:
  - `username`: String value for username
  - `counter`: Integer value for counter
  - `darkMode`: Boolean value for theme preference
  - `fontSize`: Double value for font size (Task 10)
  - `theme`: Boolean value for theme (Task 10)

- The app demonstrates various persistence strategies:
  - Key-value storage (SharedPreferences)
  - Relational database (SQLite)
  - File system storage (path_provider)
