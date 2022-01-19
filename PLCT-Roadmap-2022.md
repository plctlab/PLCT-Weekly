# PLCT Roadmap 2022

大家好，这是 PLCT Lab 第三年公开实验室在 RISC-V 开源生态系统中的 Roadmap。
在 2022 年我们将会继续加大在工具链、虚拟机、模拟器上对 RISC-V 的支持力度。
在 GCC、LLVM、V8、QEMU 等社区的投入会继续加大。
同时我们很高兴地宣布，Tarsier Team 完成了孵化，将会开始作为ISRC的一个独立的操作系统团队进行运作。

## 主体工程

### Tarsier Team 开始独立运作

### RISC-V 笔记本电脑的软件系统

### RISC-V Lab、PTS、和其他基础设施

## 从无到有：编译器和虚拟机的 RISC-V 适配

### Spidermonkey

### LuaJIT

### DynamoRIO

### Valgrind

### DartVM

### LibreOffice

- 让 LibreOffice 的 Writer、Calc、Impress 可以在 RISC-V 平台上稳定运行，并实验性支持 Draw、Math。
- 通过 Tarsier Project 为各个 Linux 发行版用户提供预编译二进制包。

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
- 继续组织 GCC

### Clang/LLVM

- 作为 Development Partner 继续协助 RVI 提供各种草案标准的 GCC 实现。
- 提供更多的CI基础设施，更加及时的发现破坏掉RISC-V平台的patchset并进行修复。
- 将 Clang/LLVM 的速度和代码体积等性能指标纳入 PTS 进行跟踪。
- 尝试实现和优化 Vector 和 P 扩展的自动向量化支持。
- 让 Gold Linker 可以支持 RISC-V。

### OpenJDK

在 2021 年，华为BishengJDK团队和阿里云JVM团队开始向 OpenJDK 上游社区提交 RV64GC 的 patchset。 PLCT 实验室负责了 RV32GC 的适配开发任务。原计划半年的项目结果开发了一年多，终于在2022年的第一个星期完成 RV32GC 下 helloworld.class 的运行。在2022年，我们希望：

- 完成 OpenJDK RV32GC 后端的 JIT （C1） 实现，并进行上游提交。
- 跑通常见的 Java benchmarks 并寻找优化机会提高性能。
- 将 OpenJDK for RV64GC 和 RV32GC 纳入 PTS 进行实时性能跟踪。

### OpenCV

在 2022 年我们将继续支持 OpenCV 在 RISC-V 上的性能，使用包括 Vector、P扩展在内的扩展进行优化。

### openEuler RISC-V

作为 Tarsier Project 的一部分，我们将 openEuler RISC-V 的支持纳入到了 Tarsier Project 2022年的计划中。希望在 2022 年底的时候， openEuler 在 RISC-V 上能够做到 fedora 和 debian 同样的支持程度。

## 教育

- 培养100名实习生，并在实习结束时达到LV2以上。
- 完成一本 V8 相关的书籍撰写。
- 完成一本 OpenJDK 相关的书籍的撰写。
- 完成一本 QuickJS 相关的书籍的撰写。
- 完成一本模拟器原理及开发的书籍。

### 实习生、校招、社招 同时进行，欢迎咨询和投简历！

只要感兴趣就可以给我发邮件： "吴伟 <wuwei2016@iscas.ac.cn>"
