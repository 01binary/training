# Introduction to Inverse Kinematics
## Writing Numerical, Analytical, and Geometric Solvers

Explore different approaches to Inverse Kinematics and write custom solvers for the MoveIt framework in ROS.

### About this course

Learn to calculate the positions of robot arm joints that place and orient the end-effector to the desired target.

While tools like IKFast auto-generate equations and KDL integrates with MoveIt out of the box, challenges can arise with specific robot configurations and complicate troubleshooting for users unfamiliar with these solvers.

We will cover key concepts such as Gradient Descent and Jacobian matrices, examine the inner workings of KDL and IKFast, and follow the same process to write custom solvers that work with MoveIt framework, which supports standard tasks like Pick and Place out of the box.

### Who is this course for?

+ Robotics enthusiasts building robots from scratch
+ Web developers re-defining themselves as Robotics Engineers
+ Mechanical, Electrical, and Automation engineers crossing into robotics
+ Data Scientists seeking hands-on work in robotics
+ High school senior - college freshman level of education required

### Table of contents

#### Describing a robot with URDF

> Whether you use a wizard or calculate inverse kinematics manually, you'll need to describe the configuration of your robot: how its pieces are attached together and how they can move.

Welcome to the Inverse Kinematics course!

We’re going to start by learning about the Universal Robot Description Format, or URDF. This will let us experiment with real robots right away, while also helping us visualize how inverse kinematics works.

***

I hope this hands-on experience has given you a clear understanding of how the URDF comes together and how the parts connect. Great job following along—you're one step closer to controlling real robots!

#### Using the KDL solver

> Get IK working quickly for a robot arm with 6-DOF or more, characterized by forearm and wrist joints that can twist as well as rotate.

#### Auto-generating a solver with IKFast

> Get IK working quickly for a robot arm with less than 6-DOF, characterized by a wrist and forearm that can only rotate in one plane similar to an excavator arm.

#### Modeling robot joints

> Learn how homogenous (4x4) transformation matrices are used to describe the way various parts of a robot fit together and simulate the behavior of real mechanical components.

#### Denavit-Hartenberg Parameters

> Joint matrices can be built by multiplying transforms in order, or by using an old robotics convention that describes a matrix with four parameters. Restricting each joint to use few parameters with specific meanings can simplify the model and make it easier to communicate to others.

#### Forward Kinematics

> Learn how to use Blender to visualize kinematic chains, calculate forward kinematics, and preview inverse kinematics solutions.

#### Components of the End-Effector matrix

> Visualize the four vectors that make up the end-effector matrix, and understand how they affect the orientation of the end-effector. This is important whether you need to grasp or touch something with the robot arm.

#### Types of Inverse Kinematics solvers

> There are different ways to solve for joint variables that will place the end effector in a desired pose. Numerical solvers are general purpose and only require Forward Kinematics but can be slower and fail to find a solution. Analytical and Geometric Solvers are hard-coded and fast, but require math specific to your robot.

#### Numerical Solvers

> Introduction to solving Inverse Kinematics numerically, as opposed to finding exact Analytical or Geometric Solutions. This is done by iteratively making small changes to joint positions, watching what happens to the end-effector pose, and using this feedback to reach the target pose.

#### Gradient Descent in Python and C++

> Various flavors of the Gradient Descent algorithm are often used in robotics to solve non-linear equations. As we'll see later, an exact solution for Inverse Kinematics requires solving a system of non-linear equations (equations that include sines, cosines, or tangents). Gradient Descneet is a simple tool invented specifically to tackle these kinds of problems.

#### Jacobian and Newton-Raphson in Python and C++

> The Newton Raphson Iterator algorithm is similar to Gradient Descent and uses a Jacobian matrix to record the influence of each joint variable on the position of the end-effector. This matrix frequently appears in robotics because it's also used to determine the torque required on robot joints to achieve a certain force at the end-effector.

#### Sampling-based Solvers

> An overview of how sampling algorithms used by KDL sampling solver are able to find solutions in the presence of constraints and avoid collisions with objects in robot's workspace.

#### Robot Workspace

> Understand how your robot description dictates the space it's able to reach, and how to generate a mesh that desribes all points reachable by your robot.

#### Mapping Workspace to Configuration Space

> A key concept behind sampling based IK solvers is mapping the robot's workspace onto configuration space, and looking for paths through this configuration space that lead to the target pose.

#### PRM Sampling Solver in Python and C++

> Investigate how the default algorithm used by KDL sampling solver, called Probabilistic Roadmap (PRM) works under the hood and write your own sampling solver in Python and C++.

#### Analytical Solvers

> An overview of how to find an exact solution to an Inverse Kinematics problem analytically when using transformation matrices to model your robot's joints.

#### Designing Analytical Solvers

> Use popular mathematical tools like GNU Octave and Matlab to define an inverse kinematics problem for your robot and manipulate the equations until you get exact expressions for each joint variable based on the desired end effector pose.

#### Geometric Solvers

> An overview of inverse trigonometric functions and the Law of Cosines can be used to find an exact solution for simple robot arms with few degrees of freedom.

#### Inverse Tangent

> Using inverse tangent to find an angle that will make the robot arm point toward the desired location.

#### Inverse Sine

> Using inverse sine in situations when the pieces of the robot arm do not sit on the same plane, and may be offset.

#### Law of Cosines

> Using Law of Cosines to solve inverse kinematics for 3-DOF and 4-DOF (excavator-like) robot arms.

#### Writing a MoveIt IK Plugin

> While having a working inverse kinematics solution for your custom robot arm is valuable, plugging it into a framework that supports standard behaviors like Pick and Place (for warehouse robots) or Cartesian Planning (for welding robots) will let you focus on making your robot useful quickly.

#### Writing a MoveIt Motion Planning Plugin

> Sometimes the default motion planner in MoveIt may not work with a custom solver - perhaps the solutions are good enough for you, but not precise enough for MoveIt. In this case it's simple to write your own motion planning plugin, which controls how your robot arm will move through the various positions on its way to the goal.

#### Additional Resources

> Creating this course required a lot of research, and in this section we'll list all the resources used to let you go in depth on any topic. This should help you bridge the gap between what's offered in this course, and additional knowledge you may need to get your robot working perfectly in production.