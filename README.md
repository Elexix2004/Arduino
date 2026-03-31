# 🔐 Pin Generating Security System (VAULT)

## 📌 Overview
VAULT is an Arduino-based security solution that generates a **cyclic PIN every 30 seconds**, encrypts it, and transmits it via Bluetooth to an Android application. The system eliminates the need for physical keys or remembering multiple PINs, offering enhanced convenience and security. 

---

## 🛠️ Hardware Requirements
- Arduino Uno (main controller)  
- HC-05 Bluetooth module (transmission)  
- I2C LCD Display (output)  
- Keypad (input)  
- Servo Motor (locking/unlocking mechanism)  
- 9V Battery (power supply)  
- Jumper wires, breadboard, barrel jack  

---

## 💻 Software Requirements
- **Arduino IDE** → Programming the Uno board  
- **Tinkercad** → Circuit mapping and simulation  
- **Android Studio** → Android app development  
- **PowerPoint** → Presentation support  

---

## ⚙️ System Workflow
1. **PIN Generation**  
   - Arduino Uno seeds a random number generator with a time function.  
   - A new PIN is generated every 30 seconds.  

2. **Encryption**  
   - PIN is encrypted using **EXOR** and **bit rotation** operations.  

3. **Transmission**  
   - Encrypted PIN is sent via **HC-05 Bluetooth module**.  

4. **Android Application**  
   - Receives encrypted PIN, decrypts it, and displays it to the user. (the encrypted pin needs to be recieved using an alternate app and then run throught the decryption script as the integrated app is not yet finished)

5. **Validation & Access**  
   - User enters PIN via keypad.  
   - Arduino verifies PIN and signals **servo motor** to unlock vault.  

---

## 🚀 Setup & Usage
### 1. Hardware Connections
- Connect keypad to Arduino Uno input pins.  
- Connect LCD via I2C interface.  
- Attach HC-05 module for Bluetooth communication.  
- Connect servo motor to PWM pin for lock control.  

### 2. Software Installation
```bash
# Install Arduino IDE
sudo apt update
sudo apt install arduino

# Required libraries
Arduino IDE → Add libraries for HC-05, I2C LCD, Servo

