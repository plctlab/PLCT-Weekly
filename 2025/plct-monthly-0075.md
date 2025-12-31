# PLCT 开源进展·第 75 期·2025 年 10 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

## V8 / Chromium

## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/26139 (8358696: Assert with extreme values for -XX:BciProfileWidth)
- https://github.com/openjdk/jdk/pull/27512 (8368732: RISC-V: Detect support for misaligned vector access via hwprobe)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/26658 (8364570: Remove LockingMode related code from riscv64)
- https://github.com/openjdk/jdk/pull/26678 (8365047: Remove exception handler stub code in C2)
- https://github.com/openjdk/jdk/pull/26838 (8365206: RISC-V: compiler/c2/irTests/TestFloat16ScalarOperations.java is failing on riscv64)
- https://github.com/openjdk/jdk/pull/26854 (8365841: RISC-V: Several IR verification tests fail after JDK-8350960 without Zvfh)
- https://github.com/openjdk/jdk/pull/26855 (8365844: RISC-V: TestBadFormat.java fails when running without RVV)
- https://github.com/openjdk/jdk/pull/26883 (8365772: RISC-V: correctly prereserve NaN payload when converting from float to float16 in vector way)
- https://github.com/openjdk/jdk/pull/26935 (8366127: RISC-V: compiler/intrinsics/TestVerifyIntrinsicChecks.java fails when running without RVV)
- https://github.com/openjdk/jdk/pull/26944 (8365926: RISC-V: Performance regression in renaissance (chi-square))
- https://github.com/openjdk/jdk/pull/27047 (8363966: GHA: Switch cross-compiling sysroots to Debian trixie)
- https://github.com/openjdk/jdk/pull/26999 (8364936: Shenandoah: Switch nmethod entry barriers to conc_instruction_and_data_patch)
- https://github.com/openjdk/jdk/pull/26938 (8366747: RISC-V: Improve VerifyMethodHandles for method handle linkers)
- https://github.com/openjdk/jdk/pull/27510 (8368724: RISC-V: Remove AvoidUnalignedAccesses Flag)
- https://github.com/openjdk/jdk/pull/27506 (8368722: RISC-V: Several vector load/store tests fail without support for misaligned vector access)

3. Reviewed JDK-21u/25u mainline PRs:
- https://github.com/openjdk/jdk25u/pull/207 (8365926: RISC-V: Performance regression in renaissance (chi-square))
- https://github.com/openjdk/jdk21u-dev/pull/2121 (8362838: RISC-V: Incorrect matching rule leading to improper oop instruction encoding)

## Go

1. Authored/Co-authored Go-mainline CLs:
- 647596: runtime: unify C -> Go ABI transitions on riscv64 | https://go-review.googlesource.com/c/go/+/647596
- 659175: cmd/link: generate proper attributes for riscv profile | https://go-review.googlesource.com/c/go/+/659175
- 657036: internal/bytealg: vector implementation of count 1 byte for riscv64 | https://go-review.googlesource.com/c/go/+/657036 
- 663778: cmd/asm, cmd/internal/obj: add zvbb/zvbc/zvkb for riscv64 | https://go-review.googlesource.com/c/go/+/663778
- 664155: cmd/asm, cmd/internal/obj: add crypto algorithm suites for riscv64 | https://go-review.googlesource.com/c/go/+/664155
- 664375: cpu: add crypto extensions detection for riscv64 | https://go-review.googlesource.com/c/sys/+/664375
- 663675: cmd/internal/obj: add crypto extension for riscv64 | https://go-review.googlesource.com/c/go/+/663675
- 703215: cmd/compile: Const64F by MOVD with const on riscv64 | https://go-review.googlesource.com/c/go/+/703215 [merged]
- 702695: cmd/internal/obj: add zfh extensions for riscv64 | https://go-review.googlesource.com/c/go/+/702695
- 710035: internal/chacha8rand: improve block by vector for riscv64 | https://go-review.googlesource.com/c/go/+/710035 [merged]
- 711075: chacha20: improve performance for riscv64 | https://go-review.googlesource.com/c/crypto/+/711075 
- 715960: cmd/compile: add ConstantTimeSelect intrinsics for riscv64 | https://go-review.googlesource.com/c/go/+/715960

2. Reviewed Go-mainline CLs:
- 652717: doc, cmd/internal/obj/riscv: document the riscv64 assembler | https://go-review.googlesource.com/c/go/+/652717 
- 646736: internal/bytealg: vector implementation of equal for riscv64 | https://go-review.googlesource.com/c/go/+/646736
- 646737: internal/bytealg: vector implementation of compare for riscv64 | https://go-review.googlesource.com/c/go/+/646737
- 670876: riscv64: add support for RVV 1.0 instructions | https://go-review.googlesource.com/c/arch/+/670876 [merged]
- 670875: riscv64: fix the path to the RISC-V extensions in spec.go | https://go-review.googlesource.com/c/arch/+/670875
- 348389: cmd/compile: emit classify instructions for infinity tests on riscv64 | https://go-review.googlesource.com/c/go/+/348389
- 670875: riscv64: fix the path to the RISC-V extensions in spec.go | https://go-review.googlesource.com/c/arch/+/670875
- 690495: runtime: identify virtual memory layout for riscv64 | https://go-review.googlesource.com/c/go/+/690495
- 702677: cmd/internal/obj/riscv: add support for Zicond instructions | https://go-review.googlesource.com/c/go/+/702677 [merged]
- 703715: cmd/compile/internal/ssa: add codegen for Zicond extension on riscv64 | https://go-review.googlesource.com/c/go/+/703715 
- 707015: riscv64: add support for Zicond  instructions | https://go-review.googlesource.com/c/arch/+/707015 [merged]
- 713560: internal/releasetargets: update list for Go 1.26 | https://go-review.googlesource.com/c/build/+/713560
- 670595: main.star: annotate missing riscv64 builders with tracking issues | https://go-review.googlesource.com/c/build/+/670595
- 715180: runtime: avoid bound check in freebsd binuptime | https://go-review.googlesource.com/c/go/+/715180 [merged]

## OpenCV

## GNU Toolchain

## LLVM Team
- 1. Upstream llvm-project 合并的patch:
  - [DFAJumpThreading] Unfold select to the incoming block of phi user: https://github.com/llvm/llvm-project/pull/160987
  - [SDAG] Constant fold frexp in signed way: https://github.com/llvm/llvm-project/pull/161015
  - [ConstantFold] Fold inttoptr, ptrtoaddr to bitcast: https://github.com/llvm/llvm-project/pull/161087
  - [VectorCombine] Preserve cast flags in foldBitOpOfCastConstant: https://github.com/llvm/llvm-project/pull/161237
  - [GlobalOpt] Check if users are CallBase when changing CC:  https://github.com/llvm/llvm-project/pull/161399
  - [DFAJumpThreading] Constraint the number of cloned instructions: https://github.com/llvm/llvm-project/pull/161632
  - [DFAJumpThreading] Update domtree lazily: https://github.com/llvm/llvm-project/pull/162240
  - [DFAJumpThreading] Set MadeChanges only if threading happened: https://github.com/llvm/llvm-project/pull/162241
  - [DFAJumpThreading] Unify equivalent states: https://github.com/llvm/llvm-project/pull/162447
  - [DFAJumpThreading] Pretty print anonymous blocks: https://github.com/llvm/llvm-project/pull/162607
  - [RegisterCoalescer] Prune live range of early-clobber from live-in: https://github.com/llvm/llvm-project/pull/157628
  - [DFAJumpThreading] Use a single lazy DTU: https://github.com/llvm/llvm-project/pull/162802
  - [DFAJumpThreading] Precompute value => successor mapping: https://github.com/llvm/llvm-project/pull/162824
  - [DFAJumpThreading] Verify dominator tree by option: https://github.com/llvm/llvm-project/pull/163334
  - [DFAJumpThreading] Add MaxOuterUseBlocks threshold: https://github.com/llvm/llvm-project/pull/163428

## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

## DynamoRIO

## llama.cpp

## coreboot for riscv

本期没有新的进展。

## openocd

本期没有新的进展。

## opensbi

- 通过Zkr初始化stack guard。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008930.html)
- 添加P8700 aclint支持。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/009005.html)
- RPMI添加电压、设备功率和性能服务。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008950.html)
- 添加一个unknown nmi的sse event用于在内核发生消息触发panic。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008954.html)
- 把ariane的代码移动到通用平台。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008982.html)
- 添加指令模拟（Zba、 Zbb、 Zbc、 Zbs、 Zicbom、 Zicboz、 Zfhmin、 Zicond、 Zimop、 Zcmop、 Zcb、 Zfa、 Zawrs、 Zvbb、 Supm)。[1](https://lists.infradead.org/pipermail/opensbi/2025-October/008992.html)

## u-boot

本期没有新的进展。

## RevyOS (Debian for Xuantie)

### Debian

## RT-Thread

* 整理V5.2.1版本到V5.2.2版本的日志。[https://github.com/RT-Thread/rt-thread/pull/10877](https://github.com/RT-Thread/rt-thread/pull/10877)
* 推动clang-format-ignore机制。[https://github.com/RT-Thread/rt-thread/pull/10860](https://github.com/RT-Thread/rt-thread/pull/10860)
* 为GD32F5实现非阻塞发送 [https://github.com/RT-Thread/rt-thread/pull/10796](https://github.com/RT-Thread/rt-thread/pull/10796)
* 为GitHub Actions添加concurrency机制。[https://github.com/RT-Thread/rt-thread/pull/10761](https://github.com/RT-Thread/rt-thread/pull/10761)

## PLCT罗云翔测试团队

（包含 SAIL 和 ACT 测试部分）

本月在RuyiSDK的测试与生态完善、操作系统支持矩阵的扩展、Sail/ACT模型的增强以及RISC-V教育推广方面均取得了显著进展。通过多版本测试、工具开发、社区内容建设和会议参与，进一步提升了RuyiSDK的可靠性和影响力。

1. RuyiSDK 多版本测试与生态完善
- 版本测试：完成了 RuyiSDK v0.41.0 和 v0.42.0 版本的全面测试，覆盖 LicheePi4A、RevyOS、ArchLinux、Debian、Deepin、Fedora、Ubuntu、openEuler、Gentoo 等多个操作系统和架构（x86_64、riscv64、aarch64），并提交了详细的测试报告。修复了多个遗留及新增缺陷，提升了软件稳定性。
- 工具开发与增强：
  - 在 `packages-index` 提交了6个PR，修复镜像URL、更新多款开发板镜像至最新版本，并新增了对 Laptop 4A 的官方支持。
  - 在 `ruyi-packaging` 提交了4个PR，优化RevyOS系列包的生成格式和供应商信息。
- 网站与文档优化：
  - 网站前端实现了新闻更新、代码块功能增强、移动端布局优化、多语言翻译更新。
  - 文档站点修复了安装指南、Fastboot配置说明，并优化了代码块展示和IDE相关说明。

2. 操作系统支持矩阵
- 开发板与系统支持：新增了对 Bit-Brick K1、Milk-V Pioneer、LicheeRVDock、HiFive Unmatched 等开发板的支持，更新了 RevyOS、Debian Trixie、openEuler 等多款系统的测试报告。
- 元数据与前端优化：
  - 规范了板卡配置和产品命名，补充了硬件规格信息。
  - 前端修复了标点符号显示问题，提升了用户体验。
- 社区内容建设：在 `ruyisdk.cn` 发布了多篇 RevyOS 工程软件生态观测系列文章，丰富了操作系统支持矩阵的技术内容。
- 完成了20款RISC-V开发板下工具链测试测试用例的验证和验收环境准备。
  
3. Sail/ACT
- Sail模型功能增强：
  - 持续推进 H 扩展支持，测试通过率达76/82，新增 Zicfilp 指令支持。
  - 改进了 CSR 访问检查、陷阱处理等核心机制，提升了模型可靠性。
- 测试框架与工具链优化：
  - 修复了压缩指令集测试覆盖，更新了多个非法指令测试用例。
  - 参与了 Sail 编译器问题修复和代码重构，提升了架构测试的准确性。
  
4. RISC-V教育推广
- 代表软件所参加中国科学院第八届科学节，现场演示了RuyiSDK和大模型、目标检测、ROS机器人操作系统、RevyOS和OpenEuler操作系统、HPC openMPI、嵌入式等在各种国产RISC-V开发板上的应用。
- 技术视频制作：发布了多款开发板的实践教程视频，包括 Avaota F1 快速启动与Wi-Fi功能试用、CanMV K230 AI Demo 试玩等，配套了口播稿和操作文档。
 
### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK v0.42.0-beta.20251017 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251020/README.md)
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251020/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora41 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Fedora41_x86_64_测试结果.md)
    - [Fedora42 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251020/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora42 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251020/RUYI_包管理_Fedora42_riscv64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [openEuler25.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_openEuler25.03_riscv64_测试结果.md)
    - [openEuler25.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251020/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - 缺陷：
      上一版本遗留 2 个缺陷：

      | 缺陷      | 问题等级 | 备注 |
      | ----------- | ----------- | --- |
      | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，修复已经延后  |
      | [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)   | 严重 | 已有文档整体更新计划，已有具体时间节点和时间表安排  |

      新增 1 个缺陷：

      | 缺陷      | 问题等级 |备注 |
      | ----------- | ----------- | --- |
      | [ruyi 0.42.0 版本 extract 命令默认行为改变 #115](https://github.com/ruyisdk/docs/issues/115) | 一般 | 可快速修复 |

    - packages-index 测试

      上一版本遗留 2 个缺陷：

      | 缺陷      | 问题等级 |备注 |
      | ----------- | ----------- | --- |
      | [有一部分包无法下载 #37](https://github.com/ruyisdk/packages-index/issues/37)     | 一般 | 已有相关 issue 回复且已经在修复中 |
      | [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)     | 一般 | 软件自带修复功能，且已有相关 issue 回复 |

      新增 2 个缺陷：

      | 缺陷      | 问题等级 |备注 |
      | ----------- | ----------- | --- |
      | [Broken URL on new mirror:// URLs #117](https://github.com/ruyisdk/packages-index/issues/117) | 一般 | 软件自带修复功能，将在测试周期内修复 |
      | [A large number of old revyos images were deleted #116](https://github.com/ruyisdk/packages-index/issues/116)     | 一般 | 软件自带修复功能，将在下一个开发周期修复 |

      另遗留 2 个不影响出口质量的缺陷：

      | 缺陷      | 问题等级 |判定依据 |
      | ----------- | ----------- | --- |
      | [Jupiter and Megrez missing for MilkV product line support #104](https://github.com/ruyisdk/packages-index/issues/104)     | 建议|根据 ruyisdk/packages-index#6 判定不影响出口质量|
      | [Laptop 4A missing for Sipeed product line support #109](https://github.com/ruyisdk/packages-index/issues/109)    | 建议|操作系统支持矩阵中暂无对该设备支持状态为 basic 的镜像，同时根据 ruyisdk/packages-index#6 判定不影响出口质量|

    - RuyiSDK IDE 测试

      RuyiSDK Eclipse Plugins 0.0.5 版本遗留 2 个缺陷：

      | 缺陷      | 问题等级 | 判定依据 |
      | ----------- | ----------- | ---- |
      | [未配置 PATH 导致无法轻松访问 ruyi #38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)    | 建议 | RuyiSDK IDE 与 RuyiSDK 发布周期分离|
      | [Ruyi 安装下载完成不够明显 #39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)    | 建议|RuyiSDK IDE 与 RuyiSDK 发布周期分离|

      回归测试未通过，不符合入口标准。故本版本不执行回归测试之后的测试流程，或执行了部分测试流程但不载入测试报告。

    - 新增特性测试

      本版本新增特性如下：

      1. ``ruyi extract`` 增加 ``-f`` 与 ``-d`` 参数
      2. 在用户配置的本地 packages-index 缓存位置是否与默认配置相同时认为是默认配置
      3. 修复默认配置下， ruyi 对本地 packages-index 缓存中的 remote url 更新问题 [#373](https://github.com/ruyisdk/ruyi/issues/373)
      4. 默认遥测模式改为本地模式，并在首次运行时询问用户
      5. 将用户手动操作的提示信息在视觉上突出
      6. 修复自动补全会触发首次运行欢迎信息的问题 [#374](https://github.com/ruyisdk/ruyi/issues/374)

      其中 1 已经通过手动测试验证，并加入 litester 测试；其余均手动测试通过。下面的表格记录了 20251017 版本之前测得的问题，均已经修复。

      | 缺陷      | 问题等级 |判定依据 |
      | ----------- | ----------- | --- |
      | [[bug] ruyi self clean --all left ~/.local/state/ruyi/ruyipkg/installs.json undeleted #383](https://github.com/ruyisdk/ruyi/issues/383) | 严重 | 0.42.0-alpha.20251013 没有完整实现软件需求 |
      | [[bug] traceback on ruyi ruyi greet message #384](https://github.com/ruyisdk/ruyi/issues/384) | 严重 | 0.42.0-alpha.20251013 没有完整实现软件需求 |
      | [[bug] ruyi venv qemu support not work properly #392](https://github.com/ruyisdk/ruyi/issues/392) | 严重 | 0.42.0-alpha.20251013 和 v0.42.0-beta.20251015 没有完整实现软件需求 |
      | 重开 [bash-completion: not work properly when running ruyi for the first time #374](https://github.com/ruyisdk/ruyi/issues/374) | 严重 | 0.42.0-alpha.20251013 没有完整实现软件需求 |
      | [ruyi 0.42.0 版本 extract 命令默认行为改变 #115](https://github.com/ruyisdk/docs/issues/115) | 一般 | ruyi 默认行为发生改变导致文档与实际不一致 |

    - 修复情况

      | 缺陷      | 问题等级 |判定依据 |
      | ----------- | ----------- | --- |
      | [Broken URL on new mirror:// URLs #117](https://github.com/ruyisdk/packages-index/issues/117) | 修复 | 已由 [#118](https://github.com/ruyisdk/packages-index/issues/118) 修复 |
      | [ruyi 0.42.0 版本 extract 命令默认行为改变 #115](https://github.com/ruyisdk/docs/issues/115) | 修复 | 已由 [#116](https://github.com/ruyisdk/docs/pull/116) 修复 |

    - 资源
      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/c918eeb6c1fa9e40eb8c52fb76e443b9815486e9)
      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/6094edd22648e2084a2367633401fc569b92cc16)

  - [RuyiSDK v0.41.0-beta.20250922 与 0.41.0-beta.20250926 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250922/README.md)
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250922/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora41 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Fedora41_x86_64_测试结果.md)
    - [Fedora42 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250922/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [openEuler25.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_openEuler25.03_riscv64_测试结果.md)
    - [openEuler25.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - 缺陷：
      - 文档测试
  
      上一版本遗留 2 个缺陷：

      | 缺陷      | 问题等级 | 备注 |
      | ----------- | ----------- | --- |
      | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，且已拟订相关修复版本号为 0.42.0 版本  |
      | [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)   | 严重 | 已有文档整体更新计划，已有具体时间节点和时间表安排  |

      暂无新增缺陷，遗留缺陷正在按计划修复。
      
      - packages-index 测试

      上一版本遗留 2 个缺陷：

      | 缺陷      | 问题等级 |备注 |
      | ----------- | ----------- | --- |
      | [有一部分包无法下载 #37](https://github.com/ruyisdk/packages-index/issues/37)     | 一般 | 已有相关 issue 回复且已经在修复中 |
      | [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)     | 一般 | 软件自带修复功能，且已有相关 issue 回复 |

      暂无新增缺陷，遗留缺陷正在按计划修复。

      另遗留 2 个不影响出口质量的缺陷：

      | 缺陷      | 问题等级 |判定依据 |
      | ----------- | ----------- | --- |
      | [Jupiter and Megrez missing for MilkV product line support #104](https://github.com/ruyisdk/packages-index/issues/104)     | 建议|根据 ruyisdk/packages-index#6 判定不影响出口质量|
      | [Laptop 4A missing for Sipeed product line support #109](https://github.com/ruyisdk/packages-index/issues/109)    | 建议|操作系统支持矩阵中暂无对该设备支持状态为 basic 的镜像，同时根据 ruyisdk/packages-index#6 判定不影响出口质量|

      - RuyiSDK IDE 测试

      RuyiSDK Eclipse Plugins 0.0.5 版本遗留 2 个缺陷：

      | 缺陷      | 问题等级 | 判定依据 |
      | ----------- | ----------- | ---- |
      | [未配置 PATH 导致无法轻松访问 ruyi #38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)    | 建议 | RuyiSDK IDE 与 RuyiSDK 发布周期分离|
      | [Ruyi 安装下载完成不够明显 #39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)    | 建议|RuyiSDK IDE 与 RuyiSDK 发布周期分离|

      - Ruyi 包管理器测试

      发现问题但在测试周期内已经修复。测试周期内未发现可归结于 Ruyi 包管理器本身的缺陷，但仍需考虑报告中所载其他测试失败对实际使用的影响。

      - 新增特性测试

      本版本新增特性如下：

      1. 在首次运行时打印自动补全相关配置信息
      2. 在 `ruyi news` 命令添加新闻阅读情况汇总信息
      3. 在 `ruyi update` 前（显式或隐式）打印提示信息
      4. 在 `dd` 前检查磁盘是否被挂载

      其中 1、 2、 4 已经通过手动测试验证， 3 发现在隐式 update 时没有打印相关信息。新增特性的测试均不加入 litester。

      | 缺陷      | 问题等级 |判定依据 |
      | ----------- | ----------- | --- |
      | [[Feature Request] Provide information prompts when automatically running ruyi update #352](https://github.com/ruyisdk/ruyi/issues/352) | 严重 | 没有完整实现软件需求 |

    - 缺陷修复情况

      | 缺陷      | 问题等级 |判定依据 |
      | ----------- | ----------- | --- |
      | [[Feature Request] Provide information prompts when automatically running ruyi update #352](https://github.com/ruyisdk/ruyi/issues/352) | 修复 | 在 0.41.0-beta-20250926 修复 |

      已经修复，由于[修复](https://github.com/ruyisdk/ruyi/commit/22eddce3ba3bb4fd7f93ec5a22a9e323c40f1d21)只涉及到信息打印，故在 Tier1 平台重新进行 litester 测试通过后即可判定修复合格。

      0.41.0-beta.20250926 版本：

      1. [RevyOS riscv64 测试结果](./RUYI_包管理_RevyOS_riscv64_测试结果.26.md)
      2. [Debian sid riscv64 测试结果](./RUYI_包管理_Debiansid_riscv64_测试结果.26.md)
      3. [Ubuntu22.04 x86\_64 测试报告](./RUYI_包管理_Ubuntu22.04_x86_64_测试结果.26.md)
      4. [Ubuntu22.04 riscv64 测试结果](./RUYI_包管理_Ubuntu22.04_riscv64_测试结果.26.md)
      5. [Ubuntu24.04 x86\_64 测试报告](./RUYI_包管理_Ubuntu24.04_x86_64_测试结果.26.md)
      6. [Ubuntu24.04 riscv64 测试结果](./RUYI_包管理_Ubuntu24.04_riscv64_测试结果.26.md)
      7. [openEuler24.03 riscv64 测试报告](./RUYI_包管理_openEuler24.03_riscv64_测试结果.26.md)
      8. [openEuler24.03 x86\_64 测试结果](./RUYI_包管理_openEuler24.03_x86_64_测试结果.26.md)
      9. [openEuler25.03 riscv64 测试报告](./RUYI_包管理_openEuler25.03_riscv64_测试结果.26.md)
      10. [openEuler25.03 x86\_64 测试结果](./RUYI_包管理_openEuler25.03_x86_64_测试结果.26.md)
      11. [Debian12 x86\_64 测试结果](./RUYI_包管理_Debian12_x86_64_测试结果.26.md)

      新增缺陷均已修复。

     - 测试资源

      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/c918eeb6c1fa9e40eb8c52fb76e443b9815486e9)
      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/6094edd22648e2084a2367633401fc569b92cc16)

- 缺陷issues
    - [ruyi update: undocumented difference in the behavior of the first and second ruyi update after changing the repo remote url #373](https://github.com/ruyisdk/ruyi/issues/373)
    - [bash-completion: not work properly when running ruyi for the first time #374](https://github.com/ruyisdk/ruyi/issues/374)
    - [[Feature Request] check the profile and dependent package information from established ruyi virtual environment #379](https://github.com/ruyisdk/ruyi/issues/379)
    - [[bug] ruyi self clean --all left ~/.local/state/ruyi/ruyipkg/installs.json undeleted #383](https://github.com/ruyisdk/ruyi/issues/383)
    - [[bug] traceback on ruyi ruyi greet message #384](https://github.com/ruyisdk/ruyi/issues/384)
    - [[bug] ruyi venv qemu support not work properly #392](https://github.com/ruyisdk/ruyi/issues/392)
    - [ruyi 0.42.0 版本 extract 命令默认行为改变 #115](https://github.com/ruyisdk/docs/issues/115)
    - [提交的代码要自测 #59](https://github.com/ruyisdk/ruyisdk/issues/59)
    - [A large number of old revyos images were deleted #116](https://github.com/ruyisdk/packages-index/issues/116)
    - [Broken URL on new mirror:// URLs #117](https://github.com/ruyisdk/packages-index/issues/117)

#### 1.2 RuyiSDK 开发和测试工具开发

- packages-index 仓库
  - [config: fix several third-party mirrors #118](https://github.com/ruyisdk/packages-index/pull/118)
  - [board-image/revyos-sipeed-lcon4a: bump to latest version 20251025 #119](https://github.com/ruyisdk/packages-index/pull/119)
  - [board-image/revyos-sipeed-lpi4a: bump to latest version 20251025 #120](https://github.com/ruyisdk/packages-index/pull/120)
  - [board-image/revyos-milkv-pioneer: bump to latest version 20251030 #121](https://github.com/ruyisdk/packages-index/pull/121)
  - [board-image/revyos-milkv-meles: bump to latest version 20251025 #122](https://github.com/ruyisdk/packages-index/pull/122)
  - [board-image/revyos-sipeed-laptop4a: new device support #123](https://github.com/ruyisdk/packages-index/pull/123)

- ruyi-packaging 仓库
  - [New format for revyos-{lcon4a,lpi4a} #50](https://github.com/ruyisdk/ruyi-packaging/pull/50)
  - [New format for revyos-{sg2042,meles,lpi4amain} #51](https://github.com/ruyisdk/ruyi-packaging/pull/51)
  - [Change revyos-{lcon4a,meles} vendor name to PLCT #52](https://github.com/ruyisdk/ruyi-packaging/pull/52)
  - [New revyos-laptop4a support #53](https://github.com/ruyisdk/ruyi-packaging/pull/53)

#### 1.3 RuyiSDK网站

- [Update news on homepage #256](https://github.com/ruyisdk/ruyisdk-website/pull/256)
- [Delete statiticalPage's slider on mobile #257](https://github.com/ruyisdk/ruyisdk-website/pull/257)
- [Upgrade CodeBlock：Enhance the functionality and optimize the style to make it a universal component. #260](https://github.com/ruyisdk/ruyisdk-website/pull/260)
- [Upgrade CodeBlock：Enhance the functionality and optimize the style to make it a universal component. #261](https://github.com/ruyisdk/ruyisdk-website/pull/261)
- [Fix the bug where the left-hand directory (or sidebar/navigation) leaves a blank space after the top menu bar disappears. #263](https://github.com/ruyisdk/ruyisdk-website/pull/263)
- [docs: update English version #266](https://github.com/ruyisdk/ruyisdk-website/pull/266)
- [Docs web v2：Deleted the achorTitle #277](https://github.com/ruyisdk/ruyisdk-website/pull/277)
- [Condense mobile community page #279](https://github.com/ruyisdk/ruyisdk-website/pull/279)
- [Skip dummy file generation in no-update target #280](https://github.com/ruyisdk/ruyisdk-website/pull/280)
- [Fixed top bar, increase transparency #269](https://github.com/ruyisdk/ruyisdk-website/pull/269)
- [Make the CodeBlock component the global default code block. #271](https://github.com/ruyisdk/ruyisdk-website/pull/271)
- [Update biweekly to 2025/9/30 #273](https://github.com/ruyisdk/ruyisdk-website/pull/273)
- [Code block v1: optimize the CodeBlock theme #274](https://github.com/ruyisdk/ruyisdk-website/pull/274)
- [Community page layout update, optimized GitHub links #275](https://github.com/ruyisdk/ruyisdk-website/pull/275)
- [Optimize the theme of the pagination buttons #276](https://github.com/ruyisdk/ruyisdk-website/pull/276)
- [Tailwind implementation for NewsShowcase and RuyiInLive #258](https://github.com/ruyisdk/ruyisdk-website/pull/258)
- [Tailwind implementation for stats page #259](https://github.com/ruyisdk/ruyisdk-website/pull/259)
- [Tailwind implementation for community pages #264](https://github.com/ruyisdk/ruyisdk-website/pull/264) 
- [pages: change installations to telemetry uploads on statistic page #265](https://github.com/ruyisdk/ruyisdk-website/pull/265)
- [i18n: update German translation for Ruyi Telemetry Upload Installations #272](https://github.com/ruyisdk/ruyisdk-website/pull/272)

#### 1.4 RuyiSDK文档

- docs 仓库
  - [change the location of LatestReleases in installation.mdx #97](https://github.com/ruyisdk/docs/pull/97)
  - [docs: fix issue #93 and #94 #98](https://github.com/ruyisdk/docs/pull/98)
  - [docs: add explanation text for fastboot udev rules #99](https://github.com/ruyisdk/docs/pull/99)
  - [feat: add installation method with pip #101](https://github.com/ruyisdk/docs/pull/101)
  - [docs: fix documentation for IDE link and Makefile instructions #103](https://github.com/ruyisdk/docs/pull/103)
  - [docs(ruyi):Use Tabs and CodeBlock to optimize install docs #104](https://github.com/ruyisdk/docs/pull/104)

#### 1.5 RuyiSDK会议和技术分享

- ruyi 0.42.0-beta.20251017 双周报 [pr](https://github.com/ruyisdk/wechat-articles/pull/192)
- 东京秋季RISC-V会议摘要和海报准备

- 技术分享Ruyi STK下 GCC和LLVM对milk v duo 256m的支持测试[视频](https://www.bilibili.com/video/BV1SxWqzYEbA)[文档](https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2025-10/Milk-V-Duo.md)

- [文档](https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2025-10/sherpa-onnx-note.md)
  
### 2. 操作系统支持矩阵

#### 2.1 开发板操作系统支持测试

- [Add new boards, Bit-Brick_K1: update bianbu](https://github.com/ruyisdk/support-matrix/pull/383)
- [Milk-V Pioneer: RevyOS_20251030](https://github.com/ruyisdk/support-matrix/pull/382)
- [Milk-V Pioneer: RevyOS Test Report](https://github.com/ruyisdk/support-matrix/pull/381)
- [LicheePi4A: Bump RevyOS](https://github.com/ruyisdk/support-matrix/pull/380)
- [unmatched: add openeuler (mainline)](https://github.com/ruyisdk/support-matrix/pull/379)
- [LicheeRVDock: Add Debian Trixie Report](https://github.com/ruyisdk/support-matrix/pull/378)
- [LicheeRVDock: Add Debian Trixie test report](https://github.com/ruyisdk/support-matrix/pull/377)
- [Debian_13_Trixie on D1补充图片](https://github.com/ruyisdk/support-matrix/pull/376)
- [Debian_13_D1测试报告](https://github.com/ruyisdk/support-matrix/pull/375)
- [star64: armbian: add EOL notes](https://github.com/ruyisdk/support-matrix/pull/374)

- 验证了 openEuler 25.09 的 ISO 镜像 （openEuler-25.09-riscv64-dvd.iso）在 Visionfive 2 (v1.3b) 上的可用性。
  需要使用较新的 U-Boot SPL (e.g. `2025.01-1~0ubuntu2`) 方可正常启动，但加载内核进入用户态前卡在了上图所示的地方。原因尚不明确，暂未撰写测试报告。

- Add README entries and board config for BPI-RV2, A210 SODIMM V2, EBC7702, and StarPro64

- Update Bit-Brick K1 Bianbu Star report to version 3.0 beta1 and minimal report to version 3.0.1 with new metadata, image links, logs, and conclusions

- Simplify and correct LicheeRV Dock Debian documentation by consolidating source instructions, fixing filenames, and streamlining test result sections

- Update DC-ROMA Mainboard II metadata to support 32GB/64GB RAM and adjust product naming

- Add overview and metadata files for new boards

#### 2.2 操作系统支持矩阵开发

- 在测试 K230 途中基于 revyos/mkimg-k230 更新到 Debian/RevyOS Trixie base 打了一版镜像：https://github.com/KevinMX/mkimg-k230

#### 2.2 操作系统支持矩阵Web UI

入口：https://github.com/QA-Team-lo/support-matrix-frontend

- [标点符号显示错误](https://github.com/QA-Team-lo/support-matrix-frontend/issues/7)

#### 2.3 ruyisdk.cn操作系统支持矩阵板块

- [RevyOS 上的工程软件生态观测 (2): 源内开箱即用的工程类软件](https://ruyisdk.cn/t/topic/1722)
- [RevyOS上的工程软件生态观测 (3): 预编译包：英雄不问出处，好包不问来路，这我拾的](https://ruyisdk.cn/t/topic/1743)
- [RevyOS 上的工程软件生态观测 (1): 总集篇与可用性分级](https://ruyisdk.cn/t/topic/1721)
- [RevyOS上的工程软件生态观测 (4): 构建之从入门到放弃 (上)：GNU Make 偶尔也有点好用，你们都收到通知了吗？](https://ruyisdk.cn/t/topic/1744)
- [Milk-V Duo，但是光驱模拟器](https://ruyisdk.cn/t/topic/1737)

### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- SAIL
  - H 扩展推进
    - 目前测试进度 成功 76/失败 6 /总计 82 https://github.com/trdthg/sail-riscv/tree/h_ext
    - 添加 Zicfilp 支持 https://github.com/trdthg/sail-riscv/commit/b58ed9570bd216527baa14c9ae3b58e6f5a53d3b
    - 更新两个 H 扩展测试用例 \[commit\](https://github.com/trdthg/riscv-hypervisor-tests/commit/867b6556ff31f5c0500c8c1761a8c1ff5baa73d0)
    - [Improve trap_handler with TrapCause union](https://github.com/riscv/sail-riscv/pull/1338)
    - [Change is_CSR_accessible return type to CSRAccessResult enum](https://github.com/riscv/sail-riscv/pull/1357）
    - [Update is_CSR_accessible signature to accept CSRAccessType instead of isWrite](https://github.com/riscv/sail-riscv/issues/1358)
    - [#1366](https://github.com/riscv/sail-riscv/pull/1366): 提交PR, 将Sail-RISCV 的配置选项config_print_platform 拆分为五个不同的与功能相关的选项, 便于执行器的使用和调试
    - [#1531](https://github.com/rems-project/sail/pull/1531): 提交PR, 针对[#1512](https://github.com/rems-project/sail/issues/1512) 提出的Sail 编译器Bug , 提交PR 进行修复
    - [#1299](https://github.com/riscv/sail-riscv/pull/1299): 合并PR, 重构Sail-RISCV 乘法op 标识,使源代码更人类可读, 同时统一标量乘法与矢量乘法的计算以及高低位选择逻辑
    - [#1348](https://github.com/riscv/sail-riscv/pull/1348): 提交并合并PR, 使用Sail 原生编译器的num_of 方法重构vector_support_level 保证了代码简洁度
    - [7de49e](https://github.com/trdthg/sail-riscv/commit/7de49e84c60124ef03bedc7ac8bd7080672ad1f5): 修改H扩展当前结果的代码风格以及去除一些手动调试中间信息
    - [c_emulator: always check config except default](https://github.com/riscv/sail-riscv/pull/1296)
    - Fix [#1235 (comment)](https://github.com/riscv/sail-riscv/issues/1235#issuecomment-3345999052)
    - [Remove useless implementation](https://github.com/riscv/sail-riscv/pull/1372)
    - [Add callback for pt walk](https://github.com/riscv/sail-riscv/pull/1370)
    - [Add z3 cache to ignore list](https://github.com/riscv/sail-riscv/pull/1373)
    - [bump dep jsoncons to 1.4.3](https://github.com/riscv/sail-riscv/pull/1371)

- ACT
  - 更新了修复缺失的压缩非法指令缺失覆盖的pr[#695](https://github.com/riscv-non-isa/riscv-arch-test/pull/695)
  - 提交了一个修复 auipc 提示测试在其签名中包含测试二进制地址的[pr](https://github.com/riscv-non-isa/riscv-arch-test/pull/706)
  
  - Issues
    - [How about having is_CSR_accessible return enum](https://github.com/riscv/sail-riscv/issues/1350)
    - [#1512](https://github.com/rems-project/sail/issues/1512): 发现Sail 编译器在使用mapping 和when 时某种情况下会出现类型检查错误, 故提交Issue 反馈讨论
    - 回复了一个关于auipc hint test 在其签名中包含测试二进制地址的issue[#704](https://github.com/riscv-non-isa/riscv-arch-test/issues/704)
    - 回复了一个关于vclmul 和 vclmulh 检查的issue[#686](https://github.com/riscv-non-isa/riscv-arch-test/issues/686)
  
#### 3.2 SAIL技术分享

- 2025年东京峰会摘要和海报准备

#### 3.3 SAIL会议

- tech-golden-model meeting [`10.13`, `10.27`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 10.30 东亚双周会 [PPT](https://docs.google.com/presentation/d/1P82bpD9zGdjCiSiRrI5C88l1OqBVD2a3VaqIwxn-F5A/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

### 4. 独立项目/应用软件生态观测

#### 4.1 RuyiSDK GNU/LLVM 工具链测试

- 根据测试结果调整20种开发板GNU/LLVM测试用例,提交测试用例报告
  测试20种RISC-V开发板上GCC和LLVM工具链的测试情况，验证 GCC 和 LLVM 工具链是否能在目标RISC-V开发板上正常安装、编译和运行程序。通过 Hello World 和 Coremark 两个程序验证基本功能和性能。使用 RuyiSDK作为统一的工具链管理工具，确保测试环境的一致性。开发板型号列表如下：
  | 序号 | 开发板            | 处理器    | IP 核（主 CPU）       |
  |------|-------------------|-----------|-----------------------|
  | 1    | Lichee Pi 4A      | TH1520    | 玄铁 C910             |
  | 2    | Milk-V Meles      | TH1520    | 玄铁 C910             |
  | 3    | Milk-V Duo        | CV1800B   | 玄铁 C906             |
  | 4    | Milk-V Duo 256M   | SG2002    | 玄铁 C906             |
  | 5    | Milk-V Duo S      | SG2000    | 玄铁 C906             |
  | 6    | LicheeRV Nano     | SG2002    | 玄铁 C906             |
  | 7    | Milk-V Pioneer    | SG2042    | 玄铁 C920             |
  | 8    | CanMV K230        | K230      | 玄铁 C908             |
  | 9    | Lichee Pi 3A      | K1        | 进选时空 X60          |
  | 10   | BPI-F3            | K1        | 进选时空 X60          |
  | 11   | Milk-V Jupiter    | M1        | 进选时空 X60          |
  | 12   | MUSE Book         | M1        | 进选时空 X60          |
  | 13   | MUSE Box          | M1        | 进选时空 X60          |
  | 14   | MUSE Pi Pro       | M1        | 进选时空 X60          |
  | 15   | Orange Pi RV2     | Ky X1     | 进选时空 X60          |
  | 16   | VisionFive 2      | JH7110    | SiFive U74            |
  | 17   | Milk-V Mars       | JH7110    | SiFive U74            |
  | 18   | AWOL Nezha D1     | D1        | 玄铁 C906             |
  | 19   | HiFive Unmatched  | FU740     | SiFive U74            |
  | 20   | 香山笔记本        | 香山南湖（Xiangshan | 香山南湖（Xiangshan |

  调整内容为：
    - 增加 coremark Gitee mirror
    - 默认使用 ISCAS 源替代 GitHub 源
    - 256MB RAM 开发板改为交叉编译
    - Milk-V Megrez 替换为 Nezha D1
    - 增加 MUSE Box 系统刷写步骤
    - 修正部分换行和内容错误

- 北京完成验收准备（全部测试用例验证、设备申请、操作系统安装、测试环境准备）

#### 4.2 openGauss测试

- PR: [Update SG2042/openGauss7.0.0](https://github.com/QA-Team-lo/dbtest/pull/4)
进行了 openGauss 7.0.0 全量版在 SG2042/Pioneer 的 openEuler 容器中的可用性测试。

#### 4.3 Litmus 测试

- PR: https://github.com/QA-Team-lo/litmus-tests/pull/1

完成了针对以下平台的 Litmus 测试，并上传了测试数据等结果：

  - TH1520
  - JH7110
  - EIC7700X
  - D1 （失败，内存不足）
  - K230 （失败，内存不足）

#### 4.4 uboot-builder

- https://github.com/aisuneko/uboot-builder

一个实验性的主线 U-Boot/OpenSBI 的 GitHub Actions 构建脚本。

目前支持 HiFive Unmatched 和 Milk-V Duo (packed fip.bin) 的主线 U-Boot 自动化构建作为 PoC，可以很方便地添加对其他 target 的支持。

#### 4.5 英麒 RISC-V Lab

- 配合维护展厅及实验室设备运行状态，定期排查开发板连通性与系统环境稳定性
- 跟踪 RV Lab 建设进度，协助完善展厅视频内容与展示方案
  
#### 4.6 中国科学院第八届科学节

- 科学节展示物
  - SeeTheWorld，目标检测+大模型 on Licheepi 4A
    - [项目地址](https://github.com/challenger1024/SeeTheWorld)
    - RuyiSDK介绍
    - K230手势识别
    - Visionfive v2 灯光控制
    - HPC OpenMPI on Licheepi4A Cluster
    - RevyOS 操作系统演示机器学习互动实验
    - RISC-V ROS移动小车
    - RISC-V ROS无人机
    - RISC-V 发展史

- 科学节创工坊项目[小架构，大神通](https://mp.weixin.qq.com/s/stwzaGsI_YNJgwz05qjm5w)布展和现场服务（10.31-11.2）

### 5. RISC-V教育和短视频

#### 5.1 短视频制作

- [AvaotaF1 快速启动 V821 AvaotaF1](https://www.bilibili.com/video/BV1tm4uzxEkH/)
- [AvaotaF1 Wi-Fi功能试用](https://www.bilibili.com/video/BV1x14zzuEBd/)
 [CanMV K230 AI Demo 试玩](https://www.bilibili.com/video/BV1AbsqzxEoT/)

#### 5.2 短视频剧本和文档、素材

- [AvaotaF1快速启动 V821 AvaotaF1口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90AvaotaF1%E3%80%91%E5%BF%AB%E9%80%9F%E5%90%AF%E5%8A%A8AvaotaF1%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- [AvaotaF1 Wi-Fi功能试用口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90AvaotaF1%E3%80%91AvaotaF1wifi%E5%8A%9F%E8%83%BD%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- [CanMV K230 AI Demo 试玩口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90K230%E3%80%91K230%E5%8F%A3%E6%92%AD%E7%A8%BF.md)

#### 5.3 技术分享

- 2025年东京峰会摘要和海报准备
  
### 6. 职工

#### 6.1 蔡玮霖

- ruyi 0.42.0-beta.20251017 测试完成 [pr](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/84)
- ruyi 0.42.0-beta.20251017 双周报 [pr](https://github.com/ruyisdk/wechat-articles/pull/192)
- 测试 Ruyi 0.41.0、 0.42.0-alpha.20251013 和 0.42.0-beta.20251015 版本，提出 10 个 issue
  - [ruyi update: undocumented difference in the behavior of the first and second ruyi update after changing the repo remote url #373](https://github.com/ruyisdk/ruyi/issues/373)
  - [bash-completion: not work properly when running ruyi for the first time #374](https://github.com/ruyisdk/ruyi/issues/374)
  - [[Feature Request] check the profile and dependent package information from established ruyi virtual environment #379](https://github.com/ruyisdk/ruyi/issues/379)
  - [[bug] ruyi self clean --all left ~/.local/state/ruyi/ruyipkg/installs.json undeleted #383](https://github.com/ruyisdk/ruyi/issues/383)
  - [[bug] traceback on ruyi ruyi greet message #384](https://github.com/ruyisdk/ruyi/issues/384)
  - [[bug] ruyi venv qemu support not work properly #392](https://github.com/ruyisdk/ruyi/issues/392)
  - [ruyi 0.42.0 版本 extract 命令默认行为改变 #115](https://github.com/ruyisdk/docs/issues/115)
  - [提交的代码要自测 #59](https://github.com/ruyisdk/ruyisdk/issues/59)
  - [A large number of old revyos images were deleted #116](https://github.com/ruyisdk/packages-index/issues/116)
  - [Broken URL on new mirror:// URLs #117](https://github.com/ruyisdk/packages-index/issues/117)
- ruyisdk-website 审核 15 个 pr
  - [Update news on homepage #256](https://github.com/ruyisdk/ruyisdk-website/pull/256)
  - [Delete statiticalPage's slider on mobile #257](https://github.com/ruyisdk/ruyisdk-website/pull/257)
  - [Upgrade CodeBlock：Enhance the functionality and optimize the style to make it a universal component. #260](https://github.com/ruyisdk/ruyisdk-website/pull/260)
  - [Upgrade CodeBlock：Enhance the functionality and optimize the style to make it a universal component. #261](https://github.com/ruyisdk/ruyisdk-website/pull/261)
  - [Fix the bug where the left-hand directory (or sidebar/navigation) leaves a blank space after the top menu bar disappears. #263](https://github.com/ruyisdk/ruyisdk-website/pull/263)
  - [docs: update English version #266](https://github.com/ruyisdk/ruyisdk-website/pull/266)
  - [Docs web v2：Deleted the achorTitle #277](https://github.com/ruyisdk/ruyisdk-website/pull/277)
  - [Condense mobile community page #279](https://github.com/ruyisdk/ruyisdk-website/pull/279)
  - [Skip dummy file generation in no-update target #280](https://github.com/ruyisdk/ruyisdk-website/pull/280)
  - [Fixed top bar, increase transparency #269](https://github.com/ruyisdk/ruyisdk-website/pull/269)
  - [Make the CodeBlock component the global default code block. #271](https://github.com/ruyisdk/ruyisdk-website/pull/271)
  - [Update biweekly to 2025/9/30 #273](https://github.com/ruyisdk/ruyisdk-website/pull/273)
  - [Code block v1: optimize the CodeBlock theme #274](https://github.com/ruyisdk/ruyisdk-website/pull/274)
  - [Community page layout update, optimized GitHub links #275](https://github.com/ruyisdk/ruyisdk-website/pull/275)
  - [Optimize the theme of the pagination buttons #276](https://github.com/ruyisdk/ruyisdk-website/pull/276)
- ruyisdk-website 合作 3 个 pr 
  - [Tailwind implementation for NewsShowcase and RuyiInLive #258](https://github.com/ruyisdk/ruyisdk-website/pull/258)
  - [Tailwind implementation for stats page #259](https://github.com/ruyisdk/ruyisdk-website/pull/259)
  - [Tailwind implementation for community pages #264](https://github.com/ruyisdk/ruyisdk-website/pull/264)
- ruyisdk-website 提交 2 个 pr 
  - [pages: change installations to telemetry uploads on statistic page #265](https://github.com/ruyisdk/ruyisdk-website/pull/265)
  - [i18n: update German translation for Ruyi Telemetry Upload Installations #272](https://github.com/ruyisdk/ruyisdk-website/pull/272)
- packages-index 仓库提交 6 个 pr
  - [config: fix several third-party mirrors #118](https://github.com/ruyisdk/packages-index/pull/118)
  - [board-image/revyos-sipeed-lcon4a: bump to latest version 20251025 #119](https://github.com/ruyisdk/packages-index/pull/119)
  - [board-image/revyos-sipeed-lpi4a: bump to latest version 20251025 #120](https://github.com/ruyisdk/packages-index/pull/120)
  - [board-image/revyos-milkv-pioneer: bump to latest version 20251030 #121](https://github.com/ruyisdk/packages-index/pull/121)
  - [board-image/revyos-milkv-meles: bump to latest version 20251025 #122](https://github.com/ruyisdk/packages-index/pull/122)
  - [board-image/revyos-sipeed-laptop4a: new device support #123](https://github.com/ruyisdk/packages-index/pull/123)
- ruyi-packaging 仓库提交 4 个 pr
  - [New format for revyos-{lcon4a,lpi4a} #50](https://github.com/ruyisdk/ruyi-packaging/pull/50)
  - [New format for revyos-{sg2042,meles,lpi4amain} #51](https://github.com/ruyisdk/ruyi-packaging/pull/51)
  - [Change revyos-{lcon4a,meles} vendor name to PLCT #52](https://github.com/ruyisdk/ruyi-packaging/pull/52)
  - [New revyos-laptop4a support #53](https://github.com/ruyisdk/ruyi-packaging/pull/53)
  
#### 6.2 郑景坤

##### 6.2.1 操作系统支持矩阵

- PR Review (对测试团队操作系统支持矩阵产出的review审核，以下内容同测试团队产出，此处为review)
  - [Add new boards, Bit-Brick_K1: update bianbu](https://github.com/ruyisdk/support-matrix/pull/383)
  - [Milk-V Pioneer: RevyOS_20251030](https://github.com/ruyisdk/support-matrix/pull/382)
  - [Milk-V Pioneer: RevyOS Test Report](https://github.com/ruyisdk/support-matrix/pull/381)
  - [LicheePi4A: Bump RevyOS](https://github.com/ruyisdk/support-matrix/pull/380)
  - [unmatched: add openeuler (mainline)](https://github.com/ruyisdk/support-matrix/pull/379)
  - [LicheeRVDock: Add Debian Trixie Report](https://github.com/ruyisdk/support-matrix/pull/378)
  - [LicheeRVDock: Add Debian Trixie test report](https://github.com/ruyisdk/support-matrix/pull/377)
  - [Debian_13_Trixie on D1补充图片](https://github.com/ruyisdk/support-matrix/pull/376)
  - [Debian_13_D1测试报告](https://github.com/ruyisdk/support-matrix/pull/375)
  - [star64: armbian: add EOL notes](https://github.com/ruyisdk/support-matrix/pull/374)

- 前端界面
  - 前端 issue
  - [标点符号显示错误](https://github.com/QA-Team-lo/support-matrix-frontend/issues/7)

##### 6.2.2 20种RISC-V开发板下工具链测试和其他

RuyiSDK 工具链测试工作,产出验证后的20测试用例报告。

- 论坛发帖：https://ruyisdk.cn/t/topic/1737

#### 6.3 阎明铸

##### 6.3.1 sail/act

## sail/act

- H 扩展推进
    - 目前测试进度 成功 76/失败 6 /总计 82 https://github.com/trdthg/sail-riscv/tree/h_ext
    - 添加 Zicfilp 支持 https://github.com/trdthg/sail-riscv/commit/b58ed9570bd216527baa14c9ae3b58e6f5a53d3b
    - 更新两个 H 扩展测试用例 \[commit\](https://github.com/trdthg/riscv-hypervisor-tests/commit/867b6556ff31f5c0500c8c1761a8c1ff5baa73d0)
    - \[PR\] <https://github.com/riscv/sail-riscv/pull/1338> Improve trap_handler with TrapCause union
    - \[PR\] <https://github.com/riscv/sail-riscv/pull/1357> Change is_CSR_accessible return type to CSRAccessResult enum
    - \[PR\] <https://github.com/riscv/sail-riscv/issues/1358> Update is_CSR_accessible signature to accept CSRAccessType instead of isWrite
    - \[ISSUE\] <https://github.com/riscv/sail-riscv/issues/1350> How about having is_CSR_accessible return enum?

##### 6.3.2 会议和技术分享

- 准备中国科学院科学节展示物品 5 个
- 参与科学节布展、撤展和2天全程服务
- tech-golden-model meeting [`10.13`, `10.27`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 10.30 东亚双周会 [PPT](https://docs.google.com/presentation/d/1P82bpD9zGdjCiSiRrI5C88l1OqBVD2a3VaqIwxn-F5A/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

##### 6.3.3 20种RISC-V开发板北京验证

- 测试开发板17个

#### 6.4 张馥媛

##### 6.4.1 Avaota F1

- [【AvaotaF1】快速启动 V821 AvaotaF1_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1tm4uzxEkH/)
- [【AvaotaF1】快速启动 V821 AvaotaF1口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90AvaotaF1%E3%80%91%E5%BF%AB%E9%80%9F%E5%90%AF%E5%8A%A8AvaotaF1%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- [【AvaotaF1】Wi-Fi功能试用_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1x14zzuEBd/)
- [【AvaotaF1】Wi-Fi功能试用口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90AvaotaF1%E3%80%91AvaotaF1wifi%E5%8A%9F%E8%83%BD%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- 录制官网案例视频素材

##### 6.4.2 CanMV K230

-  [【CanMV K230】AI Demo 试玩](https://www.bilibili.com/video/BV1AbsqzxEoT/)
- [【CanMV K230】AI Demo 试玩口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90K230%E3%80%91K230%E5%8F%A3%E6%92%AD%E7%A8%BF.md)

##### 6.4.3 英麒RISC-V Lab
- 配合维护展厅及实验室设备运行状态，定期排查开发板连通性与系统环境稳定性
- 跟踪 RV Lab 建设进度，协助完善展厅视频内容与展示方案

##### 6.4.4 RuyiSDK
- 关注并跟进 RuyiSDK 最新版本动态，完成测试环境的初步搭建
- 学习相关文档与工具链使用方法
- 准备教学视频的视频素材和测试文档

##### 6.4.5 会议和技术分享
- 准备东京RISC-V Day 摘要和海报

#### 6.5 朱旭昌

- 更新了修复缺失的压缩非法指令缺失覆盖的pr[#695](https://github.com/riscv-non-isa/riscv-arch-test/pull/695)
- 提交了一个修复 auipc 提示测试在其签名中包含测试二进制地址的[pr](https://github.com/riscv-non-isa/riscv-arch-test/pull/706)
- 回复了一个关于auipc hint test 在其签名中包含测试二进制地址的issue[#704](https://github.com/riscv-non-isa/riscv-arch-test/issues/704)
- 回复了一个关于vclmul 和 vclmulh 检查的issue[#686](https://github.com/riscv-non-isa/riscv-arch-test/issues/686)

## SG2042/SG2044 Upstream

## Milk-V Duo Upstream

## eunomia-bpf

See the Monthly Org Report for detail links: <https://github.com/eunomia-bpf/eunomia.dev/issues/50>

- Shipped major bpftime GPU work: independent PTX transform passes, direct-run GPU examples (gemm/vec_add), new GPU maps, microbench, and multi-PTX fatbin patching. Also exploring offload eBPF to RISC-V GPU options such as Vortex and Tenstorrent accelerators.
- Agentsight matured: new PID tracker/filtering, timestamp normalization, better logging/CLI, Docker image, CI, and docs.
- bpf-developer-tutorial expanded heavily (GPU/NPU driver tracing, wall-clock profiling, HID-BPF, BPF Arena, workqueues) and improved automation/publishing.
- xpu-perf added CUPTI improvements, larger buffers, CUDA graph tracking, CPU/GPU trace merge tooling, and example workloads (incl. LLM inference).
- schedcp advanced with benchmarks (vLLM/llama.cpp), profiling guides, token tracking, and README/tests cleanup.
- Infra/ops got tighter: add org report workflows, error handling, publishing pipelines, and templates were refactored and stabilized.

## TPU-MLIR （甲辰计划 J123）

默认无更新。本项目 RISC-V 支持由实习生提供。

## LuaJIT

默认无更新。本项目 RISC-V 支持由实习生提供。

## gem5

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## Spike

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## QEMU

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## RustSBI 小队

全实习生小队，独立宣传渠道。

## Nixpkgs

默认无更新。目前无员工或实习生投入。

## Fedora

全实习生小队，独立宣传渠道。

## The Aya Theorem Prover

默认无更新。目前无员工或实习生投入。

## Arch Linux

全实习生小队，独立宣传渠道。

## 参考链接

- [PLCT 实验室的开放职位（实习生）](https://github.com/plctlab/weloveinterns/blob/master/open-internships.md)
- [PLCT 开源进展 (PLCT Weekly)](https://github.com/plctlab/PLCT-Weekly)
- [PLCT 公开报告幻灯片（选集）](https://github.com/plctlab/PLCT-Open-Reports)
