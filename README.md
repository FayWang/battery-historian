# battery-historian
Battery Historian is a tool to analyze battery consumers using Android "bugreport" files.

battery-historian工具需要使用bugreport中的Battery History数据，我们在开始的时候需要通过以下命令来打开电池数据的获取以及重置：

1、adb shell dumpsys batterystats --enable full-wake-history

2、shell dumpsys batterystats --reset

上面的操作相当于初始化操作，现在做一些测试，手动或者跑一些自动化的case都行。经过一段时间后，我们运行下面两条命令来将bugreport的信息保存到txt文档中，然后将txt文档转化为html文件：

3、adb bugreport > bugreport.txt

4、python historian.py -a bugreport.txt > battery.html
