# PLCT 开源进展·第 72 期·2025 年 7 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

项目地址：https://github.com/ruyisdk/ruyi

7 月份 RuyiSDK 包管理器发布了 4 个新版本：0.37.0、0.37.1、0.38.0、0.38.1，对应
RuyiSDK 整体的 0.37 与 0.38 两个正式版本。您可移步
[GitHub Releases][GitHub Releases] 或 [ISCAS 镜像源][iscas]下载体验。

[GitHub Releases]: https://github.com/ruyisdk/ruyi/releases/tag/0.38.1
[iscas]: https://mirror.iscas.ac.cn/ruyisdk/ruyi/tags/0.38.1/

本月的主要变更如下：

Release Engineering 与工程化方面：

* 重构了 `ruyi` 的捆绑资源处理方式，将其从虚拟环境机制中剥离了，以便后续捆绑其他非虚拟环境相关资源，如命令行自动补全脚本、多语言字符串文件等等。同时，也以 CI 方式确保了 `ruyi` 所含的压缩资源总与原始文件保持同步。
* 新增了对于 OpenCloudOS 9.4、openEuler 24.03 LTS SP2、openEuler 25.03、openKylin 2.0 的支持情况。`ruyi` 的 Python 依赖包在这些发行版上均有少量缺失，但其余依赖包的版本满足要求，我们预计将在 2025 年 10 月完成对它们的支持。

`ruyi` 包管理器命令行工具方面：

* 新增了基本的命令行自动补全支持，初期支持 Bash 与 Zsh 两种 shells。感谢 [@wychlw] 的贡献！

  要使用命令行自动补全功能，请在您的 shell profile（如 `.bashrc` 或 `.zshrc`）的合适位置引入
  `ruyi` 的自动补全脚本：

  ```sh
  # zsh 用户请将 bash 字样替换为 zsh
  eval "$(ruyi --output-completion-script=bash)"
  ```

  目前支持 `ruyi` 子命令与 `ruyi install` 等命令的软件包参数的自动补全。

* 使用 `ruyi self clean` 清除本地数据时，如果新闻已读状态文件不存在，不会报错崩溃了。感谢 [@weilinfox] [报告][ruyi-issue319]问题！
* 拉取远端 Git 仓库失败时，不会将 Python 错误信息暴露给用户了。
* 只有在文件的下载 URL 协议为 FTP 时，才会为 `curl` 或 `wget` 启用 FTP 被动模式了。这修复了部分 RuyiSDK 用户由于[cURL 8.14.1 的 bug][curl-issue17545] 而无法下载任何文件的问题。感谢 [@weilinfox] 向 `ruyi` 项目[报告][ruyi-issue316]问题！
* 为 RuyiSDK 设备安装器新增了 `ruyi device flash` 这一别名，以便理解记忆。感谢 RuyiSDK 社区论坛的 [@Sequel] 同学反馈！
* 当 `ruyi` 需要调用某些外部命令但无法找到时，如果当前终端可以交互，会等待您安装以便重试了。您可以在另一个终端下安装所需命令，再回到 `ruyi` 所在终端按回车键继续。您也可以按 Ctrl+C 退出。感谢 RuyiSDK 社区论坛的 [@Sequel] 同学反馈！

RuyiSDK 软件源方面：

* 完善了设备支持：
    * 更新了 Milk-V Duo（64 & 256M RAM）、Duo S（SD 存储）的 Buildroot SDK。感谢 [@Cyl18] 的贡献！
    * 支持了 BananaPi BPI-F3 的 SD 存储型号，有 SpacemiT 提供的 Bianbu Desktop 与 Bianbu Minimal 两种系统供使用。感谢 [@wychlw] 的贡献！
    * 新增了 Sipeed LicheePi 4A 的 RevyOS 的历史版本。感谢 [@Cyl18] 的贡献！
    * 新增了 Milk-V Duo 的 Arduino 的 1.1.2 与 1.1.4 两个版本。感谢 [@Cyl18] 的贡献！
* 实体数据库更新：
    * 新增了 SpacemiT X60 微架构。
    * 新增了 SpacemiT K1 处理器型号。
    * 新增了 BananaPi BPI-F3 的 eMMC 与 SD 存储两种设备变体。

欢迎试用或来上游围观；您的需求是我们迭代开发的目标和动力。您也可以亲自参与
RuyiSDK 软件的打包与分发工作：目前您可以直接在 GitHub 上查看、修改我们的[部分打包脚本](https://github.com/ruyisdk/ruyici)与[软件源仓库](https://github.com/ruyisdk/packages-index)。今后，按照本年度的开发计划，我们也将支持有权的第三方贡献者通过程序化的方式上传软件包、系统镜像等分发文件，以便利打包工作。

[@Cyl18]: https://github.com/Cyl18
[@Sequel]: https://ruyisdk.cn/u/Sequel
[@weilinfox]: https://github.com/weilinfox
[@wychlw]: https://github.com/wychlw
[curl-issue17545]: https://github.com/curl/curl/issues/17545
[ruyi-issue316]: https://github.com/ruyisdk/ruyi/issues/316
[ruyi-issue319]: https://github.com/ruyisdk/ruyi/issues/319

## V8 / Chromium

## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/24909 (8355667: RISC-V: Add backend implementation for unsigned vector Min / Max operations)
- https://github.com/openjdk/jdk/pull/24296 (8352251: Implement JEP 518: JFR Cooperative Sampling)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/25158 (8356192: Enable AOT code caching only on supported platforms)
- https://github.com/openjdk/jdk/pull/25272 (8357143: New test AOTCodeCompressedOopsTest.java fails on platforms without AOT Code Cache support)
- https://github.com/openjdk/jdk/pull/24910 (8355668: RISC-V: jdk/incubator/vector/Int256VectorTests.java fails when using RVV)
- https://github.com/openjdk/jdk/pull/24918 (8355796: RISC-V: compiler/vectorapi/AllBitsSetVectorMatchRuleTest.java fails after JDK-8355657)
- https://github.com/openjdk/jdk/pull/24943 (8355878: RISC-V: jdk/incubator/vector/DoubleMaxVectorTests.java fails when using RVV)
- https://github.com/openjdk/jdk/pull/24950 (8355913: RISC-V: improve hotspot/jtreg/compiler/vectorization/runner/BasicFloatOpTest.java)
- https://github.com/openjdk/jdk/pull/24968 (8355980: RISC-V: remove vmclr_m before vmsXX and vmfXX)
- https://github.com/openjdk/jdk/pull/24983 (8356030: RISC-V: enable (part of) BasicDoubleOpTest.java)
- https://github.com/openjdk/jdk/pull/25005 (8355699: RISC-V: support SUADD/SADD/SUSUB/SSUB)
- https://github.com/openjdk/jdk/pull/25055 (8356188: RISC-V: Cleanup effect of vmaskcmp_fp)
- https://github.com/openjdk/jdk/pull/25135 (8356593: RISC-V: Small improvement to array fill stub)
- https://github.com/openjdk/jdk/pull/25145 (8356642: RISC-V: enable hotspot/jtreg/compiler/vectorapi/VectorFusedMultiplyAddSubTest.java)
- https://github.com/openjdk/jdk/pull/25172 (8356700: RISC-V: Declare incompressible scope in fill_words / zero_memory assembler routines)
- https://github.com/openjdk/jdk/pull/25181 (8350960: RISC-V: Add riscv backend for Float16 operations - vectorization)
- https://github.com/openjdk/jdk/pull/25210 (8356869: RISC-V: Improve tail handling of array fill stub)
- https://github.com/openjdk/jdk/pull/25213 (8356875: RISC-V: extension flag UseZvfh should depends on UseZfh)
- https://github.com/openjdk/jdk/pull/25221 (8356924: RISC-V: Clean up cost for vector instructions)

## Go
1. Authored/Co-authored Go-mainline CLs:
- 688635: cmd/internal/obj: enable got pcrel itype in fips140 for riscv64 | https://go-review.googlesource.com/c/go/+/688635 [merged]
- x/build: gotip-freebsd-riscv64 builder is missing | https://github.com/golang/go/issues/73568 [resolved]
2. Reviewed Go-mainline CLs:
- 688975: runtime: fix asan wrapper for riscv64 | https://go-review.googlesource.com/c/go/+/688975 [merged]
- cmd/compile: line number debug info regression in go1.25 around literal rewriting | https://github.com/golang/go/issues/74576
- 665655: internal/buildcfg: add ability to get GORISCV64 variable in GOGOARCH | https://go-review.googlesource.com/c/go/+/665655 


## OpenCV

## GNU Toolchain
实现了p扩展最新草案015版本在Binutils上的支持：
- https://github.com/ruyisdk/riscv-binutils/tree/p-dev

拟定了p扩展intrinsic文档草案，正在进行GCC部分的开发中：
- https://github.com/pz9115/rvp-intrinsic-doc/blob/main/source/simd.md

Rebase了p扩展0.9.11版本的GCC与Bintuils支持：
- https://github.com/ruyisdk/riscv-gcc/pull/5
- https://github.com/ruyisdk/riscv-binutils/pull/6

更新了riscv-gnu-toolchain configure文件中关于--with-tune的配置
- https://github.com/riscv-collab/riscv-gnu-toolchain/pull/1735

## LLVM Team
1. Upstream llvm-project 合并的patch:
- [[RISCV] AddEdge between mask producer and user of V0](https://github.com/llvm/llvm-project/pull/148566)

2. Ruyisdk llvm-project合并的patch:
- [[LLVM][XTHeadVector] xtheadvector implies zfh by default](https://github.com/ruyisdk/llvm-project/pull/162)

## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

## DynamoRIO

## llama.cpp

## coreboot for riscv

## openocd

## opensbi

## Aya Prover

本月合入的 PR 都不是工作重心，主力在搞 <https://github.com/aya-prover/aya-dev/pull/1362>。

[Watch Aya Prover](https://github.com/aya-prover/aya-dev)

+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Cherry-pick context-related changes from psi-based-completion [PR-1365](https://github.com/aya-prover/aya-dev/pull/1365) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Publish to maven portal instead [PR-1363](https://github.com/aya-prover/aya-dev/pull/1363) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) doc: add init project step in "Developing in IntelliJ IDEA" [PR-1364](https://github.com/aya-prover/aya-dev/pull/1364) opened by [illusory0x0](https://github.com/illusory0x0)

## u-boot

## RevyOS (Debian for Xuantie)

### Debian

### FreeBSD
- libunwind: https://github.com/libunwind/libunwind/issues/857
- lang/go*,devel/go-perf: update default website to go.dev: https://reviews.freebsd.org/D50595
- sqlite3@default：https://sqlite.org/forum/forumpost/a92e06fc8fa3ac99
- devel/zapcc: RISC-V support? https://github.com/yrnkrn/zapcc/issues/53  
- devel/cxxtools: build failure https://github.com/maekitalo/cxxtools/issues/36 
- devel/hpx: can't link against boost-libs [WIP]
- audio/vsound: Enable riscv64 build https://github.com/freebsd/freebsd-ports/pull/423 
- devel/gn: enable riscv64 build https://github.com/freebsd/freebsd-ports/pull/421 
- devel/critcl: enable riscv64 build https://github.com/freebsd/freebsd-ports/pull/420 
- x11/virglrenderer: enable riscv64 build   https://github.com/freebsd/freebsd-ports/pull/418
- chinese/ibus-table-chinese: Update to 1.8.13 https://github.com/freebsd/freebsd-ports/pull/419 [merged]
- net/usockets: Enable riscv64 build https://reviews.freebsd.org/D51271 [merged]
- irc/undernet-ircu: enable riscv64 build https://reviews.freebsd.org/D51270

## RT-Thread

- [MAINTAINER: standardize tag writing][rtt-10505]
- [doxygen: group name all in lowcase (part 2)][rtt-10530]
- [doxygen: fix duplicated defgroup for clock][rtt-10531]
- [doxygen: promote object management to a separate page][rtt-10532]
- [bsp: k230: add support for PWM driver][rtt-10556]

mlibc:

- [Fix ARM toolchain linking error and improve documentation][milbc-69]

Articles:

- [【嘉楠堪智K230开发板试用体验】开箱测评](https://bbs.elecfans.com/jishu_2494665_1_1.html)
- [【嘉楠堪智K230开发板试用体验】手势识别](https://bbs.elecfans.com/jishu_2494970_1_1.html)
- [【嘉楠堪智K230开发板试用体验】网络收发信息](https://bbs.elecfans.com/jishu_2494971_1_1.html)
- [【嘉楠堪智K230开发板试用体验】基于RT-THREAD上的PWM驱动开发](https://bbs.elecfans.com/jishu_2496547_1_1.html)

[rtt-10505]: https://github.com/RT-Thread/rt-thread/pull/10505
[rtt-10530]: https://github.com/RT-Thread/rt-thread/pull/10530
[rtt-10531]: https://github.com/RT-Thread/rt-thread/pull/10531
[rtt-10532]: https://github.com/RT-Thread/rt-thread/pull/10532
[rtt-10556]: https://github.com/RT-Thread/rt-thread/pull/10556
[milbc-69]: https://github.com/plctlab/mlibc/pull/69

## PLCT罗云翔测试团队

（包含 SAIL 和 ACT 测试部分）

1. RuyiSDK 多版本测试与生态完善
- 完成v0.37.1和v0.38.1版本测试，提交5个核心仓库的PR（含packages-index仓库的manifest标准化工具开发）
- 新增Ubuntu打包

2. 操作系统支持矩阵
- 新增openEuler 24.03 LTS-SP2等6个系统支持，完成Pine64 Star64深度测试
- 重构元数据系统（vendor字段标准化），清理冗余测试环境数据
- 前端实现多语言Sitemap、主题系统优化和响应式布局改进
- 开发镜像自动检查工具image-checker

3. Sail/ACT
- Hypervisor扩展支持（VU/VS特权级实现）
- 验证框架优化（修复Zfinx测试用例，同步RISCOF插件）
- 提交Sail代码格式化工具和JSON语法树插件
- 本地中断处理和ELF动态加载支持（4个核心PR合并）

4. RISC-V教育推广
- 制作LicheePi 4A ROS2实战等4部技术视频（含完整口播稿）
- 开发玄铁课程《K230 AI应用开发》
- 参加2025年RISC-V中国峰会和线上活动，推广PLCT和玄铁合作课程
- 完成多份RuyiSDK、操作系统支持矩阵、SAIL和RISC-V教育海报，并在香港城市大学活动中进行展示

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK v0.38.1测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/README.md)
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora41 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Fedora41_x86_64_测试结果.md)
    - [Fedora42 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Fedora42_riscv64_测试结果.md)
    - [Fedora41 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Fedora41_riscv64_测试结果.md)
    - [Fedora42 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Fedora42_riscv64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [openEuler25.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_openEuler25.03_riscv64_测试结果.md)
    - [openEuler25.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250723/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - 缺陷：
      - Ruyi 提交 1 个新的 issue：
        - [ruyi refresh local packages-index before running any command #335](https://github.com/ruyisdk/ruyi/issues/335)

      - RuyiSDK Eclipse Plugins 0.0.5 版本遗留 issue 如下：
        - 未配置 PATH 导致无法轻松访问 ruyi [ruyisdk/ruyisdk-eclipse-plugins#38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)
        - 下载完成不够明显 [ruyisdk/ruyisdk-eclipse-plugins#39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)

    - 资源
      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/c918eeb6c1fa9e40eb8c52fb76e443b9815486e9)
      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/6094edd22648e2084a2367633401fc569b92cc16)

  - [RuyiSDK v0.37.1测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/README.md)
  由于 v0.37.0 发现虚拟环境创建相关 [bug](https://github.com/ruyisdk/ruyi/issues/326)，故新发 0.37.1 版本。
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora41 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Fedora41_x86_64_测试结果.md)
    - [Fedora42 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [openEuler25.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_openEuler25.03_riscv64_测试结果.md)
    - [openEuler25.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250712/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - 缺陷：
      提交 1 个新的 issue：
      - [在 Ubuntu jammy 上 pytest 失败 #330](https://github.com/ruyisdk/ruyi/issues/330)
      RuyiSDK Eclipse Plugins 0.0.5 版本遗留 issue 如下：
      - 未配置 PATH 导致无法轻松访问 ruyi [ruyisdk/ruyisdk-eclipse-plugins#38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)
      - 下载完成不够明显 [ruyisdk/ruyisdk-eclipse-plugins#39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)

    - 资源
      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/8467b22a23a59e241786af4d6df247bc1abf223c)
      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/6094edd22648e2084a2367633401fc569b92cc16)

- ruyi 仓库提出 2 个 issue
  - [在 Ubuntu jammy 上 pytest 失败 #330](https://github.com/ruyisdk/ruyi/issues/330)
  - [ruyi refresh local packages-index before running any command #335](https://github.com/ruyisdk/ruyi/issues/335)

#### 1.2 RuyiSDK 测试工具开发

- ruyi-packaging 仓库提交 8 个 pr，为 packages-index 重新设计的打包工具，打包功能已经完成 90%，预计个工作周开始使用该工具生成 manifest
    - [riko: setup ruyi #18](https://github.com/ruyisdk/ruyi-packaging/pull/18)
    - [riko: load packages-index and config nvchecker #19](https://github.com/ruyisdk/ruyi-packaging/pull/19)
    - [riko: use nvchecker new_ver/old_ver features #20](https://github.com/ruyisdk/ruyi-packaging/pull/20)
    - [riko: support cmdline parsing #21](https://github.com/ruyisdk/ruyi-packaging/pull/21)
    - [workflow: check DCO on branch checker #22](https://github.com/ruyisdk/ruyi-packaging/pull/22)
    - [misc: do some misc works #23](https://github.com/ruyisdk/ruyi-packaging/pull/23)
    - [riko: subcommand list to print nvchecker results #24](https://github.com/ruyisdk/ruyi-packaging/pull/24)
    - [riko: now we can get raw toml from packaging scripts #25](https://github.com/ruyisdk/ruyi-packaging/pull/25)
- packages-index
  - packages-index 仓库提交 1 个 issue
  - [需要更新 milkv-duo-examples 包 #86](https://github.com/ruyisdk/packages-index/issues/86)
  -  [board-image/arduino-milkv-{duo,duo256m}-sd: add version 1.1.2 and 1.1.4 #88](https://github.com/ruyisdk/packages-index/pull/88)
  - [Add missing versions and reformat old tomls for RevyOS LicheePi 4A #89](https://github.com/ruyisdk/packages-index/pull/89)
  - [board-image/revyos-milkv-pioneer: add missing versions and update upstream_versions #90](https://github.com/ruyisdk/packages-index/pull/90)
  - [RevyOS MilkV Meles: add missing versions and reformat some old versions #91](https://github.com/ruyisdk/packages-index/pull/91)
  - [workflows: test manifests with format-manifest #92](https://github.com/ruyisdk/packages-index/pull/92)
  - [board-image/\*: reformat old tomls by format-manifest #93](https://github.com/ruyisdk/packages-index/pull/93)
  - [board-image/\*: add missing upstream_version data #94](https://github.com/ruyisdk/packages-index/pull/94)
  - [ruyisdk-test/packages-index/#6](https://github.com/ruyisdk-test/packages-index/pull/6) Add missing RevyOS uboot images for Milk-V Meles
  - [ruyisdk-test/packages-index/#7](https://github.com/ruyisdk-test/packages-index/pull/7) Add missing and remove duplicate RevyOS uboot images for lpi4a
  - [ruyisdk-test/packages-index/#8](https://github.com/ruyisdk-test/packages-index/pull/8) Add missing RevyOS uboot images for lcon4a
  - [ruyisdk-test/packages-index/#9](https://github.com/ruyisdk-test/packages-index/pull/9) Add missing Milk-V Duo Arduino images
- Ruyi 在 Ubuntu Launchpad 进行新版本的实验性打包 [仓库](https://launchpad.net/~weilinfox/+archive/ubuntu/ruyi/+build/31008991)（后将改用新仓库用于正式发布）

#### 1.3 RuyiSDK网站

- [New CodeBlock for documentation #164](https://github.com/ruyisdk/ruyisdk-website/pull/164)
- [第一部分考核题作答 #165](https://github.com/ruyisdk/ruyisdk-website/pull/165)（重新分为多个 pr 合并）
- [Task02 #166](https://github.com/ruyisdk/ruyisdk-website/pull/166)（由其他 pr 合并）
- [chore: add Prettier configuration and plugins to project #169](https://github.com/ruyisdk/ruyisdk-website/pull/169)
- [docs: update the English version for case7 #171](https://github.com/ruyisdk/ruyisdk-website/pull/171)
- [mv files into appropriate location #183](https://github.com/ruyisdk/ruyisdk-website/pull/183)
- [Add toggle for main copy button #184](https://github.com/ruyisdk/ruyisdk-website/pull/184)
- [update the newcase #185](https://github.com/ruyisdk/ruyisdk-website/pull/185)
- [Add footer link and translations for ruyi community #167](https://github.com/ruyisdk/ruyisdk-website/pull/167)
- [Homepage finetune #172](https://github.com/ruyisdk/ruyisdk-website/pull/173)
- [Update 'de' documentations for new CodeBlock #173](https://github.com/ruyisdk/ruyisdk-website/pull/173)
- [Fix issue #163](https://github.com/ruyisdk/ruyisdk-website/pull/174)
- [Making Maindisplay display elegantly on XL screens #175](https://github.com/ruyisdk/ruyisdk-website/pull/175)
- [Fix/wechat qqgroup styling #177](https://github.com/ruyisdk/ruyisdk-website/pull/177)
- [Fix/homepage revyos links #179](https://github.com/ruyisdk/ruyisdk-website/pull/179)
- [Feat/custom footer style #180](https://github.com/ruyisdk/ruyisdk-website/pull/180)
- [Feat/static page #181](https://github.com/ruyisdk/ruyisdk-website/pull/181)
- [Feat/custom footer style #182](https://github.com/ruyisdk/ruyisdk-website/pull/182)
- [pages: fix index header spaces #158](https://github.com/ruyisdk/ruyisdk-website/pull/158)
- [pages: change index community page to ruyisdk.org #168](https://github.com/ruyisdk/ruyisdk-website/pull/168)
- [docs: add milkv-duo-examples tips #170](https://github.com/ruyisdk/ruyisdk-website/pull/170)
- [pages: modify copyright info #176](https://github.com/ruyisdk/ruyisdk-website/pull/176)
- [pages: update community page translations #186](https://github.com/ruyisdk/ruyisdk-website/pull/186)
- https://github.com/ruyisdk/ruyisdk-website/pull/164
  - New CodeBlock with following features:
  - Syntax highlighting
  - Filtering command for bash script copying
  - Support light/dark theme
- https://github.com/ruyisdk/ruyisdk-website/pull/173
  Update 'de' language documentations for new CodeBlock
- https://github.com/ruyisdk/ruyisdk-website/pull/184
  - Allow using prop "showTitleCopyButton" to control the toggle of main copy button.
- https://github.com/ruyisdk/ruyisdk-website/pull/167
  - Add footer link and translations for ruyi community 
- https://github.com/ruyisdk/ruyisdk-website/pull/172
  - Unify the component spacings
  - Fine-tune the homepage components for widescreen devices
- https://github.com/ruyisdk/ruyisdk-website/pull/174
  - Fix issue #163, Improve the statistics layout for better handling numbers in short bars
- https://github.com/ruyisdk/ruyisdk-website/pull/175
  - Now MainDisplay use a better scaling method to scale and display elegantly on extreme large screens.

#### 1.4 RuyiSDK文档

- [Add milkv-duo-examples tips #88](https://github.com/ruyisdk/docs/pull/88)

- 使用 Ruyi 建立 milkv-duo-examples 的运行环境 [envsetup.sh](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/envsetup.sh)

#### 1.5 RuyiSDK技术分享

- 香港海报 《RuyiSDK A Unified and Extensible Platform for RISC-V Ecosystem Development》 之 Extended Abstract [V3](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/RuyiSDK%20-%20A%20Unified%20and%20Extensible%20Platform_2P_V3.pdf) [V4](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/RuyiSDK%20-%20A%20Unified%20and%20Extensible%20Platform_2P_V4.pdf)
- 香港海报 《RuyiSDK A Unified and Extensible Platform for RISC-V Ecosystem Development》 [PDF](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/RuyiSDK_A_Unified_and_Extensible_Platform_for_RISC_V_Ecosystem_Development.pdf)
 
#### 1.6 RuyiSDK 实习生面试

- J154 新实习生面试，[考核题](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/vdx_面试考核.md)
  
### 2. 操作系统支持矩阵

#### 2.1 开发板操作系统支持测试

- [DuoS: Dump Debian](https://github.com/ruyisdk/support-matrix/pull/343)
- [LiP4A: Dump Slackware (basic->good)](https://github.com/ruyisdk/support-matrix/pull/344)
- [Tests bump (for Pine64 Star64 and more)](https://github.com/ruyisdk/support-matrix/pull/342)
- [Boards: clean metadata, remove test enviroment, test results. ](https://github.com/ruyisdk/support-matrix/pull/345)
- [Dump RT-Thread@DuoS: 5.2.0->5.2.1](https://github.com/ruyisdk/support-matrix/pull/346)
- [fix dead link for deepin](https://github.com/ruyisdk/support-matrix/pull/347)
- [metadata: use vendor to mark board manufacturer](https://github.com/ruyisdk/support-matrix/pull/348)
- [LicheePi4A: Add openEuler RISC-V 24.03 LTS-SP2 test report (good).](https://github.com/ruyisdk/support-matrix/pull/349)
- [meles: revyos 20250526](https://github.com/ruyisdk/support-matrix/pull/341)  
- 测试了 openEuler RISC-V 24.03 LTS-SP2
  - <https://github.com/ruyisdk/support-matrix/pull/349>
- [metadata: use vendor to mark board manufacturer](https://github.com/ruyisdk/support-matrix/pull/348)
  - remove [boards]/README.md metadata: board_variant,cpu_arch
  - remove [boards]/README(_zh).md test enviroment and test results
  - fix metadata_check.py CI
  - remove arch mapper in metadata.yml
  - update contributing and template
- [Boards: clean metadata, remove test enviroment, test results. ](https://github.com/ruyisdk/support-matrix/pull/345)
  - [boards]/README.md metadata: vendor to mark board manufacturer
  - CI: remove vendor check
  - duo/ThreadX: merge blink.md to README.md
  - CI: update svg status color from frontend,reflactor generate svg code
- https://github.com/ruyisdk/support-matrix/pull/346
- https://github.com/ruyisdk/support-matrix/pull/344
- https://github.com/ruyisdk/support-matrix/pull/343
- https://github.com/ruyisdk/support-matrix/pull/339
- https://github.com/ruyisdk/support-matrix/pull/347
- https://github.com/ruyisdk/support-matrix/pull/340
- 验证 LiP4A + OpenEuler 25.03
[PR](https://github.com/ruyisdk/support-matrix/pull/342)
主要进行了 Pine64 Star64 的测试。
  新增 6 篇：
  - Ubuntu @ Sipeed LicheeRV Nano
  - NetBSD @ MangoPi MQ Pro
  - Deepin @ Pine64 Star64
  - irradium @ Pine64 Star64
  - NetBSD @ Pine64 Star64
  - NuttX @ Pine64 Star64
  更新 2 篇：
  - DietPi @ Pine64 Star64 (CFH -> Basic)
  - Yocto @ Pine64 Star64 (CFH -> Basic)
  - 其他现有文档的 typo 修复

#### 2.2 操作系统支持矩阵Web UI

- 合并 6 月代码修改到主线
- 统一支持状态的颜色定义到 site.ts
- 重构 Overview 代码,修复了网页首次打开排序失效的问题 [#5](https://github.com/QA-Team-lo/support-matrix-frontend/issues/5)
- 更新测试报告页标题
- 制作了在手机端适用的汉堡菜单替代 Header
- 重构 Header,[修复 Logo 跳转问题](https://github.com/QA-Team-lo/support-matrix-frontend/issues/4),添加 Ruyi 相关链接.
- 更新 Copyright
- 增加和修复 I18n
- 根据 RISC-V style guide 设计了一套完整带暗色的网站主题颜色并应用
- 网站统一为 OpenSans 字体
- 调整网站整体圆角,缩短 Header Logo 名称
- 更新依赖,适配新的 radix-ui 破坏性更新
- [修复默认主题](https://github.com/QA-Team-lo/support-matrix-frontend/issues/6),引入全局状态管理,实现在整个网站浏览和切换语言时都遵循用户主题设置.
- 网站添加多语言 sitemap 支持,在构建时生成,更新语言设置至 ISO 标准
- 代码重构,bug 修复等
- 网站新界面与功能设计
- [网站默认排序与下拉菜单不符](https://github.com/QA-Team-lo/support-matrix-frontend/issues/6)
- [默认没有跟随系统亮色/暗色设置](https://github.com/QA-Team-lo/support-matrix-frontend/issues/6)

#### 2.3 ruyisdk.cn操作系统支持矩阵板块

- [在香蕉派 BPI-F3 运行 openKylin 2.0 SP1 与常用软件测试](https://ruyisdk.cn/t/topic/608)
- [RISC-V 开发板和操作系统支持矩阵网站功能介绍](https://ruyisdk.cn/t/topic/856)
- [RISC-V 开发板和操作系统支持矩阵网站开发规划与建议征求](https://ruyisdk.cn/t/topic/880)
- [postmarketOS 的风还是吹到了 RISC-V](https://ruyisdk.cn/t/topic/465/4)
- [RISC-V MCU 漫游 (1)：CH32V 系列](https://ruyisdk.cn/t/topic/722/1)
- [RISC-V MCU 漫游 (2)：GD32VF103](https://ruyisdk.cn/t/topic/893/1)
- [irradium on Pine64 Star64](https://ruyisdk.cn/t/topic/418/17)
  Rephrase
  使用 DeepL 直接翻译和改进文本
  点击图标打开高级模式窗口。在该窗口中，你可以进行编辑并比较版本。
- https://ruyisdk.cn/t/topic/477/2
- https://ruyisdk.cn/t/topic/667/3
- https://ruyisdk.cn/t/topic/753
- https://ruyisdk.cn/t/topic/840/2
- <https://ruyisdk.cn/t/topic/593>
- <https://ruyisdk.cn/t/topic/777>

#### 2.4 会议和技术分享

- https://github.com/ruyisdk/wechat-articles/pull/165
- https://github.com/ruyisdk/wechat-articles/pull/169
- [20250724](https://docs.google.com/presentation/d/1Y0mr96fJ8aTGZcDXtqdX83IyBsbEJfhWdrZAUteftt8/edit?slide=id.g327cde8f41c_0_0#slide=id.g327cde8f41c_0_0) 东亚双周会主持

#### 2.5 操作系统支持矩阵设备维护

- Infra/已毕业实习生
    - 公钥清理
    - 计算资源释放

### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- SAIL
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1110> Add csr_name_map and is_CSR_defined for H_ext registers
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1122> Add support for local counter-overflow interrupts
  - \[PR\] <https://github.com/rems-project/sail/pull/1375> Support formatting sail code via stdin
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1146> Decouple callbacks impl from model by introducing callback interface
  - Sail 编译器插件，将 Sail 语法树输出为 json <https://github.com/trdthg/sail-json-plugin>
  - [#1167](https://github.com/riscv/sail-riscv/pull/1167): 修复 Sail-RISCV V 扩展NISTYPE/NITYPE指令错误接收了有符号数的Bug
  - [#1166](https://github.com/riscv/sail-riscv/pull/1166): 优化Sail-RISCV V扩展代码结构, 避免不支持vmask的指令实现中的冗余函数调用
  - [#1138](https://github.com/riscv/sail-riscv/pull/1138): 优化Sail-RISCV 代码结构,统一由指令进行操作的内存宽度界定变量的命名
  - [#1108](https://github.com/riscv/sail-riscv/pull/1108): 跟踪上月提交PR, 已经合并, 解决了Sail-RISCV C 扩展的浮点数操作需要使用 cregidx 来代表浮点数从而造成混淆的问题
  - [#1131](https://github.com/riscv/sail-riscv/pull/1131): 为保证模型验证的可复现性,同时减少运行平台依赖性,将Sail-RISCV的随机数生成从`/dev/random`中截取改为C++实现
  - [#601](https://github.com/riscv/sail-riscv/pull/601): rebase 对 Smepmp的支持, 同时适配对Sail-RISCV的模型可配置接口
  - [AUR sail-model](https://aur.archlinux.org/packages/sail-model)
  - [sail_config.c: Add cJSON error message output.](https://github.com/rems-project/sail/pull/1388)
  - [config: add template rvd.json.in to generate config](https://github.com/riscv/sail-riscv/pull/1151)
  - [Validate JSON config file with schema](https://github.com/riscv/sail-riscv/pull/1161)
  - [Add DYN (Position-Independent Executable file) support](https://github.com/riscv/sail-riscv/pull/1171)
  - [riscv_sim.cpp: add SIGINT processor.](https://github.com/riscv/sail-riscv/pull/1172)
  - [valijson](https://github.com/riscv/sail-riscv/pull/1173)
  - [Bump cJSON version.](https://github.com/rems-project/sail/pull/1389)

- ACT
  - 提交了一个修复vclmul和vclmulh 测试用例ISA问题的pr[#688](https://github.com/riscv-non-isa/riscv-arch-test/pull/688)
  - 提交了更详细的readme说明文档[#676](https://github.com/riscv-non-isa/riscv-arch-test/pull/676)
  - 提交了一个将CTG生成的数据从10进制更改为16进制的pr[#680](https://github.com/riscv-non-isa/riscv-arch-test/pull/680)
  - 提交了一个同步ACT与RISCOF仓库中spike与sail插件的一个pr[#142](https://github.com/riscv-software-src/riscof/pull/142)
  - 更新了添加RV32测试用例的pr,添加了fsub测试用例[#638](https://github.com/riscv-non-isa/riscv-arch-test/pull/638)

  | 测试用例名 | 所属拓展 | 更新测试用例数 | 地址                                                         |
  | ---------- | -------- | -------------- | ------------------------------------------------------------ |
  | fadd-b11   | zfinx    | 5              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | fsub-b11   | zfinx    | 5              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | vclmul.vv  | Zvk      | 1              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | vclmul.vx  | Zvk      | 1              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | vclmulh.vv | Zvk      | 1              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | vclmulh.vx | Zvk      | 1              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |

- spike
  - \[PR\] <https://github.com/riscv-software-src/riscv-isa-sim/pull/2036> Fix pmpaddr read

- Issues
  - [#1162](https://github.com/riscv/sail-riscv/issues/1162): 针对Smepmp扩展rebase 过程中出现的问题引发讨论, Sail-RISCV 目前可能需要重构初始化部分以保证相互依赖的扩展相关的CSR可以被正确设置
  - [sail cannot be removed](https://github.com/rems-project/sail/issues/1401)
  - [Is there a good reason why some of our external libs are fetched dynamically and some are just part of the repo? We have softfloat and are about to add CLI11 as well now as part of the repo.](https://github.com/riscv/sail-riscv/issues/1164)
  - [Add AUR package for sail bin](https://github.com/rems-project/sail/issues/1381)
  - [where does this binnary c_emulator/reset_vec.bin came from?](https://github.com/riscv/sail-riscv/issues/1154)
  - [openSBI with sail-riscv](https://github.com/riscv/sail-riscv/issues/886)
  - 提交了一个关于ACT与RISCOF仓库插件同步的issue[#671](https://github.com/riscv-non-isa/riscv-arch-test/issues/671)
  
#### 3.2 SAIL技术分享
  
- Pydrofoil 01: PyPy meta-tracing JIT [PPT](https://github.com/trdthg/plct/blob/main/doc/pydrofoil/pypy_ppt/main.pdf)
- RISC-V RVFI-DII 验证协议介绍 [PPT](https://github.com/trdthg/plct/blob/main/doc/sail/rvfi_dii_ppt/main.pdf)
- An MLIR-based acceleration method for RISC-V ISA simulator generated by Sail [Poster](https://github.com/trdthg/plct/blob/main/doc/sail/na_poster/main.pdf)
- tech-golden-model meeting [`07.07`, `07.15`, `07.21`, `07.28`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- [数字信号处理](https://github.com/Arielfoever/Work-PLCT/tree/master/report/数字信号处理.pdf)

#### 3.3 SAIL会议

- 参加了每周的SAIL会议并写了会议纪要
- 参加了7月29日的ACT会议并写了会议纪要[MD](https://github.com/Pagerd/PLCT/tree/main/Report/week/week90/ACT.md)
- 参加了7月14日的ACT会议并写了会议纪要[MD](https://github.com/Pagerd/PLCT/tree/main/Report/week/week88/ACT.md)
- 建议创建预发布版本或测试版本，并加入 CI 自动发布预发布版本。
  - 选择了 valijson + nlohmann/json, 已经提交了两种方案, 分别使用 FetchContent 和直接 push 库源代码, Tim 建议直接推源代码, 认为会更简洁, 尽管可能导致难以审查.
  - 结论, 最终目标是 sail 自动生成 C 代码的验证函数, 但当前的折中方案是用 Boon
  - 建议 CLI 改进, 需要修复 --trace 选项
  - 提到 ELF 文件动态加载, 目前难以确定偏移量, 需要检查 ELF 是否位置无关
    - Tim 建议使用 Elfio 库代替 sail 目前的 elf 处理代码.
  - 提到 cJSON 版本老旧, Alasdair 解释为了实现任意精度整数, sail 的 cJSON 代码被修改过, 将所有的数字都视为字符串解析
  - 建议用看板或者里程碑等工具跟踪发布进度. Prashanth 后续研究

### 4. 独立测试项目/应用软件生态观测

#### 4.1 RuyiSDK GNU Tests

- [D1 GCC 16](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/commit/ee2e5312d6935923eb88156f24a4629fc4058bac)
- [Fix symlink](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/commit/07aa03a2fb0b162aa3aed2f3427f59a1078bd73e)
- [Edit ruyi version](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/commit/7c8b64d516a5584bf17e31c5516679fc4eace7b7)
- [commit](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/commit/394047442f0dba7ef72e9d2e5c2e8c84be5b8eda)
  - 测试了 CanMV K230 上的 gnu-plct (GCC 16) 工具链可用性
  - 测试了 SpacemiT K1 上的 gnu-plct (GCC 16) 工具链可用性

#### 4.2 玄铁课程

- RISC-V 中国峰会 RV 学院试讲 ppt [未使用玄铁模板的版本](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/玩转RISC-V开发板，从RuyiSDK开始.pdf)
- RVSC 现场 RV 学院试讲
- 0725 RISCV Infra [PPT](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/玄铁_x_PLCT_联合课程_RISC_V_中国峰会主场前_1_天.pdf)
- 提交玄铁课程《在 K230 开发板进行 AI 识别应用开发》初稿
- [在Licheepi 4A上运行Deepseek]((https://github.com/Pagerd/PLCT/blob/main/Report/25-June/runningDeepseek.pptx))

#### 4.3 英麒 RISC-V Lab

- 部署展厅，上线30台Licheepi
- 布置展厅展示牌
- 配合调试维护实验室的Licheepi 4A
 
### 5. RISC-V教育和短视频

#### 5.1 短视频课程设计

- 项目迭代计划

https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Plan_Document

- 项目迭代回溯

https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Review_Document
  
#### 5.2 短视频设计和实现

- [Milk-V Duo RuyiSDK 使用厂商发布的二进制工具链构建](https://www.bilibili.com/video/BV12887zDEbD/)
- [Licheepi 4A RuyiSDK实际案例环境配置以及编译coremark](https://www.bilibili.com/video/BV1i8gBzkE4L/)
- [在 Licheepi 4A 上基于 ROS2 框架的实际开发](https://www.bilibili.com/video/BV1CouFz2EeR/)
- [LicheePi 4A RuyiSDK 环境部署](https://www.bilibili.com/video/BV11VGnz7ENg/)
- [荔枝派4A ruyisdk环境部署](https://www.bilibili.com/video/BV12k36zKE2u)

#### 5.3 短视频剧本和文档、素材

- [milkv duo部署ubuntu](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/Milk-V%20Duo%20256m%20Ubuntu%20%E7%B3%BB%E7%BB%9F%E6%9E%84%E5%BB%BA%E4%B8%8E%E8%BF%90%E8%A1%8C.md)
- [RuyiSDK实际案例环境配置以及编译coremark，基于Licheepi 4A](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/%E4%BD%BF%E7%94%A8%20Ruyi%20%E7%BC%96%E8%AF%91%E7%8E%AF%E5%A2%83%E6%9E%84%E5%BB%BA%EF%BC%88%E4%BB%A5%20Licheepi%204A%20%E4%B8%BA%E4%BE%8B%EF%BC%89%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3.md)
- [荔枝派4A ruyisdk环境部署](https://github.com/jason-hue/plct/blob/main/%E5%8F%A3%E6%92%AD%E7%A8%BF/LicheePi%204A%20RuyiSDK%20%E7%8E%AF%E5%A2%83%E9%83%A8%E7%BD%B2%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- 荔枝派4A ros2实际开发](https://github.com/jason-hue/plct/blob/main/%E5%8F%A3%E6%92%AD%E7%A8%BF/%E5%9F%BA%E4%BA%8EROS2%E7%9A%84%E5%AE%9E%E9%99%85%E5%BC%80%E5%8F%91%E7%A4%BA%E4%BE%8B.md)
- [RuyiSDK实际案例环境配置以及编译coremark，基于Licheepi 4A](https://github.com/jason-hue/plct/blob/main/%E5%8F%A3%E6%92%AD%E7%A8%BF/%E4%BD%BF%E7%94%A8%20Ruyi%20%E7%BC%96%E8%AF%91%E7%8E%AF%E5%A2%83%E6%9E%84%E5%BB%BA%EF%BC%88%E4%BB%A5%20Licheepi%204A%20%E4%B8%BA%E4%BE%8B%EF%BC%89%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- (RuyiSDK使用厂商提供的工具链编译实际案例（milkv duo为例）](https://github.com/jason-hue/plct/blob/main/%E5%8F%A3%E6%92%AD%E7%A8%BF/RuyiSDK%E4%BD%BF%E7%94%A8%E5%8E%82%E5%95%86%E6%8F%90%E4%BE%9B%E7%9A%84%E5%B7%A5%E5%85%B7%E9%93%BE%E7%BC%96%E8%AF%91%E5%AE%9E%E9%99%85%E6%A1%88%E4%BE%8B%EF%BC%88milkv%20duo%E4%B8%BA%E4%BE%8B%EF%BC%89%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- [在 Licheepi 4A 上基于 ROS2 框架的实际开发](https://github.com/lalafua/recording/blob/main/riscv/ros2/tutorial/first.md）

#### 5.4 短视频技术分享

- [完成稿件](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/AStandardizedQualitySelectionandSystematicReconstructionApproachforRISC-VCourses.docx)
  
### 6. 职工

#### 6.1 蔡玮霖
- Ruyi v0.37.1 测试完成 [pr](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/76)
- Ruyi v0.38.1 测试完成 pr [!77](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/77)
- ruyi 仓库提出 2 个 issue
  - [在 Ubuntu jammy 上 pytest 失败 #330](https://github.com/ruyisdk/ruyi/issues/330)
  - [ruyi refresh local packages-index before running any command #335](https://github.com/ruyisdk/ruyi/issues/335)
- docs 仓库提交 1 个 pr
  - [Add milkv-duo-examples tips #88](https://github.com/ruyisdk/docs/pull/88)
- packages-index 仓库提交 1 个 issue
  - [需要更新 milkv-duo-examples 包 #86](https://github.com/ruyisdk/packages-index/issues/86)
- packages-index 仓库合作 2 个 pr
  - [board-image/arduino-milkv-{duo,duo256m}-sd: add version 1.1.2 and 1.1.4 #88](https://github.com/ruyisdk/packages-index/pull/88)
  - [Add missing versions and reformat old tomls for RevyOS LicheePi 4A #89](https://github.com/ruyisdk/packages-index/pull/89)
- packages-index 仓库提交 5 个 pr
  - [board-image/revyos-milkv-pioneer: add missing versions and update upstream_versions #90](https://github.com/ruyisdk/packages-index/pull/90)
  - [RevyOS MilkV Meles: add missing versions and reformat some old versions #91](https://github.com/ruyisdk/packages-index/pull/91)
  - [workflows: test manifests with format-manifest #92](https://github.com/ruyisdk/packages-index/pull/92)
  - [board-image/\*: reformat old tomls by format-manifest #93](https://github.com/ruyisdk/packages-index/pull/93)
  - [board-image/\*: add missing upstream_version data #94](https://github.com/ruyisdk/packages-index/pull/94)
- ruyisdk-website 仓库审核 8 个 pr
  - [New CodeBlock for documentation #164](https://github.com/ruyisdk/ruyisdk-website/pull/164)
  - [第一部分考核题作答 #165](https://github.com/ruyisdk/ruyisdk-website/pull/165)（重新分为多个 pr 合并）
  - [Task02 #166](https://github.com/ruyisdk/ruyisdk-website/pull/166)（由其他 pr 合并）
  - [chore: add Prettier configuration and plugins to project #169](https://github.com/ruyisdk/ruyisdk-website/pull/169)
  - [docs: update the English version for case7 #171](https://github.com/ruyisdk/ruyisdk-website/pull/171)
  - [mv files into appropriate location #183](https://github.com/ruyisdk/ruyisdk-website/pull/183)
  - [Add toggle for main copy button #184](https://github.com/ruyisdk/ruyisdk-website/pull/184)
  - [update the newcase #185](https://github.com/ruyisdk/ruyisdk-website/pull/185)
- ruyisdk-website 仓库合作 10 个 pr
  - [Add footer link and translations for ruyi community #167](https://github.com/ruyisdk/ruyisdk-website/pull/167)
  - [Homepage finetune #172](https://github.com/ruyisdk/ruyisdk-website/pull/173)
  - [Update 'de' documentations for new CodeBlock #173](https://github.com/ruyisdk/ruyisdk-website/pull/173)
  - [Fix issue #163](https://github.com/ruyisdk/ruyisdk-website/pull/174)
  - [Making Maindisplay display elegantly on XL screens #175](https://github.com/ruyisdk/ruyisdk-website/pull/175)
  - [Fix/wechat qqgroup styling #177](https://github.com/ruyisdk/ruyisdk-website/pull/177)
  - [Fix/homepage revyos links #179](https://github.com/ruyisdk/ruyisdk-website/pull/179)
  - [Feat/custom footer style #180](https://github.com/ruyisdk/ruyisdk-website/pull/180)
  - [Feat/static page #181](https://github.com/ruyisdk/ruyisdk-website/pull/181)
  - [Feat/custom footer style #182](https://github.com/ruyisdk/ruyisdk-website/pull/182)
- ruyisdk-website 仓库提交 5 个 pr
  - [pages: fix index header spaces #158](https://github.com/ruyisdk/ruyisdk-website/pull/158)
  - [pages: change index community page to ruyisdk.org #168](https://github.com/ruyisdk/ruyisdk-website/pull/168)
  - [docs: add milkv-duo-examples tips #170](https://github.com/ruyisdk/ruyisdk-website/pull/170)
  - [pages: modify copyright info #176](https://github.com/ruyisdk/ruyisdk-website/pull/176)
  - [pages: update community page translations #186](https://github.com/ruyisdk/ruyisdk-website/pull/186)
- ruyi-packaging 仓库提交 8 个 pr，为 packages-index 重新设计的打包工具，打包功能已经完成 90%，预计个工作周开始使用该工具生成 manifest
  - [riko: setup ruyi #18](https://github.com/ruyisdk/ruyi-packaging/pull/18)
  - [riko: load packages-index and config nvchecker #19](https://github.com/ruyisdk/ruyi-packaging/pull/19)
  - [riko: use nvchecker new_ver/old_ver features #20](https://github.com/ruyisdk/ruyi-packaging/pull/20)
  - [riko: support cmdline parsing #21](https://github.com/ruyisdk/ruyi-packaging/pull/21)
  - [workflow: check DCO on branch checker #22](https://github.com/ruyisdk/ruyi-packaging/pull/22)
  - [misc: do some misc works #23](https://github.com/ruyisdk/ruyi-packaging/pull/23)
  - [riko: subcommand list to print nvchecker results #24](https://github.com/ruyisdk/ruyi-packaging/pull/24)
  - [riko: now we can get raw toml from packaging scripts #25](https://github.com/ruyisdk/ruyi-packaging/pull/25)
- 香港海报 《RuyiSDK A Unified and Extensible Platform for RISC-V Ecosystem Development》 之 Extended Abstract [V3](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/RuyiSDK%20-%20A%20Unified%20and%20Extensible%20Platform_2P_V3.pdf) [V4](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/RuyiSDK%20-%20A%20Unified%20and%20Extensible%20Platform_2P_V4.pdf)
- 香港海报 《RuyiSDK A Unified and Extensible Platform for RISC-V Ecosystem Development》 [PDF](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/RuyiSDK_A_Unified_and_Extensible_Platform_for_RISC_V_Ecosystem_Development.pdf)
- RISC-V 中国峰会 RV 学院试讲 ppt [未使用玄铁模板的版本](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/玩转RISC-V开发板，从RuyiSDK开始.pdf)
- J154 新实习生面试，[考核题](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/vdx_面试考核.md)
- 使用 Ruyi 建立 milkv-duo-examples 的运行环境 [envsetup.sh](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/envsetup.sh)
- Ruyi 在 Ubuntu Launchpad 进行新版本的实验性打包 [仓库](https://launchpad.net/~weilinfox/+archive/ubuntu/ruyi/+build/31008991)（后将改用新仓库用于正式发布）
- RVSC 现场 RV 学院试讲
- 0725 RISCV Infra [PPT](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month25/玄铁_x_PLCT_联合课程_RISC_V_中国峰会主场前_1_天.pdf)

#### 6.2 郑景坤

##### 6.2.1 操作系统支持矩阵

- PR Review (对测试团队操作系统支持矩阵产出的review审核，以下内容同测试团队产出，此处为review)
  - [DuoS: Dump Debian](https://github.com/ruyisdk/support-matrix/pull/343)
  - [LiP4A: Dump Slackware (basic->good)](https://github.com/ruyisdk/support-matrix/pull/344)
  - [Tests bump (for Pine64 Star64 and more)](https://github.com/ruyisdk/support-matrix/pull/342)
  - [Boards: clean metadata, remove test enviroment, test results. ](https://github.com/ruyisdk/support-matrix/pull/345)
  - [Dump RT-Thread@DuoS: 5.2.0->5.2.1](https://github.com/ruyisdk/support-matrix/pull/346)
  - [fix dead link for deepin](https://github.com/ruyisdk/support-matrix/pull/347)
  - [metadata: use vendor to mark board manufacturer](https://github.com/ruyisdk/support-matrix/pull/348)
  - [LicheePi4A: Add openEuler RISC-V 24.03 LTS-SP2 test report (good).](https://github.com/ruyisdk/support-matrix/pull/349)
  - New PR
    - [meles: revyos 20250526](https://github.com/ruyisdk/support-matrix/pull/341)
  - Issue
    - 网页前端
        - [网站默认排序与下拉菜单不符](https://github.com/QA-Team-lo/support-matrix-frontend/issues/6)
        - [默认没有跟随系统亮色/暗色设置](https://github.com/QA-Team-lo/support-matrix-frontend/issues/6)

##### 6.2.2 RuyiSDK 双周报/支持矩阵部分

- https://github.com/ruyisdk/wechat-articles/pull/165
- https://github.com/ruyisdk/wechat-articles/pull/169

##### 6.2.3 独立测试项目/应用软件生态观测

- [D1 GCC 16](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/commit/ee2e5312d6935923eb88156f24a4629fc4058bac)
- [Fix symlink](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/commit/07aa03a2fb0b162aa3aed2f3427f59a1078bd73e)
- [Edit ruyi version](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/commit/7c8b64d516a5584bf17e31c5516679fc4eace7b7)

##### 6.2.4 Infra

- Infra/已毕业实习生
    - 公钥清理
    - 计算资源释放

##### 6.2.5 会议

- [20250724](https://docs.google.com/presentation/d/1Y0mr96fJ8aTGZcDXtqdX83IyBsbEJfhWdrZAUteftt8/edit?slide=id.g327cde8f41c_0_0#slide=id.g327cde8f41c_0_0) 东亚双周会主持

##### 6.2.6 RevyOS 小队

（仅包含可公开部分。）

- PR Review
    - [feat(project): beautify the projects page and add some revyos projects](https://github.com/revyos/docs/pull/54)
    - [feat(projects): add more project](https://github.com/revyos/docs/pull/56)
    - [fix(projects): update description for TH1520 U-Boot project](https://github.com/revyos/docs/pull/57)
    - [fix(imagelink): update milkv pioneer image version to 20250703](https://github.com/revyos/docs/pull/58)
    - [fix docs error](https://github.com/revyos/docs/pull/62)
- [20250710 东亚双周会](https://docs.google.com/presentation/d/1huYCnf3TGJkY6iqMFutoQvg8QqD4b2TyjAEtBMdLgb8/edit?slide=id.g36afb8f9799_13_0#slide=id.g36afb8f9799_13_0)
- [20250717 RVI Dev Board Meeting](https://lf-riscv.atlassian.net/wiki/spaces/DBXX/pages/672399362/2025-07-17+Meeting+Notes) 同步 RevyOS ROCm 进展
- GCC 14.2 + XThead matrix coremark retest
    - 提供数据，文档由实习生提交：https://github.com/revyos/docs/pull/48/commits/86a375945e9d99dcfdb94258b545054d7318b1e3

#### 6.3 阎明铸

##### 6.3.1 sail/act

- sail
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1110> Add csr_name_map and is_CSR_defined for H_ext registers
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1122> Add support for local counter-overflow interrupts
  - \[PR\] <https://github.com/rems-project/sail/pull/1375> Support formatting sail code via stdin
  - \[PR\] <https://github.com/riscv/sail-riscv/pull/1146> Decouple callbacks impl from model by introducing callback interface
  - Sail 编译器插件，将 Sail 语法树输出为 json <https://github.com/trdthg/sail-json-plugin>

- spike
  - \[PR\] <https://github.com/riscv-software-src/riscv-isa-sim/pull/2036> Fix pmpaddr read

##### 6.3.2 会议/技术分享

- tech-golden-model meeting和会议记录（每周）
- Pydrofoil 01: PyPy meta-tracing JIT [PPT](https://github.com/trdthg/plct/blob/main/doc/pydrofoil/pypy_ppt/main.pdf)
- RISC-V RVFI-DII 验证协议介绍 [PPT](https://github.com/trdthg/plct/blob/main/doc/sail/rvfi_dii_ppt/main.pdf)
- An MLIR-based acceleration method for RISC-V ISA simulator generated by Sail [Poster](https://github.com/trdthg/plct/blob/main/doc/sail/na_poster/main.pdf)
- tech-golden-model meeting [`07.07`, `07.15`, `07.21`, `07.28`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)

#### 6.4 张馥媛

##### 6.4.1 视频

- [Milk-V Duo RuyiSDK使用厂商发布的二进制工具链构建](https://www.bilibili.com/video/BV12887zDEbD/)
- [Licheepi 4A RuyiSDK实际案例环境配置以及编译coremark](https://www.bilibili.com/video/BV1i8gBzkE4L/)
- [在 Licheepi 4A 上基于 ROS2 框架的实际开发](https://www.bilibili.com/video/BV1CouFz2EeR/)
- [LicheePi 4A RuyiSDK 环境部署](https://www.bilibili.com/video/BV11VGnz7ENg/)

##### 6.4.2 项目计划

- 项目迭代计划：
https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Plan_Document

- 项目迭代回溯：
https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Review_Document

##### 6.4.3 玄铁课程

- 提交玄铁课程《在 K230 开发板进行 AI 识别应用开发》初稿

##### 6.4.4 英麒RISC-V Lab

- 部署展厅，上线30台Licheepi
- 布置展厅展示牌
- 配合调试维护实验室的Licheepi 4A

##### 6.4.5 北美峰会投稿

- [完成稿件 未提交](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/AStandardizedQualitySelectionandSystematicReconstructionApproachforRISC-VCourses.docx)

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

- [[PATCH v3 0/3] riscv: dts: sophgo: add more sg2042 isa extension support][lk-sg204x-3]
- [[PATCH v3 0/3] Add Sophgo EVB V1/V2 Board support][lk-sg204x-2]
- [[PATCH v4 0/4] spi: sophgo: Add SPI NOR controller for SG2042][lk-sg204x-1]

[lk-sg204x-1]: https://lore.kernel.org/linux-riscv/20250720-sfg-spifmc-v4-0-033188ad801e@gmail.com/
[lk-sg204x-2]: https://lore.kernel.org/linux-riscv/cover.1751700954.git.rabenda.cn@gmail.com/
[lk-sg204x-3]: https://lore.kernel.org/linux-riscv/cover.1751698574.git.rabenda.cn@gmail.com/

## Milk-V Duo Upstream

- [[PATCH v2 0/2] remoteproc: cv1800b: Add initial support for C906L processor][lk-cv18xx-1]

[lk-cv18xx-1]: https://lore.kernel.org/linux-riscv/20250728-cv1800-rproc-v2-0-5bbee4abe9dc@pigmoral.tech/

## Canaan K230 Upstream

- [[PATCH v7 0/3] riscv: canaan: Add support for K230 clock][lk-k230-1]

[lk-k230-1]: https://lore.kernel.org/linux-riscv/20250730-b4-k230-clk-v7-0-c57d3bb593d3@zohomail.com/

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
