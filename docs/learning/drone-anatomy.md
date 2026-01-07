# Drone Anatomy in Detail

To build a drone, you must understand the hardware stack. It is similar to the human body.

### 1. The Frame (The Skeleton)
* Holds everything together.
* **Material:** Usually Carbon Fiber (strong & light) or Plastic (for smaller drones).
* **Layout:** Most common is "X" configuration, where motors are on the tips of the X.

### 2. The Flight Controller (The Brain)
* **Example:** STM32 BluePill, Pixhawk.
* It has sensors (IMU) to feel if it is falling or tilting. It runs the PID loop thousands of times per second to keep the drone level.

### 3. Motors & Propellers (The Muscles)
* **BLDC Motors:** We use "Brushless" motors because they are powerful and last longer.
* **KV Rating:** Tells you how fast the motor spins. Lower KV = More Torque (Big props), Higher KV = More Speed (Small props).
* **Propellers:** They generate lift. CW (Clockwise) and CCW (Counter-Clockwise) props must be paired correctly, or the drone will just spin in circles on the ground.

### 4. ESCs (The Nerves)
* **Electronic Speed Controllers.** The Flight Controller can't power the big motors directly. It sends a weak signal to the ESC, and the ESC pumps high power from the battery to the motor to make it spin at the exact speed requested.

### 5. LiPo Battery (The Heart)
* **Lithium Polymer.** High energy density.
* **'S' Rating:** Voltage. (3S = 11.1V, 4S = 14.8V).
* **'C' Rating:** Discharge rate. How fast it can dump energy. Racing drones need high 'C' ratings.

---
**📚 Learn More**
* **Deep Dive:** [Anatomy of a Drone: Key Components Explained](https://beyondsky.xyz/blog/hardware/anatomy-of-a-drone-understanding-key-hardware-components)
* **Guide:** [How to Fly a Drone: Beginner's Guide](https://uavcoach.com/how-to-fly-a-quadcopter-guide/)
