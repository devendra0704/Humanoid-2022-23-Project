# Humanoid_2023

## Aim
To design and build a bipedal robot by synthesizing the gait of a planar biped walking on a level ground.

## Screenshots
![cea14d38dc9811ed87aa27843109546c](https://github.com/user-attachments/assets/7a1a9d75-2030-45a0-b901-0e3af0fd96e8)

## Overview
The project aims to develop a bipedal robot using Arduino which walks and moves  like a human. The model consists of ten degrees of freedom, with each leg having five degrees of freedom. Both ends of the legs are connected to the torso. The Torso is a rigid body. This robot can move in a straight line in any direction using the concepts of inverse kinematics.


## Screenshots
![download](https://github.com/user-attachments/assets/8b85455b-fb86-4059-99dc-9f1a102ccdb3)

## Tool and Technology used
- Arduino Mega
- Servo Motor
- Inverse Kinematics

## Working of the bot

According to the reciprocal contact of one leg and the ground, a classical human gait cycle is composed of stance, where the foot is on the ground, and swing. In the context of biped robots, walking can be considered as a repetition of one-step motion. The motion cycle can be divided into the single support phase and the double support phase.

Single support refers to the fact that one foot holds the robot’s weight while the other foot is moving forward in the air.

To make our robot stand properly, we hung our robot with rope above the ground and tuned each servo motor. We hung it with the rope because while tuning, it may fall down and leads to hardware damage to the robot.

 

### Walking of the robot can be described in these steps:

At first, the bot is in a standing position.
Robot bends its knees so that it will be able to  swing one leg above the ground and put both legs on the ground before making new walking steps. We say this position is a sitting position. 
Swinging one leg above the ground. To swing it's free leg to make a new step, robot tilts its upper body to the opposite side so that leg gets enough height for the swing.
Both legs in the ground to make further walking steps.
At the end, both legs come together to its normal standing position.
 

Forward and inverse kinematics are  implemented to determine the main parameters affecting humanoid robot behavior and specify the reliable method to control motion and preserve stability. The most frequently practiced parameters to be defined are joint parameters, including required drive torques, angles, and relative twists.

Forward or configuration and inverse kinematics for humanoid-The forward kinematics problem represents the relationship between the individual joints of the robot humanoid and the position and orientation of the tool or end effector.

The parameters for the 10 DOF of the lower body can be used further for forward and inverse kinematics to generate a trajectory:

Trajectory of hip, foot and center of mass was generated for the best

stability of the biped system.

A third-order polynomial function with variable t (time) is used to describe its trajectories. 

## Side View
![download](https://github.com/user-attachments/assets/8da7d8e4-0617-4d27-97d6-17ef9d529211)

## Front View
![download](https://github.com/user-attachments/assets/0d2d9fa0-2ac8-4d1f-83b8-a33872c5fa1e)

## Methodology
At first we acknowledged different motions of our robot and through that motion we planned the trajectories and find different positions of our robot.Then we used the concepts of inverse Kinematics to find different joint angles of servo motor for best possible walk

![download](https://github.com/user-attachments/assets/3e4c6388-5c29-4f10-b386-a81d14d56159)

## Trajectories
Trajectory planning helps us in finding a time series of successive joint angles that allows moving a robot from a starting configuration towards a goal configuration in order to achieve a task.

We used different trajectory equations for the better stabilization of our robot

Third order Polynomial function-A third order polynomial function with variable t (time) is used to describe the trajectories of the robot.
Third-order polynomials were used so that distance, speed, and acceleration all will come into consideration during trajectory planning.
X = a0 + a1(t) + a2(t)2 +  a3(t)3

### Trajectory of hip center
The hip center of a biped robot is a critical point for controlling its motion. By determining the trajectory of the hip center, the robot's movement can be controlled. The trajectory can be defined as a hyperbola, an ellipse, or a straight line.

Hyperbolic Trajectory: A hyperbolic trajectory of the hip center involves moving the hip center of the robot in a pattern that resembles a hyperbola. This type of trajectory is useful for applications that require the robot to move in a controlled and agile manner. The joint angles required for the robot to move the robot by using a hyperbolic trajectory of the hip center of the robot can be calculated using inverse kinematics.

Elliptical Trajectory: An elliptical trajectory of the hip center involves moving the hip center of the robot in a circular or oval pattern. This type of trajectory is helpful for applications requiring the robot to move in a more stable and controlled manner compared to hyperbolic.  The joint angles required for the robot to move by using the elliptical trajectory of the hip center of the robot can be calculated using inverse kinematics.
Straight Line Trajectory: A straight-line trajectory of the hip center involves moving the hip center of the robot in a straight line. This type of trajectory is suitable for applications requiring the robot to move from one point to another more quickly, efficiently, and in a stable and controlled manner compared to elliptical and hyperbolic. The joint angles required to move the robot by using the straight-line trajectory of the hip center of the robot can also be calculated using inverse kinematics.
 

And the straight line equation helps our robot for the best possible walk.


### The trajectory of foot

The trajectory we have used for the foot of the robot during its walking step(taking its foot above the ground and putting it forward on the ground ) is an elliptical trajectory.Because an elliptical trajectory helps our robot for better stabilization and agile walking.

#### Various motions -

-**Left leg starting-** In this process, our robot bent its knee and tilted towards the right by changing the position of the hip center to 0.54 of the width of its hip so that it gets enough height to put the left leg forward to the right leg,  ensure  both legs are in contact with the ground and for the balancing of the robot on one leg. And then re-center its hips to its primary position.
The third-order polynomial function with variable t (time) was used for movement of the hip to the right when the robot takes its left foot off the ground. And we have used a straight-line trajectory for bringing the hip to its primary position.

-**Right leg walking-** In this process the robot swings its right leg above the ground and moves forward by tilting towards left for the further walking steps and when both legs are in contact with ground the hip comes back to its primary position.
The third-order polynomial function with variable t (time) was used for the movement of the hip to the left when the robot takes its right foot off the ground. And we have used a straight-line trajectory for bringing the hip to its primary position

 
-**Left leg walking-** In this process, the robot swings its left leg above the ground and moves forward by tilting towards the right for the further walking steps, and when both legs are in contact with the ground, the hip comes back to its primary position.
Here also, the same concept was used for hip center trajectory as used in the right leg walking .

-**Right leg stopping-** In this process, the robot swings its right leg above the ground and moves forward by tilting towards the left and puts the right leg parallel to the left so that it comes back to its standing position.
To stop the robot, firstly, we used the straight line trajectory to re-center the hip to its primary position and then used the third order polynomial function to put the foot also to its primary function and so once again our robot comes to its standing position.

## Inverse kinematics
To control the motion of a biped robot, it is necessary to determine the movement of its individual parts. Inverse kinematics is the method used to calculate the required joint angles for the robot to achieve a particular desired position or motion.
The inverse kinematics provide closed-form solutions to finding joint configurations that drive the end effectors of the robot to desired target positions in the three-dimensional physical space.

![download](https://github.com/user-attachments/assets/9c617f77-f9a0-4a17-a626-55b8cf0f570e)

By using inverse kinematics we find the different joint angles of each servo motor from the position of our robot for the perfect stable motion.

The joint angles was found by using the concepts shown below:
![download](https://github.com/user-attachments/assets/5563bb66-b232-4847-b88b-826bc5d38173)


### Joint angle positioning
Once the trajectory pattern is determined, the required joint angles for the robot to achieve the desired motion along that trajectory can be calculated using inverse kinematics. Inverse kinematics involves using the geometric properties of the robot and the desired position or motion to calculate the required joint angles.



