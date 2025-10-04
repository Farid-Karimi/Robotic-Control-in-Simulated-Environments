# Robotic-Control-in-Simulated-Environments

This project explores how reinforcement learning can be applied to robotic control tasks in simulated settings. Using the Panda-Gym environment, an agent was trained to perform two tasks of increasing complexity: reaching a target and pushing an object. The work aims to show how learning-based control methods can be developed and tested safely within simulations before being applied to physical systems.

### Project Overview

The Panda-Gym simulation provides a controlled environment for testing reinforcement learning algorithms on robotic manipulation problems. The project begins with a simple task where a robotic arm must move its gripper to a given target position. This serves as a foundation for understanding the environment’s dynamics and the training process. Once the agent succeeds at this level, the focus shifts to a more demanding pushing task that involves interaction between the robot and an external object.

### Methods

The initial phase used the PandaReach-v3 environment, where the agent controls the robot’s end-effector using continuous actions along three axes. The Deep Deterministic Policy Gradient (DDPG) algorithm was trained for 25,000 timesteps using a dense reward signal that encourages the agent to minimize the distance between its gripper and the target. Training results show a consistent increase in rewards, suggesting the model learned an effective control strategy.

The next phase introduced the PandaPush-v3 environment, where the robot must push a block toward a goal position. The same DDPG architecture was first applied and trained for 50,000 timesteps. A Soft Actor-Critic (SAC) agent was also trained on the same task for 500,000 timesteps to compare performance. Limited GPU access restricted longer runs, but both agents showed learning progress. The results suggest that while DDPG can learn reasonable strategies, its performance is less stable and slower to improve than SAC in complex manipulation tasks.

### Evaluation

Both agents were tested on 50 new episodes with random initial conditions. For the reaching task, the DDPG agent consistently achieved success across all trials, showing strong generalization. In the pushing task, both agents demonstrated measurable learning, with the SAC model displaying smoother progression and higher success rates over time. The results indicate that reinforcement learning methods can acquire useful control policies for simulated robotic manipulation, although longer training and more powerful hardware could further improve performance.

### Conclusion

This project demonstrates how reinforcement learning can be applied to robotic control within simulated environments. By training and evaluating agents on reaching and pushing tasks, it provides practical insight into the behavior of continuous control algorithms such as DDPG and SAC. While the reaching task was mastered efficiently, the pushing task revealed the limits of short training durations and hardware constraints. The work reinforces the potential of reinforcement learning for developing adaptable control strategies in robotics research.
