# CAN Bus Utilization

CAN 总线都有一定的带宽限制，如果 CAN 的占用率太高会导致机器上的种种问题。过多的 CAN 设备、数据刷新率太高都可能导致 CAN utilization 过高。Driverstation 上可以查看当前的利用率：

![](<../.gitbook/assets/image (3).png>)

DS 上的显示数据可能会频繁跳动导致难以识别具体的利用率，见 WPILib 官方文档[这一帖](https://docs.wpilib.org/en/stable/docs/yearly-overview/known-issues.html#can-bus-utilization-is-noisy)：

> #### CAN bus utilization is noisy[](https://docs.wpilib.org/en/stable/docs/yearly-overview/known-issues.html#can-bus-utilization-is-noisy)
>
> **Issue:** CAN bus utilization as reported live by the DS or as shown in the DS log has significant variation or “spikes” in the data. This is due to the RoboRIO occasionally counting CAN packets in the incorrect time period, so one period will have a much lower utilization than reality and the next a much higher utilization than reality.
>
> **Workaround:** Zoom in on the DS log plot and look for time periods when the utilization is stable (the spikes will be both above and below this average). The average utilization is the true utilization.

## 解决方案参考

* 参考[https://www.chiefdelphi.com/t/canbus-utilization-cancoders-can-frame-not-received-too-stale/402791](https://www.chiefdelphi.com/t/canbus-utilization-cancoders-can-frame-not-received-too-stale/402791)
* 将 PID 控制转为 on-board
* 参考 254 的 [LazyTalonFX](https://github.com/Team254/FRC-2020-Public/blob/master/src/main/java/com/team254/lib/drivers/LazyTalonFX.java)

&#x20;   不确定是否有效，见 WPILib 开发者的[回复](https://www.chiefdelphi.com/t/does-the-rev-pdh-have-adjustable-periodic-status-frames/404895/11)：

> Doing that doesn’t help anyway. Because the CAN Heartbeats for all the existing motor controllers are sent as part of the control packets, the control packets have to be repeated over the bus anyway. So the control packets are going to go out anyway.
>
> Note this could have changed in recent years, and also could change in future years, but based on the last time I looked at the control encryption this was how they all worked.

* 改变 CAN 设备的 status frame rate，如 TalonFX.setStatusFramePeriod(), CANSparkMax.setPeriodicFramePeriod()
* 参考该[笔记](https://www.hi-im.kim/canbus)

