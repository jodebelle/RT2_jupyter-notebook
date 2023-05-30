# RT2_jupyter-notebook

This notebook pertains to the second assignment completed in the Research Track 1 course. The objective was to develop a notebook that would serve as a replacement for the user interface on node_a.

In this notebook, widgets will be utilized primarily to achieve the following objectives:

- Managing the robot's movement within the environment.
- Displaying the positions of the robot and the target in the form of a plot, using FuncAnimation.
- Tracking the targets that are set or cancelled within the environment, including their distance, goal, and quantity.
- Providing information about the distance to the nearest obstacle, which can be shown either in a text box or plotted if the laser scanner is used.
This Python script provides a robot controller for goal reaching and visualizes the robot's position and sensor data in real-time using Matplotlib and IPython widgets. 

## Dependencies
Make sure you have the necessary dependencies installed before running the script.
- Python 3
- ROS (Robot Operating System)
- 'assignment_2_2022' ROS package

## Usage
- Make sure you have ROS running and the assignment_2_2022 package set up.
- Run the script using the command python <script_name>.py.
- The script will initialize the ROS node and set up the necessary publishers, subscribers, and action clients.
- You will see an input field where you can enter the goal coordinates (x and y) for the robot.
- Click the "Send Goal" button to send the goal to the robot. The robot will start moving towards the goal.
- The robot's position will be plotted in real-time using Matplotlib. The plot will be updated as the robot moves.
- The script also displays a bar chart showing the number of goals reached and goals cancelled.
- If you want to cancel the current goal, click the "Cancel Goal" button.
- The script will continue running until you stop it.

## Components
### Visualiser Class
- Manages the real-time visualization of the robot's position using Matplotlib.
- Initializes the plot and sets the plot limits.
- Receives odometry and scan data from the robot and updates the plot accordingly.
- Provides a method to display the final trajectory.
### RobotController Class
- Initializes the ROS node and sets up the necessary publishers, subscribers, and action clients.
- Uses IPython widgets to provide a user interface for sending and canceling goals.
- Updates the bar chart showing the number of goals reached and goals cancelled.
- Handles the callback function for goal reaching status.
- Runs the main loop to keep the ROS node alive.
### Laser Callback Function
- Callback function for the LaserScan topic.
- Updates the value of the closest obstacle distance.
