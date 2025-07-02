# PLCT 开源进展·第 71 期·2025 年 6 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

项目地址：https://github.com/ruyisdk/ruyi

6 月份 RuyiSDK 包管理器发布了 2 个新版本：0.35.0、0.36.0，对应
RuyiSDK 整体的 0.35 与 0.36 两个正式版本。您可移步
[GitHub Releases][GitHub Releases] 或 [ISCAS 镜像源][iscas]下载体验。

[GitHub Releases]: https://github.com/ruyisdk/ruyi/releases/tag/0.36.0
[iscas]: https://mirror.iscas.ac.cn/ruyisdk/ruyi/tags/0.36.0/

本月的主要变更如下：

Release Engineering 与工程化方面：

* 优化了 `ruyi` 工具的启动速度，现在每次运行 `ruyi` 都能省下 200-300ms 时间（视机器性能而定），有助于后续实现低延迟的命令行补全特性。并以 CI 检查的方式确保了后续代码变更不会影响本次优化效果。
* 在同时启用机读模式（porcelain mode）与调试输出（`RUYI_DEBUG=y`）时，最先输出的几条日志不会以错误格式输出了。

`ruyi` 包管理器命令行工具方面：

* 现在会记录软件包的安装状态了。该信息在 `ruyi list` 输出中也会体现，并且支持在 `ruyi list` 时传入 `--is-installed y/n` 参数进行过滤。
* 可以用 `ruyi uninstall` 卸载已安装的软件包了。另有更简短的别名 `ruyi remove` 或 `ruyi rm` 可用。
* 在 `ruyi list` 的输出中，可以看到软件包的安装文件是否完全下载了。
* 每次 `ruyi update` 完成后，会报告哪些已安装的软件包有更新版本可供安装了。考虑到具体项目对工具链版本的需求可能较为精确，您可自行 `ruyi install` 更新的版本，并自行重做相应的虚拟环境。
* `ruyi entity list` 可以带一个或多个 `-t` / `--entity-type` 参数，用来列举特定类型的实体了。
* `ruyi entity list` 现在支持机读模式（porcelain mode）输出了。

RuyiSDK 软件源方面：

* 软件源格式更新：
    * 清理了已于 RuyiSDK 0.33 版本弃用的 RuyiSDK 设备安装器的旧版配置数据。
* 完善了设备支持：
    * 新增了 Milk-V Duo (128M & 156M) 开发板镜像的历史版本。
    * 修复了 Milk-V Duo (128M & 256M) 开发板镜像 2.0.0 版本的配置。
    * 更新了多个 Milk-V Meles 的 RevyOS 镜像。
    * 修复了 Milk-V Meles 的 RevyOS 镜像 1.20250123.0 版本的配置。
* 更新软件包：
    * `toolchain/gnu-plct`：由 PLCT 维护并构建的 GNU RISC-V 工具链，包含 GNU binutils 2.45 的预览版、GCC 15.1.0 以及 glibc 2.40。
* 实体数据库更新：
    * 新增以下 RISC-V 微架构定义：
        * 香山昆明湖
        * 玄铁 C908、C908V、C910V2、C920、C920V2
        * MIPS P8700
        * 8-宽 Tenstorrent Ascalon
    * 修正了玄铁 C910 的 RISC-V ISA 字符串为上游主线 GCC 接受的标准形式。
* 更新了一些文档链接的指向。

RuyiSDK 服务端组件方面:

* 提升了发版同步组件的错误处理可靠性。

欢迎试用或来上游围观；您的需求是我们迭代开发的目标和动力。您也可以亲自参与
RuyiSDK 软件的打包与分发工作：目前您可以直接在 GitHub 上查看、修改我们的[部分打包脚本](https://github.com/ruyisdk/ruyici)与[软件源仓库](https://github.com/ruyisdk/packages-index)。今后，按照本年度的开发计划，我们也将支持有权的第三方贡献者通过程序化的方式上传软件包、系统镜像等分发文件，以便利打包工作。

## V8 / Chromium
### v8
#### PLCT提交并合入的代码
* 实现struct/array.atomic.rmw.xchg的原子交换操作 | 6633523: [riscv][wasm][shared] Implement struct/array.atomic.rmw.xchg | https://chromium-review.googlesource.com/c/v8/v8/+/6633523  
* 将 suspender 对象迁移到可信空间 | 6637888: [riscv][wasm][jspi] Move suspender object to trusted space | https://chromium-review.googlesource.com/c/v8/v8/+/6637888  
* 引入简单的截断优化pass | 6638821: [riscv][maglev] Simple truncation pass | https://chromium-review.googlesource.com/c/v8/v8/+/6638821  
* 在release模式中在常量池前增加检查 | 6653368: [riscv] Check trampoline before Constant pool in Release mode | https://chromium-review.googlesource.com/c/v8/v8/+/6653368  
* 避免在JSPI内置函数中进行可信写入 | 6656978: [riscv] [wasm][sandbox] Avoid a trusted write in a JSPI builtin | https://chromium-review.googlesource.com/c/v8/v8/+/6656978  
* 在Maglev中加入额外的peephole优化 | 6656979: [riscv][maglev] Add some peephole optimisations | https://chromium-review.googlesource.com/c/v8/v8/+/6656979
* In turbofan, produce non-canonical NaNs as result if input is Nan （6621983: [riscv] Implement non-canonical NaNs fadds in turbofan | https://chromium-review.googlesource.com/c/v8/v8/+/6621983）（6616397: [riscv][turboshaft] Propagate non-canonical NaNs | https://chromium-review.googlesource.com/c/v8/v8/+/6616397 ）
*   In liftoff, support Wasm code coverage （6621984: [riscv][wasm] Wasm code coverage: Support Liftoff | https://chromium-review.googlesource.com/c/v8/v8/+/6621984 ）
*  6605164: [riscv] Optimize Comparezero | https://chromium-review.googlesource.com/c/v8/v8/+/6605164 ）
*  6605718: [riscv] Fix add/sub overflow failed in pointer compression mode | https://chromium-review.googlesource.com/c/v8/v8/+/6605718
*  6588676: [riscv] Adjust TemporaryRegisterScope to release kMaglevFlagsRegister quickly | https://chromium-review.googlesource.com/c/v8/v8/+/6588676 


#### 审阅并合入的代码：  
* 修复RISC-V中sew()实现的错误 | 6643633: [riscv] Fix incorrect sew() implementation | https://chromium-review.googlesource.com/c/v8/v8/+/6643633 （来自syntacore）  
* 解决arm64平台模拟器编译问题 | 6651306: Fix riscv64 simulator compilation on arm64 | https://chromium-review.googlesource.com/c/v8/v8/+/6651306（以下均来自RISVOS）  
* 改进 trampoline 池检查方式 | 6650984: [riscv] Use byte-sized margin for trampoline pool checks | https://chromium-review.googlesource.com/c/v8/v8/+/6650984  
* 简化 wasm 转js流程，避免RISCV64平台上使用64bit整数指令处理unsigned 转换过的SMI时发生的符号错误 | 6650985: [wasm] Remove 'Unsigned' call during Js->Wasm conversion | https://chromium-review.googlesource.com/c/v8/v8/+/6650985  
* 更正拼写错误为 BranchLong | 6656518: [riscv] Fix spelling of Brachlong to BranchLong | https://chromium-review.googlesource.com/c/v8/v8/+/6656518  
* 优化常量池发射策略 | 6651735: [riscv] Use constant pool size as block margin when emitting it | https://chromium-review.googlesource.com/c/v8/v8/+/6651735
* Syntacore's 提交了针对 RAS feature的优化 6562942: [riscv] improve calls/jumps to avoid RAS pollution | https://chromium-review.googlesource.com/c/v8/v8/+/6562942 ）
* Syntacore 提交了针对StringCharCodeOrCodePointA内建函数的优化  （6593511: [riscv][maglev] Improve StringCharCodeOrCodePointAt to use sh1add instruction on Zba hardware | https://chromium-review.googlesource.com/c/v8/v8/+/6593511 ）

### Chromium:

- [\[Sysroot\] remove sys/hwprobe.h for riscv64](https://chromium-review.googlesource.com/c/chromium/src/+/6629552)
- [Rebuild riscv64 sysroot](https://chromium-review.googlesource.com/c/chromium/src/+/6635209)
- [\[Updater\] Use ProcessCPUArchitecture](https://chromium-review.googlesource.com/c/chromium/src/+/6634009)
- [\[clang\] Build runtime libraries for riscv64 linux](https://chromium-review.googlesource.com/c/chromium/src/+/6633809)

## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/24307 (8353219: RISC-V: Fix client builds after JDK-8345298)
- https://github.com/openjdk/jdk/pull/24433 (8353695: RISC-V: compiler/cpuflags/TestAESIntrinsicsOnUnsupportedConfig.java is failing with Zvkn)
- https://github.com/openjdk/jdk/pull/24344 (8353344: RISC-V: Detect and enable several extensions for debug builds)
- https://github.com/openjdk/jdk/pull/24478 (8353829: RISC-V: Auto-enable several more extensions for debug builds)
- https://github.com/openjdk/jdk/pull/24787 (8355239: RISC-V: Do not support subword scatter store)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/24229 (8352730: RISC-V: Disable tests in qemu-user)
- https://github.com/openjdk/jdk/pull/24153 (8352607: RISC-V: use cmove in min/max when Zicond is supported)
- https://github.com/openjdk/jdk/pull/24233 (8352897: RISC-V: Change default value for UseConservativeFence)
- https://github.com/openjdk/jdk/pull/24035 (8351949: RISC-V: Cleanup and enable store-load peephole for membars)
- https://github.com/openjdk/jdk/pull/24129 (8329887: RISC-V: C2: Support Zvbb Vector And-Not instruction)
- https://github.com/openjdk/jdk/pull/24414 (8353600: RISC-V: compiler/vectorization/TestRotateByteAndShortVector.java is failing with Zvbb)
- https://github.com/openjdk/jdk/pull/24490 (8352504: RISC-V: implement and enable CMoveI/L)
- https://github.com/openjdk/jdk/pull/24618 (8354815: RISC-V: Change type of bitwise rotation shift to iRegIorL2I)
- https://github.com/openjdk/jdk/pull/24549 (8354119: Missing C2 proper allocation failure handling during initialization (during generate_uncommon_trap_blob))
- https://github.com/openjdk/jdk/pull/24797 (8355293: [TEST] RISC-V: enable more ir tests)
- https://github.com/openjdk/jdk/pull/24709 (8355074: RISC-V: C2: Support Vector-Scalar version of Zvbb Vector And-Not instruction)
- https://github.com/openjdk/jdk/pull/24846 (8355476: RISC-V: using zext_w directly in vector_update_crc32 could trigger assert)
- https://github.com/openjdk/jdk/pull/24865 (8355562: RISC-V: Cleanup names of vector-scalar instructions in riscv_v.ad)
- https://github.com/openjdk/jdk/pull/24904 (8355657: RISC-V: Improve PrintOptoAssembly output of vector-scalar instructions)
- https://github.com/openjdk/jdk/pull/24905 (8355654: RISC-V: Relax register constraint for some vector-scalar instructions)
- https://github.com/openjdk/jdk/pull/25350 (8357460: RISC-V: Optimize array fill stub for small size)

## Go

## OpenCV

## GNU Toolchain
在RISC-V GCC后端添加了香山昆明湖架构支持:
- https://patchwork.sourceware.org/project/gcc/patch/20250604095649.457763-1-jiawei@iscas.ac.cn/

在GCC中添加了一系列RISC-V特权指令扩展支持，包括Sm/scsrind，Smrnmi，Ssccptr，Sscounterenw，Sstvala，Sstvecd，Ssu64xl，Svbare:
- https://patchwork.sourceware.org/project/gcc/list/?series=48226&state=%2A&archive=both
- https://patchwork.sourceware.org/project/gcc/patch/20250603012002.12274-1-chendongyan@isrc.iscas.ac.cn/

更新了Smrnmi扩展在Binutils中的依赖关系:
- https://patchwork.sourceware.org/project/binutils/patch/20250606025050.335183-1-jiawei@iscas.ac.cn/

提交了XOR(AND(ROTATE(~1), A), ASHIFT(1, A))表达式在gcc SHIFT_COUNT_TRUNCATED后端的优化:
- https://patchwork.sourceware.org/project/gcc/patch/20250611132047.34928-1-jiawei@iscas.ac.cn/

更新了RVA23 Profiles中的展开:
- https://patchwork.sourceware.org/project/gcc/patch/20250616032129.423078-1-jiawei@iscas.ac.cn/
- https://patchwork.sourceware.org/project/binutils/patch/20250624110927.758118-1-jiawei@iscas.ac.cn/

提交了RVA23S Profiles的支持:
- https://patchwork.sourceware.org/project/gcc/patch/20250624093802.476871-1-jiawei@iscas.ac.cn/
- https://patchwork.sourceware.org/project/binutils/patch/20250624131126.1494452-1-jiawei@iscas.ac.cn/

修改了默认的branch cost以修复gcc中zicond优化：
- https://gcc.gnu.org/pipermail/gcc-patches/2025-June/686893.html

添加generic参数作为默认的-mtune=选项：
- https://gcc.gnu.org/pipermail/gcc-patches/2025-June/686987.html

将riscv-core.cc中定义的cpu进行分离，统一写入riscv-core.def中，方便管理与生成描述文档：
- https://gcc.gnu.org/pipermail/gcc-patches/2025-June/687548.html

更新了riscv-gnu-toolchain的configure：
- https://github.com/riscv-collab/riscv-gnu-toolchain/pull/1735

添加了ftarget-clones-table=traget_clones选项的支持：
- https://inbox.sourceware.org/gcc-patches/tencent_815F8860AE36BFA3102E4ECC77C843231606@qq.com/

提交了Compiler Explorer中Binutils的版本支持，升级至2.44:
- https://github.com/compiler-explorer/compiler-explorer/pull/7814

## LLVM Team
1. Upstream llvm-project 合并的patch:
- [SelectionDAG] Make `(a & x) | (~a & y) -> (a & (x ^ y)) ^ y` available for all targets [#143651](https://github.com/llvm/llvm-project/pull/143651) #137648 #137641
- [clang][Parser] Fix crash on malformed using declaration in constexpr function [#144286](https://github.com/llvm/llvm-project/pull/144286)
- [RISCV] Implement Feature Bit for Q [#145001](https://github.com/llvm/llvm-project/pull/145001)
- [InstSimplify] Simplify 'x u>= 1' to true when x is known non-zero [#145204](https://github.com/llvm/llvm-project/pull/145204)
- [SelectionDAG] Handle `fneg`/`fabs`/`fcopysign` in `SimplifyDemandedBits` [#139239](https://github.com/llvm/llvm-project/pull/139239)
- [InstCombine] Fold `ceil(X / (2 ^ C)) == 0` -> `X == 0` [#143683](https://github.com/llvm/llvm-project/pull/143683)
- [RISCV][MC] Support Base P non-GPR pair instructions https://github.com/llvm/llvm-project/pull/137927
- [OpenMP][Flang]Fix omp_get_cancellation return type from integer to logical https://github.com/llvm/llvm-project/pull/142990

2. Ruyisdk llvm-project合并的patch:
- xtheadvector: [Clang][XTHeadVector] fix zvlsseg strided load/store: https://github.com/ruyisdk/llvm-project/pull/158
- xtheadvector: [Clang][XTHeadVector] make zvlsseg compatible with RVV1.0: https://github.com/ruyisdk/llvm-project/pull/159
- xtheadvector: [Clang][XTHeadVector] implement zvlsseg indexed load/store: https://github.com/ruyisdk/llvm-project/pull/160
- xtheadvector: [Clang][XTHeadVector] fix compatibility of zvlsseg indexed load/store: https://github.com/ruyisdk/llvm-project/pull/161

3. Upstream llvm-project开的issue:
- [RISCV] 507.cactuBSSN_r regression after bidirectional scheduling/register pressure tracking https://github.com/llvm/llvm-project/issues/143005 


## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

## DynamoRIO

## coreboot for riscv

本期没有新的进展。

## openocd

本期没有新的进展。

## opensbi

- 修正fdt\_parse\_aclint\_node中hartid不连续的问题。[1](https://lists.infradead.org/pipermail/opensbi/2025-June/008554.html)
- 一些关于启动过程的改进，让non-coldboot执行更多的初始化，移除多核对称的假设。[1](https://lists.infradead.org/pipermail/opensbi/2025-June/008609.html)
- 修正8255串口初始化代码，在读取RBR之前检测LSR确认RBR中有数据。[1](https://lists.infradead.org/pipermail/opensbi/2025-June/008586.html)
- 改进堆内存的分配，管理堆内存节点的个数之前在初始化时是确定的，现在改成动态分配。[1](https://lists.infradead.org/pipermail/opensbi/2025-June/008593.html)
- 添加一个宏用于安全的进行列表的遍列。[1](https://lists.infradead.org/pipermail/opensbi/2025-June/008600.html)
- RPMI规格冻结，根据规格更新代码添加实现id和version。[1](https://lists.infradead.org/pipermail/opensbi/2025-June/008601.html)[2](https://lists.infradead.org/pipermail/opensbi/2025-June/008602.html)
- 在test payload中添加shutdown ecall。[1](https://lists.infradead.org/pipermail/opensbi/2025-June/008620.html)

## u-boot

本期没有新的进展。

## RevyOS (Debian for Xuantie)

### Debian

## RT-Thread

- [doxygen: group name all in lowcase][rtt-10432]
- [bsp: k230: imprvove README][rtt-10424]
- [doxygen: use layout to control the html display][rtt-10408]
- [componnets: utest: fix case-name matching problem][rtt-10381]
- [bsp: k230: support adc][rtt-10378]
- [componnets: drivers: adc: remove build warnings and cppcheck error][rtt-10373]
- [bsp: k230: add gpio driver][rtt-10372]
- [bsp: k230: support pinctrl driver][rtt-10369]

rttpkgtool:

[README: add python package install requirement][rttpkgtool-10]

Smart-Build:

- [ignore downloaded bitbake and oe-core][rtt-smart-build-37]
- [doc: add description so people how where to change the MACHINE][rtt-smart-build-36]

2025 RT-Thread 全球技术大会报告，RT-Thread 内核仓库文档改进工作介绍:<https://www.bilibili.com/video/BV1DvMczoEzD>

[rtt-10432]: https://github.com/RT-Thread/rt-thread/pull/10432
[rtt-10424]: https://github.com/RT-Thread/rt-thread/pull/10424
[rtt-10408]: https://github.com/RT-Thread/rt-thread/pull/10408
[rtt-10381]: https://github.com/RT-Thread/rt-thread/pull/10381
[rtt-10378]: https://github.com/RT-Thread/rt-thread/pull/10378
[rtt-10373]: https://github.com/RT-Thread/rt-thread/pull/10373
[rtt-10372]: https://github.com/RT-Thread/rt-thread/pull/10372
[rtt-10369]: https://github.com/RT-Thread/rt-thread/pull/10369
[rttpkgtool-10]: https://github.com/plctlab/rttpkgtool/pull/10
[rtt-smart-build-37]:https://github.com/RT-Thread/smart-build/pull/37
[rtt-smart-build-36]:https://github.com/RT-Thread/smart-build/pull/36

## PLCT罗云翔测试团队

（包含 SAIL 和 ACT 测试部分）

1. RuyiSDK 多版本测试与生态完善
- 完成 RuyiSDK v0.34.0 v0.35.0 和 v0.36.0 多平台测试（Fedora/openEuler/x86_64/RISCV64），产出详细测试报告，新增对沁恒 MCU 的初步支持测试，新增 openEuler v25.03 创新版测试。
- RuyiSDK 网站和文档优化，改进主页、下载页和社区板块，新增 IDE 插件下载功能。
2. 操作系统支持矩阵
- 新增 megrez RockOS 和 openCloudOS 桌面版 支持，完成 LicheePi 3A、Bit-Brick K1 等多款开发板的系统兼容性测试（openKylin/Fedora/Bianbu）。
- 完成8个 RT-Thread/Zephyr 系统测试报告，覆盖 CH32V003、Sipeed M1s 等小众开发板。
- 优化支持矩阵元数据与 CI 流程，合并 15+ PR 修复版本冗余问题，标准化测试报告模板。
- 独立开发镜像检查工具 [image-checker](https://github.com/QA-Team-lo/image-checker)，自动化检测官方和社区最新镜像并提交 Issue。
3. Sail和ACT
- Hypervisor 扩展支持：提交初始实现 PR（#1023），新增 VU/VS 特权级和虚拟化模式寄存器（#1067）。
- 测试框架优化：修复 Zfinx/Zdinx 测试用例（#651/#654），同步 RISCOF 插件（#142），解决内存占用问题（#662）。
- 性能与代码质量：重构 vzext/vsext 实现（#1105），修复 Softfloat 符号丢失问题（#1103），发布 Sail 代码格式化 VS Code 插件。
4. RISC-V 生态推广与教育
- 制作LicheePi 4A 运行 ROS2 和 Milk-V Duo 新手教程技术视频。
- 开发玄铁课程（K230 AI 应用、DeepSeek 部署），提供完整 PPT 、课程视频和口播稿。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)

  - [RuyiSDK v0.36测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/README.md)
        
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora41 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Fedora41_x86_64_测试结果.md)
    - [Fedora42 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Fedora42_riscv64_测试结果.md)
    - [Fedora41 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Fedora41_riscv64_测试结果.md)
    - [Fedora42 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Fedora42_riscv64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [openEuler25.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_openEuler25.03_riscv64_测试结果.md)
    - [openEuler25.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250630/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - Ruyi 0.35.0 版本遗留 issue 如下：

      - curl 8.14.1 bug 导致 ruyi 软件包下载失败 [ruyisdk/ruyi#316](https://github.com/ruyisdk/ruyi/issues/316)

      - Ruyi 新增 issue 如下：
        - ruyi self clean --news-read-status 在记录文件不存在时报错 [ruyisdk/ruyi#319](https://github.com/ruyisdk/ruyi/issues/319)

      - RuyiSDK Eclipse Plugins 0.0.5 版本遗留 issue 如下：

        - 未配置 PATH 导致无法轻松访问 ruyi [ruyisdk/ruyisdk-eclipse-plugins#38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)
        - 下载完成不够明显 [ruyisdk/ruyisdk-eclipse-plugins#39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)

    - 资源

      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/8467b22a23a59e241786af4d6df247bc1abf223c)

      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/6094edd22648e2084a2367633401fc569b92cc16)

  - [RuyiSDK v0.35测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/README.md)
        
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora39 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Fedora39_x86_64_测试结果.md)
    - [Fedora38 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Fedora38_riscv64_测试结果.md)
    - [Fedora41 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Fedora41_riscv64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler23.09 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_openEuler23.09_riscv64_测试结果.md)
    - [openEuler23.09 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_openEuler23.09_x86_64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250610/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - Ruyi 新增 issue 如下：

      - curl 8.14.1 bug 导致 ruyi 软件包下载失败 [ruyisdk/ruyi#316](https://github.com/ruyisdk/ruyi/issues/316)

    - RuyiSDK IDE 新增 issue 如下：

      - 下载完成不够明显 [ruyisdk/ruyisdk-eclipse-plugins#39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)
      - 未配置 PATH 导致无法轻松访问 ruyi [ruyisdk/ruyisdk-eclipse-plugins#38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)
      - Ruyi Package Explorer 的问题 [ruyisdk/ruyisdk-eclipse-plugins#37](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/37)

    - 资源

      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/755f149a44b8238047b9cbbfe31eba50ca9c0ef8)

      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/6094edd22648e2084a2367633401fc569b92cc16)

  - [RuyiSDK v0.34测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/README.md)
        
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora39 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Fedora39_x86_64_测试结果.md)
    - [Fedora38 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Fedora38_riscv64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler23.09 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_openEuler23.09_riscv64_测试结果.md)
    - [openEuler23.09 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_openEuler23.09_x86_64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250528/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - 本版本无新增 issue

    - 资源

      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/bbd4fb24b11802f1079c99680338daa1a09eb1dc)

      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/ce05926b26fe13e6a5ce5d20897309a55a211108)

- Ruyi v0.36.0 版本对沁恒 MCU 的支持进行了[测试](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250630/RUYI_包管理_对WCH单片机支持情况附加测试.md)

- RuyiSDK Eclipse Plugin v0.0.5 测试报告 [!6 Add ruyi ide 0.0.5 test report](https://gitee.com/weilinfox/ruyisdk-test/pulls/6)

- Ruyi ide 0.0.5 版本测试

    - PR [docs/#86](https://github.com/ruyisdk/docs/pull/86) 更新 Ruyi IDE 安装教程

    - Ruyi ide 0.0.5 版本发现了如下问题，[测试报告](https://gitee.com/weilinfox/ruyisdk-test/pulls/6)：
    
    - 下载完成不够明显 [ruyisdk-eclipse-plugins/#39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)：
    
    - 未配置 PATH 导致无法轻松访问 ruyi，希望可以有替代解决方案，如安装完提示，或者只修改当前进程的 PATH [ruyisdk-eclipse-plugins/#38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)
    - 新加的 Package Resource Management -> “Windows > Show View > Other > Other > Ruyi Package Explorer“ 有窗口大小问题，而且不易找到，可以添加到菜单栏里 [ruyisdk-eclipse-plugins/#37](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/37)

#### 1.2 RuyiSDK 测试工具开发
- ruyi 
    - [docs: modify ruyisdk.github.io related links #307](https://github.com/ruyisdk/ruyi/pull/307)
    - [curl 8.14.1 bug 导致 ruyi 软件包下载失败 #316](https://github.com/ruyisdk/ruyi/issues/316)
    - [ruyi self clean --news-read-status 在记录文件不存在时报错 #319](https://github.com/ruyisdk/ruyi/issues/319)

- packages-index
    - [docs: modify ruyisdk.github.io related links #81](https://github.com/ruyisdk/packages-index/pull/81)
    - [board-image/buildroot-sdk-milkv-{duo,duo256m,duos-sd}: bump to version v2.0.1 #85](https://github.com/ruyisdk/packages-index/pull/85)（暂未合并）
    - [Add BPi-F3 (Bianbu [minimal|desktop]) #84](https://github.com/ruyisdk/packages-index/pull/84)
    - [ruyi-packaging 整体设计 #17](https://github.com/ruyisdk/ruyi-packaging/issues/17)

    - 检查了 packages-index 中部分缺失的 board-image 配置

      - [ruyisdk-test/packages-index/#2](https://github.com/ruyisdk-test/packages-index/pull/2) Add missing RevyOS images for Milk-V Meles
      - [ruyisdk-test/packages-index/#3](https://github.com/ruyisdk-test/packages-index/pull/3) Add missing RevyOS images for lpi4a
      - [ruyisdk-test/packages-index/#4](https://github.com/ruyisdk-test/packages-index/pull/4) Add new buildroot images
      - [ruyisdk-test/packages-index/#5](https://github.com/ruyisdk-test/packages-index/pull/5) Add missing RevyOS images for Milk-V Pioneer
      - [脚本代码](https://github.com/Cyl18/plct_working/blob/main/month7/4.md)
       
#### 1.3 RuyiSDK网站

- [pages: add plct lab to footer #139](https://github.com/ruyisdk/ruyisdk-website/pull/139)
- [pages: change licheepi 4a image #140](https://github.com/ruyisdk/ruyisdk-website/pull/140)
- [pages: fix subscribe input margin #142](https://github.com/ruyisdk/ruyisdk-website/pull/142)
- [pages: fix index description #143](https://github.com/ruyisdk/ruyisdk-website/pull/143)
- [pages: update homepage news with AsiaLLVM 2025 #147](https://github.com/ruyisdk/ruyisdk-website/pull/147)
- [pages: add IDE plugin download info #152](https://github.com/ruyisdk/ruyisdk-website/pull/152)
- [pages: add More Developer Tools footer #153](https://github.com/ruyisdk/ruyisdk-website/pull/153)
- [Homepage fine-tuning #1 #138](https://github.com/ruyisdk/ruyisdk-website/pull/138)
- [Optimizations to the website #141](https://github.com/ruyisdk/ruyisdk-website/pull/141)
- [New data load mechenism, better UI, and improved NewsShowcase #144](https://github.com/ruyisdk/ruyisdk-website/pull/144)
- [Add community page #149](https://github.com/ruyisdk/ruyisdk-website/pull/149)（暂未合并）
- [add categories downloads #148](https://github.com/ruyisdk/ruyisdk-website/pull/148)（与预期有尚偏差但仍可合并）
- [Widescreen optimization #155](https://github.com/ruyisdk/ruyisdk-website/pull/155)
- [docs: update the English version for download page and Ruyi IDE installation guide #156](https://github.com/ruyisdk/ruyisdk-website/pull/156)
- ruyisdk-website issue
    - [下载菜单：增加 IDE 和插件下载 #70](https://github.com/ruyisdk/ruyisdk-website/issues/70)
    - [博客双周报的合并 #145](https://github.com/ruyisdk/ruyisdk-website/issues/145)（暂未分配实习生任务）
    - [社区板块的更新 #146](https://github.com/ruyisdk/ruyisdk-website/issues/146)

- https://github.com/ruyisdk/ruyisdk-website/pull/144
  - Updated SlideNews to crop picture with better sizing
  - Aligned the mobile button size with the desktop
  - Updated RuyiInLive with a background thread for loading data
  - Updated NewsShowcase to avoid cropping of buttons
  - Add truncate mechanism for NewsShowcase

- https://github.com/ruyisdk/ruyisdk-website/pull/141
  - Updated SlideNews for popup logic
  - Updated the colouring of subsription box
  - Updated SEO message

- https://github.com/ruyisdk/ruyisdk-website/pull/155
  - Optimized widescreen layout for homepage components

- https://github.com/ruyisdk/ruyisdk-website/pull/149
  - Add community page with community link, peoples, sponsors and rubric.
  - Update the navbar for new page.
  - The page have glass-like effect if use a vibrant background. Keep light-grey in this version for simplicity.
  - TODO BEFORE MERGING: replace the placeholder text.
  - Add i18n support for new page and components

#### 1.4 RuyiSDK文档

- [Update Ruyi IDE installation guide #86](https://github.com/ruyisdk/docs/pull/86)

- [使用 ruyi 虚拟环境编译 milkv-duo-examples 文档](https://github.com/Cyl18/plct_working/blob/83e76692423d9c4046ef6333a41ba8e482763c27/month7/1.md)

#### 1.5 RuyiSDK技术分享

- RISC-V 北美峰会海报准备
  
#### 1.6 RuyiSDK 测试机和测试套件更新和维护

- Ruyi v0.35.0 测试中 Fedora 环境新增 41 riscv64
- Ruyi v0.36.0 测试中 Fedora 环境新增 41 x86\_64 和 42 x86\_64/riscv64，移除 38 riscv64 和 39 x86\_64
- Ruyi v0.36.0 测试中 openEuler 环境新增 25.03 x86\_64/riscv64，移除 23.09 x86\_64，减少了一个 23.09 riscv64 平台（还剩一个）
- [更新测试报告模板](https://github.com/weilinfox/ruyi-litester-reports/compare/5a360bd272965372083012c1382744cd7afd606e...02027b8805c826210cf75436566bb344bb7143b9)
- [缓解部分测试机磁盘空间不足](https://github.com/weilinfox/ruyi-reimu/commit/6094edd22648e2084a2367633401fc569b92cc16)
- [测试套件适配 0.35.0 版本输出变化](https://github.com/weilinfox/ruyi-litester/compare/ad02bbb6ca2a7afe8f8bbfae540884ca8bd22751...755f149a44b8238047b9cbbfe31eba50ca9c0ef8)
- [测试套件适配 0.36.0 镜像结构变化](https://github.com/weilinfox/ruyi-litester/commit/8467b22a23a59e241786af4d6df247bc1abf223c)
  
### 2. 操作系统支持矩阵

#### 2.1 开发板操作系统支持测试
- [Mars: Add irradium, openKylin, openSUSE test reports.](https://github.com/ruyisdk/support-matrix/pull/313)
- [OrangePi RV2: Add irradium test report.](https://github.com/ruyisdk/support-matrix/pull/314)
- [LicheePi4A: Add irradium test report (CFT).](https://github.com/ruyisdk/support-matrix/pull/315)
- [Metadata: Fix redundant vendor, update CONTRIBUTING and temple metadata, add esp32-p4 metadata](https://github.com/ruyisdk/support-matrix/pull/316)
- [Clean deprecated codes](https://github.com/ruyisdk/support-matrix/pull/317)
- [Add metadata for oz64 and pinecone](https://github.com/ruyisdk/support-matrix/pull/319)
- [Visionfive/Alpine: Update result to basic.](https://github.com/ruyisdk/support-matrix/pull/320)
- [LicheePi 3A: Add board and systems; Some fixes and tweaks](https://github.com/ruyisdk/support-matrix/pull/321)
- [DuoS: Dump Debian to v1.6.31](https://github.com/ruyisdk/support-matrix/pull/322)
- [Bit-Brick_K1: add test for bianbu 2.2 minimal](https://github.com/ruyisdk/support-matrix/pull/323)
- [LiP4A: merge 8+32G and 16+128G](https://github.com/ruyisdk/support-matrix/pull/324)
- [LPi4A/RevyOS: Bump to 20250526](https://github.com/ruyisdk/support-matrix/pull/325)
- [LicheePi4A: Add irradium test report (good).](https://github.com/ruyisdk/support-matrix/pull/327)
- [Bit-Brick_K1: add test for bianbu 2.2 minimal](https://github.com/ruyisdk/support-matrix/pull/323)
- [Miscellaneous tests bump](https://github.com/ruyisdk/support-matrix/pull/326)
- [Add test for booting from SATA on Megrez](https://github.com/ruyisdk/support-matrix/pull/331)
- [Jupiter/openKylin: Fix wrong `sys_ver`](https://github.com/ruyisdk/support-matrix/pull/337)
- Visifive/Alpine: 完成测试 [#320](https://github.com/ruyisdk/support-matrix/pull/320)
- LicheePi 3A：添加板子并对多个系统进行测试 [#321](https://github.com/ruyisdk/support-matrix/pull/321)
  - openKylin：Good
  - Fedora：Good
    - Desktop
    - Miminal
  - Bianbu：
    - 使用官方工具、fastboot、sd卡镜像均触发kp
- [Miscellaneous tests bump](https://github.com/ruyisdk/
  - Zephyr @ CH32V003
  - Zephyr @ TTGO T-OI-Plus
  - postmarketOS @ Sipeed M1s Dock (CFH)
  - RT-Thread @ Sipeed M0P Dock
  - RT-Thread @ Sipeed M1s Dock (CFH)
  - RT-Thread @ MangoPi MQ-Pro
  - RT-Thread @ DongshanPI Nezha-STU
  - FreeBSD @ VisionFive2 (CFH)
  - BuildRoot @ Sipeed M1s Dock (CFH)
  - xv6 @ MangoPi MQ-Pro (edit)
- DuoS Debian 更新
  - https://github.com/ruyisdk/support-matrix/pull/322
- LiP4A Merge 不同版本的开发板
  - https://github.com/ruyisdk/support-matrix/pull/324
- [Bit-Brick_K1: add test for bianbu 2.2 minimal](https://github.com/ruyisdk/support-matrix/pull/323)
- [Add metadata for oz64 and pinecone](https://github.com/ruyisdk/support-matrix/pull/319)
- 测试 Bit-Brick K1 @ bianbu minimal 2.2, 2.1.2, 2.1.1, 2.1 
- 修复 metadata 导致的 CI 错误
#### 2.2 操作系统支持矩阵Web UI

开发仓库: https://github.com/panglars/VeRForTe

  - 添加 package-index,使用 package-index/entities/device 进行来确认 ruyisdk 支持情况,并修改排序逻辑
  - 修复 matadata 引入 archers 的分类错误
  - 扁平化路由,分为/boards, /systems, /reports 三部分
  - 创建[systems]页和 BoardsList 组件用于显示该操作系统支持的开发板
  - 添加 SystemsGrid 用于在主页显示操作系统
  - 将主页搜索与排序代码与 Boards 卡片分离,主页添加标签进行分类显示,并修改搜索逻辑
  - 依赖更新与修复
  - 更新readme
  
#### 2.3 操作系统支持矩阵测试开发

- 镜像检查工具，用于自动检查上游新发布的操作系统版本

  - 根据讨论将原先放置在支持矩阵中的镜像检查单独独立作为一个repo进行运行：仓库可见 [image-checker](https://github.com/QA-Team-lo/image-checker)
  - 目前已经可以进行工作，自动提交issue示例如：[#239](https://github.com/ruyisdk/support-matrix/issues/329)
  - 每次检查详情见：[workflow](https://github.com/QA-Team-lo/image-checker/actions/runs/15812799385)

- ruyi
  - 尝试为其添加 bash/zsh completion支持[#301](https://github.com/ruyisdk/ruyi/pull/301)
  
- packages-index
  - 根据新ruyi仓库配置，添加bpi-f3作为模板：[#84](https://github.com/ruyisdk/packages-index/pull/84)

- lintestor
  - [v0.2.0 templated test execution, enhanced report generator, and "variable" system for template](https://github.com/255doesnotexist/lintestor/pull/96) 为 Review 准备好
    - 清理旧代码、简化逻辑，executor options 之前留的 TODO 做完了
    - 修了下 Clippy workflow
    - 新增 `--keep-template-directory-structure (-k)` 选项，使报告目录默认保留模板目录结构
    - 移除分支中非代码的脏文件
  -  合并上个月提的 v0.2.0 版本重构 PR ([#96](https://github.com/255doesnotexist/lintestor/pull/96))
      - 废弃基于 Shell 脚本的测试执行器、聚合器和报告生成器。
      - 引入基于 Markdown 模板 (`.test.md`) 的测试定义和执行引擎，包含解析器、依赖管理器、变量系统和报告生成器。
      - 重写 CLI 接入，支持模板发现、测试筛选（按单元、标签、目标）和执行控制。
      - 实现连接管理器 (`ConnectionManager`)，支持本地、SSH、串口等执行方式，并引入连接池。
  - 增加 MUSL 静态编译支持 ([`c42e31a`](https://github.com/255doesnotexist/lintestor/commit/c42e31a), [`eb55bf1`](https://github.com/255doesnotexist/lintestor/commit/eb55bf1), [`af69fa6`](https://github.com/255doesnotexist/lintestor/commit/af69fa6))
      - 更新 `Dockerfile`，增加 `musl-tools` 和 `musl-dev`，并添加 MUSL 编译目标。
      - 在 Cargo 配置和 CI 工作流中添加静态链接配置。
  - 代码清理和缺陷修复
      - 升级到 Rust 2024 Edition 并清理无用依赖 ([`f863086`](https://github.com/255doesnotexist/lintestor/commit/f863086))。
      -   修复因模板文件名相同导致的模板 ID 冲突问题 ([`ba15cad`](https://github.com/255doesnotexist/lintestor/commit/ba15cad))。
      -   修复摘要报告文件名中的错误 ([`66a28aa`](https://github.com/255doesnotexist/lintestor/commit/66a28aa))。
  -   重构 CI/CD 流程
      -   将构建环境从 self-hosted runner 迁移到 GitHub-hosted runner ([`cff8967`](https://github.com/255doesnotexist/lintestor/commit/cff8967))。
      - 将发布流程（crates.io 和 Release）改为手动触发 ([`b280b7c`](https://github.com/255doesnotexist/lintestor/commit/b280b7c), [`a7ac8f2`](https://github.com/255doesnotexist/lintestor/commit/a7ac8f2))。
      - 新增 `pre-commit` 钩子，用于自动格式化 Rust 代码 ([`4b7d54b`](https://github.com/255doesnotexist/lintestor/commit/4b7d54b))。
  - 更新项目文档
      - 更新 `README.md` 和 `USAGE.md` 以匹配 v0.2.0 架构和用法 ([`98b2b0c`](https://github.com/255doesnotexist/lintestor/commit/98b2b0c))。
  - [fix: target config probing](https://github.com/255doesnotexist/lintestor/pull/96/commits/82296ea42f43d7e81d6f9ae7487f58c12c1882d1)
  - [fix: deduplicate discovered template paths](https://github.com/255doesnotexist/lintestor/pull/96/commits/c33195de2337569a2f1863216f6adb8b74cb0314)
  - [fix: proper serial session handling](https://github.com/255doesnotexist/lintestor/commit/3538489c612dcbbfc17fb1dfc5138a0cf78abf94)
  
#### 2.4 会议和技术分享
- https://github.com/ruyisdk/wechat-articles/pull/157
- https://github.com/ruyisdk/wechat-articles/pull/160
- 双周五RISC-V研讨会RISC-V操作系统支持矩阵进展报告

#### 2.5 操作系统支持矩阵设备维护

- 机器迁移
 - SDWireC + Remote BPI-F3 迁移至实体机
 - VM 销毁
- Jupiter 系统更新
- Nezha (D1-H) 系统更新 & 电源更换
- Pioneer 系统重装至 oERV（用于 openGauss 测试）
- 重新上架 LPi4A 和 Meles
- Uptime 监控 [Radiata](https://radiata.kevinmx.top) 迁移（修复之前的频繁掉线问题）

### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- SAIL
  - [PR] <https://github.com/riscv-non-isa/riscv-arch-test/pull/658> Fix missing val_comb values after expand_cgf
  - [PR] <https://github.com/riscv-non-isa/riscv-arch-test/pull/660> Add ruff format check in pre-commit hook and CI
  - [PR] <https://github.com/riscv/sail-riscv/pull/1023> Add initial setup for hypervisor extension
  - [PR] <https://github.com/rems-project/sail/pull/1345> Add flag --fmt-emit
  - [PR] <https://github.com/rems-project/sail/pull/1346> Add flag --fmt-debug
  - 工具：vscode sail 代码格式化插件 [下载链接](https://marketplace.visualstudio.com/items?itemName=trdthg.sail-fmt) [仓库](https://github.com/trdthg/sail-fmt-vscode)
  - [PR] <https://github.com/riscv/sail-riscv/pull/1067> Add VU and VS privilege level
  - [PR] <https://github.com/riscv/sail-riscv/pull/1061> Add current virtualization mode register
  - [PR] <https://github.com/riscv/sail-riscv/pull/1063> Split rvfi_dii v1 and v2
  - [PR] <https://github.com/riscv/sail-riscv/pull/1099> Move RVFI to C
  - [#1103](https://github.com/riscv/sail-riscv/pull/1103) : 修复了Softfloat 在sail的接口中f32 转 i16 之类函数会丢失符号flag 的问题
  - [#1105](https://github.com/riscv/sail-riscv/pull/1105) : 重构整合了 vzext/vsext 的实现代码，优化了代码结构
  - [#990](https://github.com/riscv/sail-riscv/pull/990) : 重载了 regidx_offset 函数，使得支持类型 regidx 的一些常用计算
  - [#1042](https://github.com/riscv/sail-riscv/pull/1042) : 在sail 解码过程中添加守卫，以减少保留指令亦被解码处理从而效率降低的问题
  - [#1108](https://github.com/riscv/sail-riscv/pull/1108) : 添加新类型 cfregidx ，从而 C 扩展的浮点数操作不需要使用 cregidx 来代表浮点数造成混淆
  - [#956](https://github.com/riscv/sail-riscv/pull/956) ：修复了几个review的问题
  - [#792](https://github.com/riscv/sail-riscv/pull/792) ：解决冲突
- ACT
  - 提交了一个关于两个仓库插件不同步导致riscof无法正常实现的bug[#671](https://github.com/riscv-non-isa/riscv-arch-test/issues/671)
  - 更新了提交RV32 Zfinx的测试用例的pr[#638](https://github.com/riscv-non-isa/riscv-arch-test/pull/638)
  - 更新了修复zdinx错误的测试用例的pr[#651](https://github.com/riscv-non-isa/riscv-arch-test/pull/651)
  - 更新了提交RV64 Zdinx的测试用例的pr[#654](https://github.com/riscv-non-isa/riscv-arch-test/pull/654)
  - 提交了暂时同步RISCOF仓库中的riscof插件的pr[#142](https://github.com/riscv-software-src/riscof/pull/142)
  - 提交了修复请求内存过多的issue的pr并成功合并[#662](https://github.com/riscv-non-isa/riscv-arch-test/pull/662)

  | 更新测试指令名 | 所属拓展 | 测试用例数 | 地址                                                         |
  | -------------- | -------- | ---------- | ------------------------------------------------------------ |
  | fadd.d         | Zdinx    | 11         | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fclass.d       | Zdinx    | 1          | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fdiv.d         | Zdinx    | 11         | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | feq.d          | Zdinx    | 2          | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fle.d          | Zdinx    | 2          | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | flt.d          | Zdinx    | 2          | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fmadd.d        | Zdinx    | 62         | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fmadd-b11  | zfinx    | 13             | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fmsub-b11  | zfinx    | 13             | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |

- Issues
  - [#1072](https://github.com/riscv/sail-riscv/issues/1072) : 参与了Issue 讨论，关于vstart在移动整个v寄存器中作用以及行为的疑问

#### 3.2 SAIL技术分享
  
- [sail code gen](https://github.com/rez5427/plct/blob/main/Report/sailcodegen.pptx)

#### 3.3 SAIL会议

- tech-golden-model meeting [`06.12`, `06.16`, `06.23`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- OpenHour [06.12](https://docs.google.com/presentation/d/1o1kiyiEf6-bbtsUyDOpUHlufqf-pSytKfzFySkYvfUM/edit?slide=id.g30342600295_22_0#slide=id.g30342600295_22_0)
- 第 13 次 RISC-V 研讨会：SAIL 进展介绍与 RISC-V 项目动态分享 [PPT](https://github.com/trdthg/plct/blob/main/outcome/202506/%E7%AC%AC%2013%20%E6%AC%A1%20RISCV%20%E7%A0%94%E8%AE%A8%E4%BC%9A%EF%BC%9ASAIL%20%E8%BF%9B%E5%B1%95%E4%BB%8B%E7%BB%8D%E5%8F%8A%E5%8A%A8%E6%80%81%E5%88%86%E4%BA%AB.pptx)
- 参加了6月2日的ACT会议并写了会议纪要[MD](https://github.com/Pagerd/PLCT/blob/main/Report/week/week85/ACT.md)
- 参加了6月30日的ACT会议并写了会议纪要[MD](https://github.com/Pagerd/PLCT/blob/main/Report/week/week87/ACT.md)

### 4. 独立测试项目/应用软件生态观测

#### 4.1 RuyiSDK GNU Tests

- [gnu-plct/SG2042: Add ver 20250615](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/8)
- [gnu-plct/SG2000 Add GCC16 Report](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/9)
- [gnu-plct/TH1520: Add ver 20250615](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/10)
- [CV1800B: Add ver 20250615](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/12)
  
- 完成以下两个系统 gnu-plct 16.0.0 版本的测试：
  - [SG2042](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/8)
  - [TH1520](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/10)

- 正在进行 GCC 15 在 K230 上的测试，使用 lintestor 完成（边使用边开发）。

- SG2000/GCC16
  - https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/9
  
#### 4.2 OpenCloud OS test

- OpenCloud OS 要求的基础测试报告，包含性能测试和内核测试，见 [ocs_test](https://github.com/wychlw/plct/tree/main/memo/ocs_test)

#### 4.3 openGauss 测试

- [Add SG2042 openGauss7.0.0-RC1 test report, add K1/M1, SG2042, TH1520…](https://github.com/QA-Team-lo/dbtest/pull/2)

#### 4.4 ROS1/2 测试和Demo原型开发
- [演示视频](https://github.com/lalafua/sim_llm/blob/main/assets/demo_iscas.webm)

- [文档](https://github.com/lalafua/plct-working/blob/main/other/%E5%BC%80%E6%94%BE%E6%97%A5/sim_llm.pdf)

- [源代码](https://github.com/lalafua/slides/blob/main/slides/sim_llm.md)

- 使用 MavRos 开发树莓派和 APM 飞控的小车
  - [过程记录](https://github.com/lalafua/recording/tree/main)

#### 4.5 玄铁课程

-  [RV学院_在 K230 开发板进行 AI 识别应用开发ppt](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/XuanTie/RV%E5%AD%A6%E9%99%A2_%E5%9C%A8%20K230%20%E5%BC%80%E5%8F%91%E6%9D%BF%E8%BF%9B%E8%A1%8C%20AI%20%E8%AF%86%E5%88%AB%E5%BA%94%E7%94%A8%E5%BC%80%E5%8F%91ppt_%E5%BC%A0%E9%A6%A5%E5%AA%9B.pptx)
   -  [口播稿+分镜](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/XuanTie/%E7%8E%84%E9%93%81%E8%AF%BE%E7%A8%8B%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
   - 录制课程介绍/个人介绍视频

- [在Licheepi 4A上运行Deepseek]((https://github.com/Pagerd/PLCT/blob/main/Report/25-June/runningDeepseek.pptx))

#### 4.6 英麒 RISC-V Lab

- [英麒视频素材库策划方案](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/Video_library_plan.md)
- 部署展厅软路由
- 部署展厅，上线3台Licheepi，写新闻稿
- 配合调试维护实验室的Licheepi 4A
- 部署展厅交换机，确认布置格局
 
### 5. RISC-V教育和短视频

#### 5.1 短视频课程设计

- 项目迭代计划

https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Plan_Document

- 项目迭代回溯

https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Review_Document
  
#### 5.2 短视频设计和实现

- [Milk-V Duo 盘点一下新手常用命令_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1eVTrzgEkQ)

- [在Licheepi 4A 上运行 ROS2_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1MFgfz9Err)
 
#### 5.3 短视频剧本和文档、素材

- [在Licheepi 4A 上运行 ROS2文档](https://github.com/lalafua/recording/blob/main/riscv/ros2/tutorial/first.md)

#### 5.5 短视频技术分享

- 2025年 RISC-V 北美峰会海报准备
 
### 6. 职工

#### 6.1 蔡玮霖
- Ruyi v0.35.0 测试完成 pr [!73](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/73)
- Ruyi v0.35.0 测试报告更新 pr [!74](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/74)
- Ruyi v0.36.0 测试完成 pr [!75](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/75)
- Ruyi v0.36.0 版本对沁恒 MCU 的支持进行了[初步测试](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250630/RUYI_包管理_对WCH单片机支持情况附加测试.md)
- RuyiSDK Eclipse Plugin v0.0.5 测试报告的审核 [!6 Add ruyi ide 0.0.5 test report](https://gitee.com/weilinfox/ruyisdk-test/pulls/6)
- ruyi 提交 1 个 pr
    - [docs: modify ruyisdk.github.io related links #307](https://github.com/ruyisdk/ruyi/pull/307)
- ruyi 提交 2 个 issue
    - [curl 8.14.1 bug 导致 ruyi 软件包下载失败 #316](https://github.com/ruyisdk/ruyi/issues/316)
    - [ruyi self clean --news-read-status 在记录文件不存在时报错 #319](https://github.com/ruyisdk/ruyi/issues/319)
- packages-index 提交 1 个 pr
    - [docs: modify ruyisdk.github.io related links #81](https://github.com/ruyisdk/packages-index/pull/81)
- packages-index 合作 1 个 pr
    - [board-image/buildroot-sdk-milkv-{duo,duo256m,duos-sd}: bump to version v2.0.1 #85](https://github.com/ruyisdk/packages-index/pull/85)（暂未合并）
- packages-index 审核 1 个 pr
    - [Add BPi-F3 (Bianbu [minimal|desktop]) #84](https://github.com/ruyisdk/packages-index/pull/84)
- ruyisdk-website 提交 7 个 pr
    - [pages: add plct lab to footer #139](https://github.com/ruyisdk/ruyisdk-website/pull/139)
    - [pages: change licheepi 4a image #140](https://github.com/ruyisdk/ruyisdk-website/pull/140)
    - [pages: fix subscribe input margin #142](https://github.com/ruyisdk/ruyisdk-website/pull/142)
    - [pages: fix index description #143](https://github.com/ruyisdk/ruyisdk-website/pull/143)
    - [pages: update homepage news with AsiaLLVM 2025 #147](https://github.com/ruyisdk/ruyisdk-website/pull/147)
    - [pages: add IDE plugin download info #152](https://github.com/ruyisdk/ruyisdk-website/pull/152)
    - [pages: add More Developer Tools footer #153](https://github.com/ruyisdk/ruyisdk-website/pull/153)
- ruyisdk-website 合作 4 个 pr
    - [Homepage fine-tuning #1 #138](https://github.com/ruyisdk/ruyisdk-website/pull/138)
    - [Optimizations to the website #141](https://github.com/ruyisdk/ruyisdk-website/pull/141)
    - [New data load mechenism, better UI, and improved NewsShowcase #144](https://github.com/ruyisdk/ruyisdk-website/pull/144)
    - [Add community page #149](https://github.com/ruyisdk/ruyisdk-website/pull/149)（暂未合并）
- ruyisdk-website 审核 3 个 pr
    - [add categories downloads #148](https://github.com/ruyisdk/ruyisdk-website/pull/148)（与预期有尚偏差但仍可合并）
    - [Widescreen optimization #155](https://github.com/ruyisdk/ruyisdk-website/pull/155)
    - [docs: update the English version for download page and Ruyi IDE installation guide #156](https://github.com/ruyisdk/ruyisdk-website/pull/156)
- ruyisdk-website 关闭 1 个 issue
    - [下载菜单：增加 IDE 和插件下载 #70](https://github.com/ruyisdk/ruyisdk-website/issues/70)
- ruyisdk-website 新开 2 个 issue
    - [博客双周报的合并 #145](https://github.com/ruyisdk/ruyisdk-website/issues/145)（暂未分配实习生任务）
    - [社区板块的更新 #146](https://github.com/ruyisdk/ruyisdk-website/issues/146)
- docs 合作 1 个 pr
    - [Update Ruyi IDE installation guide #86](https://github.com/ruyisdk/docs/pull/86)
- ruyi-packaging 提出 1 个 issue
    - [ruyi-packaging 整体设计 #17](https://github.com/ruyisdk/ruyi-packaging/issues/17)
- 测试机和测试套件更新和维护
    - Ruyi v0.35.0 测试中 Fedora 环境新增 41 riscv64
    - Ruyi v0.36.0 测试中 Fedora 环境新增 41 x86\_64 和 42 x86\_64/riscv64，移除 38 riscv64 和 39 x86\_64
    - Ruyi v0.36.0 测试中 openEuler 环境新增 25.03 x86\_64/riscv64，移除 23.09 x86\_64，减少了一个 23.09 riscv64 平台（还剩一个）
    - [更新测试报告模板](https://github.com/weilinfox/ruyi-litester-reports/compare/5a360bd272965372083012c1382744cd7afd606e...02027b8805c826210cf75436566bb344bb7143b9)
    - [缓解部分测试机磁盘空间不足](https://github.com/weilinfox/ruyi-reimu/commit/6094edd22648e2084a2367633401fc569b92cc16)
    - [测试套件适配 0.35.0 版本输出变化](https://github.com/weilinfox/ruyi-litester/compare/ad02bbb6ca2a7afe8f8bbfae540884ca8bd22751...755f149a44b8238047b9cbbfe31eba50ca9c0ef8)
    - [测试套件适配 0.36.0 镜像结构变化](https://github.com/weilinfox/ruyi-litester/commit/8467b22a23a59e241786af4d6df247bc1abf223c)

#### 6.2 郑景坤

##### 6.2.1 操作系统支持矩阵

- PR Review (对测试团队操作系统支持矩阵产出的review审核，以下内容同测试团队产出，此处为review)
  - [Mars: Add irradium, openKylin, openSUSE test reports.](https://github.com/ruyisdk/support-matrix/pull/313)
  - [OrangePi RV2: Add irradium test report.](https://github.com/ruyisdk/support-matrix/pull/314)
  - [LicheePi4A: Add irradium test report (CFT).](https://github.com/ruyisdk/support-matrix/pull/315)
  - [Metadata: Fix redundant vendor, update CONTRIBUTING and temple metadata, add esp32-p4 metadata](https://github.com/ruyisdk/support-matrix/pull/316)
  - [Clean deprecated codes](https://github.com/ruyisdk/support-matrix/pull/317)
  - [Add metadata for oz64 and pinecone](https://github.com/ruyisdk/support-matrix/pull/319)
  - [Visionfive/Alpine: Update result to basic.](https://github.com/ruyisdk/support-matrix/pull/320)
  - [LicheePi 3A: Add board and systems; Some fixes and tweaks](https://github.com/ruyisdk/support-matrix/pull/321)
  - [DuoS: Dump Debian to v1.6.31](https://github.com/ruyisdk/support-matrix/pull/322)
  - [Bit-Brick_K1: add test for bianbu 2.2 minimal](https://github.com/ruyisdk/support-matrix/pull/323)
  - [LiP4A: merge 8+32G and 16+128G](https://github.com/ruyisdk/support-matrix/pull/324)
  - [LPi4A/RevyOS: Bump to 20250526](https://github.com/ruyisdk/support-matrix/pull/325)
  - [LicheePi4A: Add irradium test report (good).](https://github.com/ruyisdk/support-matrix/pull/327)
  - [Bit-Brick_K1: add test for bianbu 2.2 minimal](https://github.com/ruyisdk/support-matrix/pull/323)
  - [Miscellaneous tests bump](https://github.com/ruyisdk/support-matrix/pull/326)
  - [Add test for booting from SATA on Megrez](https://github.com/ruyisdk/support-matrix/pull/331)
  - [Jupiter/openKylin: Fix wrong `sys_ver`](https://github.com/ruyisdk/support-matrix/pull/337)

##### 6.2.2 RuyiSDK 双周报/支持矩阵部分

- https://github.com/ruyisdk/wechat-articles/pull/157
- https://github.com/ruyisdk/wechat-articles/pull/160

##### 6.2.3 独立测试项目/应用软件生态观测

- RuyiSDK GNU Test PR Review
  - [gnu-plct/SG2042: Add ver 20250615](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/8)
  - [[gnu-plct/SG2000] Add GCC16 Report](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/9)
  - [gnu-plct/TH1520: Add ver 20250615](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/10)
  - [CV1800B: Add ver 20250615](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/pull/12)

##### 6.2.4 Infra

- 机器迁移
 - SDWireC + Remote BPI-F3 迁移至实体机
 - VM 销毁
- Jupiter 系统更新
- Nezha (D1-H) 系统更新 & 电源更换
- Pioneer 系统重装至 oERV（用于 openGauss 测试）
- 重新上架 LPi4A 和 Meles
- Uptime 监控 [Radiata](https://radiata.kevinmx.top) 迁移（修复之前的频繁掉线问题）

##### 6.2.5 RevyOS 小队

- PR Review
    - [fix(benchmark): Update benchmark documentation for CoreMark, glmark2, lmbench, p7zip, and stream](https://github.com/revyos/docs/pull/48)
    - [Update image version of lpi4a and meles to 20250526](https://github.com/revyos/docs/pull/47)
- revyos/lmbench3: [fix: build error on gcc 14](https://github.com/revyos/lmbench3/pull/5)
- RISC-V Open Hours[20250626](https://docs.google.com/presentation/d/1V0prRioAV0kNjeEcPae90I6VFp60KZ7uSGeGfEK-yqQ/edit?slide=id.g2c2a5d80f05_5_0#slide=id.g2c2a5d80f05_5_0) & [20250612](https://docs.google.com/presentation/d/1o1kiyiEf6-bbtsUyDOpUHlufqf-pSytKfzFySkYvfUM/edit?slide=id.g2c2a5d80f05_5_0#slide=id.g2c2a5d80f05_5_0)
- [东亚双周会 20250626](https://docs.google.com/presentation/d/1DwQQIhldZxITSbBNLRzb9Tsi62_99NnMGcDs7HqIEcc/edit?slide=id.g36afb8f9799_13_0#slide=id.g36afb8f9799_13_0) & [20250612](https://docs.google.com/presentation/d/13iJrwJzhYFoKok3ehq69BAWnkhkqILAt9PKB6ti9W1Y/edit?slide=id.g365a87dc147_0_3#slide=id.g365a87dc147_0_3)

#### 6.3 阎明铸

##### 6.3.1 sail/act
# 本月工作

## sail/act

- \[PR\] <https://github.com/riscv-non-isa/riscv-arch-test/pull/658> Fix missing val_comb values after expand_cgf
- \[PR\] <https://github.com/riscv-non-isa/riscv-arch-test/pull/660> Add ruff format check in pre-commit hook and CI
- \[PR\] <https://github.com/riscv/sail-riscv/pull/1023> Add initial setup for hypervisor extension
- \[PR\] <https://github.com/rems-project/sail/pull/1345> Add flag --fmt-emit
- \[PR\] <https://github.com/rems-project/sail/pull/1346> Add flag --fmt-debug
- 工具：vscode sail 代码格式化插件 [下载链接](https://marketplace.visualstudio.com/items?itemName=trdthg.sail-fmt) [仓库](https://github.com/trdthg/sail-fmt-vscode)
- \[PR\] <https://github.com/riscv/sail-riscv/pull/1067> Add VU and VS privilege level
    - \[PR\] <https://github.com/riscv/sail-riscv/pull/1061> Add current virtualization mode register
- \[PR\] <https://github.com/riscv/sail-riscv/pull/1063> Split rvfi_dii v1 and v2
- \[PR\] <https://github.com/riscv/sail-riscv/pull/1099> Move RVFI to C

##### 6.3.2 会议/技术分享

- tech-golden-model meeting [`06.12`, `06.16`, `06.23`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- OpenHour [06.12](https://docs.google.com/presentation/d/1o1kiyiEf6-bbtsUyDOpUHlufqf-pSytKfzFySkYvfUM/edit?slide=id.g30342600295_22_0#slide=id.g30342600295_22_0)
- 第 13 次 RISC-V 研讨会：SAIL 进展介绍与 RISC-V 项目动态分享 [PPT](https://github.com/trdthg/plct/blob/main/outcome/202506/%E7%AC%AC%2013%20%E6%AC%A1%20RISCV%20%E7%A0%94%E8%AE%A8%E4%BC%9A%EF%BC%9ASAIL%20%E8%BF%9B%E5%B1%95%E4%BB%8B%E7%BB%8D%E5%8F%8A%E5%8A%A8%E6%80%81%E5%88%86%E4%BA%AB.pptx)

#### 6.4 张馥媛

##### 6.4.1 Milk-V Duo
# Month15

本月工作

## 1. Milk-V Duo

### 视频AI配音

- [【Milk-V Duo】盘点一下新手常用命令_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1eVTrzgEkQ/?spm_id_from=333.1387.homepage.video_card.click&vd_source=417238cd96b1b549d14bcb35a9da3cf0)
## 2.Licheepi 4A
### 视频AI配音

- [在Licheepi 4A 上运行 ROS2_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1MFgfz9Err/?spm_id_from=333.1387.homepage.video_card.click&vd_source=417238cd96b1b549d14bcb35a9da3cf0)

##### 6.4.2 玄铁课程

-  [RV学院_在 K230 开发板进行 AI 识别应用开发ppt](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/XuanTie/RV%E5%AD%A6%E9%99%A2_%E5%9C%A8%20K230%20%E5%BC%80%E5%8F%91%E6%9D%BF%E8%BF%9B%E8%A1%8C%20AI%20%E8%AF%86%E5%88%AB%E5%BA%94%E7%94%A8%E5%BC%80%E5%8F%91ppt_%E5%BC%A0%E9%A6%A5%E5%AA%9B.pptx)
-  [口播稿+分镜](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/XuanTie/%E7%8E%84%E9%93%81%E8%AF%BE%E7%A8%8B%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- 录制课程介绍/个人介绍视频

##### 6.4.3 RISC-V short video项目
建议和修改同学们提交的视频，发布视频和控制进度

- 项目迭代计划：

https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Plan_Document

- 项目迭代回溯：

https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Review_Document

##### 6.4.4 英麒 RISC-V Lab

- [英麒视频素材库策划方案](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/Video_library_plan.md)
- 部署展厅软路由
- 部署展厅，上线3台Licheepi，写新闻稿
- 配合调试维护实验室的Licheepi 4A
- 部署展厅交换机，确认布置格局

#### 6.5 朱旭昌

- Sail/ACT

  - 提交了一个关于两个仓库插件不同步导致riscof无法正常实现的bug[#671](https://github.com/riscv-non-isa/riscv-arch-test/issues/671)
  - 更新了提交RV32 Zfinx的测试用例的pr[#638](https://github.com/riscv-non-isa/riscv-arch-test/pull/638)
  - 更新了修复zdinx错误的测试用例的pr[#651](https://github.com/riscv-non-isa/riscv-arch-test/pull/651)
  - 更新了提交RV64 Zdinx的测试用例的pr[#654](https://github.com/riscv-non-isa/riscv-arch-test/pull/654)

  - 提交了暂时同步RISCOF仓库中的riscof插件的pr[#142](https://github.com/riscv-software-src/riscof/pull/142)
  - 提交了修复请求内存过多的issue的pr并成功合并[#662](https://github.com/riscv-non-isa/riscv-arch-test/pull/662)

  | 更新测试指令名 | 所属拓展 | 测试用例数 | 地址                                                         |
  | -------------- | -------- | ---------- | ------------------------------------------------------------ |
  | fadd.d         | Zdinx    | 11         | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fclass.d       | Zdinx    | 1          | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fdiv.d         | Zdinx    | 11         | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | feq.d          | Zdinx    | 2          | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fle.d          | Zdinx    | 2          | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | flt.d          | Zdinx    | 2          | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fmadd.d        | Zdinx    | 62         | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fmadd-b11  | zfinx    | 13             | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fmsub-b11  | zfinx    | 13             | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |

- ACT会议
  - 参加了6月2日的ACT会议并写了会议纪要[MD](https://github.com/Pagerd/PLCT/blob/main/Report/week/week85/ACT.md)

  - 参加了6月30日的ACT会议并写了会议纪要[MD](https://github.com/Pagerd/PLCT/blob/main/Report/week/week87/ACT.md)

- 玄铁课程
  - [在Licheepi 4A上运行Deepseek]((https://github.com/Pagerd/PLCT/blob/main/Report/25-June/runningDeepseek.pptx))

## SG2042/SG2044 Upstream

SG2042 Upstream

- [[PATCH v3 0/4] spi: sophgo: Add SPI NOR controller for SG2042][sg2042-lk-1]: SPI NOR 控制器补丁 第 3 版。

[sg2042-lk-1]:https://lore.kernel.org/linux-riscv/20250629-sfg-spifmc-v3-0-28db1f27e999@gmail.com/

## Milk-V Duo Upstream

- [[PATCH 0/2] remoteproc: cv1800b: Add initial support for C906L processor][cv18xx-lk-1]: Remoteproc 驱动补丁第 1 版。

[cv18xx-lk-1]:https://lore.kernel.org/linux-riscv/20250608-cv1800-rproc-v1-0-57cf66cdf6a3@pigmoral.tech/

## K230 Upstream

- [[PATCH v4 0/2] reset: canaan: add Kendryte K230 reset support][k230-lk-1]: Reset 补丁第 4 版，已经被 reset 仓库收录到 next 分支，期望合入 6.17。

[k230-lk-1]:https://lore.kernel.org/linux-riscv/20250613-k230-reset-v4-0-e5266d2be440@pigmoral.tech/

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
