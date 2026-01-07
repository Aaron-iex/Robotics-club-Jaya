# Understanding PID Control

### The Intuitive Explanation
PID is the math that keeps your drone stable. Without it, if your drone tilted slightly left, it would just keep sliding left until it crashed. PID is what tells the motors: *"Hey, we are tilting left! Spin the left motors faster to push us back!"*

Think of it like walking to a goal line on a soccer field:

* **P (Proportional) - The Present:**
    You see you are 50 meters away. You walk fast. As you get closer (10 meters), you slow down.
    * *In Drones:* If the drone is far from stable, correct it hard. If it's almost stable, correct it gently.
    * *Problem:* If you only use P, you might stop slightly short or overshoot constantly.

* **I (Integral) - The Past:**
    Imagine a strong wind is pushing you back. You are trying to walk forward, but you aren't moving. The "I" term realizes, *"I've been stuck here for 10 seconds and haven't moved!"* So, it adds extra power to overcome the wind.
    * *In Drones:* This fixes "Drift." If one motor is slightly weaker, the "I" term notices the error adding up over time and spins that motor faster to compensate.

* **D (Derivative) - The Future:**
    You are running towards the goal line. You know if you don't slow down *now*, you will run past it. The "D" term predicts the future based on your current speed and hits the brakes early.
    * *In Drones:* This stops the "Wobble." It dampens the movement so the drone snaps to a locked position rather than bouncing around.

### Summary
* **P:** How far are you? (Power)
* **I:** How long have you been wrong? (Precision)
* **D:** How fast are you going? (Dampening)

---
**📚 Learn More**
* **Watch:** [MATLAB: Understanding PID Control (Part 1)](https://youtu.be/wkfEZmsQqiA?si=seEsNX35H22UxuhU)
* **Read:** [PID Tuning Guide for Multirotors (PX4 Guide)](https://docs.px4.io/main/en/config_mc/pid_tuning_guide_multicopter)
