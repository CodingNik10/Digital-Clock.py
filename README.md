This project is a Digital Clock with Integrated Stopwatch built using PyQt5 in Python. It features a modern neon-themed user interface inspired by futuristic “technology” aesthetics. The application displays the current time and date in real-time and includes a fully functional stopwatch with start, stop, and reset capabilities.

Users can toggle between 12-hour and 24-hour formats, and the stopwatch supports precise time tracking down to milliseconds. The UI uses a custom font and glowing neon styling to enhance visual appeal, making it both functional and visually engaging.

This project demonstrates the use of:

PyQt5 GUI components and layouts
Timers (QTimer) for real-time updates
Time handling (QTime, QDate, QElapsedTimer)
Event-driven programming in Python

# Features
-Real-time digital clock (updates every second)
-Toggle between 12-hour and 24-hour format
-Displays current date
-Stopwatch with:
   Start
   Stop
   Reset
-Custom font support (Technology.ttf)
-Neon UI styling

# Technologies Used
Python
PyQt5 (GUI framework)
Qt Core Modules:
   QTimer
   QTime
   QDate
   QElapsedTimer

# Project Structure

DigitalClockProject/
│
├── main.py                # Main application code
├── Technology.ttf        # Custom font file
└── README.md             # Documentation

# code Architecture
1. Class: DigitalClock(QWidget)
Main class that handles:
   UI creation
   Clock functionality
   Stopwatch functionality
   
2. Key Components
🔹 UI Components
     QLabel → Display time, date, stopwatch
     QPushButton → Controls (Start, Stop, Reset, Toggle Format)
     QLayout → Organizes UI elements
🔹 Timers
     QTimer (clock_timer) → Updates clock every second
     QTimer (sw_timer) → Updates stopwatch every 50ms
🔹 Time Handling
     QTime → Current time
     QDate → Current date
     QElapsedTimer → Stopwatch timing

# Application Flow (Flowchart)

START
  ↓
Initialize Application
  ↓
Create DigitalClock Window
  ↓
Setup UI Components
  ↓
Start Clock Timer (1 sec interval)
  ↓
-------------------------------
|        CLOCK LOOP           |
|  Fetch Current Time         |
|  Format Time (12/24)        |
|  Update Labels              |
-------------------------------
  ↓
User Interaction:
  ├── Toggle Format → Switch 12/24
  ├── Start Stopwatch → Start Timer
  ├── Stop Stopwatch → Pause Timer
  ├── Reset Stopwatch → Reset Time
  ↓
Update Stopwatch Display (every 50ms)
  ↓
END (on window close)

# Pseudocode
🔹 Main Program

START
Create QApplication
Create DigitalClock object
Show window
Execute app loop
END

🔹 Initialize UI

FUNCTION initUI():
    Set window title and size
    Set background color (black)

    Load custom font

    Create labels:
        time_label
        date_label
        stopwatch_display

    Create buttons:
        start, stop, reset
        format toggle button

    Connect buttons to functions

    Arrange layout using VBox and HBox

    Start clock timer (1 second)
    Initialize stopwatch variables
END FUNCTION

🔹 Update Clock

FUNCTION update_clock():
    Get current time
    Get current date

    IF 24-hour format:
        format = HH:mm:ss
    ELSE:
        format = hh:mm:ss AM/PM

    Update time label
    Update date label
END FUNCTION

🔹 Toggle Time Format

FUNCTION toggle_time_format():
    Switch is_24h boolean
    Update button text
    Call update_clock()
END FUNCTION

🔹 Stopwatch Start

FUNCTION sw_start():
    IF stopwatch not running:
        IF first time:
            start timer
        ELSE:
            resume from paused time

        set running = TRUE
        start stopwatch timer
END FUNCTION

🔹 Stopwatch Stop

FUNCTION sw_stop():
    IF running:
        store elapsed time
        stop timer
        set running = FALSE
END FUNCTION

🔹 Stopwatch Reset

FUNCTION sw_reset():
    stop timer
    reset elapsed time
    display 00:00:00.000
END FUNCTION

🔹 Update Stopwatch Display

FUNCTION update_stopwatch():
    total_time = previous_time + current_elapsed

    hours = total_time / 3600000
    minutes = remaining / 60000
    seconds = remaining / 1000
    milliseconds = remaining % 1000

    update display label
END FUNCTION

# Known Issues / Improvements
-Resume logic uses a custom attribute (elapsed_display_ms) which can be improved
-UI can be enhanced with animations
-Add lap functionality in stopwatch
-Add alarm feature

# Output Description
-Black background window
-Neon green glowing text
-Large digital clock display
-Date below clock
-Stopwatch with control buttons

# How to Run
Step 1: Install PyQt5
pip install PyQt5
Step 2: Run the program
python main.py

# Conclusion

This project demonstrates:

-GUI development using PyQt5
-Real-time event handling
-Timer-based applications
-Clean UI structuring

It is a great beginner-to-intermediate level project combining UI + logic + real-time systems.

# Author
 Nikhil Kumar
 22BME10002
