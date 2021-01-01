# PLCT实验室在RISC-V开发工具方向上的2021规划

更改历史：
- 2021-1-1 v0.2 添加熊大的 wasm-micro-runtime 许愿
- 2021-1-1 v0.1 确定今年的目标

感谢大家在许愿池计划中的踊跃投稿，今年收到了比去年多得多的心愿和建议。根据目前的汇总和排序，我们将 PLCT Lab 在2021年的目标公开如下：

### V8 for RISC-V

在2020年已经开始跟 FutureWei、RIOS Lab 联合成一个团队并向 Google Chromium/V8 进行 Upstreaming。相信在2021年初即可进入上游。根据目前收集到的内容，V8 for RISC-V 项目的2021年度目标如下：

- 继续寻找JS的速度优化机会，将RV64GC上JS的性能相对于当前的速度提升N倍。N尚未确定，由 邱吉 主管后续通过对 AArch64 同性能的V8性能数据决定。
- 开始将 NodeJS 生态纳入跟 V8 项目同等重要的维护，让 RV64GC 上可以无障碍的运行 nodejs 程序。
- 更多的关注 wasm 在RV64GC上的功能完整性和性能提升，为后续的 AIoT 等 wasm 具体的应用场景提供支持。
- 尝试支持 C、V、B、P 等扩展。
- 利用 PLCT Lab 和 RISC-V 国际基金会提供的基础设施对 V8 的性能改进进行跟踪，同时完善 CI 基础设施。
- 新培养至少1名全职员工和至少10名LV3+实习生。

### OpenJDK for RISC-V

2020年Q4我们发起了一个雄心勃勃的计划：让 Java 程序在 RISC-V 上的执行速度相对于 OpenJDK/Zero 提升 100 倍以上。在我们公开发起此项目后不久，我们跟华为公司的 BishengJDK 团队进行了合作，BishengJDK 已经实现了 OpenJDK/HotSpot RV64G 后端的基本实现并进行了开源。经过 PLCT Lab 在 Hifive Unleashed 上的实际对比测试，目前在各类 Benchmark 上获得了 ～20x 的速度提升。在2021年，PLCT Lab 的年度目标如下：

- 与包括华为在内的更多的国内外团队合作，让 Java 程序在 RV64GC 上的执行速度相对于 OpenJDK/Zero 提升 100 倍以上。
- 协助BishengJDK团队进行 Upstreaming。
- 尝试支持 C、V、B、P 等扩展。
- 利用 PLCT Lab 和 RISC-V 国际基金会提供的基础设施对 OpenJDK/HotSpot 的性能改进进行跟踪，同时完善 CI 基础设施。
- 新培养至少1名全职员工和至少10名LV3+实习生。

### C/C++ Toolchain for RISC-V

在2020年 PLCT Lab 的编译器分支将主要精力放在 RISC-V Vector Extension 在 LLVM 上的实现。通过 rvv-llvm 开源实现，培养了约10名新人员工及实习生；与LLVM上游社区以及sifive等活跃的同行开始建立更为广泛和频繁的联系。在 rvv-llvm 项目之外，编译器分支还在 Zfinx 等扩展上进行了尝试。

在2020年下半年，PLCT Lab 开始更加积极的融入 RISC-V International 基金会的工作。随着陈嘉炜新员工接手 Zfinx 在 GCC/Binutils/GDB 上的参考实现，PLCT Lab 正式开始参与到 GNU Toolchain 的开发中。与此同时，PLCT Lab 推动了中国科学院软件研究所完成了 FSF Copyright Assignments 的签署，为后续直接参与 GNU Toolchain 上游的开发和代码提交完成了准备。

在2021年，PLCT Lab 计划在 GCC 和 LLVM 项目上完成以下目标：

- 继续推进 rvv-llvm 项目，支持 OpenCV for RISC-V 等V扩展的大型应用项目；培养不少于10名LV3+实习生。
- 更加积极的参与到 RISC-V GNU Toolchain 的开发中，新增至少1名全职员工和至少5名LV3+实习生的投入。
- 在RISC-V领域将LLVM的代码性能和代码体积等指标继续追赶 GNU Toolchain 的进度。
- 提升 LLVM 和 GCC 在 RV64GCV 平台的的代码体积和速度提升（目前没有具体的优化目标）。
- 让 Gold Linker 可以支持 RISC-V。
- 吸引至少3名全职同事加入；培养至少15名LV3+实习生。

### AOSP for RISC-V

Android Open Source Project （AOSP）是目前在手机、平板等领域最为重要的开源系统之一，在软件生态中的重要性是不言而喻的。目前为止除了 PLCT Lab 还没有公司或团队公开的宣称在做 RISC-V 的移植工作，包括 Google 在内。或许大家都在等。不过对于 PLCT Lab 而言，我们应该尽可能早的开始着手尝试，推进整个社区往更广阔的应用场景推进。

在2020年，PLCT Lab 的汪辰老师完成了AOSP的最小系统在RISC-V上运行。在2021年，我们计划：

- 继续推进 AOSP for RISC-V 项目的进行；吸引更多的厂商和社区开发者加入到我们的移植团队中。
- 开始对关键部件 Davlik/ART 进行 RISC-V 的porting工作。此工作 史宁宁 主管将会加入。
- 在2021年12月31日之前，在RV64GC开发板上跑起来AOSP系统并能够启动 hello world Activity。如果进度快的话，能够启动起来 V8 引擎。

### Firefox on RV64GCV

Mozilla Firefox 是自由软件领域非常重要的存在，不仅仅是一个桌面浏览器，Firefox 同时还是多种自由发行版的基础。虽然 PLCT Lab 并不擅长图形栈及渲染引擎部分，但是我们依然觉得 PLCT Lab 有能力也因此应该成为推动 Firefox on RISC-V 的主导/促进力量。在2021年，PLCT Lab 计划完成以下目标：

- 确保 Rust 语言及工具可以流畅的运行在 RV64GCV 平台上。
- 移植 Spidermonkey 到 RV64GC 上，实现功能完整性；如果时间和人力来得及话会开始IonMonkey等JIT的移植工作。
- 组建新的联合开发团队，让 Firefox 能够在 RV64GC Linux 上运行起来。
- 吸引至少1名全职同事加入；培养至少5名LV3+实习生。

### Enable DynamoRIO running on RV64GC

DynamoRIO 是一个比较重要的开发人员使用的性能跟踪和分析工具。在2021年，PLCT Lab 计划完成以下目标：

- 让 DynamoRIO 及依赖的性能分析工具，能够运行在 RV64GC 平台，能够用于 RISC-V 系统或程序的性能跟踪和剖析。

### wasm micro runtime for RISC-V

感谢熊大的补充。在2021年，PLCT Lab 计划完成以下目标：

- 在V8/SM大型引擎之外，移植更多的WASM运行时到RISC-V平台，包括RV32G和RV64G。

https://github.com/bytecodealliance/wasm-micro-runtime


### OpenCV for RV64GCV

OpenCV 是 PLCT Lab 在 RISC-V 领域选定的重点应用库之一。在2020年，张尹同学在GSoC项目的契机下完成了OpenCV对 RVV 1.0-draft 的基本支持，并已经合并到 upstream。后续要做的工作还有很多。在2021年，PLCT Lab 计划完成以下目标：

- 持续维护 OpenCV for RISC-V 项目，追踪 V 扩展的变更直到最终的 ratification 完成。
- 在国产 RISC-V 平台支持 RVV 之后，支持至少一款国产 RISC-V 平台的 OpenCV 优化。
- 吸引至少1名全职同事加入；培养至少2名LV3+实习生。

### LuaJIT RV64G porting

- 尝试进行 LuaJIT 的 RV64G porting；培养至少2名LV3+实习生。

### RISC-V 软件生态完成度跟踪

- 完成一个更为详细的、各种软件对于RISC-V平台的支持情况的跟踪平台。

### Toolchain/Emulator Support for RISC-V International

- 继续 Zfinx 的参考实现。目前已经完成了 GNU GCC/Binuitls/GDB、LLVM、QEMU、Spike 的参考实现，后续随着 ABI 等的草案推进继续更新。
- 参与推动 V、B、P 等扩展的 GNU GCC/Binuitls/GDB、LLVM、QEMU、Spike 的参考实现。

### 实习生、校招、社招 同时进行，欢迎咨询和投简历！

只要感兴趣就可以给我发邮件： "吴伟 <wuwei2016@iscas.ac.cn>"
