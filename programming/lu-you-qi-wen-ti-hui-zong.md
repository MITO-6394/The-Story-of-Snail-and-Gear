# 路由器问题汇总

## Radio Configuration

* 每赛季记得重新下载新版本的 Radio Configuration Utility
* 刷路由器时须**禁用**除连接路由器的以太网口外的**其他网络适配器**\
  ****Windows 11：Ctrl + I 打开 Settings - 左侧选择 Network & Internet - Advanced network settings - More network adapter options，右键其他的适配器，逐一 disable（包括 WiFi 适配器）。刷完路由器后再逐一 enable 即可
* 刷路由器时 Windows 语言须为**英文**（Windows 10/11 在国内有专门的中文版，不可更改系统语言。如果发现自己系统不能更改成英文，须重装英文版的 Windows 或更换设备刷路由器）

![](<../.gitbook/assets/image (4).png>)

* 确保刷练习路由器时勾选 "BW Limit"，该选项会模拟真实 FMS 中的网络带宽限制。测试时如果带宽占用率过高及时调整（减少 Dashboard 回传、减少 print、降低摄像头 resolution 等）以免赛场上出现连接故障
* 不要勾选 "Firewall"，该选项勾选后会模拟真实 FMS 中的防火墙设置，勾选后就无法无线 deploy 程序了，测试时会带来很多不便
* 其他选项和详细解释见 [https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/radio-programming.html](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/radio-programming.html)

## 交换机

* 当机器上有多个网络设备时，需要使用交换机（network switch）来扩展以太网口

{% hint style="warning" %}
淘宝上一拖二/一拖多的水晶网线无法满足多设备共用一口的需求，必须使用交换机
{% endhint %}

* chiefdelphi 上[该帖](https://www.chiefdelphi.com/t/why-you-probably-shouldnt-use-the-second-port-on-your-openmesh-om5p-radio-and-embrace-using-an-ethernet-switch-instead/406374)宣称不应使用路由器的第二个接口而转用交换机，下边有人反驳称应尽量避免使用交换机，值得一看
