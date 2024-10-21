# VmBasic

2001-2002 期间开发的虚拟机/编译器开源项目代码和资料：

- 关于虚拟机及其编译器的说明
- VmBasic 开发/调试环境的介绍及说明
- 关于其他

所有资料可以通过下面地址下载：

[下载可执行](https://www.skywind.me/resource/vmbeta.zip) [源程序下载](https://www.skywind.me/resource/skywind/vmbsrc.zip) [设计说明书](https://www.skywind.me/maker/VmBasicDesign.pdf)


### 关于虚拟机及其编译器的说明

记得 3DS/MAX 里面实现了一个类似 BASIC 的脚本，Animator 里面实现了一个类 C 的脚本语言，Autodesk 公司的软件对于脚本支持的很出色，好的脚本引擎在乎平台无关性、高效性和扩充性，一个脚本引擎的需要对一个好程序来说非常迫切，于是半年前我写了一款虚拟机，最近又实现了一个类 Basic 的脚本编译器，特性说明：

1) 高效性和独立于平台：由于虚拟机运行是解释二进制的字节码因此速度明显快于每次运行及时解释的脚本语言，比如 Perl 和 PHP，而虚拟机的核心程序代码也经过数个 C++编译器和平台的测试，可以毫无修改的编译运行于多个操作系统。
2) 充分的开放：通过虚拟机的端口 I/O 技术，要对它进行扩充变得十分容易，VmBeta 指令通过输出/输入的方法向用户自己的程序进行通讯，用户通过处理输出输入消息来达到功能的扩充，使它符合你产品的需要，具体的虚拟机实现和设计说明参考文档　`vmbeta.txt` 。
3) 可设安全级别：通过可设置安全级别，对程序运行状态进行监控。

通过半年的修改我自己觉得虚拟机够高效开放，就是 vmbasic 编译器写的没有多高的水准：完全没有对生成代码做优化，弄出许多繁琐的中间代码，不过还是明显快于及时解释语言，通过测试速度大概是 DOS 自带的 QBASIC 程序的三倍左右（可以通过目录下的几个算法程序来实验）。

为了检验其效率和扩充性，我将虚拟机程序扩充了一些作图功能写成了 Windows 版本的，然后用 vmbasic 编写了一个空战小游戏，虽然由于一开始我太相信 GDI 而没有选择 DDraw，且编译器要生成 1/2 左右的重复性代码，但是仍可以从游戏中看出效率来（可以用 vmbide.exe 打开 fire.bas 运行），关于编译程序 VmBasic 的更详细说明见 basic.htm

程序说明：压缩档包括虚拟机运行程序 (vmbeta.exe)，VmBasic 调试开发平台 (vmbide.exe)，四个算法例子 (alex1-4.bas)，一个射击游戏例子 (fire.bas) 及其图片，说明帮助文档若干。。。

### VmBasic开发/调试环境介绍及说明

右边的图是完整的开发环境左边是语句帮助，中间是代码编写区，下面是编译的错误和过程记录，系统热键说明：

1) F8 编译成 VMS 文件
2) F9 编译并运行程序
3) F1 对 VmBasic 的帮助
4) Shift+F1 帮助 IDE

![](https://skywind3000.github.io/images/p/vmbasic/vmbasic1.gif)

另外点击运行图表左边的图表可以查看编译出来的虚拟机汇编代码。点击工具目录，可以做一系列设置：虚拟机程序设置，预连接库设置，开发环境设置等，都是简单的东西。

用 VmBasic 编写的射击小游戏：必须 Windows 版的虚拟机程序运行（扩充了 GDI 图形功能）

![](https://skywind3000.github.io/images/p/vmbasic/vmbasic3.gif)

显示查看虚拟机汇编：

![](https://skywind3000.github.io/images/p/vmbasic/vmbasic2.gif)

### 关于其他

半年前在论坛上面看见过一些师兄们关于编译的争论，忽然有所感悟，那时刚好写了虚拟机，于是就决定为它写款语言，本来考虑写类 C 或者类 Pascal 的，但是想着 Basic 用起来简单，而且分析起来似乎也简单，后来我才发现虽然没有 C 的编译难写但由于 Basic 经历了长时间的发展，语法变化很大，总的来说没有同意的规范，模块表示也不明确，就连 IF 语句都有好多种版本，所以一个支持函数/过程的 Basic 编译器我觉得比 Pascal 难写的多。目录 DOS 下有 DOS 环境的编译器和虚拟机，可以用来编译运行非扩展的 vmbasic 程序：alex1-4.bas，可以在 IDE 的工具->设置里面设定虚拟机的运行程序。

这是个引擎的演示版本，毕竟好的东西都不是一个人整出来的，我也会在学校不断的学习，非常欢迎来信讨论相关技术，和游戏/图形程式设计，如果你觉得这套引擎对你有价值，可以写信给我，如果你对相关的东西很感兴趣，也可以写信给我。

## Credit

欢迎关注：

- 我的博客：https://skywind.me/blog
- 我的推特：https://x.com/skywind3000



