# PLCT Roadmap 2022

大家好，这是 PLCT Lab 第三年公开实验室在 RISC-V 开源生态系统中的 Roadmap。
在 2022 年我们将会继续加大在工具链、虚拟机、模拟器上对 RISC-V 的支持力度。
在 GCC、LLVM、V8、QEMU 等社区的投入会继续加大。
同时我们很高兴地宣布，Tarsier Team 完成了孵化，将会开始作为ISRC的一个独立的操作系统团队进行运作。

## 关键目标

在2022年PLCT实验室希望能够达到以下关键目标：

1. 准备好RISC-V笔记本电脑需要的软件系统，使得流行的Linux发行版和常用的OA软件、开发工具可以流畅运行在RISC-V笔记本上。
2. 完成一半以上「最后5%」的常用开源软件在 RISC-V 上的移植和适配工作。
3. 通过 Tarsier Project 组建一支 RISC-V 软件测试队伍，为 RISC-V 生态中开源软件的稳定性和软件质量提供保证。

## 主体工程： Tarsier Project

中科院软件所（ISCAS）智能软件研究中心（ISRC）在2021年开始孵化 Tarsier Project。 Tarsier Project 的目标是促进主流 Linux 发行版（包括 Debian/Ubuntu、Fedora、Arch Linux、Gentoo、openEuler 等）对于 RISC-V 平台的支持，达到或超过 AArch64 平台的支持程度。具体分成了以下几个不同的方面：

### Tarsier Team

眼镜猴团队（Tarsier Team）成立于2021年末，承担着软件所 Tarsier Project 所需的各项具体工作。2022年的眼镜猴团队将会从开源操作系统的集成和测试切入，组建超过300名全职、兼职、实习生和志愿者组成的测试小队，为 RISC-V 软件生态系统提供更为全面的质量保证和现状摸底。

欢迎所有对 RISC-V 以及开源工作感兴趣的小伙伴加入我们。随时可以发邮件到 "吴伟 <wuwei2016@iscas.ac.cn>" 询问。同时也招聘修包和开发人员，没有人数限制。

### 为 RISC-V 笔记本电脑优化的操作系统及常用软件

我们预期在2022年底有希望看到 RISC-V 笔记本电脑的问世。中科院软件所会在 RISC-V 软件生态上做好准备。 在2021年，Chromium 和 Firefox 两大开源浏览器已经完成了初步的支持，在2022年PLCT实验室将会与Tarsier团队通力合作，完成包括 LibreOffice 在内的常用软件及系统库的移植和优化工作。

### RISC-V CI Infrastructure for Open Source Communities

在2021年，PLCT Lab 与 RVI 合作，开始组建一个预期超过2000套 RISC-V 开发板的基础设施，并向所有 RISC-V 软件生态中所有的开源社区开放。在2022年，我们将继续完善 RISC-V Lab 的基础设施，完成对 RVI 企业及个人会员的免费开放，RVI 会员将能够直接登陆到哪吒D1开发板上使用RISC-V的软件。

同时，在2022年， Performance Tracking System (PTS) 将会依托于 Tarsier Project 建立的基础设施，开始对 GCC、LLVM、V8、OpenJDK 等基础软件进行性能跟踪。

## 从无到有：编译器和虚拟机的 RISC-V 适配

### LibreOffice

LibreOffice 是非常重要的办公软件，目前还没有能够在 RISC-V 上移植成功。在2022年我们希望能够在 RISC-V 笔记本上使用 LibreOffice 进行日常的OA办公。

- 让 LibreOffice 的 Writer、Calc、Impress 可以在 RISC-V 平台上稳定运行，并实验性支持 Draw、Math。
- 通过 Tarsier Project 为各个 Linux 发行版用户提供预编译二进制包。

### Python Wheels for RISC-V

仿照 [Python Wheels for the Raspberry Pi](https://piwheels.org/)，我们将在2022年尝试维护一个 for RISC-V 的 python 包仓库。感谢 [alexfanqi](https://github.com/alexfanqi) 的建议

### DartVM

Dart 语言正在某些领域变得越来越重要，DartVM 也是目前少数没有被移植到 RISC-V 平台的语言执行环境之一。我们希望在2022年完成 DartVM 的移植工作，为 RISC-V 社区带来一个新的软件生态。

### Valgrind

我们在2021年低估了 Valgrind 的重要性，它被大量的应用软件依赖。我们希望在2022年完成 Valgrind 的移植工作，结束对依赖软件包的阻塞。

### Spidermonkey

Spidermonkey 已经可以在 RISC-V 上通过解释器模式执行。在 2021 年我们与RVI合作开放了一个 Spidermonkey 的 JIT 开发实习岗位。有两名同学进行了开发，遗憾的是目前还没有完成开发工作，尚未运行起来 helloworld.js。在2022年我们预期完成 Baseline JIT 和 IonMonkey JIT 的适配工作，并能够获得超过10倍的性能提升。

### DynamoRIO

我们在2021年提出希望完成 DynamoRIO 的移植工作。很遗憾在2021年没有完成。希望在2022年结束之前完成 DynamoRIO 的 RISC-V 移植并进入 upstream。


### LuaJIT

我们在2021年提出希望完成 LuaJIT 的移植工作。很遗憾在2021年没有完成。希望在2022年结束之前完成 LuaJIT 的 RISC-V 移植。

## 2022年的改进工作

### V8

2021年， 在 Brice Dobry 的带领下， V8 RISC-V 项目顺利的被 Google V8 上游接收，进入 upstream。 由于 RISC-V 目前还是 tier-3 支持平台，开发者新的提交随时有可能会破坏掉 RISC-V 后端， PLCT实验室建立一个独立的CI来检测 V8 最新代码在 RISC-V 平台上的可用性，并已经做到了在平均 1-2 个工作日内提交修复补丁。

在 2022 年，我们希望：
- 继续寻找 V8 的速度优化机会，结合2021年底新 ratify 的 ISA Specs，将 JS 的代码执行速度提升 25% 左右。去年设定的目标是提升N倍，有点草率了。
- 将 V8 的速度纳入 PTS 进行跟踪。

### Node.js

随着 V8 进入上游， Node.js 在 RISC-V 上的使用成为可能。

在 2022 年，我们希望：
- 从 Node.js 16 LTS 开始，提供 RISC-V 的技术支持，确保 node.js LTS 版本在 RV64GC 上的正常运行。
- 通过 Tariser 项目，帮助各大Linux发行版完成 node.js 依赖的 fix。

### Chromium Browser

Chromium Browser 的 RISC-V 适配由 SUSE 工程师 Andreas Schwab 在 2021 年首先完成，PLCT 实验室提供了 V8 方面的技术支持。 除了 openSUSE， Arch Linux、Gentoo Linux、Fedora 等都已经成功的运行起来了 Chromium。

在2022年，我们希望：
- 协助所有 RISC-V 支持的patchset进入 Chromium 上游。
- 将 Chromium 的性能纳入 PTS 进行实时跟踪。
- Tarsier Project 将确保所有流行的 Linux 发行版上有稳定的 Chromium 二进制安装包。

### Firefox

Firefox 的 RISC-V 适配由 Firefox 开发者 Makoto Kato 在 2021 年首先完成，PLCT 实验室的实习生同学将 patchset 成功 rebase 到最新版本并在 Arch Linux、Gentoo Linux、Fedora 等发行版上完成了打包，可以流畅的运行一些常见网页。由于 Spidermonkey 目前还是解释器执行，所以速度上与 V8 相比还有一个数量级的差距。

在2022年，我们希望：
- 完成 Spidermonkey 的 JIT 支持并集成进入 Firefox。
- 协助所有 RISC-V 支持的patchset进入 Mozilla Firefox 上游。
- 将 Firefox 的性能纳入 PTS 进行实时跟踪。
- Tarsier Project 将确保所有流行的 Linux 发行版上有稳定的 Firefox 二进制安装包。

### GCC

- 作为 Development Partner 继续协助 RVI 提供各种草案标准的 GCC 实现。
- 建立基于邮件列表的动态CI，更加及时的发现破坏掉RISC-V平台的patchset并进行修复。
- 将 GCC 的速度和代码体积等性能指标纳入 PTS 进行跟踪。
- 尝试实现和优化 Vector 和 P 扩展的自动向量化支持。
- 持续集成全家桶分支，确保功能可用。
- 让 Gold Linker 可以支持 RISC-V。
- 完善 GDB 中尚未支持的 RISC-V 功能并修复 GDB 中目前已知的所有 bugs。

### Clang/LLVM

- 作为 Development Partner 继续协助 RVI 提供各种草案标准的 LLVM 实现。
- 提供更多的CI基础设施，更加及时的发现破坏掉RISC-V平台的patchset并进行修复。
- 将 Clang/LLVM 的速度和代码体积等性能指标纳入 PTS 进行跟踪。
- 尝试实现和优化 Vector 和 P 扩展的自动向量化支持。
- 完善 LLVM 中 JITLink 中的 RISC-V 支持。
- 完善 Flang 的 RISC-V 支持。

### OpenJDK

在 2021 年，华为BishengJDK团队和阿里云JVM团队开始向 OpenJDK 上游社区提交 RV64GC 的 patchset。 PLCT 实验室负责了 RV32GC 的适配开发任务。原计划半年的项目结果开发了一年多，终于在2022年的第一个星期完成 RV32GC 下 helloworld.class 的运行。在2022年，我们希望：

- 完成 OpenJDK RV32GC 后端的 JIT （C1） 实现，并进行上游提交。
- 跑通常见的 Java benchmarks 并寻找优化机会提高性能。
- 将 OpenJDK for RV64GC 和 RV32GC 纳入 PTS 进行实时性能跟踪。

### Chisel

- 改进 Chisel/FIRRTL 以及 Verilator 的执行速度，减少内存开销。使得 16GB 内存的笔记本也能构建香山开源处理器。感谢 []() 的建议。

### OpenCV

在 2022 年我们将继续支持 OpenCV 在 RISC-V 上的性能，使用包括 Vector、P扩展在内的扩展进行优化。

### openEuler RISC-V

作为 Tarsier Project 的一部分，我们将 openEuler RISC-V 的支持纳入到了 Tarsier Project 2022年的计划中。希望在 2022 年底的时候， openEuler 在 RISC-V 上能够做到 fedora 和 debian 同样的支持程度。

### 来自社区的更多建议

非常感谢所有评论者的建议！

- oreboot & rustSBI： 在2022年我们将会开始关注和提供对 oreboot & rustSBI 的支持。
- herbceptions： 在2022年我们尝试熟悉 [herbceptions：](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0709r1.pdf) 并在RISC-V工具链中进行支持。感谢 [tearosccebe](https://github.com/tearosccebe) 的建议。
- wasm GCC backend： 有趣的想法，我们会在2022年做一些尝试。感谢 [tearosccebe](https://github.com/tearosccebe) 的建议。
- FPGA 优化的 RV64GC （最好 V）软核。感谢 [Icenowy](https://github.com/Icenowy) 的建议。虽然我们还不知道怎么做，但是会努力了。
- 希望PLCT能出够写出关于讲解编译器GCC和QEMU原理的书籍，通过实战来进行分析。感谢 [bigmagic123](https://github.com/bigmagic123) 的建议。今年我们一定不拖了！
- 希望PLCT能够在 RISC-V GCC 上投入精力更好的支持RVV，同时能够支持p扩展和v扩展的自动向量化。感谢 [bigmagic123](https://github.com/bigmagic123) 的建议。已经包含在GCC的年度计划中。
- 希望早日用上GCC/LLVM的RISC-V全家桶版本，并且支持V/P扩展的自动向量化。感谢 [fanghuaqi](https://github.com/fanghuaqi) 的建议。已经包含在GCC的年度计划中。

## 教育、培训、出版物

- 培养100名实习生，并在实习结束时达到LV2以上。
- 策划出一个 RISC-V Linux hacks 系列，为爱好者上手 RISC-V 提供更加有趣的学习体验。
- 完成一本 V8 相关的书籍撰写。
- 完成一本 OpenJDK 相关的书籍的撰写。
- 完成一本 QuickJS 相关的书籍的撰写。
- 完成一本模拟器原理及开发的书籍。

### 实习生、校招、社招 同时进行，欢迎咨询和投简历！

只要感兴趣就可以给我发邮件： "吴伟 <wuwei2016@iscas.ac.cn>"
