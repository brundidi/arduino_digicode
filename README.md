# Arduino Password Management System

This Arduino project allows you to secure access using a password, a 16x2 LCD screen, a 4x4 matrix keypad. It also lets you change the password securely at any time.

## Hardware Required

- Arduino Uno (or compatible)
- 16x2 LCD display (LiquidCrystal compatible)
- 4x4 Matrix Keypad
- Jumper wires
- (Optional) LED or relay on pin 13 for access indication

## Features

- **Password entry** using a 4x4 keypad
- **Instructions displayed** on the LCD screen
- **Password verification** (default: `1234`)
- **Change password** with secure confirmation
- **Password stored** in EEPROM (persists after reset)
- **Access indication** via pin 13 (LED or relay)

## Wiring Diagram

| LCD Pin | Arduino Pin | Keypad Row/Col | Arduino Pin |
|---------|-------------|----------------|-------------|
| RS      | 12          | Row 1          | 6           |
| EN      | 11          | Row 2          | 7           |
| D4      | 5           | Row 3          | 8           |
| D5      | 4           | Row 4          | 9           |
| D6      | 3           | Col 1          | A1          |
| D7      | 2           | Col 2          | A2          |
|         |             | Col 3          | A3          |
|         |             | Col 4          | A4          |

## Installation

1. **Download the code** and open it in the Arduino IDE.
2. **Install required libraries:**
   - [LiquidCrystal](https://www.arduino.cc/en/Reference/LiquidCrystal)
   - [Keypad](https://playground.arduino.cc/Code/Keypad/)
   - [EEPROM](https://www.arduino.cc/en/Reference/EEPROM)
3. **Wire your hardware** according to the table above.
4. **Upload the code** to your Arduino.

## Usage

- **On startup:**
  - The system displays "Entrer Code".
  - Enter the 4-digit password (`1234` by default).
  - If correct, pin 13 is activated and "OUVERT" ("OPEN") is displayed.
  - If incorrect, "INCORRECT!" is displayed.

- **Change the password:**
  - When the system is open ("OUVERT"), press `#` to enter password change mode.
  - Follow the on-screen instructions: enter the new code, then confirm it.
  - The new password is saved to EEPROM.

- **Close the system:**
  - Press `*` in "OUVERT" mode to lock and return to the password entry screen.

## Customization

- **Password length:** Default is 4 digits. Change the `Password_Lenght` constant in the code if needed.
- **Default password:** Modify the `FistTimePassword` variable in the code.

Just an STI2D Project
