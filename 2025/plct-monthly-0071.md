# PLCT 开源进展·第 71 期·2025 年 6 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

1. 新增功能: Eclips插件中使用 ruyi venv 构建指定的程序（hello）

   - open:[feat:add new plugin: projectcreator](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/46)
2. 新增功能：定制 Welcome 页面

   - [feat:add plugin for intro page](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/18)
   - [Optimization:fix html cannot open in some environments](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/19)
   - [fix: Fix the packaging problem of the third-party librar](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/24)
3. 软件包资源管理代码完善：

   - 解决软件包不能稳定呈现问题：
     - [Fix:packaged resources cannot be loaded](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/31)
   - 接入ruyi中的所有支持的开发板型号：
     - [feat: automatically get the development board list from the server](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/25)
     - [fix ui problem and add serach borad wiht no rse processing logic,add ruyisdk submenu in view list](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/40)
   - 新增软件包卸载功能：
     - [feat:Add uninstall package function](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/44)
4. 按reviewer要求规范代码和修复安全性问题

   - [Fix:fix potential security and locale-sensitive string handling issues](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/35)
   - [fix:Change the new method execution to an absolute path and standardize the code](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/pull/33)

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
