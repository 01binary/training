# Introduction to Control Design
## Design and practical applications of PID control
Learn how to control robot actuators with Proportional-Integral-Derivative or PID controllers in C++.

### About this course

Learn about Proportional-Integral-Derivative (PID) algorithm - the most popular way to control devices ranging from valves and heaters to electric motors that move robot joints.

Gain an in-depth understanding of how PID controllers work, examine issues that come up in PID controller design and how to fix them, and understand trade-offs and operational constraints when comparing solutions.

Watch a hands-on demonstration of tuning PID parameters by estimating a mathematical model of a motor under load using a specially built fixture for capturing data.

### Who is this course for?

+ Robotics enthusiasts building robots from scratch
+ Web developers re-defining themselves as Robotics Engineers
+ Mechanical, Electrical, and Automation engineers crossing into robotics
+ Data Scientists seeking hands-on work in robotics
+ High school senior – college freshman level of education required

### Table of contents

#### Why should we learn about control design?

Understanding control design will let you build your own actuators and servomotors. However, even if you use off-the-shelf actuators, you still need control loops to make robots balance, walk, and apply precise amounts of force to objects in their environment.

#### Why should we learn about PID control?

Proportional-Integral-Derivative controllers are ubiquitous not only in robotics (inside Robot Operating System packages like ROS Control) but also in many other areas of mechanical and electrical engineering. It's also a deep subject that starts at high-school level math but quickly drops into graduate level mechanical engineering, making it a great entrypoint for studying control design.

#### What are we going to learn in this course?

Starting from PID controller basics, we will not only implement it in C++ and Python and upload it to a real robot, but also explain how to tune it for your particular application.

#### Who invented PID control?

A brief history of how PID control was invented, and how it spread and gained notoriety until it ended up running on a great deal of modern devices.

#### How does a PID controller work?

PID controllers are a contradiction: they are simple to implement, but hard to configure for a particular application so they work reliably and with no surprises. This makes them a dangerous tool which could be easily misunderstood. We start this course by distilling PID control down to its most basic behaviors.

#### Who is using PID controllers?

Motivation is important for learning - and so we aim to prove that there are quite impressive academic and industrial robots that do fine with PID control. We will also explore more advanced types of controllers in the next two sections.

#### What is Model Predictive Control (MPC)?

In this section we explore MPC controllers popularized by impressive Boston Dynamics walking robots like Atlas. Designing an MPC controller requires understanding the Kalman Filter and Lagrangian Mechanics. Kalman is available as a separate course and Lagrangian Mechanics will be covered in our upcoming course about building two- and four-legged walking robots.

#### What is Non-Linear control?

Modern controllers often use neural networks. Some are tuned by a neural network that learns to respond to non-linear dynamics, others are linearized, and some run real-time predictions. Still others mimic nature using real-time gradient descent to minimize energy use. We won't be covering the design of these controllers in this course as we have a separate course on machine learning.

#### PID controller as a composite of behaviors

Now that we explored where this course fits into the overall robotics curriculum we will take a closer look at what PID controllers really do, and how they can be understood as a sum of disparate behaviors.

#### Proportional term

Proportional term immediately reacts to present error, and it's a measure of how responsive the controller is.

#### Integral term

The integral term rejects constant disturbances and bias: that's why it's less common to see a controller with this term. This term affects how much the controller remembers about the past.

#### Derivative term

The derivative term applies brakes after the proportional term steps on the gas. A derivative is a simple way of predicting the future by extrapolating the current trajectory - much how a driver decides to step off the gas for a smooth transition to a stop, avoiding harsh braking when possible.

#### PID controller envelope

Studying dynamics is challenging because they are so fleeting - that is, until you look at the entire trajectory of an impulse frozen in time.

#### How are PID terms used?

Examine what each PID controller term does concretely by looking at what the response of the controller looks like with the terms added and removed, or re-configured.

#### PID controller characteristics

As you tune PID controllers, you need a way to describe their behavior as opposed to behavior you're looking for. This section provides the foundations for evaluating PID controller performance.

#### Writing a PID controller in Python and C++

We are now ready to look at a concrete implementation of a PID controller. Clocking in at about 3 lines of code it's as simple as it gets - which is why they are so easy to misuse.

#### What are advantages of PID control?

In this section we'll look at why PID controllers have made it into virtually all modern devices from gas meters, stoves, baking ovens and thermostats to servo motors and actuators used in robotics and automation, not to mention industrial process control. These reasons have to do not only with the ease of implementation in hardware or software but also our ability to analyze their behavior.

#### What are PID control weaknesses?

For all of the advantages that a PID controllers offer, tuning them is not that simple. In this section we'll look at common issues to watch out for.

#### Windup

We start with a problem that's the easiest to fix: a controller that's been struggling with a force that was keeping it away from its target for some time, and this force is suddenly removed. The controller has to "be careful" and not lean too far into the force to avoid "losing its balance". Limiting the integral is what gives us that effect.

#### Delay

One of the most confusing issues to debug when tuning a PID controller are violent oscillations caused by feedback delays. They make the controller think what it's doing is not working, and it responds by over-correcting, which in turn causes it to miss the target and cause it to over-correct again.

#### Non-linear dynamics?

One important property of PID controllers is they assume the system they are controlling is linear, but nothing in nature is linear. The trick to handling non-linear dynamics with a simple tool like a PID controller then, is to linearize the model around the area you care about. Of course, to even do that, requires having a deep understanding of the model you're dealing with.

#### Increasing oscillations

One of the most unpleasant aspects of modeling dynamic systems is that it's easy to end up with an unstable model - that is, given a certain impulse the model will start oscillating at ever increasing amplitude: literally spiralling out of control.

#### Steady State oscillation

After considering unstable oscillations, since those are the most dangerous, we now look at a stable oscillation around the resting point of the system being controlled. This is called a steady state oscillation, and we can use the Integral controller parameter to cancel it out.

#### Tuning PID controllers

In this section we explore tuning a PID controller by hand, and explain why more sophisticated methods are necessary to achieve a reliable and precise performance.

#### Building a motor tuning fixture

If you don't already have the hardware you are planning to control you can build a fixture to use for labs in this course. This fixture will combine a motor, one or more encoders, a motor driver, a controller like an Arduino, and a load attached to the motor. If you do have the hardware, you may still want a test fixture so that you don't destroy your robot while tuning its controllers.

#### Writing PID tuning tools

Once you have the hardware to control, you need a simple way to tell the motor to run in a certain direction and with a certain speed. You will also need to collect data from the sensor(s) to examine how the motor responds to these commands. In this section we'll explore how a simple desktop/mobile app can be built to facilitate this. We'll also provide the complete project for you to modify for your particular application.

#### System Identification in Matlab

Matlab System Identification Toolbox makes it easy to profile your motor, given the commands sent to it and the output from the encoder(s). This makes for a simple introduction to this complicated and deep topic. A trial of Matlab with System Identification and Control Design toolboxes will be used.

#### System Identification in GNU Octave

After doing System Identification the "easy way" (with a wizard in Matlab) we'll now get our hands dirty with doing system identification manually, since GNU Octave doesn't have any easy-to-use tools.

#### PID controller tuning in Matlab

Builds on the previous section describing how to perform System Identification in Matlab, and uses the Matlab Control Toolbox to tune a PID controller based on the identified motor profile.

#### PID controller tuning in GNU Octave

Builds on the previous section of manually performed System Identification in GNU Octave to tune a PID controller without simple-to-use visual tools only available in Matlab.

#### Additional resources

We've covered a lot of ground, but System Identification and PID Controller Tuning are deep topics requiring increasingly complex math and engineering sills. In this section we'll explore resources that will help you go deeper and bridge the gap between this introductory course and your application.