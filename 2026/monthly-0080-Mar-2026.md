# RISC-V 软件生态进展 · 第 80 期·2026 年 3 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium
#### Update:
1. 在liftoff中独立分配simd registers而不是绑定浮点寄存的分配  
   7658971: [riscv][liftoff] Separate floating-point and simd registers | https://chromium-review.googlesource.com/c/v8/v8/+/7658971
3. 7699576: [riscv] Fix build for cross compile | https://chromium-review.googlesource.com/c/v8/v8/+/7699576
4. 7695091: [riscv] Add simd in LiftoffAssembler::Push/Pop | https://chromium-review.googlesource.com/c/v8/v8/+/7695091
5. 7695806: [riscv] Fix SIMD lane load source register | https://chromium-review.googlesource.com/c/v8/v8/+/7695806
6. 重构cpu 文件  
   7683553: [base] Refactor CPU detection code into architecture-specific files | https://chromium-review.googlesource.com/c/v8/v8/+/7683553
8. 7669710: [riscv] Fix vector lmul calculation for RVV | https://chromium-review.googlesource.com/c/v8/v8/+/7669710
9. 7669917: [riscv] Optimize memory access for allocatable double registers in DeoptimizationEntry | https://chromium-review.googlesource.com/c/v8/v8/+/7669917

#### Port:
1. 7707695: [riscv][base] Refactor EmbeddedVector: decouple from Vector | https://chromium-review.googlesource.com/c/v8/v8/+/7707695   
2. 7699360: [riscv][wasm][wasmfx] Implement switch instruction | https://chromium-review.googlesource.com/c/v8/v8/+/7699360
3. 7695807: [riscv][turboshaft] Direct call for known functions | https://chromium-review.googlesource.com/c/v8/v8/+/7695807  
4. 7687330: [riscv][maps] Prepare for splitting MAP_TYPE into multiple values | https://chromium-review.googlesource.com/c/v8/v8/+/7687330
5. 7685620: [riscv][wasmfx] Trap on null for resume_throw_ref | https://chromium-review.googlesource.com/c/v8/v8/+/7685620
6. 7683933: Reland "[riscv][superspread] port to riscv" | https://chromium-review.googlesource.com/c/v8/v8/+/7683933

## Spidermonkey / Firefox

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/29464 (8376575: aarch64: incorrect array index load in aastore)
- https://github.com/openjdk/valhalla/pull/2009 (8376883: [lworld] Only enable compiler/valhalla/inlinetypes/TestTrivialMethods.java for aarch64 and x86)
- https://github.com/openjdk/valhalla/pull/2020 (8377065: [lworld] Fix merge removing VM_Version::supports_fast_class_init_checks() check)
- https://github.com/openjdk/valhalla/pull/2071 (8377563: [lworld] Lower ReservedCodeCacheSize for runtime/valhalla/inlinetypes/classloading/ConcurrentClassLoadingTest.java)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/29458 (8376572: RISC-V: Interpreter: Load array index as signed int)
- https://github.com/openjdk/jdk/pull/29310 (8377225: RISC-V: Improve receiver type profiling reliability)
- https://github.com/openjdk/jdk/pull/29383 (8373595: A new ObjectMonitorTable implementation)
- https://github.com/openjdk/jdk/pull/29682 (8376168: RISC-V：Improve performance of copy_memory_v)
- https://github.com/openjdk/jdk/pull/29683 (8376167: RISC-V: Fix redundant zext.w in macroAssembler_riscv.cpp)
- https://github.com/openjdk/jdk/pull/29933 (8378752: Enable some subword vector casts IR matching tests for RISC-V)
- https://github.com/openjdk/jdk/pull/29951 (8378810: Enable missing FFM test via jtreg requires for RISC-V)
- https://github.com/openjdk/jdk/pull/29974 (8378883: Enable more vector reductions IR matching tests for RISC-V)

3. Proposed JDK-25u/26u backport PRs:
- https://github.com/openjdk/jdk26u/pull/48 (8374056: RISC-V: Fix argument passing for the RiscvFlushIcache::flush)
- https://github.com/openjdk/jdk25u-dev/pull/216 (8376572: RISC-V: Interpreter: Load array index as signed int)
- https://github.com/openjdk/jdk25u-dev/pull/245 (8374056: RISC-V: Fix argument passing for the RiscvFlushIcache::flush)
- https://github.com/openjdk/jdk25u-dev/pull/270 (8368677: acvp test should throw SkippedException when no ACVP-Server available)
- https://github.com/openjdk/jdk21u-dev/pull/2608 (8374056: RISC-V: Fix argument passing for the RiscvFlushIcache::flush)
- https://github.com/openjdk/jdk17u-dev/pull/4264 (8374056: RISC-V: Fix argument passing for the RiscvFlushIcache::flush)

## Go

## GNU Toolchain

## LLVM Team

## MLIR / Buddy Compiler

## opensbi

## 罗云翔测试团队
（包含 SAIL 和 ACT 测试部分）

本月完成 RuyiSDK 0.47.0-beta.20260316 版本在多发行版、多架构下的全面测试，持续开发自动化测试工具与示例库，推进 RuyiAI 项目 2026年 Q1 任务。在 SAIL 方向提交 10 余个 PR，参与多个 PR 评审。完成2026年RISC-V欧洲峰会5个项目的扩展摘要提交。团队成员获得2026年玄铁社区开源贡献奖。协助RISC-V International 完成中国地区RISC-V硬件厂商调查问卷等材料的翻译工作。

1. RuyiSDK

1.1 RuyiSDK `0.47.0-beta.20260316` 测试  
- 测试覆盖 Debian、Ubuntu、openEuler、Fedora、Deepin、openKylin、OpenCloudOS、Archlinux 等主流发行版，共计 20 余个版本。  
- 在 x86_64、aarch64、riscv64 三种架构上完成验证，生成 30 余份测试报告。  
- 对 RuyiSDK Eclipse 插件与 VSCode 插件进行系统性手动测试，跟踪并反馈遗留缺陷与新增问题。  
- 包管理器、文档、IDE 插件均无新增严重缺陷，版本符合发版标准。

1.2 RuyiSDK 测试工具开发  
- 完善 `ruyi-litester` 测试框架，提升测试覆盖率。  
- 开发 Riko Go 版本，支持上游版本检测与包清单生成。  
- 完成 Ruyi GUI Provision 原型，实现 Windows 环境下可视化烧录流程。  
- 推动 packages-index 自动化更新机制，集成 Telegram Bot 推送与数据库记录。

1.3 RuyiSDK 示例库与开发指南建设  
- 为 LicheePi 4A、Milk-V Duo256/DuoS 等多款开发板编写示例教程，涵盖 cpufetch、Dhrystone、llama.cpp、tiny-AES-c、zstd、blink 等应用。  
- 完成示例库前端站点搭建，支持开发板与示例的导航、搜索与展示。  
- 输出 Triton 在 RISC-V 平台的静态编译调研报告，并录制多款应用演示视频。

1.4 RuyiSDK 网站与文档  
- 向 `ruyisdk-website` 仓库提交 10 余个 PR，优化首页布局、导航栏、卡片组件及贡献者页面。  
- 新增博客与社区文章，涵盖游戏编译、虚拟环境使用、RuyiSDK 入门等内容。  
- 更新 IDE 使用文档与示例代码，完善开发者资源。

2. RuyiAI  
- 提交 5 个 PR 至 `buddy-mlir` 仓库，包括 CI 修复、安装文档更新、发布物打包等。  
- 更新 `ruyiai-stack.github.io` 文档，完善 PyTorch RISC-V 安装说明。

3. SAIL/ACT  
- 提交 10 余个 PR 至 `sail-riscv`，新增 Zilsd/Zclsd、Zvfbfa、Zbr 等扩展支持，优化 CSR 访问与异常处理逻辑。  
- 参与 ACT 测试套件开发，提交 Zibi、Zvabd 等扩展测试。  
- 参加技术黄金模型会议与东亚双周会，完成技术分享与实习成果展示。  
- 投稿 RISC-V 欧洲峰会，提交多篇扩展摘要。
- 团队成员获得社区开源贡献奖

4. RISC-V 操作系统支持矩阵建设与工具链测试  
- 持续维护操作系统支持矩阵。  
- 完成工具链项目评估的演示工作。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.47.0-beta.20260316 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/README.md)
    - [Debian12 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Debian12 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260317/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu22.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260317/RUYI_包管理_Ubuntu22.04_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260317/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu24.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Ubuntu24.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora42 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Fedora42_aarch64_测试结果.md)
    - [Fedora43 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Fedora43_x86_64_测试结果.md)  
    - [Fedora43 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Fedora43_aarch64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Deepin25 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Deepin25_x86_64_测试结果.md)
    - [Deepin25 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Deepin25_riscv64_测试结果.md)
    - [Deepin25 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Deepin25_aarch64_测试结果.md)
    - [openKylin2.0 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openKylin_x86_64_测试结果.md)
    - [openKylin2.0 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openKylin_riscv64_测试结果.md)
    - [openKylin2.0 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_openKylin_aarch64_测试结果.md)
    - [OpenCloudOS 9.4 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)
    - [OpenCloudOS 9.4 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_OpenCloudOS_aarch64_测试结果.md)
    - [Archlinux x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260317/RUYI_包管理_Archlinux_x86_64_测试结果.md)

    - 缺陷：  
      - 文档测试
        上一版本遗留 2 个缺陷：

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，修复已经延后  |

      - packages-index 测试
        无新增缺陷
      - RuyiSDK IDE 测试
        RuyiSDK Eclipse IDE 测试
        本版本无同步发版的 Eclipse 插件。

        遗留缺陷：

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [命令执行提示框可以任意关闭且无法重新打开 #82](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/82)   | 建议 |   |
        | [开发板选择框中开发板型号未排序 #83](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/83) | 建议 |  |
        | [虚拟环境建立的项目绑定问题 #84](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/84) | 建议 |  |
        | [安装插件时 Eclipse 提示未签名 #85](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/85) | 建议 |  |
        | [打开 Ruyi Package Explorer 时必须选择某款开发板 #86](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/86) | 建议 |  |
        | [虚拟环境建立的 quirks 过滤问题 #87](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/87) | 建议 |  |
        | [虚拟环境建立的 ruyi update 错误处理问题 #88](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/88) | 建议 |  |
        | [虚拟环境建立的 profile 排序问题 #89](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/89) | 建议 |  |
        | [有一些可以自动获取的东西，不需要手动填写 #90](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/90) | 建议 |  |
        | [RuyiSDK IDE 主文档的更新 #123](https://github.com/ruyisdk/docs/issues/123) | 一般 | 已有修复计划 |

        无新增缺陷。
      
      - RuyiSDK VSCode IDE 测试
      本版本无同步发布的 VSCode 插件。

      遗留缺陷：

      | 缺陷 | 问题等级 | 备注 |
      | --- | --- | --- |
      | [创建虚拟环境时profile中文乱码 #122](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/122) | 一般 | 已有修复 commit |
      | [同时安装ruyi最新版和其他版本时，启动旧版ruyi会提示更新ruyi最新版。 #115](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/115) | 一般 | 已有 issue 回复  |

      - Ruyi 包管理器测试
        遗留缺陷：

        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415) | 一般 | 已有 issue 回复 |
    
    - 测试结论
      - 本版本无新增缺陷；
      - 本版本包含遗留的严重缺陷，均按照修复时间表修复中；

      RuyiSDK v0.47.0-beta.20260316 版本符合出口判定标准，准予发版。

    - 资源
      - [本版本 litester 测试程序](https://github.com/ruyisdk-test/ruyi-litester/tree/0f6c010632aadc177afe98e100ebd833e601a8d0)

- [Issue 126](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/126)
  - Get Start With RuyiSDK新手引导完成状态自动点亮不敏感
- [Issue 127](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/127) 
  - 虚拟环境创建时添加sysroot选项失败 
- [Issue 435](https://github.com/ruyisdk/ruyi/issues/435)
  - 虚拟环境允许使用用户自制的 sysroot 
- [ruyisdk/ruyi#436](https://github.com/ruyisdk/ruyi/issues/436)
  - 上游高版本 qemu 兼容问题

- [RuyiSDK 测试报告]( https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK.md)

- [RuyiSDK Eclipse IDE 测试报告](https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK%20IDE%20Eclipse.md)

- [RuyiSDK VSCode IDE 测试报告](https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK%20IDE%20VS.md)

#### 1.2 RuyiSDK 开发和测试工具开发

- ruyisdk-vscode-extension-test
  - [PR #8](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/8)
    - 在vscode marketplace搜索keywords安装插件
    - bug：交互式创建虚拟环境时sysroot无法正常配置

- Ruyi GUI Provision

  将 Ruyi 的 provision 命令流程整合到 Fyne GUI 中，提供 Windows 环境下的可视化设备烧录向导。

  - USB 设备自动检测（基于 usb_detect 库）
  - 自动从 ruyisdk/packages-index 获取镜像列表
  - 三步式烧录流程：选择镜像 → 选择设备 → 下载写入  
  - 仓库: https://github.com/21758/ruyi_provision_gui
  - USB 检测库: https://github.com/21758/usb_detect

- Riko Go 仓库

  Riko 是 Ruyi 打包机器人的核心工具，用于自动检测上游软件版本更新并生成包清单。本项目将原 Python 版本重构为 Go 语言版本。

  - `riko check` - 上游版本检测（支持 GitHub API、正则表达式）
  - `riko list` - 结果查询和过滤（updated/error/any）
  - `riko manifests` - 包清单生成（支持指定版本、降级）

  - 仓库: https://github.com/ruyisdk/ruyi-packaging
  - Go 版本: https://gitee.com/huoyi_chen/ruyi_package_go

- packages-index 仓库
  - [New Package Request: wiringx GPIO Library]( https://github.com/ruyisdk/packages-index/issues/172)
  - [New Package Request: SDL2 (Development Libraries)]( https://github.com/ruyisdk/packages-index/issues/173)
  - [New Package Request: Go Toolchain]( https://github.com/ruyisdk/packages-index/issues/174)
  - [New Package Request: Xuantie GNU Toolchain]( https://github.com/ruyisdk/packages-index/issues/175)
  - [New Package Request: Nuclei RISC-V GNU Toolchain#176](https://github.com/ruyisdk/packages-index/issues/176)
  - [New Package Request: Nuclei LLVM Project#177](https://github.com/ruyisdk/packages-index/issues/177)
  - [New Package Request: Rust Programming Language#178](https://github.com/ruyisdk/packages-index/issues/178)
  - [New Package Request: Allegro 5.2.9#179](https://github.com/ruyisdk/packages-index/issues/179)
  - [New Package Request: cpufetch for Architecture Identification](https://github.com/ruyisdk/packages-index/issues/168)
  - [New Package Request: Dhrystone CPU Benchmark](https://github.com/ruyisdk/packages-index/issues/170)
  - issue: [Adapt RuyiSDK + Milk-V Duo256m (riscv64) to improve zstd source compilation](https://github.com/ruyisdk/packages-index/issues/171)
  - 提交 Issue <https://github.com/ruyisdk/packages-index/issues/180> 创建虚拟环境后里面没有 qemu-system

#### 1.3 RuyiSDK开发示例库开发

-  RuyiSDK 示例库文档展示的前端页面
	- 仓库链接： [https://github.com/DuoQilai/board-docs-frontend.git](https://github.com/DuoQilai/board-docs-frontend.git)

- 开发板定制开发项目
	- Licheepi4A 示例库扩充
		- [在 LicheePi4A_上运行 cpufetch 示例](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/cpufetch/LicheePi4A_cpufetch.md)
			- 视频： [在Licheepi4A上使用cpufetch获取CPU信息](https://www.bilibili.com/video/BV1j8wFzSE2x)
			- 视频： [使用Ruyi工具链编译cpufetch](https://www.bilibili.com/video/BV1fiw7zBE6F)
			- 教程：[Ruyi 平台下 cpufetch 安装与使用](https://github.com/DuoQilai/ruyisdk-dev-archive/blob/main/examples/cpufetch/Ruyi%20%E5%B9%B3%E5%8F%B0%E4%B8%8B%20cpufetch%20%E5%AE%89%E8%A3%85%E4%B8%8E%E4%BD%BF%E7%94%A8%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)
			- demo：[Demo_LicheePi4A_cpufetch](https://github.com/DuoQilai/ruyisdk-dev-archive/blob/main/examples/cpufetch/Demo_LicheePi4A_cpufetch)
		- [在 LicheePi 4A 上运行 `tinn` 示例](https://github.com/EnzoDing-rgb/plct_works/blob/main/reports/licheepi4a_tinn.md)
		- [在 LicheePi4A_上运行 Dhrystone 示例](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Dhrystone/Licheepi4A_Dhrystone.md)
			- demo：[Demo_LicheePi4A_Dhrystone](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Dhrystone/Demo_Licheepi4A_Dhrystone)
		-  [在 LicheePi4A 上运行 llama.cpp 示例](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Licheepi4A/llama_cpp_LPi4A.md)
			- demo：[Demo_llama_cpp](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/llama.cpp/Demo_llama_cpp)
	- Duo256 示例库扩充
		- [在 Milk-V Duo256m 上运行 tiny-AES-c 示例](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91%20tiny-AES-c%20%E6%95%99%E7%A8%8B.md)
			- demo：[tiny-AES-c 教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/tiny-AES-c%20%E6%95%99%E7%A8%8B_demo.md)
		- [在 Milk-V Duo256m 上运行 zstd 示例](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E6%88%90%E5%8A%9F%E7%BC%96%E8%AF%91%20zstd%20%E6%95%99%E7%A8%8B.md)
			- demo：[zstd教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/zstd%E6%95%99%E7%A8%8B_demo.md)
		- [在 Milk-V Duo256m 上运行 blink 示例](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91blink%E6%95%99%E7%A8%8B.md)
			- demo：[blink教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/blink%E6%95%99%E7%A8%8B_demo.md)
	- DuoS 示例库扩充
		- [在 Milk-V DuoS 上运行 helloworld 示例](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/Report_Duo_s_helloworld.md)

- RuyiSDK开发资源梳理和资源申请
	- [开发板资源梳理](https://www.kdocs.cn/l/cl3WweaKB9XO)
	- [New Package Request: cpufetch for Architecture Identification](https://github.com/ruyisdk/packages-index/issues/168)
	- [New Package Request: Dhrystone CPU Benchmark](https://github.com/ruyisdk/packages-index/issues/170)
	- [Adapt RuyiSDK + Milk-V Duo256m (riscv64) to improve zstd source compilation](https://github.com/ruyisdk/packages-index/issues/171)
	- [New Package Request: wiringx GPIO Library](https://github.com/ruyisdk/packages-index/issues/172)
	- [New Package Request: SDL2 (Development Libraries)](https://github.com/ruyisdk/packages-index/issues/173)
	- [New Package Request: Go Toolchain](https://github.com/ruyisdk/packages-index/issues/174)
	- [New Package Request: Xuantie GNU Toolchain](https://github.com/ruyisdk/packages-index/issues/175)
	- [New Package Request: Nuclei RISC-V GNU Toolchain#176](https://github.com/ruyisdk/packages-index/issues/176)
	-  [New Package Request: Nuclei LLVM Project#177](https://github.com/ruyisdk/packages-index/issues/177)
	- [New Package Request: Rust Programming Language#178](https://github.com/ruyisdk/packages-index/issues/178)
	- [New Package Request: Allegro 5.2.9#179](https://github.com/ruyisdk/packages-index/issues/179)

- RuyiSDK 工具使用示例
	- [RuyiSDK 使用](https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK.md)
	- [RuyiSDK Eclipse IDE 使用](https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK%20IDE%20Eclipse.md)
	- [RuyiSDK VSCode IDE 使用](https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK%20IDE%20VS.md)
	- [实例代码](https://github.com/ZihanCheng63/my-repo/blob/main/%E5%AE%9E%E4%BE%8B%E4%BB%A3%E7%A0%81.md)

- Triton 在 RISC-V 平台（LicheePi 4A）的静态编译调研：
	1. 已经成功打通了 ZCC 交叉编译工具链，通过测试命令，已经确认编译器能正常生成支持向量扩展的指令。
	2. 在尝试构建 Triton 后端插件时，发现教程中展示的 third_party/riscv 源代码目录在官方 Triton 仓库中并不存在。教程中的 RISC-V 后端（包含 compiler.py 和 driver.py 等核心逻辑）是针对 ZCC 编译器定制开发的非公开代码。
  - [新JD](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/JD.md)
  - [LicheePi 4A平台 运行Home Assistant 视频](https://www.bilibili.com/video/BV1UxwYzhECo/)
  - [LicheePi 4A平台 运行Home Assistant](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/Home_Assistant.md)

- 在 LicheePi 4A 上运行 `tinn` 示例，并完成报告。  
  报告链接：https://github.com/EnzoDing-rgb/plct_works/blob/main/reports/licheepi4a_tinn.md

- 完成开发板 Ruyi 工具链示例库文档展示的前端页面，并迭代两次：搭建独立的 Examples 教程站点（Astro + React + TS + Tailwind），从 `test-doc` 子模块扫描并解析各开发板 `README` 与示例 Markdown（frontmatter + 正文），实现厂商/SoC/开发板/示例的导航与搜索（侧栏按 **芯片厂商 silicon_vendor** 分组，可收起），首页板卡网格展示与筛选，开发板详情页展示属性与示例列表（按 status 分类、展示更新时间），示例详情页支持 Markdown 排版、图片与代码高亮；第二次迭代主要做 UI/UX 打磨与问题修复（示例标题去重、README 标题重复处理、返回首页入口等）。  
  代码链接：https://github.com/DuoQilai/board-docs-frontend.git

- 产出已在备份仓库提出PR: https://github.com/DuoQilai/ruyisdk-dev-archive/pull/6

- [实例代码](https://github.com/ZihanCheng63/my-repo/blob/main/实例代码.md)

- [Milk-V Duo S 开发板 Hello World 测试报告](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/Report_Duo_s_helloworld.md)

- [cpufetch架构识别](https://github.com/Dr-Noob/cpufetch)）:
  - 用户手册： [LicheePi4A_cpufetch](https://github.com/DuoQilai/ruyisdk-dev-archive/blob/main/examples/cpufetch/LicheePi4A_cpufetch.md)
  - Demo： [Demo_LicheePi4A_cpufetch](https://github.com/DuoQilai/ruyisdk-dev-archive/blob/main/examples/cpufetch/Demo_LicheePi4A_cpufetch)

- [Dhrystone性能测试](https://github.com/Keith-S-Thompson/dhrystone)）:
  - 用户手册： [LicheePi4A_Dhrystone](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Dhrystone/Licheepi4A_Dhrystone.md)
  - Demo： [Demo_LicheePi4A_Dhrystone](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Dhrystone/Demo_Licheepi4A_Dhrystone)

- [llama.cpp Demo](https://wiki.sipeed.com/hardware/zh/lichee/th1520/lpi4a/8_application.html#llama.cpp)）：
  - 用户手册： [LicheePi4A_llama.cpp](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Licheepi4A/llama_cpp_LPi4A.md)
  - Demo： [Demo_llama_cpp](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/llama.cpp/Demo_llama_cpp)

- [在Licheepi4A上使用cpufetch获取CPU信息](https://www.bilibili.com/video/BV1j8wFzSE2x)
- [使用Ruyi工具链编译cpufetch](https://www.bilibili.com/video/BV1fiw7zBE6F)

- [Ruyi 平台下 cpufetch 安装与使用测试报告](https://github.com/DuoQilai/ruyisdk-dev-archive/blob/main/examples/cpufetch/Ruyi%20%E5%B9%B3%E5%8F%B0%E4%B8%8B%20cpufetch%20%E5%AE%89%E8%A3%85%E4%B8%8E%E4%BD%BF%E7%94%A8%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)
  
- tiny-AES-c
  - 用户手册：[使用 RuyiSDK 在 Milk-V Duo256m 上编译 tiny-AES-c 教程](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91%20tiny-AES-c%20%E6%95%99%E7%A8%8B.md)
  - demo：[tiny-AES-c 教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/tiny-AES-c%20%E6%95%99%E7%A8%8B_demo.md)

- zstd
  - 用户手册:[使用 RuyiSDK 在 Milk-V Duo256m 上成功编译 zstd 教程](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E6%88%90%E5%8A%9F%E7%BC%96%E8%AF%91%20zstd%20%E6%95%99%E7%A8%8B.md)
  - demo:[zstd教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/zstd%E6%95%99%E7%A8%8B_demo.md)

- blink
  - 用户手册：[使用 RuyiSDK 在 Milk-V Duo256m 上编译blink教程](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91blink%E6%95%99%E7%A8%8B.md)
  - demo:[blink教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/blink%E6%95%99%E7%A8%8B_demo.md)

#### 1.4 RuyiSDK 文档编写

- [Cavestoryen](https://github.com/qingwan12138/PLCT-WORK/blob/main/March/blog/ruyisdk%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91nxengine-evo%E5%B9%B6%E8%BF%90%E8%A1%8Ccavestoryen.md)
  - 通过ruyisdk虚拟环境从源代码编译和运行 nxengine-evo引擎并运行cavestoryen
  - [RuyiSDK.cn博客网址](https://ruyisdk.cn/t/topic/2539)
- [Sonic Robo Blast 2](https://github.com/qingwan12138/PLCT-WORK/blob/main/March/blog/RuyiSDK%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91Sonic%20Robo%20Blast%202.md)
  - 通过ruyisdk虚拟环境构建运行 Sonic Robo Blast 2(索尼克机器人爆炸2)
  - [RuyiSDK.cn博客网址](https://ruyisdk.cn/t/topic/2579)
- [supertux](https://github.com/qingwan12138/PLCT-WORK/blob/main/March/blog/RuyiSDK%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91supertux.md)
  - 通过ruyisdk虚拟环境从源代码编译和运行 supertux
  - [RuyiSDK.cn博客网址](https://ruyisdk.cn/t/topic/2581)
- [Endless-Sky](https://github.com/qingwan12138/PLCT-WORK/blob/main/March/blog/RuyiSDK%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91endless-sky.md)
  - 通过ruyisdk虚拟环境构建运行 Endless-Sky
- [从零开始的ruyisdk之旅](https://github.com/qingwan12138/PLCT-WORK/blob/main/March/blog/%E4%BB%8E%E9%9B%B6%E5%BC%80%E5%A7%8B%E7%9A%84ruyisdk%E4%B9%8B%E6%97%85.md)
- [OpenRuyi+RuyiSDK](https://github.com/qingwan12138/PLCT-WORK/blob/main/March/blog/openRuyi%2BRuyiSDK.md)
  - 用OpenRuyi的rootfs与RuyiSDK交叉编译
- [busybox构建文档](https://github.com/ruyisdk-test/test-working/tree/main/jxy687/March%202026/busybox/Busybox.md)
  - 使用 RuyiSDK 创建虚拟环境并构建项目，成功运行
  - 项目源代码 [busybox](https://busybox.net/downloads/busybox-1.36.1.tar.bz2)
- [Update vscode 0.1.2 test status #243](https://github.com/ruyisdk/wechat-articles/pull/243)

#### 1.5 RuyiSDK网站

- [misc: add mermaid support #385](https://github.com/ruyisdk/ruyisdk-website/pull/385)
- [misc: add mermaid support #385](https://github.com/ruyisdk/ruyisdk-website/pull/385)
- [pages: fix index background #388](https://github.com/ruyisdk/ruyisdk-website/pull/388)
- [pages(index): adjust main display width #389](https://github.com/ruyisdk/ruyisdk-website/pull/389)
- [pages: fix navbar dropdown shadow #390](https://github.com/ruyisdk/ruyisdk-website/pull/390)
- [pages: replace icon with tabler icon #391](https://github.com/ruyisdk/ruyisdk-website/pull/391)
- [pages: better homepage hero, footer, and community sections with locale-aware links and updated calls-to-action #397](https://github.com/ruyisdk/ruyisdk-website/pull/397)
- [pages(index): better ruyiinlive component #399](https://github.com/ruyisdk/ruyisdk-website/pull/399)
- [pages(index): new content for cardnews #400](https://github.com/ruyisdk/ruyisdk-website/pull/400)
- [pages(index): replace cardnews images #401](https://github.com/ruyisdk/ruyisdk-website/pull/401)
- [pages(index): refactor CardNews #403](https://github.com/ruyisdk/ruyisdk-website/pull/403)
- [pages(about): fix image loading failure #404](https://github.com/ruyisdk/ruyisdk-website/pull/404)
- [pages(index): better CardNews color #409](https://github.com/ruyisdk/ruyisdk-website/pull/409)
- [pages(index): add border between MainDisplay and RuyiInLive #410](https://github.com/ruyisdk/ruyisdk-website/pull/410)
- [pages(index): add partner section and better section gap #411](https://github.com/ruyisdk/ruyisdk-website/pull/411)
- [pages(news): text size fine-tune #413](https://github.com/ruyisdk/ruyisdk-website/pull/413)
- [misc: remove --site-container-width #414](https://github.com/ruyisdk/ruyisdk-website/pull/414)
- [pages(contributors): better image loading effect #415](https://github.com/ruyisdk/ruyisdk-website/pull/415)
- [pages(navbar): better navbar #422](https://github.com/ruyisdk/ruyisdk-website/pull/422)
- [pages(navbar): adjust navbar sidebar width and color #423](https://github.com/ruyisdk/ruyisdk-website/pull/423)
- [pages(navbar): navbar sidebar hamburger button animation #424](https://github.com/ruyisdk/ruyisdk-website/pull/424)
- [pages(navbar): navbar sidebar wipe effect #425](https://github.com/ruyisdk/ruyisdk-website/pull/425)
- [pages(index): terminal components hide scrollbar #427](https://github.com/ruyisdk/ruyisdk-website/pull/427)
- [Migrate site to tailwind #354](https://github.com/ruyisdk/ruyisdk-website/pull/354)
- [Add issue data in contributors page (issue #307) #395](https://github.com/ruyisdk/ruyisdk-website/pull/395)
- [Refactor about page #396](https://github.com/ruyisdk/ruyisdk-website/pull/396)
- [Index news three cards layout #407](https://github.com/ruyisdk/ruyisdk-website/pull/407)
- [Fix height calculation in /about page #408](https://github.com/ruyisdk/ruyisdk-website/pull/408)

#### 1.6 RuyiSDK.cn 社区

- [XSCC 快速上手：基于 RuyiSDK 的游戏编译](https://ruyisdk.cn/t/topic/2562)
- [利用 RuyiSDK 玩转 RISC-V 版洞窟物语](https://ruyisdk.cn/t/topic/2563)
- [使用 RuyiSDK 创建虚拟环境并编译太空射击游戏](https://ruyisdk.cn/t/topic/2565)
- [使用 RuyiSDK 创建虚拟环境编译并游玩 PVZ](https://ruyisdk.cn/t/topic/2583)
- [使用 RuyiSDK 创建虚拟环境编译并游玩 Flappy Bird](https://ruyisdk.cn/t/topic/2589)
- [基于 RuyiSDK 虚拟环境编译 2048 并在 QEMU 运行 RISC-V 可执行文件](https://ruyisdk.cn/t/topic/2520)
- [XSCC 快速上手：基于 RuyiSDK 的游戏编译](https://ruyisdk.cn/t/topic/2591)
- [基于 RuyiSDK 搭建虚拟环境，通过配置 sysroot、安装并编译 SDL 系列等依赖，完成太空射击游戏 SDLShooter 的交叉编译与模拟运行](https://ruyisdk.cn/t/topic/2565)
- [XSCC 快速上手：基于 RuyiSDK 的游戏编译](https://ruyisdk.cn/t/topic/2583)
- [基于 RuyiSDK 搭建虚拟环境，通过配置 sysroot、安装并编译 SDL 系列等依赖，完成太空射击游戏 SDLShooter 的交叉编译与模拟运行](https://ruyisdk.cn/t/topic/2589)
  
#### 1.7 RuyiSDK实习生招募

- [P119\_cyu.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month31/P119_cyu.md)
- [P119\_luz.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month31/P119_luz.md)

#### 1.8 RuyiSDK双周报

- [P119_cuh.md](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month33/P119_cuh.md)
- [P119_hl.md](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month33/P119_hl.md)

#### 1.9 RISC-V 欧洲峰会

- [扩展摘要 From Fragmentation to Systematization A Standardized Quality Selection and Systematic Reconstruction Approach for RISC-V Courses](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/From%20Fragmentation%20to%20Systematization%20A%20Standardized%20Quality%20Selection%20and%20Systematic%20Reconstruction%20Approach%20for%20RISC-V%20Courses.pdf)

- [RuyiSDK Package Manager - A Unified Package Management and Development Environment for RISC-V](https://cfp.riscv-europe.org/eu-summit-2026/talk/review/GXE9CB8EZPTVJTKQKNZDHH3VUMKLTBM9)

- [Scenario-Oriented Differentiated Maintenance for RISC-V Support Matrix](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/Scenario-Oriented_Differentiated_PGZ2FPl.pdf)

### 2. RuyiAI

- [set black line-lenght back to 80](https://github.com/buddy-compiler/buddy-mlir/pull/709)
- [Add pre-commit to CI](https://github.com/buddy-compiler/buddy-mlir/pull/708)
- [Fix cmake install buddy_mlir](https://github.com/buddy-compiler/buddy-mlir/pull/711)
- [Include llvm/buddy install tarballs in release artifacts](https://github.com/buddy-compiler/buddy-mlir/pull/713)
- [CI fix build-manylinux.yml syntax error](https://github.com/buddy-compiler/buddy-mlir/pull/715) 
- [DOCS Add Install document](https://github.com/RuyiAI-Stack/ruyiai-stack.github.io/pull/20) 
- [Add CI and pre-commit](https://github.com/RuyiAI-Stack/ruyiai-stack.github.io/pull/21)
- [DOCS Update install PyTorch for RISC-V](https://github.com/RuyiAI-Stack/ruyiai-stack.github.io/pull/22)

### 3. RISC-V 编译工具链测试

项目演示展示

### 4. RISC-V 操作系统支持矩阵

- [开发板资源梳理](https://www.kdocs.cn/l/cl3WweaKB9XO)

- RevyOS LPi4A 版本测试报告 
    PR 链接：[DuoQilai/support-matrix#2](https://github.com/DuoQilai/support-matrix/pull/2)
      
### 5. SAIL和ACT

#### 5.1 SAIL和ACT开发

- SAIL
  - 更新 PR <https://github.com/riscv/sail-riscv/pull/765> Add Zilsd/Zclsd Support
  - 审查 PR <https://github.com/riscv/sail-riscv/pull/1556> Refactor CSR access checking to handle virtual-instruction exceptions.
  - [sail#pr1617](https://github.com/rems-project/sail/pull/1617)（进行中)  – Lean：修复了浮点库中 fp_bits 编译被跳过的问题。我尝试添加了一些修改，但目前被阻塞，因为 Lean 4 依赖于 rems-project/lean-sail。
  - [lean-sail#pr5](https://github.com/rems-project/lean-sail/pull/5)（进行中） – 这是 sail 项目的一个子部分。我们需要先将其合并到rems-projects/lean-sail中，第一部分才能正常工作。为 Sigma 类型添加了 Inhabited 和 BEq 实例。
  - [#1622](https://github.com/riscv/sail-riscv/pull/1622) : 提交PR, 将当前冗余的 `Memory_Exception` 的处理逻辑合并到 `Trap`的处理逻辑中
  - [#1609](https://github.com/riscv/sail-riscv/pull/1609) : 提交PR, 将`trace-regs`控制的日志输出分为不同类别的寄存器日志输出
  - [#1593](https://github.com/riscv/sail-riscv/pull/1593) : 提交PR, 添加 QEMU 新添加的未被批准的扩展 Zbr
  - [riscv/sail-riscv#1581](https://github.com/riscv/sail-riscv/pull/1581) Add unratified Zvfbfa extension (Draft)
    - 主要工作包括：
      - 补齐 BF16 softfloat 接口，以及 Sail / Lean / Lem 对接；
      - 抽取 BF16/FP 公共 helper，统一算术、比较、widening、conversion 路径；
      - 替换分散的 ad hoc BF16 处理逻辑，统一 scalar/helper 使用方式；
      - 收紧 `altfmt` 的合法行为边界，修正 `vsetivli` / `vtype` 相关编码与语义；
      - 修正 `Zvfbfa` 与 `Zfbfmin` 的依赖关系，以及部分非法指令行为。
    - 工作量：
      - PR 总体：`20 files changed, +714/-183`
      - 本月第二次 commit：`16 files changed, +536/-381`
    - 整体属于较大工作量整改与重构工作，涉及 C emulator、Sail model、bfloat16 工具层和证明支撑接口。
  - [riscv/riscv-arch-test#1168](https://github.com/riscv/riscv-arch-test/pull/1168) Add unratified Zvabd extension test

- ACT
  - pr#1060 [add Zibi test](https://github.com/riscv/riscv-arch-test/pull/1060)

#### 5.2 技术分享和知识储备

技术分享：
  - [实习成果展示.pdf](https://github.com/TinyuengKwan/plct_works/tree/main/report/实习成果展示.pdf)
  - [ACT框架下，为非特权指令添加测试套件](https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2026-03-ACT4%E6%A1%86%E6%9E%B6%E4%B8%8B%E6%B7%BB%E5%8A%A0%E6%96%B0%E6%B5%8B%E8%AF%95%E5%A5%97%E4%BB%B6.md)
  - [实习成果展示](https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2026-03-%E5%AE%9E%E4%B9%A0%E6%88%90%E6%9E%9C%E5%B1%95%E7%A4%BA.md)

#### 5.3 SAIL会议

- 参加 tech-golden-model meeting [`03.16`, `03.30`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 参加东亚双周会 0305，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1UMRFOpRX47gO3zhshyqDmfgfgQ6B9LZ_7c6G_xN5PBc/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0319，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1VquRhGyJbqzo3fDxb8seyqxRCtpjxHoXqmm93heHk7I/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

- 2026年 RISC-V 欧洲峰会 
  - 扩展摘要 An Efficient Approach to Apply the RISC-V Sail Model to Chip Verification [PDF](https://github.com/trdthg/plct/blob/main/doc/sail/europe-summit-2026/An%20Efficient%20Approach%20to%20Apply%20the%20RISC-V%20Sail%20Model%20to%20Chip%20Verification.pdf)
  - 扩展摘要 Sail-RISCV-WASM A Browser-Native RISC-V Toolchain and Debugging Workbench [PDF](https://github.com/trdthg/plct/blob/main/doc/sail/europe-summit-2026/Sail-RISCV-WASM%20A%20Browser-Native%20RISC-V%20Toolchain%20and%20Debugging%20Workbench.pdf)

### 6. 职工

#### 6.1 蔡玮霖

- 测试 Ruyi 0.47.0-beta.20260316 提交测试报告
  - [!92 Add v0.47.0 test report](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/92)
- ruyisdk-website 仓库参与和审核提交 23 个 pr
  - [misc: add mermaid support #385](https://github.com/ruyisdk/ruyisdk-website/pull/385)
  - [misc: add mermaid support #385](https://github.com/ruyisdk/ruyisdk-website/pull/385)
  - [pages: fix index background #388](https://github.com/ruyisdk/ruyisdk-website/pull/388)
  - [pages(index): adjust main display width #389](https://github.com/ruyisdk/ruyisdk-website/pull/389)
  - [pages: fix navbar dropdown shadow #390](https://github.com/ruyisdk/ruyisdk-website/pull/390)
  - [pages: replace icon with tabler icon #391](https://github.com/ruyisdk/ruyisdk-website/pull/391)
  - [pages: better homepage hero, footer, and community sections with locale-aware links and updated calls-to-action #397](https://github.com/ruyisdk/ruyisdk-website/pull/397)
  - [pages(index): better ruyiinlive component #399](https://github.com/ruyisdk/ruyisdk-website/pull/399)
  - [pages(index): new content for cardnews #400](https://github.com/ruyisdk/ruyisdk-website/pull/400)
  - [pages(index): replace cardnews images #401](https://github.com/ruyisdk/ruyisdk-website/pull/401)
  - [pages(index): refactor CardNews #403](https://github.com/ruyisdk/ruyisdk-website/pull/403)
  - [pages(about): fix image loading failure #404](https://github.com/ruyisdk/ruyisdk-website/pull/404)
  - [pages(index): better CardNews color #409](https://github.com/ruyisdk/ruyisdk-website/pull/409)
  - [pages(index): add border between MainDisplay and RuyiInLive #410](https://github.com/ruyisdk/ruyisdk-website/pull/410)
  - [pages(index): add partner section and better section gap #411](https://github.com/ruyisdk/ruyisdk-website/pull/411)
  - [pages(news): text size fine-tune #413](https://github.com/ruyisdk/ruyisdk-website/pull/413)
  - [misc: remove --site-container-width #414](https://github.com/ruyisdk/ruyisdk-website/pull/414)
  - [pages(contributors): better image loading effect #415](https://github.com/ruyisdk/ruyisdk-website/pull/415)
  - [pages(navbar): better navbar #422](https://github.com/ruyisdk/ruyisdk-website/pull/422)
  - [pages(navbar): adjust navbar sidebar width and color #423](https://github.com/ruyisdk/ruyisdk-website/pull/423)
  - [pages(navbar): navbar sidebar hamburger button animation #424](https://github.com/ruyisdk/ruyisdk-website/pull/424)
  - [pages(navbar): navbar sidebar wipe effect #425](https://github.com/ruyisdk/ruyisdk-website/pull/425)
  - [pages(index): terminal components hide scrollbar #427](https://github.com/ruyisdk/ruyisdk-website/pull/427)
- ruyisdk-website 仓库合作 4 个 pr
  - [Migrate site to tailwind #354](https://github.com/ruyisdk/ruyisdk-website/pull/354)
  - [Add issue data in contributors page (issue #307) #395](https://github.com/ruyisdk/ruyisdk-website/pull/395)
  - [Refactor about page #396](https://github.com/ruyisdk/ruyisdk-website/pull/396)
  - [Index news three cards layout #407](https://github.com/ruyisdk/ruyisdk-website/pull/407)
- ruyisdk-website 仓库审核 1 个 pr
  - [Fix height calculation in /about page #408](https://github.com/ruyisdk/ruyisdk-website/pull/408)
- wechat-articles 仓库提交 1 个 pr
  - [Update vscode 0.1.2 test status #243](https://github.com/ruyisdk/wechat-articles/pull/243)
- 组织和审核实习生 ruyisdk.cn 帖子
  - [XSCC 快速上手：基于 RuyiSDK 的游戏编译](https://ruyisdk.cn/t/topic/2562)
  - [利用 RuyiSDK 玩转 RISC-V 版洞窟物语](https://ruyisdk.cn/t/topic/2563)
  - [使用 RuyiSDK 创建虚拟环境并编译太空射击游戏](https://ruyisdk.cn/t/topic/2565)
  - [使用 RuyiSDK 创建虚拟环境编译并游玩 PVZ](https://ruyisdk.cn/t/topic/2583)
  - [使用 RuyiSDK 创建虚拟环境编译并游玩 Flappy Bird](https://ruyisdk.cn/t/topic/2589)
- 实习生面试
  - [P119_cuh.md](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month33/P119_cuh.md)
  - [P119_hl.md](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month33/P119_hl.md)
  
#### 6.2 阎明铸

##### 6.2.1 Sail

- 更新 PR <https://github.com/riscv/sail-riscv/pull/765> Add Zilsd/Zclsd Support
- 审查 PR <https://github.com/riscv/sail-riscv/pull/1556> Refactor CSR access checking to handle virtual-instruction exceptions.

##### 6.2.2 Ruyi AI

- 提交 PR <https://github.com/buddy-compiler/buddy-mlir/pull/709> [style] set black line-lenght back to 80
- 提交 PR <https://github.com/buddy-compiler/buddy-mlir/pull/708> Add pre-commit to CI
- 提交 PR <https://github.com/buddy-compiler/buddy-mlir/pull/711> Fix cmake install buddy_mlir
- 提交 PR <https://github.com/buddy-compiler/buddy-mlir/pull/713> [package] Include llvm/buddy install tarballs in release artifacts
- 提交 PR <https://github.com/buddy-compiler/buddy-mlir/pull/715> [ci] fix build-manylinux.yml syntax error
- 提交 PR <https://github.com/RuyiAI-Stack/ruyiai-stack.github.io/pull/20> [DOCS] Add Install document
- 提交 PR <https://github.com/RuyiAI-Stack/ruyiai-stack.github.io/pull/21> Add CI and pre-commit
- 提交 PR <https://github.com/RuyiAI-Stack/ruyiai-stack.github.io/pull/22> [DOCS] Update install PyTorch for RISC-V

##### 6.2.3 会议

- 参加 tech-golden-model meeting [`03.16`, `03.30`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 参加东亚双周会 0305，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1UMRFOpRX47gO3zhshyqDmfgfgQ6B9LZ_7c6G_xN5PBc/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0319，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1VquRhGyJbqzo3fDxb8seyqxRCtpjxHoXqmm93heHk7I/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加玄铁大会，获得年度社区生态贡献奖

##### 6.2.4 RuyiSDK和工具链

- 提交 Issue <https://github.com/ruyisdk/packages-index/issues/180> 创建虚拟环境后里面没有 qemu-system

- 准备和参加项目评估会议演示

#### 6.3 张馥媛

##### 6.3.1 RuyiSDK 示例代码库建设

-  RuyiSDK 示例库文档展示的前端页面
	- 仓库链接： [https://github.com/DuoQilai/board-docs-frontend.git](https://github.com/DuoQilai/board-docs-frontend.git)

- 组织和审核示例代码库建设
  - 开发板定制开发项目
    - Licheepi4A 示例库扩充
      - [在 LicheePi4A_上运行 cpufetch 示例](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/cpufetch/LicheePi4A_cpufetch.md)
        - 视频： [【RISC-V架构识别】在Licheepi4A上使用cpufetch获取CPU信息](https://www.bilibili.com/video/BV1j8wFzSE2x)
        - 视频： [【RuyiSDK示例】使用Ruyi工具链编译cpufetch](https://www.bilibili.com/video/BV1fiw7zBE6F)
        - 测试报告：[Ruyi 平台下 cpufetch 安装与使用测试报告](https://github.com/DuoQilai/ruyisdk-dev-archive/blob/main/examples/cpufetch/Ruyi%20%E5%B9%B3%E5%8F%B0%E4%B8%8B%20cpufetch%20%E5%AE%89%E8%A3%85%E4%B8%8E%E4%BD%BF%E7%94%A8%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)
        - demo：[Demo_LicheePi4A_cpufetch](https://github.com/DuoQilai/ruyisdk-dev-archive/blob/main/examples/cpufetch/Demo_LicheePi4A_cpufetch)
      - [在 LicheePi 4A 上运行 `tinn` 示例](https://github.com/EnzoDing-rgb/plct_works/blob/main/reports/licheepi4a_tinn.md)
      - [在 LicheePi4A_上运行 Dhrystone 示例](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Dhrystone/Licheepi4A_Dhrystone.md)
        - demo：[Demo_LicheePi4A_Dhrystone](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Dhrystone/Demo_Licheepi4A_Dhrystone)
      -  [在 LicheePi4A 上运行 llama.cpp 示例](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Licheepi4A/llama_cpp_LPi4A.md)
        - demo：[Demo_llama_cpp](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/llama.cpp/Demo_llama_cpp)
    - Duo256 示例库扩充
      - [在 Milk-V Duo256m 上运行 tiny-AES-c 示例](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91%20tiny-AES-c%20%E6%95%99%E7%A8%8B.md)
        - demo：[tiny-AES-c 教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/tiny-AES-c%20%E6%95%99%E7%A8%8B_demo.md)
      - [在 Milk-V Duo256m 上运行 zstd 示例](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E6%88%90%E5%8A%9F%E7%BC%96%E8%AF%91%20zstd%20%E6%95%99%E7%A8%8B.md)
        - demo：[zstd教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/zstd%E6%95%99%E7%A8%8B_demo.md)
      - [在 Milk-V Duo256m 上运行 blink 示例](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91blink%E6%95%99%E7%A8%8B.md)
        - demo：[blink教程_demo](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/blink%E6%95%99%E7%A8%8B_demo.md)
    - DuoS 示例库扩充
      - [在 Milk-V DuoS 上运行 helloworld 示例](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/Report_Duo_s_helloworld.md)
    - Triton 在 RISC-V 平台（LicheePi 4A）的静态编译调研：
      1. 已经成功打通了 ZCC 交叉编译工具链，通过测试命令，已经确认编译器能正常生成支持向量扩展的指令。
      2. 在尝试构建 Triton 后端插件时，发现教程中展示的 third_party/riscv 源代码目录在官方 Triton 仓库中并不存在。教程中的 RISC-V 后端（包含 compiler.py 和 driver.py 等核心逻辑）是针对 ZCC 编译器定制开发的非公开代码。
    - [新JD](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/JD.md)
    - [LicheePi 4A平台 运行Home Assistant 视频](https://www.bilibili.com/video/BV1UxwYzhECo/)
    - [LicheePi 4A平台 运行Home Assistant](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/Home_Assistant.md)

- RuyiSDK开发资源梳理和资源申请（参与、组织和审核）
	- [开发板资源梳理](https://www.kdocs.cn/l/cl3WweaKB9XO)
	- [New Package Request: cpufetch for Architecture Identification](https://github.com/ruyisdk/packages-index/issues/168)
	- [New Package Request: Dhrystone CPU Benchmark](https://github.com/ruyisdk/packages-index/issues/170)
	- [Adapt RuyiSDK + Milk-V Duo256m (riscv64) to improve zstd source compilation](https://github.com/ruyisdk/packages-index/issues/171)
	- [New Package Request: wiringx GPIO Library](https://github.com/ruyisdk/packages-index/issues/172)
	- [New Package Request: SDL2 (Development Libraries)](https://github.com/ruyisdk/packages-index/issues/173)
	- [New Package Request: Go Toolchain](https://github.com/ruyisdk/packages-index/issues/174)
	- [New Package Request: Xuantie GNU Toolchain](https://github.com/ruyisdk/packages-index/issues/175)
	- [New Package Request: Nuclei RISC-V GNU Toolchain#176](https://github.com/ruyisdk/packages-index/issues/176)
	-  [New Package Request: Nuclei LLVM Project#177](https://github.com/ruyisdk/packages-index/issues/177)
	- [New Package Request: Rust Programming Language#178](https://github.com/ruyisdk/packages-index/issues/178)
	- [New Package Request: Allegro 5.2.9#179](https://github.com/ruyisdk/packages-index/issues/179)

- RuyiSDK 技术测试报告（组织和审核）
	- [Ruyi SDK 测试报告](https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK.md)
	- [Ruyi SDK IDE Eclipse 测试报告](https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK%20IDE%20Eclipse.md)
	- [Ruyi SDK IDE VS 测试报告](https://github.com/ZihanCheng63/my-repo/blob/main/Ruyi%20SDK%20IDE%20VS.md)
	- [实例代码](https://github.com/ZihanCheng63/my-repo/blob/main/%E5%AE%9E%E4%BE%8B%E4%BB%A3%E7%A0%81.md)

##### 6.3.2 支持矩阵
- 审核RevyOS LPi4A 版本测试报告 
    PR 链接：[DuoQilai/support-matrix#2](https://github.com/DuoQilai/support-matrix/pull/2)

##### 6.3.3 2026 RISC-V 欧洲峰会投稿

- 扩展摘要
	- [Scenario-Oriented Differentiated Maintenance for RISC-V Support Matrix](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/Scenario-Oriented_Differentiated_PGZ2FPl.pdf)

## 参考链接
