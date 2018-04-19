# PID-Control-Project-T2P4

Udacity Self-Driving Car Nanodegree - PID Control project

# Introduction

In this project I have implemented a [PID controller](https://en.wikipedia.org/wiki/PID_controller) to control a car in Udacity's simulator([it could be downloaded here](https://github.com/udacity/self-driving-car-sim/releases)). PID control is used here to adjust a car to the recieved values of speed and angle. The simulator sends cross-track error(which is the error in the car position with respect to the lane center), speed and angle to the PID controller(PID) and the contoller responds back with the steering angle ([-1, 1] normalized) and the throttle to drive the car.

### Describe the effect each of the P, I, D components had in your implementation.

- The proportional part of the controller tries to keep the car in the center of the line. It changes the steering angle proportionally according to the CTE. 

- The integral portion tries to eliminate a possible bias on the controlled system that could prevent the error to be eliminated. If used along, it makes the car to go in circles. In the case of the simulator, no bias is present. 

- The differential portion helps to counteract the proportional trend to overshoot the center line by smoothing the approach to it. It also checks if a car has mantained an error over a period of time and tries to minimize this. This might be due to the wrong alignment of the wheel.

### Describe how the final hyperparameters were chosen.

I arrived at the final values of the hyperparameters by manual trial and error approach. I used the same value of Kp as was given in Udacity's lessons. I tried using only P controller but found that the car was oscillating to much. Then I used a Kd of 5.0 which allowed the car to have a term of differential error according to the change in the CTE. I have kept the Integral coefficient small enough. Integral error is minimized to smoothen the adjustment of the car to the desired values.

My final Hyper parameters are as below:
#### P: 0.2 
#### I: 0.00004 
#### D: 5.0

## Simulation

### The vehicle must successfully drive a lap around the track.

A short video with the final parameters is [./video_output.mp4](./video_output.mp4).
