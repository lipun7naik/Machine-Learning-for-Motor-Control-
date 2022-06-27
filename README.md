# Machine-Learning-for-Motor-Control
MATLAB Simulation for Motor Control using reinforcement learning.
Please find the Mathworks-excellence-in-innovation  project-218 details from [here](https://github.com/mathworks/MathWorks-Excellence-in-Innovation/tree/main/projects/Machine%20Learning%20for%20Motor%20Control).

## Documentation:-

### Overview
Currently, many industrial motor applications are driven by classical and robust control-based methods. These methods are also cost-effective to run on embedded systems. Conventional control approaches are effective when the system can be modelled predictably. It can be difficult to predict system nonlinearities due to motor parameter changes caused by aging and temperature variation. Therefore, implementing Machine Learning-based motor control methods may provide an alternate pathway to overcome the real-world challenges. Therefore I have used [reinforcement learning](https://in.mathworks.com/help/reinforcement-learning/ug/train-td3-agent-for-pmsm-control.html) which is about learning the optimal behavior in an environment to obtain maximum reward.


### Summary
It is an advanced model for [Permanent magnet synchronous motor](https://in.mathworks.com/help/physmod/sps/powersys/ref/permanentmagnetsynchronousmachine.html) control by using [RL agent](https://in.mathworks.com/help/reinforcement-learning/ref/rlagent.html), Clarke and Park Transform, and three phase inverter.


### Functionality
Basically this model uses field oriented control which is a performant AC motor control strategy that decouples torque and flux by transforming the stationary phase currents to a rotating frame. The Clarke and Park transform uses the stator current(a,b,c) and gives output as D-axis current and Q-axis current. Further the RL agent uses the current control system as agent and PMSM and Inverter as environment. Also, D-axis current, Q-axis current, and its errors, Speed reference(as Speed ref in [p.u.](https://en.wikipedia.org/wiki/Per-unit_system)), Speed feedback(as Speed fb in p.u.) are used as its observation. Then the RL agent determines the actions with D-axis and Q-axis voltages which are used to generate the pulse for three phase inverter which is designed by six numbers of IGBTs and LC filter. Then the RL agent uses the reward signal to minimize the control effort from the previous time step.

### Operation
The Rlagent.m and L7_Project_218.slx are the main files of this project. So keep both the files in the same path while running on matlab. Open and Run the RLagent.m script file. This script file will open a simulink model namely L7_Project_218.slx and after simulation it gives the result. Run at different stop times to see and analyze the graphs. For example run at 0.2 sec stop time to see the three phase voltage Vph graph and run at 10 sec stop time to clearly see the estimated torque graph.
It is known that FOC is used if the rotor speed is known. So for more analysis you can run the model at different Ref_input( Mechanical input to the PMSM) like 3000 rpm, 1500 rpm, 5000 rpm etc and simultaneously different Speed_fb like 2 pu(3000 rpm), 1 pu(1500 rpm), 3.33 pu(5000 rpm) etc.
For video tutorial click [here](https://youtu.be/pflJYQsLRYI)

## Skills:-
+ Matlab and Simulink
+ Power Electronics
+ Control System
+ Reinforcement Learning


