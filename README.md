# Motion Planning and Control of Self-Driving Car

<p align="justify">
This project was centered on the complex and challenging task of hierarchical motion planning and control of an autonomous vehicle in a structured urban setting. The entire simulation was carried out using CARLA Simulator.
</p>

<p align="justify">
The global plan was manually incorporated as a list of waypoints and a local planner was implemented in order to handle the behaviour planning (using finite state machines to select safe behaviors to execute and obey traffic laws) and trajectory generation tasks (generating optimal, smooth paths and velocity profiles to navigate safely around static and dynamic obstacles). The planned trajectory was then tracked using PID controller (for longitudinal control) and Stanley controller (for lateral control).
