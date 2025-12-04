# PLCT 开源进展·第 76 期·2025 年 11 月汇总

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
- https://github.com/openjdk/jdk/pull/27445 (8368366: RISC-V: AlignVector is mistakenly set to AvoidUnalignedAccesses)
- https://github.com/openjdk/loom/pull/222 (RISC-V: Allow virtual thread preemption on some common class initialization paths)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/27138 (8367066: RISC-V: refine register selection in MacroAssembler::decode_klass_not_null)
- https://github.com/openjdk/jdk/pull/27134 (8367048: RISC-V: Correct pipeline descriptions of the architecture)
- https://github.com/openjdk/jdk/pull/27142 (8367098: RISC-V: sync CPU features with related JVM flags for dependant ones)
- https://github.com/openjdk/jdk/pull/27155 (8367137: RISC-V: Detect Zicboz block size via hwprobe)
- https://github.com/openjdk/jdk/pull/27181 (8367293: RISC-V: enable vectorapi test for VectorMask.laneIsSet)
- https://github.com/openjdk/jdk/pull/27152 (8367103: RISC-V: store cpu features in a bitmap)
- https://github.com/openjdk/jdk/pull/27277 (8367616: RISC-V: Auto-enable Zicboz extension for debug builds)
- https://github.com/openjdk/jdk/pull/27228 (8367532: Declare all stubgen stub entries including internal cross-stub entries)
- https://github.com/openjdk/jdk/pull/27409 (8368180: RISC-V: Remove redundant ext_Zicboz.enable_feature())
- https://github.com/openjdk/jdk/pull/27414 (8368206: RISC-V: compiler/vectorapi/VectorMaskCompareNotTest.java fails when running without RVV)
- https://github.com/openjdk/jdk/pull/27420 (8368247: RISC-V: enable vectorapi test for expand operation)
- https://github.com/openjdk/jdk/pull/27448 (8365191: Cleanup after removing LockingMode related code)
- https://github.com/openjdk/jdk/pull/27467 (8367692: RISC-V: Align post call nop)
- https://github.com/openjdk/jdk/pull/27171 (8367253: RISC-V: refactor dependent cpu extensions)

## Go

## OpenCV

## GNU Toolchain

## LLVM Team
- Upstream llvm-project 合并的patch:
  - [[DAG] Update canCreateUndefOrPoison to handle ISD::VECTOR_COMPRESS](https://github.com/llvm/llvm-project/pull/168010)
  - [[DAG] Add generic m_TernaryOp() / m_c_TernaryOp() matchers](https://github.com/llvm/llvm-project/pull/165520)
  - [[LLDB][DWARF] Use the same qualified name computation for Rust](https://github.com/llvm/llvm-project/pull/165840)
  - [[LLDB][Editline] empty current line before el_wgets](https://github.com/llvm/llvm-project/pull/165830)
  - [RISCV] Intrinsic Support for XCVelw: https://github.com/llvm/llvm-project/pull/129168
  - [DAGCombiner] Bail out if BitWidthDiff > BitWidth when folding cltz(and) - BitWidthDiff: https://github.com/llvm/llvm-project/pull/166607
  - [WebAssembly][FastISel] Bail out on meeting non-integer type in selectTrunc: https://github.com/llvm/llvm-project/pull/167165
  - [WebAssembly] Truncate extra bits of large elements in BUILD_VECTOR: https://github.com/llvm/llvm-project/pull/167223
  - [GISel][RISCV] Compute CTPOP of small odd-sized integer correctly: https://github.com/llvm/llvm-project/pull/168559
  - [DAGCombiner] Don't optimize insert_vector_elt into shuffle if implicit truncation exists: https://github.com/llvm/llvm-project/pull/169022
  - [Clang] Generalize interp__builtin_ia32_shuffle_generic to handle single op permute shuffles. https://github.com/llvm/llvm-project/pull/167236

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

- 修正拼写错误。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009041.html)
- 修正lib/utils/irqchip/plic.c中从plic\_data结构体中获取context\_id的类型问题。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009042.html)
- fdt预留空间，防止u-boot崩溃。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009043.html)
- ariane/openpiton修改硬编码的代码改为从dt获取初始化信息。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009053.html)[2](https://lists.infradead.org/pipermail/opensbi/2025-November/009054.html)
- 修正sbi_pmu抑制标志的配置。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009068.html)
- 修正Makefile只在V=1时打印移除section信息。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009071.html)
- 添加EIC7700支持。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009074.html)
- 添加SiFive的cache驱动。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009091.html)
- 添加运行时栈overrun检测。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009130.html)
- 修正S模式MMIO的权限检测。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009137.html)
- 修正K1的Makefile修正丢失的目标文件。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009144.html)
- 在异常处理访问低特权等级内存时有一个异常处理程序记录异常信息，添加代码清除MPRV。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009146.html)
- HART保护抽象，为将来添加更多保护机制做准备。[1](https://lists.infradead.org/pipermail/opensbi/2025-November/009154.html)

# edk2

- 修正RISC-V PlatformSecLib缺少库。[1](https://github.com/tianocore/edk2-platforms/pull/909)
- 修正RISC-V下一些平台的代码，适配库的变化。[1](https://github.com/tianocore/edk2-platforms/pull/910)
- RISC-V下非对齐内存访问支持。[1](https://github.com/tianocore/edk2/pull/11809)

## u-boot

本期没有新的进展。

## RevyOS (Debian for Xuantie)

### Debian

## RT-Thread

## PLCT罗云翔测试团队

（包含 SAIL 和 ACT 测试部分）

1. RuyiSDK 多版本测试与生态完善
- 版本测试：完成了 RuyiSDK v0.43.0-beta.20251118 版本在多个操作系统（包括 LicheePi4A、RevyOS、ArchLinux、Debian、Deepin、Fedora、Ubuntu、openEuler 等）和架构（x86_64、riscv64、aarch64）下的全面测试，并发布了详细测试报告。修复了多个遗留缺陷，提升了软件稳定性。
- 工具开发与增强：
  - 在 `packages-index` 提交了6个PR，修复镜像URL、更新多款开发板镜像至最新版本，并新增了对 Laptop 4A 的官方支持。
  - 在 `ruyi-packaging` 提交了4个PR，优化了RevyOS系列包的生成格式和供应商信息。
- 网站与文档优化：
  - 网站前端实现了新闻更新、代码块功能增强、移动端布局优化、多语言翻译更新。
  - 文档站点修复了安装指南、Fastboot配置说明，并优化了代码块展示和IDE相关说明。

2. 工具链测试
- 工具链测试环境准备：完成了20款RISC-V开发板下工具链测试用例的验证和验收环境准备。
- 开发板与系统支持：新增了对 Bit-Brick K1、Milk-V Pioneer、LicheeRVDock、HiFive Unmatched 等开发板的支持，更新了 RevyOS、Debian Trixie、openEuler 等多款系统的测试报告。
- 社区内容建设：在 `ruyisdk.cn` 发布了多篇 RevyOS 工程软件生态观测系列文章，丰富了操作系统支持矩阵的技术内容。

3. Sail/ACT
- Sail模型功能增强：
  - 持续推进 H 扩展支持，测试通过率达76/82，新增 Zicfilp 指令支持。
  - 改进了 CSR 访问检查、陷阱处理等核心机制，提升了模型可靠性。
- 测试框架与工具链优化：
  - 修复了压缩指令集测试覆盖，更新了多个非法指令测试用例。
  - 参与了 Sail 编译器问题修复和代码重构，提升了架构测试的准确性。
- 社区分享与会议参与：发布了多篇Sail技术分享文档，参与了东亚双周会、Tech-golden-model meeting等会议，并准备了相关海报与摘要。
  
4. RISC-V和RuyiSDK推广
- 11.1-11.2 参加中国科学院第八届科学节，现场演示了RuyiSDK和RISC-V生态（从嵌入式到多模态大模型，从RISC-V发展史到机器人操作系统在移动机器人和无人机上的应用）。
- 参加RISC-V 校园行活动，在中国矿业大学和应急管理大学 报告《RuyiSDK 为RISC-V开发者构建的全栈开发环境》和《快速入门 Sail-Model 黄金模型开发》
- 完成3个会议课题摘要和海报，《Ruyi Package Manager - A Unified Package Management and Development Environment for RISC-V》、《An Efficient Approach to Apply the RISC-V Sail Model to Chip Verification》、《From Fragmentation to Systematization: A Standardized Quality Selection and Systematic Reconstruction Approach for RISC-V Courses》

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK v0.43.0-beta.20251118 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251119/README.md)
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251119/RUYI_包管理_LicheePi4A_openEuler24.03_riscv64_测试结果.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Debian13 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Debian sid x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251119/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251119/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Deepin25 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Deepin25_x86_64_测试结果.md)
    - [Fedora42 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora43 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Fedora43_x86_64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler25.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openKylin2.0 x86\64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_openKylin_x86_64_测试结果.md)
    - [OpenCloudOS 9.4 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)

    - 缺陷：
      上一版本遗留 2 个缺陷：

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，修复已经延后  |
        | [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)   | 严重 | 已有文档整体更新计划，已有具体时间节点和时间表安排  |

    - packages-index 测试

      上一版本遗留 2 个缺陷：

        | 缺陷      | 问题等级 |备注 |
        | ----------- | ----------- | --- |
        | [有一部分包无法下载 #37](https://github.com/ruyisdk/packages-index/issues/37)     | 一般 | 已有相关 issue 回复且已经在修复中 |
        | [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)     | 一般 | 软件自带修复功能，且已有相关 issue 回复 |

        新增 1 个缺陷：

        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [https://github.com/ruyisdk/packages-index/issues/132](https://github.com/ruyisdk/packages-index/issues/132)     | 一般| 软件自带修复功能，且已有相关 issue 回复|

    - RuyiSDK IDE 测试

      RuyiSDK Eclipse Plugins 0.0.5 版本遗留 2 个缺陷：

        | 缺陷      | 问题等级 | 判定依据 |
        | ----------- | ----------- | ---- |
        | [未配置 PATH 导致无法轻松访问 ruyi #38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)    | 建议 | RuyiSDK IDE 与 RuyiSDK 发布周期分离|
        | [Ruyi 安装下载完成不够明显 #39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)    | 建议|RuyiSDK IDE 与 RuyiSDK 发布周期分离|

        回归测试未通过，不符合入口标准。故本版本不执行回归测试之后的测试流程，或执行了部分测试流程但不载入测试报告。

        RuyiSDK VSCode Plugin 0.1.0 测试结果见报告 [report](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251119/vscode-ide/report.md)。  
    - 修复情况
    	新增缺陷遗留 1 个一般缺陷，将在下个开发周期修复。简单修复合格。
      
    - 资源
      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/aacca1f0f3a65b6565121e526f526ec14bc63398)

- [[bug] traceback occur on strategy = "spacemit-k1-v1" images #404]

#### 1.2 RuyiSDK 开发和测试工具开发

- packages-index 项目
    - [board-images/bianbu-{desktop,minimal}-spacemit-k1: add bianbu emmc images #124](https://github.com/ruyisdk/packages-index/pull/124)
    - [entities: new device SpacemiT MUSE {Box,Book} and modify bianbu related descriptions #125](https://github.com/ruyisdk/packages-index/pull/125)
    - [entities: new device MilkV Jupiter #126](https://github.com/ruyisdk/packages-index/pull/126)
    - [entities: new device Sipeed LicheePi 3A #127](https://github.com/ruyisdk/packages-index/pull/127)
    - [board-images/bianbu-desktop-lite-spacemit-{k1,k1-sd}: add bianbu desktop lite images #128](https://github.com/ruyisdk/packages-index/pull/128)
    - [entities: remove device pine64 star64 support #129](https://github.com/ruyisdk/packages-index/pull/129)
    - [entities: new device MilkV Megrez support #130](https://github.com/ruyisdk/packages-index/pull/130)
    - [entities: new device Xiangshan Nanhu Laptop support #131](https://github.com/ruyisdk/packages-index/pull/131)
    
- ruyi  项目
    - [docs: add new used vendor id spacemit #405](https://github.com/ruyisdk/ruyi/pull/405)
    
- ruyi-packaging  项目
    - [riko(manifests): add titan flasher capability #54](https://github.com/ruyisdk/ruyi-packaging/pull/54)
    - [ruyi_packages: add bianbu-k1 emmc image support #55](https://github.com/ruyisdk/ruyi-packaging/pull/55)
    - [ruyi_package: new config format for LicheeRV-Nano-Build #56](https://github.com/ruyisdk/ruyi-packaging/pull/56)
    - [ruyi_packages: add bianbu-k1 desktop lite images #57](https://github.com/ruyisdk/ruyi-packaging/pull/57)
    - [ruyi_packages: new package rockos-megrez #58](https://github.com/ruyisdk/ruyi-packaging/pull/58)
    - [ruyi_packages: new package redleafos-nanhu #59](https://github.com/ruyisdk/ruyi-packaging/pull/59)

#### 1.3 RuyiSDK网站

- [Refactor the news articles component to improve responsiveness, relocate images to the right on larger screens, and enhance image loading with a fallback placeholder](https://github.com/ruyisdk/ruyisdk-website/pull/292)
- [Ordering, synchronyzation & i18n for the new News systems](https://github.com/ruyisdk/ruyisdk-website/pull/284)
	- Provide markdown-based i18n for the news section
	- Synchronize the homepage NewsShowcase and the new /news page for news source
	- Now news supports ordering and homepage News component will display latest news automatically.
- [Add subscribe button on news page](https://github.com/ruyisdk/ruyisdk-website/pull/285)
	- Now button automatically resize to the page's size.
- [i18n for titles in /news page](https://github.com/ruyisdk/ruyisdk-website/pull/288)
	- Add locale-aware title formatting in the news generator plugin to produce English and 	- German versions of biweekly report and release note titles while preserving the original Chinese titles for zh-Hans locale.
- [news page style update](https://github.com/ruyisdk/ruyisdk-website/pull/289)
	- Revamp the News page styling and layout with decorative background blobs, responsive flex-based layout, and updated card designs for articles and sidebar items
- [New /about page](https://github.com/ruyisdk/ruyisdk-website/pull/292)
	- New /about page with unified design language & i18n.
	- Add a new About page at /about with project introduction, goals, products, community contributions, contact information, and QR codes
	- Localize the About page content in English, German, and Simplified Chinese using translation keys
- [Layout optimization for NewsShowcase](https://github.com/ruyisdk/ruyisdk-website/pull/298)
	- Optimized layout to prevent the cropping problem for news cards and title shadows.
- [Optimize subscribe button & email validity check](https://github.com/ruyisdk/ruyisdk-website/pull/299)
	- Disable subscribe button when no valid e-mail address entered.
	Check e-mail address validity & colour visual hint for user.
- [Add filtering feature to /Community/contributors page](https://github.com/ruyisdk/ruyisdk-website/pull/300)
	- Add a configurable filtering step to the contributors generation scripts so certain contributors are excluded from the Community contributors page.
- [Optimize /news page's layout on UHD screens](https://github.com/ruyisdk/ruyisdk-website/pull/301)
	- Rework the /news page layout and article cards for better use of space and responsiveness on large and UHD screens.
- [Added a button for copying each line and a background highlight effect](https://github.com/ruyisdk/ruyisdk-website/pull/278)
    - add title
    - add highlight
    - add copiable
    - add line-copy
- [Docs web v3:optimzed the docs web's font and layout](https://github.com/ruyisdk/ruyisdk-website/pull/286)
    - remove the sidebar
    - change the style of font
    - change the style of the navigation bar
- [Ensure all lines display as block to preserve line breaks](https://github.com/ruyisdk/ruyisdk-website/pull/287)
- [doc_web_v4:center the doc web](https://github.com/ruyisdk/ruyisdk-website/pull/295)
- [docs_web_v5:add the water-printer on background](https://github.com/ruyisdk/ruyisdk-website/pull/297)
- [modify the layout of navbar](https://github.com/ruyisdk/ruyisdk-website/pull/296)
- [Code block v3: Fixed the code highlighting issue and removed the filename attribute](Code block v3: Fixed the code highlighting issue and removed the filename attribute)

- x86_64 测试迁移到 GitHub Action
    - 测试工具 ruyi-litester 仓库 18 个 commits [adcbfeb4...aacca1f0](https://github.com/weilinfox/ruyi-litester/compare/adcbfeb4b37e77c44737c61bf365bc6db97dfeed...aacca1f0f3a65b6565121e526f526ec14bc63398)
    - 测试报告生成模板 ruyi-litester-reports 仓库 1 个 commit [54568cf0](https://github.com/weilinfox/ruyi-litester-reports/commit/54568cf0e6d7685fbd5c5398c4814351dc292296)

#### 1.4 RuyiSDK文档

- [codeblock: use new codeblock #118](https://github.com/ruyisdk/docs/pull/118) 应用新代码块

#### 1.5 RuyiSDK会议和技术分享

- RISC-V DAY TOKYO 2025 AUTUMN 海报 Extended Abstract 和 PPT
  
### 2. RISC-V 工具链测试

#### 2.1 RISC-V 工具链测试

- 20种开发板测试用例在北京完成验证和环境准备，产出测试用例文档和安装好的开发板测试环境

- 测试大纲Visionfive v2 + LLVM用例完成测试验证，产出测试用例（更正版本）

#### 2.2 开发板操作系统支持测试

- [Add new boards, Bit-Brick_K1: update bianbu](https://github.com/ruyisdk/support-matrix/pull/383/commits)
	- Bit-Brick_K1: update bianbu 3.0.1 minimal, bianbu star 3.0 beta1
	- new board: BPI-RV2,A210_SODIMM_V2,EBC7702,StarPro64
	- fix filename and report format for LicheeRV_Dock/Debian

#### 2.3 ruyisdk.cn操作系统支持矩阵板块

- [RevyOS上的工程软件生态观测 (5): 构建之旅：从入门到放弃 (中)：pkg-config 小时候借书 not found in the pkg-config search path 了](https://ruyisdk.cn/t/topic/1900)
- [RevyOS上的工程软件生态观测 (7): 那些失传的软件：吃我一记洛阳铲！](https://ruyisdk.cn/t/topic/1906)
- [RevyOS上的工程软件生态观测 (6): 构建之旅：从入门到放弃 (下)：我来 port？真的假的？](https://ruyisdk.cn/t/topic/1905)
- 大饼：RISC-V 开发板和操作系统支持矩阵网站开发规划与建议征求](https://ruyisdk.cn/t/topic/880)

### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- SAIL
	- [PR](https://github.com/riscv/sail-riscv/pull/1380)Fix htif memory range check
	- [PR](https://github.com/riscv/sail-riscv/pull/1357) Change is_CSR_accessible return type to CSRAccessResult enum
  	- [PR](https://github.com/riscv/sail-riscv/pull/1402) Enhance CSR access result granularity and report illegal access reasons
  	- H 扩展测试 [链接](https://github.com/trdthg/riscv-hypervisor-tests)
    	- 支持 sail 运行 riscv-hyp-tests, riscv-hs-tests 两个测试套
    	- 修复了 riscv-hs-tests 测试套
	- [#1413](https://github.com/riscv/sail-riscv/pull/1413): 提交PR, 针对spec中提出的`mstatus`中`FS`, `VS`字段在某些扩展的配置关闭的情况下,须为只读的问题, 添加可配置选项, 并修改字段写入guard.
	- [#1412](https://github.com/riscv/sail-riscv/pull/1412): 提交PR, 针对当前physaddr 的所有bits 都被实现的情况, 添加配置选项, 使得physaddr 的实现位可配置, 同时保证高位为只读零
	- [#1366](https://github.com/riscv/sail-riscv/pull/1366): 将Sail-RISCV 的配置选项config_print_platform 拆分为五个不同的与功能相关的选项, 便于执行器的使用和调试, 目前已经合并
	- [#1531](https://github.com/rems-project/sail/pull/1531): 针对[#1512](https://github.com/rems-project/sail/issues/1512) 提出的Sail 编译器Bug , 提交PR 进行修复, 目前已经合并
	- [#1384](https://github.com/riscv/sail-riscv/pull/1384): 更改 Sail 编译命令，將 sail_smt_cache 文件放在 ${CMAKE_CURRENT_BINARY_DIR} 中。
	- [Remove useless implementation](https://github.com/riscv/sail-riscv/pull/1372)
	- [Add callback for pt walk](https://github.com/riscv/sail-riscv/pull/1370)
	- [#1403](https://github.com/riscv/sail-riscv/pull/1403)

- LLVM
	- [DAGCombiner Add sra-xor-sra pattern fold](https://github.com/llvm/llvm-project/pull/166777) 优化riscv shift相关的逻辑
  
#### 3.2 SAIL技术分享

- [Linux下，如何开始sail编程](https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2025-11/linux下，如何开始sail编程.md)

- [Sail内置类型和用户自定义类型](https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2025-11/sail内置类型和用户自定义类型.md)

- [Sail语言学习比较](https://github.com/challenger1024/plct-works/blob/main/sail/sail-note.md)

- [Sail model](https://github.com/challenger1024/plct-works/blob/main/sail/sail-model.md)

- 应急管理大学校园行 [快速入门 Sail-Model 黄金模型开发](https://github.com/trdthg/plct/blob/main/doc/sail/ppt/PLCT%E6%A0%A1%E5%9B%AD%E8%A1%8C%20%E9%98%8E%E6%98%8E%E9%93%B8%20%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8%20Sail-Model%20%E9%BB%84%E9%87%91%E6%A8%A1%E5%9E%8B%E5%BC%80%E5%8F%91.pptx)

#### 3.3 SAIL会议

- 会议海报：An Efficient Approach to Apply the RISC-V Sail Model to Chip Verification [abstract + poster](https://github.com/trdthg/plct/tree/main/doc/sail/2025-autume-tokyo-day)

- Tech-golden-model meeting [`10.3`, `10.10`, `10.17`, `10.24`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)

- 11.27 东亚双周会 [PPT](https://docs.google.com/presentation/d/1auFwfVUTf_CiCPb2OaYoRpqQTeuyg3bKEMlhZBOTXfM/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

### 4. 独立项目

#### 4.1 中国科学院第八届科学节(11.1-11.2)

- 科学节创工坊项目[小架构，大神通]
  展示项目：
	- RuyiSDK
    - Visionfive v2 灯光控制
    - K230手势识别
    - Licheepi 4A多模态大模型
    - HPC OpenMPI on Licheepi4A Cluster
    - RevyOS 操作系统演示机器学习互动实验
    - RISC-V ROS移动小车
    - RISC-V ROS无人机
    - RISC-V 发展史

#### 4.2 英麒 RISC-V Lab

- 配合维护展厅及实验室设备运行状态，定期排查开发板连通性与系统环境稳定性
- 跟踪 RISCV- Lab 建设进度，协助完善展厅视频内容与展示方案

### 5. RISC-V教育和短视频

#### 5.1 短视频制作

- [K230使用 RuyiSDK 快速烧录 K230](https://www.bilibili.com/video/BV1GdkDBNEc5/)

- [BananaPi使用 RuyiSDK 快速烧录 BananaPi BPI-F3](https://www.bilibili.com/video/BV1j6CRBdE8t/)

- [Milk-V Mars使用 RuyiSDK 快速烧录 Milk-V Mars](https://www.bilibili.com/video/BV1EhSvBXEiq/)

- [丁真教你玩转荔枝派 (一)](https://www.bilibili.com/video/BV1naCRBwE5D/)

- [RuyiSDK介绍视频](https://www.bilibili.com/video/BV1sQSkBHETp/)

- Licheepi 4a 跑 Deepseek模型的视频，包含运行Deepseek R1 chat模型和Qwen coder 代码生成模型（制作中）

#### 5.2 短视频剧本和文档、素材

- [LicheePi 4A 镜像刷写教程 (Windows)](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/)
- [使用 RuyiSDK 快速烧录 Milk-V Mars口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90Mars%E3%80%91Mars%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- [使用 RuyiSDK 快速烧录 BananaPi BPI-F3口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90BananaPi_BPI-F3%E3%80%91%E7%83%A7%E5%BD%95BPI-F3%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- [K230使用 RuyiSDK 快速烧录 K230视频脚本](https://github.com/DuoQilai/PLCT-Works/blob/main/Avaota%20F1/%E5%BF%AB%E9%80%9F%E5%90%AF%E5%8A%A8AvaotaF1%E8%84%9A%E6%9C%AC.md)
- [RuyiSDK介绍视频脚本](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/RuyiSDK/RuyiSDK%E5%8F%A3%E6%92%AD%E7%A8%BF.docx)
- [RuyiSDK介绍PPT](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/RuyiSDK/RuyiSDK%E4%BB%8B%E7%BB%8D.pptx)

#### 5.3 会议

- 编写《A Standardized Quality Selection and Systematic Reconstruction Approach for RISC-V Courses》会议摘要和海报
	- [摘要](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/1113_AStandardizedQualitySelectionandSystematicReconstructionApproachforRISC-VCourses.docx)
	- [海报](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/%E4%B8%9C%E4%BA%AC%E6%B5%B7%E6%8A%A5.pdf)

#### 5.4 实习生招聘

- [招新两名实习生 JD](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/JD.md)

### 6. 职工

#### 6.1 蔡玮霖

##### 6.1.1 RuyiSDK

- 测试 Ruyi 0.43.0-beta.20251118 和 ruyisdk-vscode-extension f153304 版本，测试报告 [pr](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/85)
- ruyi 仓库提出 1 个 issue
    - [[bug] traceback occur on strategy = "spacemit-k1-v1" images #404](https://github.com/ruyisdk/ruyi/issues/404)
- packages-index 仓库提交 8 个 pr
    - [board-images/bianbu-{desktop,minimal}-spacemit-k1: add bianbu emmc images #124](https://github.com/ruyisdk/packages-index/pull/124)
    - [entities: new device SpacemiT MUSE {Box,Book} and modify bianbu related descriptions #125](https://github.com/ruyisdk/packages-index/pull/125)
    - [entities: new device MilkV Jupiter #126](https://github.com/ruyisdk/packages-index/pull/126)
    - [entities: new device Sipeed LicheePi 3A #127](https://github.com/ruyisdk/packages-index/pull/127)
    - [board-images/bianbu-desktop-lite-spacemit-{k1,k1-sd}: add bianbu desktop lite images #128](https://github.com/ruyisdk/packages-index/pull/128)
    - [entities: remove device pine64 star64 support #129](https://github.com/ruyisdk/packages-index/pull/129)
    - [entities: new device MilkV Megrez support #130](https://github.com/ruyisdk/packages-index/pull/130)
    - [entities: new device Xiangshan Nanhu Laptop support #131](https://github.com/ruyisdk/packages-index/pull/131)
- ruyi 仓库提出 1 个 pr
    - [docs: add new used vendor id spacemit #405](https://github.com/ruyisdk/ruyi/pull/405)
- ruyi-packaging 仓库提交 6 个 pr
    - [riko(manifests): add titan flasher capability #54](https://github.com/ruyisdk/ruyi-packaging/pull/54)
    - [ruyi_packages: add bianbu-k1 emmc image support #55](https://github.com/ruyisdk/ruyi-packaging/pull/55)
    - [ruyi_package: new config format for LicheeRV-Nano-Build #56](https://github.com/ruyisdk/ruyi-packaging/pull/56)
    - [ruyi_packages: add bianbu-k1 desktop lite images #57](https://github.com/ruyisdk/ruyi-packaging/pull/57)
    - [ruyi_packages: new package rockos-megrez #58](https://github.com/ruyisdk/ruyi-packaging/pull/58)
    - [ruyi_packages: new package redleafos-nanhu #59](https://github.com/ruyisdk/ruyi-packaging/pull/59)
- ruyisdk-website 审核 18 个 pr
    - [Subscribe button on news page #285](https://github.com/ruyisdk/ruyisdk-website/pull/285)
    - [Code block v2：Added a button for copying each line and a background highlight effect. #278](https://github.com/ruyisdk/ruyisdk-website/pull/278)
    - [Move pictures display of /news #282](https://github.com/ruyisdk/ruyisdk-website/pull/282)
    - [Ordering, synchronyzation & i18n for the new News systems. #284](https://github.com/ruyisdk/ruyisdk-website/pull/284)
    - [Docs web v3:optimzed the docs web's font and layout #286](https://github.com/ruyisdk/ruyisdk-website/pull/286)
    - [Ensure all lines display as block to preserve line breaks #287](https://github.com/ruyisdk/ruyisdk-website/pull/287)
    - [i18n for titles in /news page #288](https://github.com/ruyisdk/ruyisdk-website/pull/288)
    - [/news page style update #289](https://github.com/ruyisdk/ruyisdk-website/pull/289)
    - [update news #290](https://github.com/ruyisdk/ruyisdk-website/pull/290)
    - [docs: update English version #291](https://github.com/ruyisdk/ruyisdk-website/pull/291)
    - [New /about page #292](https://github.com/ruyisdk/ruyisdk-website/pull/292)
    - [doc_web_v4:center the doc web #295](https://github.com/ruyisdk/ruyisdk-website/pull/295)
    - [modify the layout of navbar #296](https://github.com/ruyisdk/ruyisdk-website/pull/296)
    - [docs_web_v5:add the printer on background #297](https://github.com/ruyisdk/ruyisdk-website/pull/297)
    - [Layout optimization for NewsShowcase #298](https://github.com/ruyisdk/ruyisdk-website/pull/298)
    - [Optimize subscribe button & email validity check #299](https://github.com/ruyisdk/ruyisdk-website/pull/299)
    - [Add filtering feature to /Community/contributors page #300](https://github.com/ruyisdk/ruyisdk-website/pull/300)
    - [Optimize /news page's layout on UHD screens. #301](https://github.com/ruyisdk/ruyisdk-website/pull/301)
- ruyisdk-website 提交 1 个 pr
    - [pages: use new about page #293](https://github.com/ruyisdk/ruyisdk-website/pull/293) 新的关于页面
    - [docs: new CodeBlock #302](https://github.com/ruyisdk/ruyisdk-website/pull/302)
- docs 提交 1 个 pr
    - [codeblock: use new codeblock #118](https://github.com/ruyisdk/docs/pull/118) 应用新代码块
- x86_64 测试迁移到 GitHub Action
    - 测试工具 ruyi-litester 仓库 18 个 commits [adcbfeb4...aacca1f0](https://github.com/weilinfox/ruyi-litester/compare/adcbfeb4b37e77c44737c61bf365bc6db97dfeed...aacca1f0f3a65b6565121e526f526ec14bc63398)
    - 测试报告生成模板 ruyi-litester-reports 仓库 1 个 commit [54568cf0](https://github.com/weilinfox/ruyi-litester-reports/commit/54568cf0e6d7685fbd5c5398c4814351dc292296)

##### 6.1.2 会议

- RISC-V DAY TOKYO 2025 AUTUMN 海报 Extended Abstract 和 PPT

#### 6.2 阎明铸

##### 6.2.1 Sail

- \[PR\] <https://github.com/riscv/sail-riscv/pull/1380> Fix htif memory range check
- \[PR\] <https://github.com/riscv/sail-riscv/pull/1357> Change is_CSR_accessible return type to CSRAccessResult enum
- \[PR\] <https://github.com/riscv/sail-riscv/pull/1402> Enhance CSR access result granularity and report illegal access reasons
- H 扩展测试 [链接](https://github.com/trdthg/riscv-hypervisor-tests)
    - 支持 sail 运行 riscv-hyp-tests, riscv-hs-tests 两个测试套
    - 修复了 riscv-hs-tests 测试套

##### 6.2.2 会议和技术分享

- 中国科学院科学节服务（11.1 11.2）
- 玄铁课程，产出课程视频 12 个
- An Efficient Approach to Apply the RISC-V Sail Model to Chip Verification [abstract + poster](https://github.com/trdthg/plct/tree/main/doc/sail/2025-autume-tokyo-day)
- 校园行 快速入门 Sail-Model 黄金模型开发 [PPT](https://github.com/trdthg/plct/blob/main/doc/sail/ppt/PLCT%E6%A0%A1%E5%9B%AD%E8%A1%8C%20%E9%98%8E%E6%98%8E%E9%93%B8%20%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8%20Sail-Model%20%E9%BB%84%E9%87%91%E6%A8%A1%E5%9E%8B%E5%BC%80%E5%8F%91.pptx)
- tech-golden-model meeting [`10.3`, `10.10`, `10.17`, `10.24`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 11.27 东亚双周会 [PPT](https://docs.google.com/presentation/d/1auFwfVUTf_CiCPb2OaYoRpqQTeuyg3bKEMlhZBOTXfM/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

##### 6.2.3 RISC-V 工具链测试

- 测试 vf2 开发板+LLVM测试用例

#### 6.3 张馥媛

##### 6.3.1 K230

- [【K230】使用 RuyiSDK 快速烧录 K230](https://www.bilibili.com/video/BV1GdkDBNEc5/)
- [【K230】使用 RuyiSDK 快速烧录 K230视频脚本](https://github.com/DuoQilai/PLCT-Works/blob/main/Avaota%20F1/%E5%BF%AB%E9%80%9F%E5%90%AF%E5%8A%A8AvaotaF1%E8%84%9A%E6%9C%AC.md)

##### 6.3.2  BananaPi

- [【BananaPi】使用 RuyiSDK 快速烧录 BananaPi BPI-F3](https://www.bilibili.com/video/BV1j6CRBdE8t/)
- [使用 RuyiSDK 快速烧录 BananaPi BPI-F3口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90BananaPi_BPI-F3%E3%80%91%E7%83%A7%E5%BD%95BPI-F3%E5%8F%A3%E6%92%AD%E7%A8%BF.md)

##### 6.3.3  Milk-V Mars
- [【Milk-V Mars】使用 RuyiSDK 快速烧录 Milk-V Mars](https://www.bilibili.com/video/BV1EhSvBXEiq/)
- [使用 RuyiSDK 快速烧录 Milk-V Mars口播稿](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/VideoScripts/%E3%80%90Mars%E3%80%91Mars%E5%8F%A3%E6%92%AD%E7%A8%BF.md)

##### 6.3.4  英麒RISC-V Lab
- [招新两名实习生 JD](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/JD.md)
-  [丁真教你玩转荔枝派 (一)](https://www.bilibili.com/video/BV1naCRBwE5D/)
- [LicheePi 4A 镜像刷写教程 (Windows)](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/)
- [RuyiSDK介绍视频](https://www.bilibili.com/video/BV1sQSkBHETp/)
- [RuyiSDK介绍视频脚本](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/RuyiSDK/RuyiSDK%E5%8F%A3%E6%92%AD%E7%A8%BF.docx)
- [RuyiSDK介绍PPT](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/RuyiSDK/RuyiSDK%E4%BB%8B%E7%BB%8D.pptx)
- Licheepi 4a 跑 Deepseek模型的视频，包含运行Deepseek R1 chat模型和Qwen coder 代码生成模型
-  Licheepi 4a 跑 开源我的世界 文档
- 配合维护展厅及实验室设备运行状态，定期排查开发板连通性与系统环境稳定性
- 跟踪 RISCV- Lab 建设进度，协助完善展厅视频内容与展示方案

##### 6.3.5  RuyiSDK
- 发布K230、BananaPi、Milk-V Mars环境搭建文档和视频

##### 6.3.6  东京RISC-V Day 海报

- [摘要](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/1113_AStandardizedQualitySelectionandSystematicReconstructionApproachforRISC-VCourses.docx)
- [海报](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/%E4%B8%9C%E4%BA%AC%E6%B5%B7%E6%8A%A5.pdf)

## SG2042/SG2044 Upstream

## Milk-V Duo Upstream

## [BLDClock](https://github.com/BrokenClient/BLDClock.md) (甲辰计划 J156)

### 完成内容

- 移植 `RT-Thread`, `LVGL`, `SimpleFOC`
- 完成表盘与编码器的协同
- 完成编码器与USB设备的协同
- 完成衍生作品 `LCD2004_Clock` 的电路和测试程序设计

### 目前效果

- 电机定力矩运动，角度闭环运动
- 旋转电机，屏幕表盘计时点移动
- 插入USB电脑时，转动电机，电脑屏幕丝滑滑动

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

## Jeandle 

### 实习生

#### 王鸿宇

- \[PR\]<https://github.com/jeandle/jeandle-jdk/pull/159> feat: add iabs/labs intrinsics
- \[PR\]<https://github.com/jeandle/jeandle-jdk/pull/184> feat: support dispatch by exception class type

#### 邓冲之

- \[PR\] <https://github.com/jeandle/jeandle-jdk/pull/216> enhance: Support stack overflow check for jeandle-compiled functions
- \[PR\] <https://github.com/jeandle/jeandle-jdk/pull/218> enhance: Add Dockerfile build instructions to getting started guide
- \[PR\] <https://github.com/jeandle/jeandle-jdk/pull/219> fix: Correct typos and improve comments

## 参考链接

- [PLCT 实验室的开放职位（实习生）](https://github.com/plctlab/weloveinterns/blob/master/open-internships.md)
- [PLCT 开源进展 (PLCT Weekly)](https://github.com/plctlab/PLCT-Weekly)
- [PLCT 公开报告幻灯片（选集）](https://github.com/plctlab/PLCT-Open-Reports)
