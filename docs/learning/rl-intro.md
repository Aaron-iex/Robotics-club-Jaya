# Introduction to Reinforcement Learning (RL)

### How Machines Learn to "Think"
Traditional coding involves giving a robot strict rules: *"If you see a wall, turn left."*
Reinforcement Learning (RL) is different. We don't tell the robot *how* to fly; we tell it *what we want* (e.g., "Don't crash") and let it figure out the rest.

### The Core Concepts
RL is like training a dog with treats.
1.  **The Agent:** The Drone.
2.  **The Environment:** The Field or Simulation (Gazebo).
3.  **The Action:** What the drone can do (Move Up, Down, Left, Right).
4.  **The Reward:** The "Treat."
    * +10 Points: Reached the target.
    * -100 Points: Crashed into a wall.
    * -1 Point: Took too long (encourages speed).

### How it Works
At first, the drone crashes randomly (Exploration). Over thousands of attempts, it realizes, *"Hey, every time I fly near that wall, I lose points. But if I fly through the hoop, I get points."* Eventually, it learns the perfect flight path (Exploitation) without a human ever writing a line of flight code.

### Real World Use
In the **CropDrop Bot**, you might use RL to decide the most efficient path to harvest all the ripe crops before the battery runs out.

---
**📚 Learn More**
* **Course:** [Reinforcement Learning Specialization (Coursera)](https://www.coursera.org/specializations/reinforcement-learning)
* **Deep Dive:** [Spinning Up in Deep RL (OpenAI)](https://spinningup.openai.com/en/latest/)
