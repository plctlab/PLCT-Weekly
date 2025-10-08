# PLCT 开源进展·第 74 期·2025 年 9 月汇总

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
- https://github.com/openjdk/jdk/pull/26495 (8364150: RISC-V: Leftover for JDK-8343430 removing old trampoline call)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/26101 (8360000: RISC-V: implement aot)
- https://github.com/openjdk/jdk/pull/26161 (8361504: RISC-V: Make C1 clone intrinsic platform guard more specific)
- https://github.com/openjdk/jdk/pull/26150 (8361449: RISC-V: Code cleanup for native call)
- https://github.com/openjdk/jdk/pull/26178 (8361532: RISC-V: Several vector tests fail after JDK-8354383)
- https://github.com/openjdk/jdk/pull/26238 ([TESTBUG] RISC-V: compiler/vectorization/runner/BasicIntOpTest.java fails with RVV but not Zvbb)
- https://github.com/openjdk/jdk/pull/26239 (8361836: RISC-V: Relax min vector length to 32-bit for short vectors)
- https://github.com/openjdk/jdk/pull/26328 (8362284: RISC-V: cleanup NativeMovRegMem)
- https://github.com/openjdk/jdk/pull/26370 (8362515: RISC-V: cleanup NativeFarCall)
- https://github.com/openjdk/jdk/pull/26318 (8362838: RISC-V: Incorrect matching rule leading to improper oop instruction encoding)
- https://github.com/openjdk/jdk/pull/26408 (8357694: RISC-V: Several IR verification tests fail when vlen=128)
- https://github.com/openjdk/jdk/pull/26409 (8362596: RISC-V: Improve _vectorizedHashCode intrinsic)
- https://github.com/openjdk/jdk/pull/26437 (8363898: RISC-V: TestRangeCheckHoistingScaledIV.java fails after JDK-8355293 when running without RVV)
- https://github.com/openjdk/jdk/pull/26481 (8364120: RISC-V: unify the usage of MacroAssembler::instruction_size)
- https://github.com/openjdk/jdk/pull/26719 (8365200: RISC-V: compiler/loopopts/superword/TestGeneralizedReductions.java fails with Zvbb and vlen=128)
- https://github.com/openjdk/jdk/pull/26738 (8365302: RISC-V: compiler/loopopts/superword/TestAlignVector.java fails when vlen=128)
- https://github.com/openjdk/jdk/pull/17413 (8322174: RISC-V: C2 VectorizedHashCode RVV Version)

## Go

## OpenCV

## GNU Toolchain

## LLVM Team
- 1. Upstream llvm-project 合并的patch:
  - [RISC-V] Add P-ext MC Support for Remaining Pair Operations  https://github.com/llvm/llvm-project/pull/159247
  - [VectorCombine] Support pattern bitop(bitcast(x), C) -> bitcast(bitop(x, InvC)): https://github.com/llvm/llvm-project/pull/155216 
  - [FuncSpec] Invalidate analysis by setting MadeChanges explicitly: https://github.com/llvm/llvm-project/pull/155833
  - [X86] Fold vpmadd52h/l for pattern X * 0 + Y --> Y: https://github.com/llvm/llvm-project/pull/156086
  - [X86] Fold X * Y + Z --> C + Z for vpmadd52l/vpmadd52h: https://github.com/llvm/llvm-project/pull/156293
  - [llvm-reduce] Treat CallBrInst as Branch: https://github.com/llvm/llvm-project/pull/156366
  - [X86] Compute the known bits for VPMADD52L/VPMADD52H in SimplifyDemandedBitsForTargetNode: https://github.com/llvm/llvm-project/pull/156847
  - [VectorCombine] Relax vector type constraint on bitop(bitcast, bitcast): https://github.com/llvm/llvm-project/pull/157245
  - [VectorCombine] Relax vector type constraint on bitop(bitcast, constant): https://github.com/llvm/llvm-project/pull/157246
  - [InstCombine] Preserve nneg in foldLogicCastConstant: https://github.com/llvm/llvm-project/pull/157865
  - [RISCV] Extend zvqdot matching to handle disjoint or: https://github.com/llvm/llvm-project/pull/157901
  - [VectorCombine] Add Ext and Trunc support in foldBitOpOfCastConstant: https://github.com/llvm/llvm-project/pull/157822
  - [X86] Handle undef/zero/ones cases after modifying Ops and Masks: https://github.com/llvm/llvm-project/pull/158428
  - [X86] Fold X * 1 + Z --> X + Z for VPMADD52L: https://github.com/llvm/llvm-project/pull/158516
  - [AArch64] Unfold adds when eliminating frame index with scalable offset: https://github.com/llvm/llvm-project/pull/158597
  - [AArch64] Fold uaddv(a) to a if the all lanes except the 0th are zeros: https://github.com/llvm/llvm-project/pull/159086
  - [RISCV] Disable slideup optimization on the inconsistent element type of EVec and ContainerVT: https://github.com/llvm/llvm-project/pull/159373
  - [Docs][RISCV]Remove experimental from Smctr, Ssctr,Sdext and Sdtrig https://github.com/llvm/llvm-project/pull/161058

- 2. plctlab llvm-project合并的patch:
  - fix bitrev C intrinsic test error https://github.com/plctlab/llvm-project/pull/75

- 3. ruyisdk llvm-project合并的patch:
  - [LLVM][XTHeadVector] fix vwcvt, vwcvtu https://github.com/ruyisdk/llvm-project/pull/163

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

- ipi驱动添加rating，来标识驱动的优先级，通过rating自动选择ipi设备。移除sbi\_platform\_operations中的ipi初始化操作，通过fdt\_early\_drivers初始化ipi。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008807.html)
- 在首次调用sbi\_domain\_context\_enter添加hart context初始化并阻止目标domain和当前domain相同。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008814.html)
- 在修改PMP后刷新tlb缓存。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008841.html)
- 添加VisionFive 2 Lite。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008855.html)
- 在挂起恢复时添加mideleg保存恢复。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008857.html) [2](https://lists.infradead.org/pipermail/opensbi/2025-September/008858.html)
- 添加spacemit k1支持。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008916.html)
- 添加SiFive Clint v2支持，和v0的区别支持Zicntr。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008891.html)
- 在休眠后唤醒后添加代码恢复性能计数器。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008896.html)
- 添加代码检测Zkr扩展。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008919.html)
- 允许访问自定义CSR，isa spec预留了自定义的CSR，添加代码允许csr\_read\_num/csr\_write\_num访问，避免特定平台添加csr访问的代码。[1](https://lists.infradead.org/pipermail/opensbi/2025-September/008926.html)

## The Aya Theorem Prover

[Watch Aya Prover](https://github.com/aya-prover/aya-dev)

近期改动中文总结：

* 为 let 定义做准备。这一特性的实现和 IR 相关的代码耦合，但 IR 目前还没做好
* 在代码中引入注解，标记 De Bruijn 编号的 open/closed 并借此发现了几个 bug（理想情况下可以借此做数据流分析，并且自动查找不一致之处，但在 Java 源码上做数据流分析太复杂了）
* 完全重写 normalizer，彻底解决之前 normalize 不完全导致的各种问题。这应该性能也会更好，因为遍历次数更少了，代价是代码更复杂、复用的逻辑更少（但精神上是更简单的）
* 一些面向用户的小改动，比如上下文为空时 holes 直接不显示 `Context:` 这一栏
* 重写 `IApplyConfl`，之前的实现有 bug 但是不容易触发。我们现在让 normalizer 拒绝化简 De Bruijn-open 的 term，因为这不安全（破坏了一些 invariance），然后发现 `IApplyConfl` 正好触发了这样的 normalization。原因是 pattern 里面存的类型都是 De Bruijn index，需要用前面的变量去 inst，而之前的代码组织方式使得这件事很困难。新的实现完全没有这个问题，抄了一些 `PatUnify` 的代码，并且生成排列组合的代码也更紧凑

争取短期内能搞定 let 定义。这个工作对语言特性也不影响，但对编译优化很重要，因为 let 是古希腊掌管求值顺序的神，如果能在表层语言有这个机制，那么在表层语言就能做一些有保证的优化，利好元编程等还没做的特性。

具体 PR：

+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Let-term cherry pick on annotations [PR-1379](https://github.com/aya-prover/aya-dev/pull/1379) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Dependency upgrades [PR-1378](https://github.com/aya-prover/aya-dev/pull/1378) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) docs: make `Term.bindAllFrom` documentation more concrete. [PR-1367](https://github.com/aya-prover/aya-dev/pull/1367) opened by [illusory0x0](https://github.com/illusory0x0)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) CI [PR-1376](https://github.com/aya-prover/aya-dev/pull/1376) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Let term cp [PR-1375](https://github.com/aya-prover/aya-dev/pull/1375) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Normaliser rework [PR-1373](https://github.com/aya-prover/aya-dev/pull/1373) opened by [ice1000](https://github.com/ice1000)
+ Clean up tests with `tools-test` [PR-1350](https://github.com/aya-prover/aya-dev/pull/1350) opened by [linxuanm](https://github.com/linxuanm)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Some user interaction changes [PR-1372](https://github.com/aya-prover/aya-dev/pull/1372) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Fix something and make `Expr.Lambda` `WithTerm` so that we can provide inlay hint for them [PR-1369](https://github.com/aya-prover/aya-dev/pull/1369) opened by [HoshinoTented](https://github.com/HoshinoTented)

## eunomia-bpf

- AgentSight: System-Level Observability for AI Agents Using eBPF <https://dl.acm.org/doi/10.1145/3766882.3767169>
- MCP for Linux scheduler <https://arxiv.org/html/2509.01245v4> is accepted to MLforsystem'24 workshop
- eBPF for GPU is accepted by Linux Plumber, bpftime again: <https://lpc.events/event/19/contributions/2168/>
- [**gpu: fix memtrace example**](https://github.com/eunomia-bpf/bpftime/pull/455)
- [**example: add cpu and gpu together**](https://github.com/eunomia-bpf/bpftime/pull/454)
- [**enhances the CUDA benchmarking and add memtrace**](https://github.com/eunomia-bpf/bpftime/pull/453)
- [**fix: Resolve compilation failure when BPFTIME_ENABLE_CUDA_ATTACH=1**](https://github.com/eunomia-bpf/bpftime/pull/452)
- [**Reorder examples and add documents**](https://github.com/eunomia-bpf/bpftime/pull/451)
- [**[+] New CI for testing bpftime under gcc-13**](https://github.com/eunomia-bpf/bpftime/pull/446)
- [**[WIP] Fix new maps example test in new bpftool & libbpf version**](https://github.com/eunomia-bpf/bpftime/pull/445)
- Add SPIRV support in llvmbpf: <https://github.com/eunomia-bpf/llvmbpf/>
- Update docs page: <https://eunomia.dev/GPTtrace/>
- Update main page: <https://eunomia.dev/>
- Add tutorial and fix bugs in tutorial
  
## u-boot

## RevyOS (Debian for Xuantie)

### Debian
#### yubo(vimer)
本月继续协助维护 Debian riscv64 的一些基础设施，同时修复一些构建问题.

* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1113855#10 [review justbuild upload]
* http://vimer.7766.org:63015/chromium/140/ [chromium 140]
* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1106256#31  [upload package]
* https://chromium-review.googlesource.com/c/chromium/third_party/ffmpeg/+/5054185/comments/72ecb31a_56bf277d [confirm patch]
* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1115251 [cuneiform fix riscv64 ftbfs]
* https://salsa.debian.org/pkg-llvm-team/llvm-toolchain/-/merge_requests/183 [llvm multi-path]
* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1113855#24 [close the bug]
* https://fast-mirror.isrc.ac.cn/redleafos/dev/redleafos-addons/pool/main/c/chromium/ [chromium 129 for redleados]
* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1117144 [python-tornado upload]

#### zerokaze
* https://github.com/zerokaze420/build_image_script [OrangePi RV2 Debian image]

### Redleafos
V2: 新出 2 版镜像， 主要更新如下:

* https://fast-mirror.isrc.ac.cn/redleafos/extra/images/20250922/ [基于 Debian Trixie 基准仓库构建]
* https://fast-mirror.isrc.ac.cn/redleafos/extra/images/20250927/ [集成 ruyi 包管理器 0.39 版本]

V3: 在多核的基础上， boot on nvme 依旧 WIP, boot on usb 可以工作.

## RT-Thread

- [doxygen: align code for kenerl object doc][rtt-10662]
- [utest/utest: intergare testcases into utest framework ][rtt-10665]
- [doxygen: updated doc for thread management subsystem][rtt-10666]
- [doxygen: fixed duplicated comments for cpu APIs][rtt-10674]
- [doxygen: fixed duplicated comments for scheduler APIs][rtt-10677]
- [doxygen: update doc for env to latest][rtt-10683]
- [utest: unify utest name][rtt-10698]
- [bsp/qemu-virt64-riscv: disable RT_USING_UTEST][rtt-10721]
- [bsp/cvitek: Increase the value of RT_NAME_MAX][rtt-10740]
- [utest: remove RT_UTEST_USING_ALL_CASES][rtt-10741]
- [utest: move core utest cases to under src/utest][rtt-10742]
- [utest: move driver related case under to drivers][rtt-10750]
- [doxygen: fixed build warning for RT_CAN_FILTER_ITEM_INIT][rtt-10758]
- [doxygen: cleanup code for group_object_management][rtt-10759]
- [doxygen: cleanup code for group_thread_management][rtt-10760]
- [bsp: k230: add rtc driver][rtt-10709]

技术文章：
- [[K230学习笔记 01] RTC](https://www.cnblogs.com/Ze-Hou/p/19115269)

[rtt-10662]:https://github.com/RT-Thread/rt-thread/pull/10662
[rtt-10665]:https://github.com/RT-Thread/rt-thread/pull/10665
[rtt-10666]:https://github.com/RT-Thread/rt-thread/pull/10666
[rtt-10674]:https://github.com/RT-Thread/rt-thread/pull/10674
[rtt-10677]:https://github.com/RT-Thread/rt-thread/pull/10677
[rtt-10683]:https://github.com/RT-Thread/rt-thread/pull/10683
[rtt-10698]:https://github.com/RT-Thread/rt-thread/pull/10698
[rtt-10721]:https://github.com/RT-Thread/rt-thread/pull/10721
[rtt-10740]:https://github.com/RT-Thread/rt-thread/pull/10740
[rtt-10741]:https://github.com/RT-Thread/rt-thread/pull/10741
[rtt-10742]:https://github.com/RT-Thread/rt-thread/pull/10742
[rtt-10750]:https://github.com/RT-Thread/rt-thread/pull/10750
[rtt-10758]:https://github.com/RT-Thread/rt-thread/pull/10758
[rtt-10759]:https://github.com/RT-Thread/rt-thread/pull/10759
[rtt-10760]:https://github.com/RT-Thread/rt-thread/pull/10760
[rtt-10709]:https://github.com/RT-Thread/rt-thread/pull/10709

## PLCT罗云翔测试团队

（包含 SAIL 和 ACT 测试部分）

本月在RuyiSDK的测试与生态完善、操作系统支持矩阵的扩展、Sail/ACT模型的增强以及RISC-V教育推广方面均取得了显著进展。通过多版本测试、工具开发、社区内容建设和会议参与，进一步提升了RuyiSDK的可靠性和影响力。

1. RuyiSDK 多版本测试与生态完善
- **版本测试**：完成了 RuyiSDK v0.40.0 和 v0.41.0 版本的全面测试，覆盖 LicheePi4A、RevyOS、ArchLinux、Debian、Deepin、Fedora、Ubuntu、openEuler 等多个操作系统和架构（x86_64、riscv64、aarch64），并提交了详细的测试报告。
- **工具开发与增强**：
  - 在 `ruyi-packaging` 提交了10个PR，支持新包生成、Armbian适配、版本降级等功能。
  - 在 `packages-index` 提交了8个PR，修复manifest问题并新增多个板卡镜像支持。
- **网站与文档优化**：
  - 网站前端实现了多语言Sitemap、主题系统优化、响应式布局改进、数据统计页面增强。
  - 规范了代码块格式和术语使用，修复了文档中的多个问题。

2. 操作系统支持矩阵
- **开发板与系统支持**：新增了对DC-ROMA系列、OrangePi-R2S/RV、PineTab-V等开发板的支持，更新了Fedora、Debian、Irradium等系统的测试报告。
- **元数据系统与前端优化**：
  - 实现了`vendor`字段标准化，清理了冗余测试数据。
  - 前端支持多语言Sitemap、响应式布局和测试报告筛选功能。
- **工具开发**：开发了`image-checker`工具，提升了镜像发布的可靠性。
- **社区内容建设**：在`ruyisdk.cn`发布了多篇RISC-V MCU技术文章，丰富了操作系统支持矩阵内容。

3. Sail/ACT
- **Sail模型功能增强**：
  - 实现了Hypervisor扩展（VU/VS特权级）、ELF动态加载、本地中断处理等核心功能。
  - 开发了JSON配置验证工具，提升了配置可靠性。
- **测试框架优化**：
  - 修复了Zfinx测试用例，同步了RISCOF插件，提升了验证覆盖率。
- **Pydrofoil与XiangShan的diff测试支持**：
  - 在ACT中修复了Zdinx等ISA错误，更新了多个压缩指令测试用例。

4. RISC-V教育推广
- **技术视频制作**：发布了多个实践教程视频，包括LicheePi 4A运行游戏、RuyiSDK安装使用、CoreMark编译、K230烧录和人脸检测、HiFive Unmatched镜像烧录等。
- **校园推广**：在安徽大学和合肥工业大学进行了校园行演讲，推广RISC-V开发板教学与Lab共建。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
- [RuyiSDK 双周新版本发布判定方法](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/Conditions_for_Releases.md)
  - [RuyiSDK v0.40.0-beta.20250902 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250903/README.md)
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250903/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora41 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Fedora41_x86_64_测试结果.md)
    - [Fedora41 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250903/RUYI_包管理_Fedora41_riscv64_测试结果.md)
    - [Fedora42 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250903/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora42 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250903/RUYI_包管理_Fedora42_riscv64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [openEuler25.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_openEuler25.03_riscv64_测试结果.md)
    - [openEuler25.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250903/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - 缺陷：
      - 上一版本遗留 4 个缺陷：
        | 缺陷      | 问题等级 | 判定依据 |
        | ----------- | ----------- | --- |
        | [文档代码块格式不统一 #93](https://github.com/ruyisdk/docs/issues/93)       | 一般 | 软件文档存在其他影响较小的问题|
        | [链接中的 RuyiSDK 大小写问题 #94](https://github.com/ruyisdk/docs/issues/94)   | 一般 | 软件文档存在一致性等影响较小的问题        |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 |软件文档对主要功能、性能描述缺失        |
        | [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)   | 严重 | 软件文档对主要功能、性能描述缺失       |

        回归测试未通过，不符合入口标准。故本版本不执行回归测试之后的测试流程，或执行了部分测试流程但不载入测试报告。

      - packages-index 测试
        本版本测试开始前发现并修复 1 个问题，提交 2 个修复 pr
        | 提交      |
        | ----------- |
        | [board-image/debian-desktop-sdk-milkv-mars-cm-sd: fix 1.0.5+3.6.1 manifest #105](https://github.com/ruyisdk/packages-index/pull/105)      |
        | [workflows: test manifests data structure with ruyi list #108](https://github.com/ruyisdk/packages-index/pull/108)|

        上一版本遗留 2 个缺陷：
        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [有一部分包无法下载 #37](https://github.com/ruyisdk/packages-index/issues/37)     | 一般 | 对软件主要功能造成影响，但软件自带修复功能|
        | [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)     | 一般 |对软件主要功能造成影响，但软件自带修复功能|

        回归测试未通过，不符合入口标准。故本版本不执行回归测试之后的测试流程，或执行了部分测试流程但不载入测试报告。
      - 另遗留 2 个不影响出口质量的缺陷：
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
      
      - 缺陷修复情况
        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [文档代码块格式不统一 #93](https://github.com/ruyisdk/docs/issues/93)       | 修复 | 见 issue 下方更新 |
        | [链接中的 RuyiSDK 大小写问题 #94](https://github.com/ruyisdk/docs/issues/94)   | 修复 | 见 issue 下方更新      |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，且已拟订相关修复版本号为 0.42.0 版本  |
        | [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)   | 严重 | 已有文档整体更新计划，已有具体时间节点和时间表安排  |
        | [有一部分包无法下载 #37](https://github.com/ruyisdk/packages-index/issues/37)     | 一般 | 已有相关 issue 回复且已经在修复中 |
        | [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)     | 一般 | 软件自带修复功能，且已有相关 issue 回复 |

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
    - [Gentoo Linux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250922/RUYI_包管理_Gentoo_riscv64_测试结果.md)

    - 缺陷：
      - 上一版本遗留 4 个缺陷：
        | 缺陷      | 问题等级 | 判定依据 |
        | ----------- | ----------- | --- |
        | [文档代码块格式不统一 #93](https://github.com/ruyisdk/docs/issues/93)       | 一般 | 软件文档存在其他影响较小的问题|
        | [链接中的 RuyiSDK 大小写问题 #94](https://github.com/ruyisdk/docs/issues/94)   | 一般 | 软件文档存在一致性等影响较小的问题        |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 |软件文档对主要功能、性能描述缺失        |
        | [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)   | 严重 | 软件文档对主要功能、性能描述缺失       |

        回归测试未通过，不符合入口标准。故本版本不执行回归测试之后的测试流程，或执行了部分测试流程但不载入测试报告。

      - packages-index 测试
        本版本测试开始前发现并修复 1 个问题，提交 2 个修复 pr
        | 提交      |
        | ----------- |
        | [board-image/debian-desktop-sdk-milkv-mars-cm-sd: fix 1.0.5+3.6.1 manifest #105](https://github.com/ruyisdk/packages-index/pull/105)      |
        | [workflows: test manifests data structure with ruyi list #108](https://github.com/ruyisdk/packages-index/pull/108)|

        上一版本遗留 2 个缺陷：

        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [有一部分包无法下载 #37](https://github.com/ruyisdk/packages-index/issues/37)     | 一般 | 对软件主要功能造成影响，但软件自带修复功能|
        | [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)     | 一般 |对软件主要功能造成影响，但软件自带修复功能|

        回归测试未通过，不符合入口标准。故本版本不执行回归测试之后的测试流程，或执行了部分测试流程但不载入测试报告。

        另遗留 2 个不影响出口质量的缺陷：

        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [Jupiter and Megrez missing for MilkV product line support #104](https://github.com/ruyisdk/packages-index/issues/104)     | 建议|根据 ruyisdk/packages-index#6 判定不影响出口质量|
        | [Laptop 4A missing for Sipeed product line support #109](https://github.com/ruyisdk/packages-index/issues/109)    | 建议|操作系统支持矩阵中暂无对该设备支持状态为 basic 的镜像，同时根据 ruyisdk/packages-index#6 判定不影响出口质量|
      
      - 缺陷修复情况
        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [文档代码块格式不统一 #93](https://github.com/ruyisdk/docs/issues/93)       | 修复 | 见 issue 下方更新 |
        | [链接中的 RuyiSDK 大小写问题 #94](https://github.com/ruyisdk/docs/issues/94)   | 修复 | 见 issue 下方更新      |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，且已拟订相关修复版本号为 0.42.0 版本  |
        | [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)   | 严重 | 已有文档整体更新计划，已有具体时间节点和时间表安排  |
        | [有一部分包无法下载 #37](https://github.com/ruyisdk/packages-index/issues/37)     | 一般 | 已有相关 issue 回复且已经在修复中 |
        | [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)     | 一般 | 软件自带修复功能，且已有相关 issue 回复 |
      - RuyiSDK IDE 测试
        RuyiSDK Eclipse Plugins 0.0.5 版本遗留 2 个缺陷：
        | 缺陷      | 问题等级 | 判定依据 |
        | ----------- | ----------- | ---- |
        | [未配置 PATH 导致无法轻松访问 ruyi #38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)    | 建议 | RuyiSDK IDE 与 RuyiSDK 发布周期分离|
        | [Ruyi 安装下载完成不够明显 #39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)    | 建议|RuyiSDK IDE 与 RuyiSDK 发布周期分离|

        回归测试未通过，不符合入口标准。故本版本不执行回归测试之后的测试流程，或执行了部分测试流程但不载入测试报告。
      - 测试修复情况
        由于 issue 无法在几天甚至几周内修复完成，决定暂不修复部分 issue 而是编写修复计划，将允许简单修复后发布新版本。
        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [文档代码块格式不统一 #93](https://github.com/ruyisdk/docs/issues/93)       | 修复 | 见 issue 下方更新 |
        | [链接中的 RuyiSDK 大小写问题 #94](https://github.com/ruyisdk/docs/issues/94)   | 修复 | 见 issue 下方更新      |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，且已拟订相关修复版本号为 0.42.0 版本  |
        | [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)   | 严重 | 已有文档整体更新计划，已有具体时间节点和时间表安排  |
        | [有一部分包无法下载 #37](https://github.com/ruyisdk/packages-index/issues/37)     | 一般 | 已有相关 issue 回复且已经在修复中 |
        | [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)     | 一般 | 软件自带修复功能，且已有相关 issue 回复 |

    - 资源
      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/c918eeb6c1fa9e40eb8c52fb76e443b9815486e9)
      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/6094edd22648e2084a2367633401fc569b92cc16)

- issue [Profile milkv-duo won't work with LLVM](https://github.com/ruyisdk/ruyi/issues/368)
- [RuyiSDK IDE 使用问题求助文档](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/RuyiSDK%20IDE%20%E4%BD%BF%E7%94%A8%E9%97%AE%E9%A2%98%E6%B1%82%E5%8A%A9%E6%96%87%E6%A1%A3.md)
- [RuyiSDK官方文档PR - 修复Milk-V Duo IDE使用案例中的Makefile格式错误和工具链名称问题](https://github.com/ruyisdk/docs/pull/108)
- [RuyiSDK社区问题反馈 - RuyiSDK IDE使用问题求助和解决方案](https://ruyisdk.cn/t/topic/1566/6)
- [RuyiSDK IDE 使用问题求助文档](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/RuyiSDK%20IDE%20%E4%BD%BF%E7%94%A8%E9%97%AE%E9%A2%98%E6%B1%82%E5%8A%A9%E6%96%87%E6%A1%A3.md)
- [RuyiSDK官方文档PR - 修复Milk-V Duo IDE使用案例中的Makefile格式错误和工具链名称问题](https://github.com/ruyisdk/docs/pull/108)

#### 1.2 RuyiSDK 开发和测试工具开发

- ruyi 仓库提交 3 个 Feature Request
  - [[Feature Request] ruyi news prints news summary first and then prints usage #351](https://github.com/ruyisdk/ruyi/issues/351)
  - [[Feature Request] Provide information prompts when automatically running ruyi update #352](https://github.com/ruyisdk/ruyi/issues/352)
  - [[Feature Request] print auto-completion information on the first run #354](https://github.com/ruyisdk/ruyi/issues/354)

- ruyi仓库提交 1 个 pr
  - [ci: auto trigger ruyi-package-ci on new tag #355](https://github.com/ruyisdk/ruyi/pull/355)

- ruyi文档wechat-articles 仓库提交 1 个 pr
  - [Update test status #187](https://github.com/ruyisdk/wechat-articles/pull/187)

- ruyi-package-ci
  - [ci: build on ruyisdk/ruyi new tag with workflow_dispatch #2](https://github.com/ruyisdk/ruyi-package-ci/pull/2)
- ruyi-packaging 仓库 issue
  - [riko.yaml 打包设计](https://github.com/ruyisdk/ruyi-packaging/issues/38)
- ruyi-packaging 仓库
  - [Sync some recent changes #36](https://github.com/ruyisdk/ruyi-packaging/pull/36)
  - [ruyi_packages: update revyos-sg2042 packaging #37](https://github.com/ruyisdk/ruyi-packaging/pull/37)
  - [riko: ready for riko.yaml #39](https://github.com/ruyisdk/ruyi-packaging/pull/39)
  - [cli(manifests): load riko.yaml and parse python commands #40](https://github.com/ruyisdk/ruyi-packaging/pull/40)
  - [riko(manifests): finish riko.yaml running #41](https://github.com/ruyisdk/ruyi-packaging/pull/41)
  - [cli(manifests): write manifests generate process and remain some TODOs #42](https://github.com/ruyisdk/ruyi-packaging/pull/42)
  - [cli(manifests): riko.yaml add more apis root, boot, uboot #43](https://github.com/ruyisdk/ruyi-packaging/pull/43)
  - [cli(manifests): manifests reasoning runner #44](https://github.com/ruyisdk/ruyi-packaging/pull/44)
  - [cli(manifests): reasoning and validating #45](https://github.com/ruyisdk/ruyi-packaging/pull/45)
  - [cli(manifests): parse new versions #46](https://github.com/ruyisdk/ruyi-packaging/pull/46)
  - [ruyi_packages: add ubuntu-cdimage package #47](https://github.com/ruyisdk/ruyi-packaging/pull/47)
  - [cli(manifests): add new provisionable.partition_map live #48](https://github.com/ruyisdk/ruyi-packaging/pull/48)
  - [ruyi_packages: some new packages #49](https://github.com/ruyisdk/ruyi-packaging/pull/49)
- packages-index 仓库提交 issue
  - [Laptop 4A missing for Sipeed product line support #109](https://github.com/ruyisdk/packages-index/issues/109)
- packages-index 仓库
  - [board-image/debian-desktop-sdk-milkv-mars-cm-sd: fix 1.0.5+3.6.1 manifest #105](https://github.com/ruyisdk/packages-index/pull/105) 修了一个 bug
  - [board-image/debian-fishwaldo-sg200x-sipeed-licheervnano: add old versions 1.2.0 and 1.3.0 #106](https://github.com/ruyisdk/packages-index/pull/106) debian-fishwaldo-sg200x-sipeed-licheervnano
  - [board-image/revyos-milkv-pioneer: bump to version 20250901 #107](https://github.com/ruyisdk/packages-index/pull/107) RevyOS Pioneer Box 新版本 20250901
  - [workflows: test manifests data structure with ruyi list #108](https://github.com/ruyisdk/packages-index/pull/108) 增加 #105 相关的 ci check
  - [board-image/ubuntu-server-riscv64-sifive-unmatched: remove broken man… #112](https://github.com/ruyisdk/packages-index/pull/112)
  - [board-image/openbsd-riscv64-live: fix broken old link and add new… #113](https://github.com/ruyisdk/packages-index/pull/113)
  - [board-image/freebsd-riscv64-mini-live: fix broken old link and add ne… #114](https://github.com/ruyisdk/packages-index/pull/114)
  - [board-image/openwrt-sifive-unmatched: bump to 24.10.2 #115](https://github.com/ruyisdk/packages-index/pull/115)
    
#### 1.3 RuyiSDK网站

- [ruyisdk.org 需要一个 FAQs 页面 #51](https://github.com/ruyisdk/ruyisdk/issues/51)
- [Add striping for codeblock #214](https://github.com/ruyisdk/ruyisdk-website/pull/214)
- [feat/Mobilenews #215](https://github.com/ruyisdk/ruyisdk-website/pull/215)
- [feat the QQgrouplist #216](https://github.com/ruyisdk/ruyisdk-website/pull/216)
- [fix the en docs #217](https://github.com/ruyisdk/ruyisdk-website/pull/217)
- [fix staticalDataPage's bug #219](https://github.com/ruyisdk/ruyisdk-website/pull/219)
- [Update download.mdx #220](https://github.com/ruyisdk/ruyisdk-website/pull/220)
- [Update barchart color #221](https://github.com/ruyisdk/ruyisdk-website/pull/221)
- [Optimize qr code #222](https://github.com/ruyisdk/ruyisdk-website/pull/222)
- [Design qr group #223](https://github.com/ruyisdk/ruyisdk-website/pull/223)
- [Updated the English and German download documents. #229](https://github.com/ruyisdk/ruyisdk-website/pull/229)
- [fix(news): filter out future-dated items #230](https://github.com/ruyisdk/ruyisdk-website/pull/230)
- [feat: add responsive design for news page #231](https://github.com/ruyisdk/ruyisdk-website/pull/231)
- [Add GitHub metrics to the data statistics page #232](https://github.com/ruyisdk/ruyisdk-website/pull/232)
- [feat(news): enhance article display #240](https://github.com/ruyisdk/ruyisdk-website/pull/240)
- [docs: update English version #242](https://github.com/ruyisdk/ruyisdk-website/pull/242)
- [pages(download): add command-line completion support info #247](https://github.com/ruyisdk/ruyisdk-website/pull/247)
- [fix(news): update news file path for localization support #249](https://github.com/ruyisdk/ruyisdk-website/pull/249)
- [fix(news): wrong news.json path when default language #250](https://github.com/ruyisdk/ruyisdk-website/pull/250)
- [docs: update English version #252](https://github.com/ruyisdk/ruyisdk-website/pull/252)
- [Add dynamic sizing to stats in the contributor page #253](https://github.com/ruyisdk/ruyisdk-website/pull/253)
- [Add a no-update target for debugging #254](https://github.com/ruyisdk/ruyisdk-website/pull/254)
- [merge blog and biweekly into news #213](https://github.com/ruyisdk/ruyisdk-website/pull/213)
- [Carefully refactor the entire project source code #224](https://github.com/ruyisdk/ruyisdk-website/pull/224)
- [German documentation update #227](https://github.com/ruyisdk/ruyisdk-website/pull/227)
- [Optimize the sliding effect on mobile devices. #244](https://github.com/ruyisdk/ruyisdk-website/pull/244)
- [docs: update docs to the latest #226](https://github.com/ruyisdk/ruyisdk-website/pull/226)
- [docs: update docs to the latest #233](https://github.com/ruyisdk/ruyisdk-website/pull/233)
- [pages: replace CodeBlock in download pages #238](https://github.com/ruyisdk/ruyisdk-website/pull/238)
- [pages: update LatestReleases related codes #239](https://github.com/ruyisdk/ruyisdk-website/pull/239)
- [docs: update biweekly 52 #243](https://github.com/ruyisdk/ruyisdk-website/pull/243)
- [feat(news): implement i18n support for news page #241](https://github.com/ruyisdk/ruyisdk-website/pull/241)
- [fix(news): wrong i18n json path #248](https://github.com/ruyisdk/ruyisdk-website/pull/248)
- Pull #227 https://github.com/ruyisdk/ruyisdk-website/pull/227
Add translations to the categories header.
New translated article: case7
Fixed the bug for not displaying German in indiaction text.
- Pull #228 https://github.com/ruyisdk/ruyisdk-website/pull/228
Refactored the community page into "Contributor" "Partners" and "CoC" pages.
Added a build-time contributer update.
Added stats for contributions
Update openEuler logo path
Corresponding translations
- Pull #207 https://github.com/ruyisdk/ruyisdk-website/pull/207
Add a background for news section for hint the topic change.
Some minor improvements to spacing.
Changes for PR #205 is merged here(Fix the button position issue for some Chromium-based browsers).
- Pull #253 https://github.com/ruyisdk/ruyisdk-website/pull/253
Now stats reflows dynaimcally and adapt to mobile layouts.
- Pull #254 https://github.com/ruyisdk/ruyisdk-website/pull/254
Now can run npm run build-noupdate to skip accessing GItHub api for faster local debugging

#### 1.4 RuyiSDK文档

- docs 仓库
  - [change the location of LatestReleases in installation.mdx #97](https://github.com/ruyisdk/docs/pull/97)
  - [docs: fix issue #93 and #94 #98](https://github.com/ruyisdk/docs/pull/98)
  - [docs: add explanation text for fastboot udev rules #99](https://github.com/ruyisdk/docs/pull/99)
  - [feat: add installation method with pip #101](https://github.com/ruyisdk/docs/pull/101)
  - [docs: fix documentation for IDE link and Makefile instructions #103](https://github.com/ruyisdk/docs/pull/103)
  - [docs(ruyi):Use Tabs and CodeBlock to optimize install docs #104](https://github.com/ruyisdk/docs/pull/104)

#### 1.5 RuyiSDK会议和技术分享

- 东京秋季RISC-V会议摘要和海报准备

#### 1.6 RuyiSDK 实习生面试

- 实习生快速了解 Ruyi 包管理器 [new_to_ruyisdk.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Note/ruyisdk/new_to_ruyisdk.md)

- 实习生考核内容：packages-index 软件包和 vendor 整理 [packages-index_v0.40.0.csv](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Note/packages-index/packages-index_v0.40.0.csv)

### 2. 操作系统支持矩阵

#### 2.1 开发板操作系统支持测试

- [Dump ArchLinux@Duo_S](https://github.com/ruyisdk/support-matrix/pull/365)
- [Fix OrangePi-RV metadata](https://github.com/ruyisdk/support-matrix/pull/366)
- [Add Tizen](https://github.com/ruyisdk/support-matrix/pull/368)
- [Bit-Brick_K1,LicheePi4A@OpenKylin 2.0 SP2](https://github.com/ruyisdk/support-matrix/pull/369)
- [Test LicheePi4A/Tizen](https://github.com/ruyisdk/support-matrix/pull/370)
- [Update mangopi_mq](https://github.com/ruyisdk/support-matrix/pull/371)
- [Mainline Debian Trixie @ Milk-V Mars](https://github.com/ruyisdk/support-matrix/pull/367)
- [test LicheePi3A: Bianbu Desktop/Desktop Lite](https://github.com/ruyisdk/support-matrix/pull/372)（自行测试，由实习生代写测试报告）
- [BPI-F3/Jupiter: bianbu 3.0.1 minimal/desktop/desktop lite](https://github.com/ruyisdk/support-matrix/pull/373)（自行测试，由实习生代写测试报告）
- [BPI-F3/Jupiter: bianbu 3.0.1 minimal/desktop/desktop lite](https://github.com/ruyisdk/support-matrix/pull/373)
- [test LicheePi3A: Bianbu Desktop/Desktop Lite](https://github.com/ruyisdk/support-matrix/pull/372)
- [Test LicheePi4A/Tizen](https://github.com/ruyisdk/support-matrix/pull/370)
- [Bit-Brick_K1,LicheePi4A@OpenKylin 2.0 SP2](https://github.com/ruyisdk/support-matrix/pull/369)
- 新增了对 Tizen 的观测，及 MangoPi MQ 的相关测试。
  因测试用的 MangoPi MQ 上电仅能进入 FEL 模式，无法测试除 RT-Thread 和 xv6 外的其他系统。
  - Tizen @ VisionFive2
  - Tizen @ LicheePi4A (CFT)
  - Tizen @ BPI-F3 (CFT)
  - xv6 @ MangoPi MQ (CFH)
  - TinaLinux @ MangoPi MQ (CFH)
  - RT-Thread @ MangoPi MQ
- [Add Tizen](https://github.com/ruyisdk/support-matrix/pull/368)
- [Update mangopi_mq](https://github.com/ruyisdk/support-matrix/pull/371)
- 完成了全志 V821 文档（https://docs.aw-ol.com/docs/soc/v821/）的校对和 Review 任务的内部交付。

#### 2.2 操作系统支持矩阵开发

- 在测试 K230 途中基于 revyos/mkimg-k230 更新到 Debian/RevyOS Trixie base 打了一版镜像：https://github.com/KevinMX/mkimg-k230

#### 2.2 操作系统支持矩阵Web UI

入口：https://github.com/QA-Team-lo/support-matrix-frontend

- 修改组件文件结构
- 重新设计测试报告数据结构,分离原始支持矩阵测试报告的文件结构,分为原始开发板,原始测试报告,单开发板,单系统,全站数据
- 重构数据获取与处理代码,分离工具函数,增加数据检查与统计函数
- 使用新数据结构更新测试报告页,更新 UI,增加按处理器和时间筛选和多选功能,调整列表展示数据与宽度
- 更新 i18n,更新 astro 等

#### 2.3 ruyisdk.cn操作系统支持矩阵板块

- [RISC-V MCU 漫游 (3)：博流传奇之 BL602](https://ruyisdk.cn/t/topic/1032)
- [RISC-V MCU 漫游 (4)：博流传奇之 BL70x 系列（上）](https://ruyisdk.cn/t/topic/1040)
- [RISC-V MCU 漫游 (5)：博流传奇之 BL70x 系列（下）](https://ruyisdk.cn/t/topic/1264)
- [RISC-V MCU 漫游 (6)：黄紫色的 ESP32 之 ESP32-S3 系列](https://ruyisdk.cn/t/topic/1296)
- https://ruyisdk.cn/t/topic/957
- https://ruyisdk.cn/t/topic/1054
- https://ruyisdk.cn/t/topic/1182
- https://ruyisdk.cn/t/topic/1239
- https://ruyisdk.cn/t/topic/942
- https://ruyisdk.cn/t/topic/1087
- https://ruyisdk.cn/t/topic/1192
  
#### 2.4 会议和技术分享

- RuyiSDK 双周报 https://github.com/ruyisdk/wechat-articles/pull/186

### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- SAIL
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1263> Move print_log_instr to new fetch_callback
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1259> Link CLI11 to simulator instead of model
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1276> Add Semihosting Support
  - H 扩展推进 <https://github.com/riscv/sail-riscv/compare/master...trdthg:sail-riscv:h_ext>
      - 修复 misa 初始化
      - 添加配置项
      - 添加寄存器
      - 添加 Option 相关辅助函数
  - H 扩展测试收集，文档编写，修复编译 https://github.com/trdthg/riscv-hypervisor-tests
  - XinagShan 补丁，支持 Pydrofoil 作为 Ref <https://github.com/trdthg/plct/tree/main/outcome_byear/2025/m09_files>
  - rebase 并修复 lean build issue <https://github.com/riscv/sail-riscv/pull/1099>
  - [#1067](https://github.com/riscv/sail-riscv/pull/1067): rebase 并推进 H 扩展相关PR 合并
  - [#1267](https://github.com/riscv/sail-riscv/pull/1267): 提交并合并PR , 重构Sail-RISCV 源代码文件架构, 使得其更加清晰 
  - [#1290](https://github.com/riscv/sail-riscv/pull/1290): 提交 H 扩展相关PR , 实现支持 H 扩展的trap 处理功能
  - [#1299](https://github.com/riscv/sail-riscv/pull/1299): PR 提交, 统一标量乘法和向量乘法对两个乘数的处理逻辑
  - [#1243](https://github.com/riscv/sail-riscv/pull/1243): 修改review 提出问题,并进行rebase
  
- Pydrofoil
  - [Fix workload linking with PyPy3 interpreter](https://github.com/OpenXiangShan/xs-env/commit/3ac81d778534a558db88f1876d6c2fd2bbb799cd)
    Pydrofoil can now *work*, at minimal level, with XiangShan co-simulation, yet halts at PyPy initialisation.
  - [packaging PyPy3 interpreter with pydrofoil-riscv module](https://github.com/rpypkgs/rpypkgs/commit/15c008aa553c140cef28af1f553bb455718e4b74), XiangShan should work without build issues.~~
  - [In-tree build for pydrofoil-riscv, pypy-c-pydrofoil-riscv](https://github.com/pydrofoil/pydrofoil/pull/146)
  - [(WIP) XiangShan co-simulation devShell] Fix suspicious linking issue of XiangShan sim `./build/emu` with pydrofoil-riscv-plugin.
  - Analyse of PyPy3 dynamic linking
  - [pydrofoil: prepare pydrofoil difftest devShell within xs-env](https://github.com/definfo/xs-env/commit/73596f09cac8cae0b7870871cdcc5bde351567c8)
  - [In-tree build for pydrofoil-riscv, pypy-c-pydrofoil-riscv](https://github.com/pydrofoil/pydrofoil/pull/146)
  After heavily patching pypy2 sources, pydrofoil-riscv with PyPy plugin can successfully build with Nix. 

- ACT
  - 更新了一个修复缺失的压缩非法指令缺失覆盖的pr[#695](https://github.com/riscv-non-isa/riscv-arch-test/pull/695)
  - 提交了一个添加了Zfbmin拓展支持的[pr](https://github.com/Pagerd/riscv-arch-test/tree/zfbmin)
  - 回复了一个关于测试 riscof 示例时出现错误的issue[#697](https://github.com/riscv-non-isa/riscv-arch-test/issues/697)
  - 回复了一个关于vclmul 和 vclmulh 检查的issue[#686](https://github.com/riscv-non-isa/riscv-arch-test/issues/686)
  - 回复了一个关于Zfinx FMadd/sub 测试太大的issue[#632](https://github.com/riscv-non-isa/riscv-arch-test/issues/632)

  | 测试用例名      | 所属拓展 | 地址                                                         |
  | --------------- | -------- | ------------------------------------------------------------ |
  | cadd-01         | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi16sp-01    | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi4spn-01    | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cand-01         | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | candi-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cbeqz-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cbnez-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cjr-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cli-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clui            | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clw-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clwsp-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cmv-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cor-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cslli-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csrai-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csrli-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csub-01         | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csw-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cswsp-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cxor-01         | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.bf16.s_b1  | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.bf16.s_b22 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.bf16.s_b23 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.bf16.s_b24 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.bf16.s_b27 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.bf16.s_b28 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.bf16.s_b29 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.s.bf16_b1  | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.s.bf16_b22 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.s.bf16_b23 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.s.bf16_b24 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.s.bf16_b27 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.s.bf16_b28 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fcvt.s.bf16_b29 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |

  - Issues
    - \[ISSUE\] <https://github.com/picolibc/picolibc/issues/1086> [RISCV] Picolibc compile failed with riscv-gnu-toolchain
    - [Discussion about refactoring Pydrofoil build targets](https://github.com/pydrofoil/pydrofoil/issues/142)
    The SAIL team has confirmed that they are planning to integrate Pydrofoil into sail-riscv CI.
    - [Missing bzip2/zlib from portable tarball created by `tool/release/package.py`](https://github.com/pypy/pypy/issues/5336)
    Packaging issue in PyPy release script.
  
#### 3.2 SAIL技术分享

- 2025年东京峰会摘要和海报准备

#### 3.3 SAIL会议

- tech-golden-model meeting [`09.01`, `09.08`, `09.15`, `09.22`, `09.29`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 09.18 东亚双周会 [PPT](https://docs.google.com/presentation/d/1aW8Zwu68K8TV0BsrzFJ6TvvVmXT_agHXLK3VQnHpGfU/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加了9月9日的Architectural Compatible Test SIG Meeting，并记录了会议文档[#MD](https://github.com/Pagerd/PLCT/blob/main/Report/week/week92/ACT.md)
- 参加了9月23日的Architectural Compatible Test SIG Meeting，并记录了会议文档[#MD](https://github.com/Pagerd/PLCT/blob/main/Report/week/week93/ACT.md)

### 4. 独立项目/应用软件生态观测

#### 4.1 RuyiSDK GNU/LLVM 工具链测试

- 编写20种开发板GNU/LLVM测试用例
- 上海验证测试用例
- 北京验收准备（设备申请、操作系统安装、测试用例验证）

#### 4.2 Opennovations 工程软件测试

- 报告入口：https://github.com/QA-Team-lo/engineering-riscv/
- [CAD: add all](https://github.com/QA-Team-lo/engineering-riscv/pull/3)
- [Add SPFSims (2/2), BEM (1/1), PrePost (8/14) and convert opennovation table to README(s)](https://github.com/QA-Team-lo/engineering-riscv/pull/1)
- [Add test reports for FEA (15/15)](https://github.com/QA-Team-lo/engineering-riscv/pull/2)
- [Add completed EN reports for EM, ICME, MBD, Plumbing](https://github.com/QA-Team-lo/engineering-riscv/pull/4)
- [CFD report](https://github.com/QA-Team-lo/engineering-riscv/pull/5)
- [Add the rest of PrePost(14/14)](https://github.com/QA-Team-lo/engineering-riscv/pull/6)
- [Update README](https://github.com/QA-Team-lo/engineering-riscv/pull/7)
- [Update link](https://github.com/QA-Team-lo/engineering-riscv/pull/8)
- [FEA: Update software adaptation info](https://github.com/QA-Team-lo/engineering-riscv/pull/9)
- [Add Chinese Translation for EM, ICME, MBD](https://github.com/QA-Team-lo/engineering-riscv/pull/10)
- Gmsh: https://github.com/255doesnotexist/engineering-riscv/tree/main/PrePost/Gmsh
- OpenCASCADE: https://github.com/255doesnotexist/engineering-riscv/tree/main/PrePost/OpenCASCADE
- NETGEN: https://github.com/255doesnotexist/engineering-riscv/tree/main/PrePost/NETGEN
- enGrid: https://github.com/255doesnotexist/engineering-riscv/tree/main/PrePost/enGrid
- MeshLab: https://github.com/255doesnotexist/engineering-riscv/tree/main/PrePost/MeshLab
- Paraview: https://github.com/255doesnotexist/engineering-riscv/tree/main/PrePost/Paraview
- FiPy: https://github.com/255doesnotexist/engineering-riscv/tree/main/SPFSims/FiPy
- Julian: https://github.com/255doesnotexist/engineering-riscv/tree/main/BEM/Julian
- RheoPlast: https://github.com/255doesnotexist/engineering-riscv/tree/main/SPFSims/RheoPlast
- Illuminator: https://github.com/255doesnotexist/engineering-riscv/tree/main/PrePost/Illuminator
- Salome: https://github.com/255doesnotexist/engineering-riscv/tree/main/PrePost/Salome
- Caret: https://github.com/255doesnotexist/engineering-riscv/blob/main/PrePost/Caret/README.md
- Discretizer: https://github.com/255doesnotexist/engineering-riscv/blob/main/PrePost/Discretizer/README.md
- FSLView: https://github.com/255doesnotexist/engineering-riscv/blob/main/PrePost/FSLView/README.md
- MayaVi: https://github.com/255doesnotexist/engineering-riscv/blob/main/PrePost/MayaVi/README.md
- MeshLab: https://github.com/255doesnotexist/engineering-riscv/blob/main/PrePost/MeshLab/README.md
- VisIt: https://github.com/255doesnotexist/engineering-riscv/blob/main/PrePost/VisIt/README.md
- VisTrails: https://github.com/255doesnotexist/engineering-riscv/blob/main/PrePost/VisTrails/README.md
- [CFD report](https://github.com/QA-Team-lo/engineering-riscv/pull/5)
- 完成了对如下软件包 在 Milk-V Pioneer (RevyOS) 上的编译验证，测试，及中英文报告编写工作，[报告](https://github.com/QA-Team-lo/engineering-riscv/pull/4, https://github.com/QA-Team-lo/engineering-riscv/pull/10)
  - EM/Meep
  - EM/Tessa
  - EM/MPB
  - ICME/abinit
  - ICME/LAMMPS
  - MBD/MBDyn
  - MBD/ORSA
  - Plumbing
- FEA 软件可用性测试: https://github.com/QA-Team-lo/engineering-riscv/pull/2
- FEA 测试失败的软件做 RISC-V 适配的可行性: https://github.com/QA-Team-lo/engineering-riscv/pull/9
- https://github.com/QA-Team-lo/engineering-riscv/pull/7
- https://github.com/QA-Team-lo/engineering-riscv/pull/8

#### 4.3 Ruyisdk.cn 论坛

- [RISC-V MCU 漫游 (6)：黄紫色的 ESP32 之 ESP32-C3 系列](https://ruyisdk.cn/t/topic/1296)
- [RISC-V MCU 漫游 (7)：黄紫色的 ESP32 之 ESP32-C2/C6](https://ruyisdk.cn/t/topic/1441)
- [RISC-V MCU 漫游 (8)：Kendryte K210](https://ruyisdk.cn/t/topic/1557)
- [Pine64 RISC-V 开发板介绍 (1)：Ox64](https://ruyisdk.cn/t/topic/1613)
- [(OpenNovation) RISC-V × 有限元分析: 在 RevyOS 上运行 CalculiX](https://ruyisdk.cn/t/topic/1447)
- [RuyiSDK社区问题反馈 - RuyiSDK IDE使用问题求助和解决方案](https://ruyisdk.cn/t/topic/1566/6)
- [Pine64 RISC-V 开发板介绍 (1)：Ox64](https://ruyisdk.cn/t/topic/1613)  
- [深夜开创·未曾设想的道路：在 HiFive Unmatched 上用主线 U-Boot 启动 openEuler 24.03 LTS SP2](https://ruyisdk.cn/t/topic/1525)
- [在 StarFive VisionFive2 上运行 DietPi](https://ruyisdk.cn/t/topic/1332/3)
- [大饼：RISC-V 开发板和操作系统支持矩阵网站开发规划与建议征求](https://ruyisdk.cn/t/topic/880)
  
#### 4.4 Litmus 测试

- for sg2042: https://github.com/QA-Team-lo/litmus-tests/tree/main/SG2042

#### 4.5 Avaota F1

- [AvaotaF1 启动](https://github.com/DuoQilai/PLCT-Works/blob/main/Avaota%20F1/Report_AvaotaF1_Setup.md)

#### 4.6 英麒 RISC-V Lab

- [部署三台unmatched](https://github.com/DuoQilai/PLCT-Works/blob/main/images/yq2.png)

### 5. RISC-V教育和短视频

#### 5.1 短视频课程设计

- [Job_Description](https://github.com/DuoQilai/PLCT-Works/blob/main/RISC-V_short_video/Job_Description.md)
  
#### 5.2 短视频设计和实现

- [Licheepi 4A运行游戏Baby Is You_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1opa4zPErq)
- [安装 RuyiSDK 包管理器_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1KMabzpETz)
-  [在 Licheepi4A 使用 Ruyi 编译环境构建coremark_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1VfpKz2EVn)
- [k230 烧录流程和人脸检测示例_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1yCaozwEuY)
- [HiFive Unmatched 镜像烧录_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1VRHrzVE3o)
- 录制ruyisdk ide示例素材

#### 5.3 短视频剧本和文档、素材
- [口播稿（RuyiSDK使用 qemu llvm cmake）](https://github.com/jason-hue/plct/blob/main/%E5%8F%A3%E6%92%AD%E7%A8%BF/%E5%8F%A3%E6%92%AD%E7%A8%BF%EF%BC%88RuyiSDK%E4%BD%BF%E7%94%A8%20qemu%20llvm%20cmake%EF%BC%89.md)

- [RuyiSDK文档-Taisei 交叉编译测试结果](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/RuyiSDK%E6%96%87%E6%A1%A3-Taisei%20%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91%E6%B5%8B%E8%AF%95%E7%BB%93%E6%9E%9C.md)

#### 5.4 会议和技术分享

安徽大学和合肥工业大学校园行演讲

- [张馥媛-RISC-V 开发板教学与 RISC-V Lab 共建之路](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/%E5%BC%A0%E9%A6%A5%E5%AA%9B-RISC-V%20%E5%BC%80%E5%8F%91%E6%9D%BF%E6%95%99%E5%AD%A6%E4%B8%8E%20RISC-V%20Lab%20%E5%85%B1%E5%BB%BA%E4%B9%8B%E8%B7%AF%20.pptx)
- [安徽大学校园行](https://mp.weixin.qq.com/s/KrkhFyZFY22aGSOsQVtndA)
- [合肥工业大学开放日](https://mp.weixin.qq.com/s/BNRZfGiAbu8FPx8sjQeC5g)
- https://github.com/jason-hue/plct/blob/main/%E6%9C%88%E6%8A%A5/%E4%B9%9D%E6%9C%88%E6%9C%88%E6%8A%A5.md
- [东亚双周会](https://docs.google.com/presentation/d/1aW8Zwu68K8TV0BsrzFJ6TvvVmXT_agHXLK3VQnHpGfU/edit?usp=sharing)

### 6. 职工

#### 6.1 蔡玮霖

- Ruyi v0.40.0-beta.20250902 测试完成 [pr](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/79) [更新](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/82)
- Ruyi v0.41.0-beta.20250922 测试完成 [pr](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/83)
- 编写 [RuyiSDK 双周新版本发布判定方法](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/80) [更新](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/81)
- ruyisdk 仓库提交 1 个 issue
  - [ruyisdk.org 需要一个 FAQs 页面 #51](https://github.com/ruyisdk/ruyisdk/issues/51)
- ruyi 仓库提交 3 个 Feature Request
  - [[Feature Request] ruyi news prints news summary first and then prints usage #351](https://github.com/ruyisdk/ruyi/issues/351)
  - [[Feature Request] Provide information prompts when automatically running ruyi update #352](https://github.com/ruyisdk/ruyi/issues/352)
  - [[Feature Request] print auto-completion information on the first run #354](https://github.com/ruyisdk/ruyi/issues/354)
- ruyi 仓库提交 1 个 pr
  - [ci: auto trigger ruyi-package-ci on new tag #355](https://github.com/ruyisdk/ruyi/pull/355)
- wechat-articles 仓库提交 1 个 pr
  - [Update test status #187](https://github.com/ruyisdk/wechat-articles/pull/187)
- ruyi-package-ci 仓库提交 1 个 pr
  - [ci: build on ruyisdk/ruyi new tag with workflow_dispatch #2](https://github.com/ruyisdk/ruyi-package-ci/pull/2)
- ruyisdk-website 仓库审核 21 个 pr
  - [Add striping for codeblock #214](https://github.com/ruyisdk/ruyisdk-website/pull/214)
  - [feat/Mobilenews #215](https://github.com/ruyisdk/ruyisdk-website/pull/215)
  - [feat the QQgrouplist #216](https://github.com/ruyisdk/ruyisdk-website/pull/216)
  - [fix the en docs #217](https://github.com/ruyisdk/ruyisdk-website/pull/217)
  - [fix staticalDataPage's bug #219](https://github.com/ruyisdk/ruyisdk-website/pull/219)
  - [Update download.mdx #220](https://github.com/ruyisdk/ruyisdk-website/pull/220)
  - [Update barchart color #221](https://github.com/ruyisdk/ruyisdk-website/pull/221)
  - [Optimize qr code #222](https://github.com/ruyisdk/ruyisdk-website/pull/222)
  - [Design qr group #223](https://github.com/ruyisdk/ruyisdk-website/pull/223)
  - [Updated the English and German download documents. #229](https://github.com/ruyisdk/ruyisdk-website/pull/229)
  - [fix(news): filter out future-dated items #230](https://github.com/ruyisdk/ruyisdk-website/pull/230)
  - [feat: add responsive design for news page #231](https://github.com/ruyisdk/ruyisdk-website/pull/231)
  - [Add GitHub metrics to the data statistics page #232](https://github.com/ruyisdk/ruyisdk-website/pull/232)
  - [feat(news): enhance article display #240](https://github.com/ruyisdk/ruyisdk-website/pull/240)
  - [docs: update English version #242](https://github.com/ruyisdk/ruyisdk-website/pull/242)
  - [pages(download): add command-line completion support info #247](https://github.com/ruyisdk/ruyisdk-website/pull/247)
  - [fix(news): update news file path for localization support #249](https://github.com/ruyisdk/ruyisdk-website/pull/249)
  - [fix(news): wrong news.json path when default language #250](https://github.com/ruyisdk/ruyisdk-website/pull/250)
  - [docs: update English version #252](https://github.com/ruyisdk/ruyisdk-website/pull/252)
  - [Add dynamic sizing to stats in the contributor page #253](https://github.com/ruyisdk/ruyisdk-website/pull/253)
  - [Add a no-update target for debugging #254](https://github.com/ruyisdk/ruyisdk-website/pull/254)
- ruyisdk-website 仓库合作 4 个 pr
  - [merge blog and biweekly into news #213](https://github.com/ruyisdk/ruyisdk-website/pull/213)
  - [Carefully refactor the entire project source code #224](https://github.com/ruyisdk/ruyisdk-website/pull/224)
  - [German documentation update #227](https://github.com/ruyisdk/ruyisdk-website/pull/227)
  - [Optimize the sliding effect on mobile devices. #244](https://github.com/ruyisdk/ruyisdk-website/pull/244)
- ruyisdk-website 仓库提交 7 个 pr
  - [docs: update docs to the latest #226](https://github.com/ruyisdk/ruyisdk-website/pull/226)
  - [docs: update docs to the latest #233](https://github.com/ruyisdk/ruyisdk-website/pull/233)
  - [pages: replace CodeBlock in download pages #238](https://github.com/ruyisdk/ruyisdk-website/pull/238)
  - [pages: update LatestReleases related codes #239](https://github.com/ruyisdk/ruyisdk-website/pull/239)
  - [docs: update biweekly 52 #243](https://github.com/ruyisdk/ruyisdk-website/pull/243)
  - [feat(news): implement i18n support for news page #241](https://github.com/ruyisdk/ruyisdk-website/pull/241)
  - [fix(news): wrong i18n json path #248](https://github.com/ruyisdk/ruyisdk-website/pull/248)
- ruyi-packaging 仓库提交 1 个 issue
  - [riko.yaml 打包设计](https://github.com/ruyisdk/ruyi-packaging/issues/38)
- ruyi-packaging 仓库提交 13 个 pr
  - [Sync some recent changes #36](https://github.com/ruyisdk/ruyi-packaging/pull/36)
  - [ruyi_packages: update revyos-sg2042 packaging #37](https://github.com/ruyisdk/ruyi-packaging/pull/37)
  - [riko: ready for riko.yaml #39](https://github.com/ruyisdk/ruyi-packaging/pull/39)
  - [cli(manifests): load riko.yaml and parse python commands #40](https://github.com/ruyisdk/ruyi-packaging/pull/40)
  - [riko(manifests): finish riko.yaml running #41](https://github.com/ruyisdk/ruyi-packaging/pull/41)
  - [cli(manifests): write manifests generate process and remain some TODOs #42](https://github.com/ruyisdk/ruyi-packaging/pull/42)
  - [cli(manifests): riko.yaml add more apis root, boot, uboot #43](https://github.com/ruyisdk/ruyi-packaging/pull/43)
  - [cli(manifests): manifests reasoning runner #44](https://github.com/ruyisdk/ruyi-packaging/pull/44)
  - [cli(manifests): reasoning and validating #45](https://github.com/ruyisdk/ruyi-packaging/pull/45)
  - [cli(manifests): parse new versions #46](https://github.com/ruyisdk/ruyi-packaging/pull/46)
  - [ruyi_packages: add ubuntu-cdimage package #47](https://github.com/ruyisdk/ruyi-packaging/pull/47)
  - [cli(manifests): add new provisionable.partition_map live #48](https://github.com/ruyisdk/ruyi-packaging/pull/48)
  - [ruyi_packages: some new packages #49](https://github.com/ruyisdk/ruyi-packaging/pull/49)
- packages-index 仓库提交 1 个 issue
  - [Laptop 4A missing for Sipeed product line support #109](https://github.com/ruyisdk/packages-index/issues/109)
- packages-index 仓库提交 8 个 pr
  - [board-image/debian-desktop-sdk-milkv-mars-cm-sd: fix 1.0.5+3.6.1 manifest #105](https://github.com/ruyisdk/packages-index/pull/105) 修了一个 bug
  - [board-image/debian-fishwaldo-sg200x-sipeed-licheervnano: add old versions 1.2.0 and 1.3.0 #106](https://github.com/ruyisdk/packages-index/pull/106) debian-fishwaldo-sg200x-sipeed-licheervnano
  - [board-image/revyos-milkv-pioneer: bump to version 20250901 #107](https://github.com/ruyisdk/packages-index/pull/107) RevyOS Pioneer Box 新版本 20250901
  - [workflows: test manifests data structure with ruyi list #108](https://github.com/ruyisdk/packages-index/pull/108) 增加 #105 相关的 ci check
  - [board-image/ubuntu-server-riscv64-sifive-unmatched: remove broken man… #112](https://github.com/ruyisdk/packages-index/pull/112)
  - [board-image/openbsd-riscv64-live: fix broken old link and add new… #113](https://github.com/ruyisdk/packages-index/pull/113)
  - [board-image/freebsd-riscv64-mini-live: fix broken old link and add ne… #114](https://github.com/ruyisdk/packages-index/pull/114)
  - [board-image/openwrt-sifive-unmatched: bump to 24.10.2 #115](https://github.com/ruyisdk/packages-index/pull/115)
- docs 仓库审核 6 个 pr
  - [change the location of LatestReleases in installation.mdx #97](https://github.com/ruyisdk/docs/pull/97)
  - [docs: fix issue #93 and #94 #98](https://github.com/ruyisdk/docs/pull/98)
  - [docs: add explanation text for fastboot udev rules #99](https://github.com/ruyisdk/docs/pull/99)
  - [feat: add installation method with pip #101](https://github.com/ruyisdk/docs/pull/101)
  - [docs: fix documentation for IDE link and Makefile instructions #103](https://github.com/ruyisdk/docs/pull/103)
  - [docs(ruyi):Use Tabs and CodeBlock to optimize install docs #104](https://github.com/ruyisdk/docs/pull/104)
- 实习生快速了解 Ruyi 包管理器 [new_to_ruyisdk.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Note/ruyisdk/new_to_ruyisdk.md)
- packages-index 软件包和 vendor 整理 [packages-index_v0.40.0.csv](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Note/packages-index/packages-index_v0.40.0.csv)

#### 6.2 郑景坤

##### 6.2.1 操作系统支持矩阵

- PR Review (对测试团队操作系统支持矩阵产出的review审核，以下内容同测试团队产出，此处为review)
  - [Dump ArchLinux@Duo_S](https://github.com/ruyisdk/support-matrix/pull/365)
    - [Fix OrangePi-RV metadata](https://github.com/ruyisdk/support-matrix/pull/366)
    - [Add Tizen](https://github.com/ruyisdk/support-matrix/pull/368)
    - [Bit-Brick_K1,LicheePi4A@OpenKylin 2.0 SP2](https://github.com/ruyisdk/support-matrix/pull/369)
    - [Test LicheePi4A/Tizen](https://github.com/ruyisdk/support-matrix/pull/370)
    - [Update mangopi_mq](https://github.com/ruyisdk/support-matrix/pull/371)

##### 6.2.2 双周报

- https://github.com/ruyisdk/wechat-articles/pull/186

##### 6.2.3 Opennovations 工程软件测试

- [CAD: add all](https://github.com/QA-Team-lo/engineering-riscv/pull/3)
- PR Review(审核)
  - [Add SPFSims (2/2), BEM (1/1), PrePost (8/14) and convert opennovation table to README(s)](https://github.com/QA-Team-lo/engineering-riscv/pull/1)
  - [Add test reports for FEA (15/15)](https://github.com/QA-Team-lo/engineering-riscv/pull/2)
  - [Add completed EN reports for EM, ICME, MBD, Plumbing](https://github.com/QA-Team-lo/engineering-riscv/pull/4)
  - [CFD report](https://github.com/QA-Team-lo/engineering-riscv/pull/5)
  - [Add the rest of PrePost(14/14)](https://github.com/QA-Team-lo/engineering-riscv/pull/6)
  - [Update README](https://github.com/QA-Team-lo/engineering-riscv/pull/7)
  - [Update link](https://github.com/QA-Team-lo/engineering-riscv/pull/8)
  - [FEA: Update software adaptation info](https://github.com/QA-Team-lo/engineering-riscv/pull/9)
  - [Add Chinese Translation for EM, ICME, MBD](https://github.com/QA-Team-lo/engineering-riscv/pull/10)

##### 6.2.4 20种RISC-V开发板下工具链测试和其他

- [Profile milkv-duo won't work with LLVM](https://github.com/ruyisdk/ruyi/issues/368)
- [Mainline Debian Trixie @ Milk-V Mars](https://github.com/ruyisdk/support-matrix/pull/367)
- [test LicheePi3A: Bianbu Desktop/Desktop Lite](https://github.com/ruyisdk/support-matrix/pull/372)（自行测试，由实习生代写测试报告）
- [BPI-F3/Jupiter: bianbu 3.0.1 minimal/desktop/desktop lite](https://github.com/ruyisdk/support-matrix/pull/373)（自行测试，由实习生代写测试报告）
- 在测试 K230 途中基于 revyos/mkimg-k230 更新到 Debian/RevyOS Trixie base 打了一版镜像：https://github.com/KevinMX/mkimg-k230
- RuyiSDK GNU/LLVM 工具链测试
Rephrase

#### 6.3 阎明铸

##### 6.3.1 sail/act

- \[PR\] <https://github.com/riscv/sail-riscv/pull/1263> Move print_log_instr to new fetch_callback
- \[PR\] <https://github.com/riscv/sail-riscv/pull/1259> Link CLI11 to simulator instead of model
- \[PR\] <https://github.com/riscv/sail-riscv/pull/1276> Add Semihosting Support
- \[ISSUE\] <https://github.com/picolibc/picolibc/issues/1086> [RISCV] Picolibc compile failed with riscv-gnu-toolchain
- H 扩展推进 <https://github.com/riscv/sail-riscv/compare/master...trdthg:sail-riscv:h_ext>
    - 修复 misa 初始化
    - 添加配置项
    - 添加寄存器
    - 添加 Option 相关辅助函数
- H 扩展测试收集，文档编写，修复编译 https://github.com/trdthg/riscv-hypervisor-tests
- XinagShan 补丁，支持 Pydrofoil 作为 Ref <https://github.com/trdthg/plct/tree/main/outcome_byear/2025/m09_files>
- rebase 并修复 lean build issue <https://github.com/riscv/sail-riscv/pull/1099>

##### 6.3.2 会议和技术分享

- tech-golden-model meeting [`09.01`, `09.08`, `09.15`, `09.22`, `09.29`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 09.18 东亚双周会 [PPT](https://docs.google.com/presentation/d/1aW8Zwu68K8TV0BsrzFJ6TvvVmXT_agHXLK3VQnHpGfU/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

##### 6.3.3 20种RISC-V开发板北京验证

- 测试开发板

#### 6.4 张馥媛

##### 6.4.1 RuyiSDK

- [RuyiSDK IDE 使用问题求助文档](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/RuyiSDK%20IDE%20%E4%BD%BF%E7%94%A8%E9%97%AE%E9%A2%98%E6%B1%82%E5%8A%A9%E6%96%87%E6%A1%A3.md)
- [RuyiSDK官方文档PR - 修复Milk-V Duo IDE使用案例中的Makefile格式错误和工具链名称问题](https://github.com/ruyisdk/docs/pull/108)
- [RuyiSDK社区问题反馈 - RuyiSDK IDE使用问题求助和解决方案](https://ruyisdk.cn/t/topic/1566/6)

##### 6.4.2 Avaota F1

- [AvaotaF1 启动](https://github.com/DuoQilai/PLCT-Works/blob/main/Avaota%20F1/Report_AvaotaF1_Setup.md)

##### 6.4.3 视频

- [Licheepi 4A运行游戏Baby Is You_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1opa4zPErq/)
- [安装 RuyiSDK 包管理器_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1KMabzpETz)
-  [在 Licheepi4A 使用 Ruyi 编译环境构建coremark_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1VfpKz2EVn/?spm_id_from=333.1387.homepage.video_card.click&vd_source=417238cd96b1b549d14bcb35a9da3cf0)
- [Job_Description](https://github.com/DuoQilai/PLCT-Works/blob/main/RISC-V_short_video/Job_Description.md)
- [k230 烧录流程和人脸检测示例_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1yCaozwEuY/)
- [HiFive Unmatched 镜像烧录_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1VRHrzVE3o/)

##### 6.4.4 英麒 RVLab 

- [部署三台unmatched](https://github.com/DuoQilai/PLCT-Works/blob/main/images/yq2.png)

##### 6.4.5 会议

- Slides：https://docs.google.com/presentation/d/1aW8Zwu68K8TV0BsrzFJ6TvvVmXT_agHXLK3VQnHpGfU/edit?usp=sharing

##### 6.4.6 安徽大学和合肥工业大学校园行演讲

- [张馥媛-RISC-V 开发板教学与 RISC-V Lab 共建之路](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/%E5%BC%A0%E9%A6%A5%E5%AA%9B-RISC-V%20%E5%BC%80%E5%8F%91%E6%9D%BF%E6%95%99%E5%AD%A6%E4%B8%8E%20RISC-V%20Lab%20%E5%85%B1%E5%BB%BA%E4%B9%8B%E8%B7%AF%20.pptx)
- [安徽大学校园行](https://mp.weixin.qq.com/s/KrkhFyZFY22aGSOsQVtndA)
- [合肥工业大学开放日](https://mp.weixin.qq.com/s/BNRZfGiAbu8FPx8sjQeC5g)

#### 6.5 朱旭昌

- 参加了9月9日的Architectural Compatible Test SIG Meeting，并记录了会议文档[#MD](https://github.com/Pagerd/PLCT/blob/main/Report/week/week92/ACT.md)
- 参加了9月23日的Architectural Compatible Test SIG Meeting，并记录了会议文档[#MD](https://github.com/Pagerd/PLCT/blob/main/Report/week/week93/ACT.md)
- 更新了一个修复缺失的压缩非法指令缺失覆盖的pr[#695](https://github.com/riscv-non-isa/riscv-arch-test/pull/695)
- 提交了一个添加了Zfbmin拓展支持的[pr](https://github.com/Pagerd/riscv-arch-test/tree/zfbmin)
- 回复了一个关于测试 riscof 示例时出现错误的issue[#697](https://github.com/riscv-non-isa/riscv-arch-test/issues/697)
- 回复了一个关于vclmul 和 vclmulh 检查的issue[#686](https://github.com/riscv-non-isa/riscv-arch-test/issues/686)
- 回复了一个关于Zfinx FMadd/sub 测试太大的issue[#632](https://github.com/riscv-non-isa/riscv-arch-test/issues/632)

| 测试用例名      | 所属拓展 | 地址                                                         |
| --------------- | -------- | ------------------------------------------------------------ |
| cadd-01         | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| caddi-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| caddi16sp-01    | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| caddi4spn-01    | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cand-01         | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| candi-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cbeqz-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cbnez-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cjr-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cli-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| clui            | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| clw-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| clwsp-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cmv-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cor-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cslli-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| csrai-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| csrli-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| csub-01         | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| csw-01          | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cswsp-01        | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| cxor-01         | C        | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.bf16.s_b1  | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.bf16.s_b22 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.bf16.s_b23 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.bf16.s_b24 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.bf16.s_b27 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.bf16.s_b28 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.bf16.s_b29 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.s.bf16_b1  | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.s.bf16_b22 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.s.bf16_b23 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.s.bf16_b24 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.s.bf16_b27 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.s.bf16_b28 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
| fcvt.s.bf16_b29 | Zfbmin   | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |

## SG2042/SG2044 Upstream

- [[PATCH] dts: sophgo: sg2042: added numa id description][lk-sg2042-1]
- [[PATCH v2 0/7] Add PCIe support to Sophgo SG2042 SoC][lk-sg2042-2]
- [[PATCH v3 0/7] Add PCIe support to Sophgo SG2042 SoC][lk-sg2042-3]
- [[PATCH v2 0/4] Add SPI NOR DTS node for SG2042 SoC and boards using it][lk-sg2042-4]
- [[PATCH v3 0/3] irqchip/sg2042-msi: Set irq type according to DT configuration][lk-sg2042-5]

[lk-sg2042-1]:https://lore.kernel.org/linux-riscv/20250910105531.519897-1-rabenda.cn@gmail.com/
[lk-sg2042-2]:https://lore.kernel.org/linux-riscv/cover.1757467895.git.unicorn_wang@outlook.com/
[lk-sg2042-3]:https://lore.kernel.org/linux-riscv/cover.1757643388.git.unicorn_wang@outlook.com/
[lk-sg2042-4]:https://lore.kernel.org/linux-riscv/20250916-sfg-spidts-v2-0-b5d9024fe1c8@gmail.com/
[lk-sg2042-5]:https://lore.kernel.org/linux-riscv/cover.1756953919.git.unicorn_wang@outlook.com/

## Milk-V Duo Upstream

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
