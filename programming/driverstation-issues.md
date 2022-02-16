---
description: 'Contributor: 屠齐越、刘适源'
---

# Driverstation 问题汇总

## Firewall

确保电脑防火墙已关闭

Windows 10  可按 Ctrl + I 打开系统设置或在控制面板内关闭防火墙

## Team number

**确保Team number是用半角（英文）输入法输入！**

### **CAN frame not received/too stale**

可以参考[https://www.chiefdelphi.com/t/canbus-utilization-cancoders-can-frame-not-received-too-stale/402791](https://www.chiefdelphi.com/t/canbus-utilization-cancoders-can-frame-not-received-too-stale/402791)

多是由 CAN bus utilization 太高造成的，driverstation上可以找到 CAN bus 的占用率

1. 将 PID 控制转为 on-board
2. 参考 254 的 [LazyTalonFX](https://github.com/Team254/FRC-2020-Public/blob/master/src/main/java/com/team254/lib/drivers/LazyTalonFX.java)
3. 考虑使用 TalonFX.setStatusFramePeriod()
