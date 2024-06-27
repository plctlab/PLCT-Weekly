# PLCT Roadmap 2024

大家好，这是 PLCT Lab 第5年公开实验室在 RISC-V 开源生态系统中的 Roadmap。

过去的 2023 年，PLCT Lab 经历了成立以来的第一次大裁员，经费削减了 60%，对多个领域进行了大幅度的重新评估的调整：解散了 TARSIER 团队，剥离了 OERV 小队，更加聚焦于 RuyiSDK。 在 2024 年，一方面实验室会会继续延续在基础开源工具链上的投入、完善 RuyiSDK 工程，继续招募超过 200 名实习生为 RISC-V 生态贡献力量；另一方面，为了缓解财务压力， 自 2023 年起承接了多个商业横向项目交付，均圆满交付，得到了甲方客户认可。

经历过挑战，才算有机会验证本心。在 2024 年，PLCT lab 与多家业内伙伴一起，在除夕夜发起了更为宏大的「甲辰计划」。让我们用一纪的时间，在所有基础关键行业领域完成面向RISC-V的适配与优化，并形成超过壹万人的顶尖人才网络。

## 关键目标

在 2024 年 PLCT Lab 希望能够达到以下关键目标：

1. 招募培养超过 200 名 RISC-V 开发实习生。这是甲辰计划 2300 名「开源实习生联合招募培养工程」的一部分。
2. 完善 RuyiSDK， 支持超过 50 款 RISC-V 开发板和超过 20 种操作系统（含 RTOS）。
3. 与国际社区合作，完成 .NET/Mono、 DynamoRIO、 DartVM 等运行时环境的 RISC-V 支持。

## 主体工程： RUYISDK（与2023年相同）

中科院软件所（ISCAS）从2022年下半年开始筹备 RUYISDK 的建设，目前已经完成了团队的初步组建，计划用三年时间为 RISC-V 开发者提供一个完整的、全家桶式的全功能开发环境。 RUYISDK 的目标有：
1. 开发者购买了（几乎）任何一款 RISC-V 开发板或模组，都可以通过 RUYISDK 系统获得硬件资料说明、固件/软件更新、调试支持等。
2. 开发者可以指定任何常用的 RISC-V 扩展指令集架构组合， 都可以通过 RUYISDK 系统生成客户所需的操作系统、工具链、语言执行环境（运行时或虚拟机）、计算库、应用框架等。RUYISDK 将完全支持 Vector 0.7.1 和 RVP 0.5.2 等已经大规模硅化的草案标准（or 厂商定制扩展）。
3. 培育运营一个活跃全面的开发者交流社区。

## 具体目标

由于大部分目标都是 [2023](https://github.com/plctlab/PLCT-Weekly/blob/master/PLCT-Roadmap-2023.md) 年和 [2022](https://github.com/plctlab/PLCT-Weekly/blob/master/PLCT-Roadmap-2022.md) 年的遗留项目，详细的项目介绍略。感兴趣的读者请参考过去两年的路线图文档。

- 完成 [PLCT 许愿池计划 2024](https://github.com/plctlab/PLCT-Weekly/issues/829) 中的所有心愿（持续更新中，摆烂了不复制粘贴过来了）
- .NET/Mono：完成带JIT的移植，达到可用状态。
- PTS： RISC-V Performance Tracking System，拖延了超过 5 年的工程。
- Keystone Engine： 将其 vendor 的 LLVM 更新到支持 RISC-V 的新版本。完成支持，集成进入 RUYISDK。2023年尚未开始。
- LLVM：增加 RISC-V PE/COFF writer 支持。
- [SBCL (Steel Bank Common Lisp)](https://sourceforge.net/p/sbcl/sbcl/ci/master/tree/)，ROS1 依赖项：增加 RISC-V支持
- [Mimick](https://github.com/Snaipe/Mimick)，ROS2 依赖项：增加 RISC-V支持

## 2023年执行情况回顾

**关键目标**

- 【设计开发 RUYISDK， 并围绕 RUYISDK 开源项目形成用户和开发者社区，为后续长期维护夯实基础。】

进行中。中规中矩。

- 【准备好 RISC-V 超算集群所需要的各类软件栈；搭建超过 1024 个计算核心的演示集群，为世界超算 TOP500 做第一步准备。】

受裁员影响，未完成，终止。

- 【进一步扩大 RISC-V 架构上支持的软件规模；阶段性完成 .NET/Mono、LuaJIT、Box64 等在 RISC-V 上的移植工作。】

部分完成。LuaJIT 和 Box64 完成度很好。

**具体目标**

- .NET/Mono：完成带JIT的移植，达到可用状态。【有实习生持续投入 Mono RISC-V 支持，进行中】
- Box64： 完成带有JIT的支持。 完成支持，集成进入 RUYISDK。【完成度很好】
- LuaJIT： 完成JIT支持，收尾。 完成支持，集成进入 RUYISDK。【完成度很好】
- OpenJDK/RV32G： 完成对C2的调试。【接近完成】
- OpenJDK8/RV64GC： 完成 backporting。【裁员终止】
- PTS： 2023Q3 上线运行。【裁员中断】
- DynamoRIO： 完成支持，集成进入 RUYISDK。【完成度很高】
- Valgrind： 完成支持，集成进入 RUYISDK。【转为RISE项目友商完成】
- GHC： 加速 RISC-V 的适配和 bug 修复。【未开始】
- Keystone Engine： 将其 vendor 的 LLVM 更新到支持 RISC-V 的新版本。完成支持，集成进入 RUYISDK。【未开始】
- LLVM：增加 RISC-V PE/COFF writer 支持【待确认】
- [SBCL (Steel Bank Common Lisp)](https://sourceforge.net/p/sbcl/sbcl/ci/master/tree/)，ROS1 依赖项：增加 RISC-V支持【待确认】
- [Mimick](https://github.com/Snaipe/Mimick)，ROS2 依赖项：增加 RISC-V支持【待确认】

