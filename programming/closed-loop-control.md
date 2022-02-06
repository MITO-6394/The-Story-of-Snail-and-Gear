# Closed-Loop Control

## Motion Profiling

Chief Delphi 上名为 nuttle 的用户在评价 [Official SDS MK3 & MK4 Code](https://www.chiefdelphi.com/t/official-sds-mk3-mk4-code/397109) 时[这样](https://www.chiefdelphi.com/t/official-sds-mk3-mk4-code/397109/9)解释 motion profile:

> Given how widely this code is likely to be used, and how much derivative work is likely to come from this code, it would be good to explore using ProfiledPIDController, and/or the equivalent on whichever motor controller (especially for steering).
>
> The basic idea is that these controllers work to drive an error to zero. Take the steering controller – its job is to ensure the given swerve module is oriented as commanded. Control inputs can cause the error term to jump (step change in setpoint ==> jump in error). The steering motor moving the module causes the error to change. The controller is chasing zero error.
>
> A basic PID (P/PD/PI) controller uses the position error, and the time integral and derivative to try to smoothly land the module at zero error, at the desired position.
>
> ProfiledPIDController defines the PID error in a different way – it essentially represents planning ahead to arrive at zero position error, then uses PID to deal with the deviation from this time-based plan; there PID error is the position error from the plan, not from the setpoint. This means that PID has less to do, the motion profile is essentially a form of (dynamic) feedforward. In this context, this should make the tuning parameters more robust (and also should allow even better performance). In particular, the plan part prevents the PID part from seeing step errors, and errors should generally be much smaller (unless they accumulate because the feedforward is way off). These things mean PID can be tuned more aggressively, and should make the tuning sweet spot much larger.
>
> The key parameters for this type of motion profiling are the maximum velocity (rotations/s for steering) and acceleration (rotations/s² for steering). There’s a good overview [here](https://www.linearmotiontips.com/how-to-generate-motion-profile-for-linear-system/). WPILib has done a bunch of work in this area.
