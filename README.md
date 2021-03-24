# Motion Planning and Control of Self-Driving Car

## Project Overview

<p align="justify">
This project was centered on the complex and challenging task of hierarchical motion planning and control of an autonomous vehicle in a structured urban setting. The entire simulation was carried out using CARLA Simulator.
</p>

<p align="justify">
The global plan was manually incorporated as a list of waypoints and a local planner was implemented in order to handle the behaviour planning (using finite state machines to select safe behaviors to execute and obey traffic laws) and trajectory generation tasks (generating optimal, smooth paths and velocity profiles to navigate safely around static and dynamic obstacles). The planned trajectory was then tracked using PID controller (for longitudinal control) and Stanley controller (for lateral control).
</p>

## File Description

- `Waypoints.txt` together with `Parked_Vehicle_Parameters.txt` and `Stop_Sign_Parameters.txt` host the global plan of the entire mission.
- `Behavioural_Planner.py` determines the high-level behaviour (in terms of goal state) to be adopted by the vehicle based on varying driving conditions.
- `Local_Planner.py` handles the reactive local path planning for the vehicle based on the planned behaviour.
  - `Path_Optimizer.py` is used to plan a set of smooth proposal paths offsetted laterally from one another using polynomial spiral optimization to each of the
        goal states (obained using behavioural planner) and returns the resulting optimized path that best fits the current goal state.
  - `Collision_Checker.py` is used to check potential collision of vehicle with any obstacles based on the planned paths and obstacle map using circle approximation.
  - `Velocity_Planner.py` is used to compute a speed estimate based on the previously planned trajectory and the time elapsed since the last planning cycle.
- `Controller.py` is used to implement the lateral and longitudinal controllers for tracking the generated trajectory.
- `Drive.py` hosts the simulation parameters, connects with the simulator and runs the entire motion planning and control pipeline for autonomous driving.
- `Live_Plotter.py` generates and updates plots of the vehicle states and trajectory in real-time.
- `Results` directory hosts the results of a complete trajectory tracking mission in form of plots and log files.
