# Virtual Piano Implementation

A C++ implementation of a virtual piano using Object-Oriented Programming concepts and DOS-based graphics. The program creates an interactive piano interface that can be controlled using both keyboard and mouse input.

## OOP Concepts Used

### 1. Class and Objects
```cpp
class piano {
    public:
        int BIGKEY, MIDKEY, back, border;
        piano() {
            BIGKEY = 15;
            MIDKEY = 1;
            back = 7;
            border = 15;
        }
} color;
```
- Implemented `piano` class to encapsulate piano properties
- Constructor initialization for default values
- Object `color` created to manage display properties

### 2. Encapsulation
- Piano properties (BIGKEY, MIDKEY, back, border) are encapsulated within the piano class
- Access to these properties is controlled through the class interface

### 3. Data Abstraction
- Complex implementation details are hidden from the user
- Piano drawing and sound generation are abstracted into separate functions

## Technical Components

### 1. Mouse Handler
- Uses Union REGS for mouse handling
- Functions implemented:
  - `initmouse()`: Initialize mouse
  - `pointer()`: Control mouse pointer visibility
  - `restrictmouse()`: Set mouse boundaries
  - `getmouse()`: Get mouse coordinates and button state

### 2. Piano Interface
- Visual Components:
  - Big keys (white keys)
  - Mid keys (black keys)
  - Range control
  - Quit button
- Functions:
  - `drawpiano()`: Renders the piano interface
  - `pianokey()`: Draws individual piano keys
  - `BOX()`: Creates bordered boxes for UI elements

### 3. Sound Generation
- Uses frequency array for musical notes:
```cpp
float freq[7] = {130.81, 146.83, 164.81, 174.61, 196, 220, 246.94};
```
- Sound control through DOS sound functions:
  - `sound()`: Generate note
  - `nosound()`: Stop sound

## Key Features

1. Dual Input Support
   - Keyboard input (A, S, D, F, J, K, L keys)
   - Mouse click interaction
   - Arrow keys for range adjustment

2. Visual Feedback
   - Interactive piano keys
   - Range indicator
   - Visual response to key presses

3. Sound Control
   - Frequency-based sound generation
   - Adjustable octave range
   - Duration control

## Implementation Approach

1. Initialization Phase
   - Mouse detection and setup
   - Screen setup
   - Piano interface drawing

2. Main Loop
   - Continuous polling for:
     - Keyboard input
     - Mouse input
     - Range adjustments
     - Exit condition

3. Event Handling
   - Key press detection
   - Mouse click detection
   - Sound generation
   - Visual feedback

## Technical Requirements

- DOS-based system
- Mouse support
- Sound card support

## Code Structure

```
Virtual-Piano.cpp
├── Class Definitions
│   └── piano class
├── Global Variables
│   ├── freq[] array
│   └── control variables
├── Function Declarations
│   ├── Interface functions
│   ├── Mouse handling functions
│   └── Event handling functions
└── Main Program Loop
```

## Usage

1. Program Start:
   - Checks for mouse availability
   - Initializes display
   - Shows piano interface

2. Playing Notes:
   - Use keyboard keys (A,S,D,F,J,K,L)
   - Click piano keys with mouse
   - Adjust range using arrow keys

3. Exit:
   - Press ESC key
   - Click quit button

## Limitations

1. DOS Environment Dependency
2. Fixed sound frequencies
3. Basic graphics implementation
4. Limited to single octave notes

## Possible Improvements

1. Enhanced UI with modern graphics
2. Multiple octave support
3. MIDI integration
4. Sound quality improvements
5. Additional instrument sounds
