## MPC with a Quadrotor to track a moving subject while avoiding a moving obstacle

Link to solution: https://colab.research.google.com/drive/11OneVFQIDeRMdVRs3Kff1fRPsFj_Q7Tq#scrollTo=-dnaeE8jFxXo

In this project I implemented Model Predictive Control to enable a drone (blue) to track a moving subject (yellow) while avoiding a moving obstacle (red) using Potential Field Theory. 
Additional constraints involved tracking the subject from a specified relative angle while also maintaining a desired range from subject. 


<img src="mpc.gif" />

My approach to solving this task:
1. First, I predict the subject and obstacle trajectories for a fixed horizon by assuming that they will both travel at a constant velocity throughout the horizon.
2. Using the predicted trajectories of the subject and the obstacle, I then generate a trajectory for the drone. This trajectory takes into account the drone's angle from the subject, the drone's range from the subject and the drone's distance from obstacles.
3. Finally, I use an MPC controller to find the optimal acceleration inputs in order for the drone to track the generated trajectory. I use the drone's acceleration limits and double integrator dynamics as constraints.
