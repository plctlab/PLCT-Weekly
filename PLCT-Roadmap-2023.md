# PLCT Roadmap 2023

大家好，这是 PLCT Lab 第三年公开实验室在 RISC-V 开源生态系统中的 Roadmap。
在 2023 年我们将会继续加大在工具链、虚拟机、模拟器上对 RISC-V 的支持力度。
在 GCC、LLVM、QEMU、Mozilla、AOSP、openEuler 等开源项目的投入会继续加大。
同时我们很高兴地宣布，中科院软件所在2023年新立项了 RUYISDK 项目，目标是大大简化目前 RISC-V 开发人员在环境配置、开发、测试、调试、分发等过程的琐碎和痛苦的工作，将更多的精力聚焦在研发内容本身。

## 关键目标

在2023年PLCT实验室（含TARSIER团队）希望能够达到以下关键目标：

1. 设计开发 RUYISDK， 并围绕 RUYISDK 开源项目形成用户和开发者社区，为后续长期维护夯实基础。
2. 准备好 RISC-V 超算集群所需要的各类软件栈；搭建超过 1024 计算核心的演示集群，为世界超算 TOP500 做第一步准备。
3. 进一步扩大 RISC-V 架构上支持的软件规模；阶段性完成 dotNet/Mono、LuaJIT、Box64 等在 RISC-V 上的移植工作。

## 主体工程： RUYISDK

中科院软件所（ISCAS）从2022年下半年开始筹备 RUYISDK 的假设，目前已经完成了团队的初步组建，计划用三年时间为 RISC-V 开发者提供一个完整的、全家桶式的全功能开发环境。 RUYISDK 的目标有：
1. 开发者购买了（几乎）任何一款 RISC-V 开发板或模组，都可以通过 RUYISDK 系统获得硬件资料说明、固件/软件更新、调试支持等。
2. 开发者可以指定任何常用的 RISC-V 扩展指令集架构组合， 都可以通过 RUYISDK 系统生成客户所需的操作系统、工具链、语言执行环境（运行时或虚拟机）、计算库、应用框架等。尤其强调 RUYISDK 将完全支持 Vector 0.7.1 和 RVP 0.5.2 等已经大规模硅化的草案标准（or 厂商定制扩展）。
3. 培育运营一个活跃全面的开发者交流社区。

欢迎所有对 RISC-V 以及开源工作感兴趣的小伙伴加入我们。随时可以发邮件到 "吴伟 <wuwei2016@iscas.ac.cn>" 询问。 同时也招聘修包和开发人员，没有人数限制。

## 具体目标

由于大部分目标都是2022年和2021年的遗留项目，详细的项目介绍略。感兴趣的读者请参考过去两年的路线图文档。

- dotNet/Mono： 完成带JIT的移植，达到可用。
- Box64: 完成带有JIT的支持。 完成支持，集成进入 RUYISDK。
- LuaJIT： 完成JIT支持，收尾。 完成支持，集成进入 RUYISDK。
- OpenJDK/RV32G： 完成对C2的调试。
- OpenJDK8/RV64GC： 完成 backporting。
- PTS： 2023Q3 上线运行。
- DynamoRIO： 完成支持，集成进入 RUYISDK。
- Valgrind： 完成支持，集成进入 RUYISDK。
- GHC： 加速 RISC-V 的适配和 bug 修复。
- Keystone Engine： 将其 vendor 的 LLVM 更新到支持 RISCV 的新版本。完成支持，集成进入 RUYISDK。

## 2022年执行情况回顾

**关键目标**

在2022年PLCT实验室希望能够达到以下关键目标：

- 准备好RISC-V笔记本电脑需要的软件系统，使得流行的Linux发行版和常用的OA软件、开发工具可以流畅运行在RISC-V笔记本上。
  【结果：达到预期目标。 LibreOffice、 Chromium、 Firefox、 OpenJDK、 NodeJS 等都已经支持或进行了速度提升。】

- 完成一半以上「最后5%」的常用开源软件在 RISC-V 上的移植和适配工作。
  【结果：WIP。 我承认在项目立项的时候对于「最后5%」的规模的评估体现了我对长尾现象的无知：随着工作的推进，我们遇到了更多之前未曾分析到的软件移植需求。新增的软件包需求都已经纳入到今年和后续的路线图中。】

- 通过 Tarsier Project 组建一支 RISC-V 软件测试队伍，为 RISC-V 生态中开源软件的稳定性和软件质量提供保证。
  【结果：达到预期目标。TARSIER伙伴们交出了一份出色的答卷。】

**具体目标**

- 为 RISC-V 笔记本电脑优化的操作系统及常用软件： 【达到预期目标。】

- RISC-V CI Infrastructure for Open Source Communities： 【CI Farm 达到预期目标； PTS 将会继续 Delay 到 2023Q3 左右。】

- LibreOffice：【完成，已经 upstream】。

- Python Wheels for RISC-V： 【未完成（未开始）。我们持续招募实习生完成此项任务，欢迎感兴趣的同学联系我们。】

- DartVM： 【Google的Dart团队实现了对 RISC-V 的初步支持。】

- Valgrind： 【推进中，尚未完全支持 RISC-V。】

- Spidermonkey： 【达到预期目标，实现了 RV64GC 的 JIT 支持，并且已经被 Mozilla upstream 接收。】

- DynamoRIO： 【推进中，较缓慢。与 RIVOS 协作。2023年需要加大力度。】

- LuaJIT： 【完成了解释器支持，JIT 的支持尚未完成。】

**2022年的改进工作**

- V8： PLCT维护的被动式CI持续稳定提供2小时内regression发现，V8小队提供了稳定的保障。

- Node.js： 稳定支持。

- Chromium Browser： 在 openEuler RISC-V 等 Linux 发行版上提供了 rpm/deb 安装包并长期更新。未纳入PTS进行跟踪。尚未完成 upstream。

- Firefox： JS 引擎的 JIT 支持合入。在 openEuler RISC-V 等 Linux 发行版上提供了 rpm/deb 安装包并长期更新。未纳入PTS进行跟踪。

- GCC： 除 Gold Linker 的 RISC-V 支持未开展之外，另外6项目标均完成。

- Clang/LLVM： Flang 支持尚未完成。

- OpenJDK： 向 uptream 提交了多份 RISC-V 相关特性支持补丁。 尚未完成 RV32GC 的 C2 JIT 实现（持续捉虫）。

- Chisel： 持续支持改进。

- OpenCV： 持续支持改进。

- openEuler RISC-V： 援引 openEuler Summit 2022 的结论： 「在 RISC-V 架构上， openEuler 已经率先迈入国际先进行列。」

- 来自社区的更多建议：全家桶版本升级成了RUYISDK；在GCC上更多精力的支持了RVV；其它项目许愿鸽了/未完成（自动滚入2023年路线图）

- 教育、培训、出版物： 完成超过100名实习生的培养，新增至少5名LV4+，新增15名 Senior 实习生。 书籍出版集体鸽了。

## 实习生、校招、社招 同时进行，欢迎咨询和投简历！

只要感兴趣就可以给我发邮件： "吴伟 <wuwei2016@iscas.ac.cn>"
