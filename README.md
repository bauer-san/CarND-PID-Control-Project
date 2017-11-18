# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

## Reflection
I instantiated one PID controller to control cross-track error (cte).  I manually adjusted the Kp, Ki, and Kd parameters.  First I zeroed Kd and Ki while I adjusted the Kp, mostly decreasing is until the vehicle lateral behavior was stable.  Then I added Kd to improve the performance and finally started to add a Ki.  I added deadbands and antiwindup to the calculation of the integral term.

Once the vehicle could stay in the lane, I increased the throttle command and saw that the gains that fit for lower speeds caused instability at higher speeds.  The gains would have to be scheduled for speed.  I am more eager to move on to the MPC lessons/projects than writing a function to do gain scheduling and manually tune more PID gains.  Rather than submit the project as-is, I instantiated a second PID controller to control the speed error with fixed SPEED_TARGET=32.  For the speed control, I only used Kp and Ki terms because I think it models the way we drive and it gave acceptable performance.  The Kp and Ki for the speed controller were tuned manually.

![](https://i.imgur.com/hErYJzY.png)

![](https://i.imgur.com/fgs9ZmC.png)