---
description: by 刘适源
---

# 海报制作

{% hint style="success" %}
2021 和 2022 赛季的宣传海报和易拉宝是用这种方式制做的，可供参考
{% endhint %}

## 主题和赛题

每赛季 FIRST 会有一个官方主题，如 2020 赛季叫 FIRST RISE，2021 赛季叫 FIRST GAMECHANGERS

同时 FRC 也会有相应赛题，如 20 和 21 年是 Infinite Recharge

这两年海报制作思路都是去 [_FIRST_ 官网](https://www.firstinspires.org)扒图片

其中 FRC 的赛季 logo 可以直接找到下载地址，是一个各种彩色/黑白/横纵的 logo 压缩包

FIRST 主题的宣传图片的话需要自己解析页面元素去扒取

## 官方资源

FRC Resource Library: [https://www.firstinspires.org/resource-library/frc/team-management-resources](https://www.firstinspires.org/resource-library/frc/team-management-resources)

FIRST Brand and Logo Files: [https://www.firstinspires.org/brand](https://www.firstinspires.org/brand)

Season Content and Logos: [https://info.firstinspires.org/free-season-content](https://info.firstinspires.org/free-season-content)\
赛季的资源，包括 logo 文件，社交媒体宣传图片和**海报模板**\
****海报模板不推荐直接使用，但其中有很多图片元素可以用 [Inkscape](https://inkscape.org) 扒下来使用

找到需要的 FIRST/FRC/赛季题目资源下载即可，里边不同文件夹名字代表logo图片文件后缀（png 支持透明背景，svg 为矢量图）

## 手动扒取资源

官方提供的资源往往是不够用的，这时我们就可以去手动扒取赛题网页上的网页元素用

以 22 年为例，[官网](https://www.firstinspires.org)能找到赛季主题入口，22 年赛题链接为[**https://info.firstinspires.org/2021season**](https://info.firstinspires.org/2021season)

该部分最好由有 HTML/CSS 基础（程序组）的同学来做

以 Chromium 内核的Edge浏览器为例（Chrome浏览器步骤一样）

打开网页，右键 - 检查（Inspect）

![](<../.gitbook/assets/Screenshot 2021-12-30 181722.png>)

浏览器右边或下边会弹出开发者工具，以下图为例

![](<../.gitbook/assets/Screenshot 2022-01-01 184726.png>)

红色小按钮用来选取页面元素，点一下后鼠标放在网页上每个选中的 block 都会和右边的 html 源码相对应

黄色圈内区域是该网页 html 代码，鼠标点到一个标签会在左边网页上标出相对应的展示效果

绿色圈内是当前选中的 html 标签的 css 样式

一般我们所需的图片都会是标签，如![](https://thisisanimage.svg)

![](https://tcs-ga.teambition.net/storage/111x5425f37350388a956dc90b3a470e6721?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTYwMzAyOTEzOSwiaWF0IjoxNjAyNDI0MzM5LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzExMXg1NDI1ZjM3MzUwMzg4YTk1NmRjOTBiM2E0NzBlNjcyMSJ9.7NoLWs0TqmTbb3yJdOZiZQ2SVVAhr7OfEZC9drVhO3g\&download=image.png)

如上图中左边logo图片被标出，右边蓝色选中区域是其对应的img标签源码

src=后的引号内是该图片的地址，复制并打开这个链接即可下载（多半是svg文件）

部分内容如页面**背景图片**可能不是由标签实现，而是在css代码中

![](https://tcs-ga.teambition.net/storage/111xea3e4b0d9700be22e22dfdd48beed4b2?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTYwMzAyOTEzOSwiaWF0IjoxNjAyNDI0MzM5LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzExMXhlYTNlNGIwZDk3MDBiZTIyZTIyZGZkZDQ4YmVlZDRiMiJ9.fyUDvHRf91rDleaKhNmGlEfWZJZ3dmEvlkgqWsIARFc\&download=Screenshot%202020-09-13%20111458.png)

如上图中是用background-image这个property实现的，url()内为图片链接

其他非图片元素的颜色、字体等等都可以在html标签或css代码中找到

![](https://tcs-ga.teambition.net/storage/111x80fc3a8365366f067bb0fc46dde0c4a7?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTYwMzAyOTEzOSwiaWF0IjoxNjAyNDI0MzM5LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzExMXg4MGZjM2E4MzY1MzY2ZjA2N2JiMGZjNDZkZGUwYzRhNyJ9.hqnRCS4sEIhO9wF9ZZnaXzWZav\_yAErGrDSeIAcBF0c\&download=Screenshot%202020-09-13%20111923.png)

如上图中"3K+"的字体为Abolition和sans-serif（一般只看第一个字体即这里的Abolition就好了）

![](https://tcs-ga.teambition.net/storage/111x9c27fd5429ea2106dea0702ebe4cc2b5?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTYwMzAyOTEzOSwiaWF0IjoxNjAyNDI0MzM5LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzExMXg5YzI3ZmQ1NDI5ZWEyMTA2ZGVhMDcwMmViZTRjYzJiNSJ9.\_1kG5vMZZ2dg59jLuHU53mzi-S2kaBTg16kY2QFPG2Y\&download=Screenshot%202020-09-13%20112137.png)

如上图中这个绿色的大方块的颜色为#9ac53d（css代码内找到）

最后弄到的图片啦什么东西啦拉到ppt里做海报就行了

如果实在看不懂（因为写详细实在太麻烦了）可以去稍微系统地了解下HTML和CSS

Anyways，这只是这两年我们制作海报的方法，其实主要元素只是FIRST和FRC，并没怎么突显我们自己的队伍。如果有很棒的美工/宣传组成员可以自行制作海报的，欢迎摒弃/结合这种方法！
