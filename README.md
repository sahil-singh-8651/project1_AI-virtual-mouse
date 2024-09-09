AI Virtual Mouse - README
Overview
The AI Virtual Mouse is a Python-based project that utilizes computer vision and hand gesture recognition to control various computer functions such as mouse movements, clicks, scrolling, volume control, and screen brightness adjustments. This system is built using the OpenCV, MediaPipe, and PyAutoGUI libraries, along with some auxiliary packages. The AI Virtual Mouse allows users to interact with their computers using hand gestures, offering a touchless and innovative approach to traditional input methods.

Features
Hand Gesture Recognition: Detects and classifies various hand gestures to perform specific actions.
Cursor Movement: Move the mouse cursor by moving your hand in front of the camera.
Click Operations: Perform left-click, right-click, and double-click actions using gestures.
Scrolling: Scroll vertically and horizontally using pinch gestures.
Volume Control: Adjust system volume using hand gestures.
Brightness Control: Change the screen brightness by performing a pinch gesture with the other hand.
Gesture Stabilization: Filters out noise in gesture recognition to avoid unintentional actions.
Installation
Prerequisites: Ensure you have Python installed on your machine.
Install Required Libraries:
bash
Copy code
pip install opencv-python
pip install mediapipe
pip install pyautogui
pip install screen-brightness-control
pip install pycaw
How It Works
Gesture Recognition:

The code uses the MediaPipe library to detect hand landmarks.
Different gestures are recognized by analyzing the relative positions of specific hand landmarks.
Gesture to Action Mapping:

Fist Gesture: Move the cursor while holding the left mouse button (drag).
V Gesture: Move the cursor freely without clicking.
Index Finger Pointing: Right-click at the current cursor position.
Two-Finger Closed: Double-click at the current cursor position.
Pinch Major: Adjust system brightness or volume based on hand movement.
Pinch Minor: Scroll the page vertically or horizontally.
Gesture Control Flow:

The system captures frames from the webcam.
The hand gestures are analyzed in real-time, and corresponding actions are executed based on the recognized gesture.
Gesture Stability:

The system waits for a consistent gesture over a few frames before performing an action to reduce unintentional triggers due to momentary noise.
Running the Application
Ensure your webcam is connected and working.
Run the Python script directly:
bash
Copy code
python ai_virtual_mouse.py
A window will open, showing the live feed from your webcam with hand landmarks overlayed.
Perform gestures to control your computer as described above.
Customization
Adding New Gestures: To add new gestures, modify the Gest and HandRecog classes.
Adjusting Sensitivity: The Controller class contains various thresholds and parameters that can be tuned for different responsiveness levels.
Gesture Mapping: Modify the Controller.handle_controls() method to change what actions are mapped to each gesture.
Dependencies
OpenCV: Used for capturing video from the webcam and processing the images.
MediaPipe: Provides hand tracking and landmark detection.
PyAutoGUI: Used for simulating mouse and keyboard events.
Screen Brightness Control: Adjusts the screen brightness programmatically.
PyCaw: Controls system audio volume.
Conclusion
The AI Virtual Mouse project demonstrates a novel way of interacting with computers using hand gestures. It can be extended and modified to suit various applications, making it a versatile tool for gesture-based control systems.
