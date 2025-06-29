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

## LLVM Team

## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

## DynamoRIO

## coreboot for riscv

## openocd

## opensbi

## u-boot

## RevyOS (Debian for Xuantie)

### Debian

## RT-Thread

## PLCT罗云翔测试团队

## SG2042/SG2044 Upstream

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
