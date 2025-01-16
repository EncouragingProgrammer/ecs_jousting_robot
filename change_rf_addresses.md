### Instructions for Changing Addresses on the Robot Car and Remote

**Purpose**: Update the RF communication addresses on the robot car and remote so they operate on unique channels without interference.

---

#### **Materials Needed**:
- A computer with Arduino IDE installed.
- USB cables for connecting the car and remote control boards.
    - NOTE: We had issues connecting to the car arduino boards using a USB-C to USB-C cable from a Mac computer. If you are having trouble connecting to the board (Board should light up), try a different cable, or different computer.
- The project files:
  - `05.1_RF24_Remote_Controller.ino` (for the remote).
  - `05.5_One_Code_Multifunctional_RF24_Remote_Car.ino` (for the car).

---

#### **Steps**:

1. **Open Arduino IDE**:
   - Launch the Arduino IDE on your computer.

2. **Connect the Remote**:
   - Use a USB cable to connect the remote control board to your computer.

3. **Edit the Remote Code**:
   - Open the file `05.1_RF24_Remote_Controller.ino`.
   - Locate the line:
     ```cpp
     const byte addresses[6] = "Free1"; // "Free1" may be different depending on what you've saved it to.
     ```
   - Change `"Free1"` to a unique name for the remote-car pair. Example:
     ```cpp
     const byte addresses[6] = "PairA"; // Use a name that is 5 characters long
     ```

4. **Upload the Remote Code**:
   - In the Arduino IDE, select the correct board (e.g., Arduino Uno) and port under **Tools > Board** and **Tools > Port**.
   - Click the **Upload** button (arrow icon). Wait for the "Done uploading" message.

5. **Connect the Car**:
   - Disconnect the remote and connect the car control board to your computer using a USB cable.

6. **Edit the Car Code**:
   - Open the file `05.5_One_Code_Multifunctional_RF24_Remote_Car.ino`.
   - Locate the same line:
     ```cpp
     const byte addresses[6] = "Free1"; // "Free1" may be different depending on what you've saved it to.
     ```
   - Change `"Free1"` to match the name you used for the remote. For example:
     ```cpp
     const byte addresses[6] = "PairA"; // Use a name that is 5 characters long
     ```

7. **Upload the Car Code**:
   - In the Arduino IDE, select the correct board and port as before.
   - Click the **Upload** button. Wait for the "Done uploading" message.

8. **Test the Pair**:
   - Disconnect the car from the computer and power it on.
   - Turn on the remote and test the communication between the car and remote.

---

#### **Notes**:
- Ensure the address string is exactly 5 characters long.
- Each car-remote pair must have a unique address to avoid interference with other pairs.
- Repeat these steps for each car-remote pair, ensuring each pair has a distinct address (e.g., `"PairB"`, `"Fire2"`, etc.).
