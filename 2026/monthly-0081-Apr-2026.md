# RISC-V 软件生态进展 · 第 81 期·2026 年 4 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

页面更新

+ 修复首页终端组件的滚动条和滑动问题
+ 顶栏下拉列表动画
+ 添加新的合作伙伴到相应板块

PR 列表

+ [pages(index): better terminal scroll #428](https://github.com/ruyisdk/ruyisdk-website/pull/428)
+ [pages(navbar): better dropdown menu transform #430](https://github.com/ruyisdk/ruyisdk-website/pull/430)
+ [pages(footer): add openRuyi projects to ecosystem section #439](https://github.com/ruyisdk/ruyisdk-website/pull/439)
+ [pages(index): add jeandle to partner section and better xuantie logo #440](https://github.com/ruyisdk/ruyisdk-website/pull/440)

## V8 / Chromium

## Spidermonkey / Firefox

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/29977 (8378888: jdk/incubator/vector/Float16OperationsBenchmark.java uses wrong package name)
- https://github.com/openjdk/jdk/pull/30153 (8379564: Hotspot fails to build with gcc 14 after JDK-8378804)
- https://github.com/openjdk/jdk/pull/30020 (8294152: AArch64: frame::id() and frame::is_older() broken for interpreted frames with large max_stack)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/29986 (8378905: RISC-V: fastdebug build fails after JDK-8377554)
- https://github.com/openjdk/jdk/pull/29836 (8377148: Remove obsolete functions Matcher::is_spillable_arg() and Matcher::interpreter_frame_pointer_reg())
- https://github.com/openjdk/jdk/pull/30104 (8379372: Enable some vector algorithms IR matching tests for RISC-V)
- https://github.com/openjdk/jdk/pull/30059 (8378559: Add setting of captured states like errno)
- https://github.com/openjdk/jdk/pull/30107 (8378985: [lworld] serviceability/sa/TestJhsdbJstackMixedWithXComp.java#xcomp fails with just Test failed!)
- https://github.com/openjdk/jdk/pull/30136 (8379464: Enable missing stack walking test via jtreg requires for RISC-V)
- https://github.com/openjdk/jdk/pull/30106 (8379260: C2: Separate volatile barrier and full barrier)
- https://github.com/openjdk/jdk/pull/30179 (8379710: Enable vector if-conversion IR matching tests for RISC-V)
- https://github.com/openjdk/jdk/pull/30210 (8367399: C2 SuperWord: add IR rules for MemorySegment cases from JDK-8329077)
- https://github.com/openjdk/jdk/pull/30250 (8380083: Enable some vector mask cast IR matching tests for RISC-V)

3. Proposed JDK-25u backport PRs:
- https://github.com/openjdk/jdk25u-dev/pull/332 (8378888: jdk/incubator/vector/Float16OperationsBenchmark.java uses wrong package name)
- https://github.com/openjdk/jdk25u-dev/pull/339 (8378810: Enable missing FFM test via jtreg requires for RISC-V)
- https://github.com/openjdk/jdk25u-dev/pull/369 (8379464: Enable missing stack walking test via jtreg requires for RISC-V)

## Go

## GNU Toolchain

## LLVM Team

## MLIR / Buddy Compiler

## opensbi

## 罗云翔测试团队
（包含 SAIL 和 ACT 测试部分）

本月完成 RuyiSDK 0.48.0-beta.20260423 版本在 20 余个发行版、3 种架构下的全面测试与发版，持续完善自动化测试工具与示例库生态。在 RuyiAI 方向提交 16 个 PR，完成 buddy-mlir v0.0.3 发布。在 SAIL 方向提交并合并多个 PR，推进 IME、smpmpmt 等扩展实现。团队 4 篇 poster 入选 2026 RISC‑V 欧洲峰会，并积极参与中国科学院公众科学日展示。社区协作方面，完成多项文档、网站优化及基础设施重构。

1. RuyiSDK

   1.1 RuyiSDK 0.48.0-beta.20260423 版本测试  
   - 测试覆盖 Debian（12/13/sid）、Ubuntu（22.04/24.04）、openEuler（24.03sp1/24.03sp2/25.03）、Fedora（42/43）、Deepin（23/25）、OpenCloudOS 9.4、Archlinux 等主流发行版，共计 20 余个版本。  
   - 在 x86_64、aarch64、riscv64 三种架构上完成验证，生成 30 余份测试报告。  
   - 对 Eclipse 插件 v0.1.3 进行系统性测试，新增并跟踪 4 个缺陷；VSCode 插件遗留缺陷持续跟进。  
   - 包管理器、文档、IDE 插件无新增严重缺陷，版本符合发版标准。

   1.2 RuyiSDK 测试与开发工具  
   - 完成 `ruyi` 测试框架从 `lit` 到 `pytest` 的全面迁移（21 commits，+2853 行），提升可维护性。  
   - 为 `packages-index` 新增 Armbian 多款开发板（含 minimal/desktop 拆分）的 manifest，修复镜像源切换逻辑与版本同步机制。  
   - 优化 `riko-bot`：支持日志持久化、版本差异双维度计算、-trunk 版本文件名修复等。

   1.3 RuyiSDK 示例库与开发指南  
   - 为 LicheePi 4A、VisionFive2Lite、Duo256/Duo S、Mars 等多款开发板编写 20+ 示例教程，涵盖 cpufetch、GStreamer、OpenCV、YOLO、Coremark、2048 游戏等。  
   - 完成示例库前端站点第二轮迭代，支持开发板导航、搜索，并与 VSCode/Eclipse 插件实现消息联动。  
   - 输出多篇技术博客（Endless‑Sky 游戏编译、Busybox 实践等）及视频演示。  
   - 梳理并提交 Go Toolchain、wiringX 等生态资源对接需求。

   1.4 RuyiSDK 网站与文档  
   - 向 `ruyisdk-website` 提交 4 个 PR（终端滚动优化、下拉菜单、页脚生态链接、合作伙伴展示），并审核 4 个 PR。  
   - 重写“快速开始”文档（两版草案），新增 Ruyi 包管理器、ruyi‑qemu+openruyi 接入自制 sysroot 等指南。  
   - 社区发布《利用 RuyiSDK 玩转 RISC‑V 版 Endless‑Sky》《RuyiSDK 实践指南：编译运行 Busybox》等文章。

2. RuyiAI  
   - 向 `buddy-mlir` 仓库提交 16 个 PR，涵盖 CI 增强（RISC‑V 64、ARM64 macOS 测试）、release 自动化、example 修复等。  
   - 正式发布 BUDDY MLIR 0.0.3，提供 runtime CLI 与打包版本。  
   - 参与公众科学日展示 RuyiAI 在 RISC‑V 硬件上的 PyTorch 性能对比。

3. SAIL/ACT  
   - 向 `sail-riscv` 合并 2 个关键 PR：统一 Memory_Exception 与 Trap 处理逻辑（#1622）、简化 xret 异常处理（#1672）。  
   - 新提交 PR #1665 实现 `smpmpmt` 扩展，持续推进 IME 扩展与 `smwid` 扩展。  
   - 参加技术黄金模型会议及东亚双周会，完成技术分享与进展汇报。

4. 2026 RISC‑V 欧洲峰会  
   - 团队 4 篇 poster 入选，主题涵盖：RuyiSDK 包管理器、Sail 模型用于芯片验证、Sail‑RISCV‑WASM 浏览器工具链、RISC‑V 课程标准化重构。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.48.0-beta.20260423 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/README.md)
    - [Debian12 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Debian12 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260421/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260421/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu24.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Ubuntu24.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora42 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Fedora42_aarch64_测试结果.md)
    - [Fedora43 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Fedora43_x86_64_测试结果.md)  
    - [Fedora43 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Fedora43_aarch64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Deepin25 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Deepin25_x86_64_测试结果.md)
    - [Deepin25 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Deepin25_riscv64_测试结果.md)
    - [Deepin25 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Deepin25_aarch64_测试结果.md)
    - [OpenCloudOS 9.4 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)
    - [OpenCloudOS 9.4 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_OpenCloudOS_aarch64_测试结果.md)
    - [Archlinux x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260421/RUYI_包管理_Archlinux_x86_64_测试结果.md)

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
        本版本同步发版的 Eclipse 插件测试[报告](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/tree/v0.1.3)。

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

        新增缺陷

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [ruyi venv 没有显示虚拟环境名称，具体名称只会在sysroot路径列表出现 #151](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/151)   | 建议 |   |
        | [ruyi-venv中的vnev path需要手动点击右侧列表，显示项目路径 #152](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/152) | 建议 |  |
        | [ruyi-venv名称可以默认设置为ruyi-venv-profile属性 #153](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/153) | 建议 |  |
        | [eclipse中版本检测中升级ruyi包管理器，显示由于不支持utf8报错 #154](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/154) | 建议 |  |

      - RuyiSDK VSCode IDE 测试
        本版本无同步发布的 VSCode 插件。

        本版本同步发布的 VSCode 插件测试[报告](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/tree/v0.1.3)。

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

        新增缺陷：

        | 缺陷 | 问题等级 | 判定依据 |
        | --- | ---- | ----- |
        | [bash-completion: not work properly when running ruyi for the first time #452](https://github.com/ruyisdk/ruyi/issues/452) | 一般 | 在边缘情况才会遇到 |
        | [ruyi version: show welcome message before print ruyi version #453](https://github.com/ruyisdk/ruyi/issues/453) | 一般 | 在边缘情况才会遇到 |
        | [ruyi extract --extract-without-subdir: does not print destination directory properly #454](https://github.com/ruyisdk/ruyi/issues/454) | 一般 | 在边缘情况才会遇到 |
    
    - 测试结论
      - 本版本包含遗留的严重缺陷，均按照修复时间表修复中；
      - 本版本包含新增的一般缺陷，均有修复时间表；

      RuyiSDK v0.48.0-beta.20260423 版本符合出口判定标准，准予发版。

    - 资源
      - [本版本 litester 测试程序](https://github.com/ruyisdk-test/ruyi-litester/tree/485453f775f81594bec55a0ba0581278b0fe2add)

- packages-index 仓库issue
  - [milkv-duo profile does not specify quirk xthead #181](https://github.com/ruyisdk/packages-index/issues/181)

- ruyi 仓库issue
  - [ruyi 0.48.0-beta.20260421 cannot run on debian bookworm #447](https://github.com/ruyisdk/ruyi/issues/447)
  - [ruyi 0.48.0-beta.20260421 see RequestsDependencyWarning: Unable to find acceptable character detection dependency #448](https://github.com/ruyisdk/ruyi/issues/448)
  - [bash-completion: not work properly when running ruyi for the first time #452](https://github.com/ruyisdk/ruyi/issues/452)
  - [ruyi version: show welcome message before print ruyi version #453](https://github.com/ruyisdk/ruyi/issues/453)
  - [ruyi extract --extract-without-subdir: does not print destination directory properly #454](https://github.com/ruyisdk/ruyi/issues/454)
  - [Issue 438](https://github.com/ruyisdk/ruyi/issues/438)
    - 上游qemu版本较低，不支持rv23
  - [Issue 455](https://github.com/ruyisdk/ruyi/issues/455)
    - Ruyi venv 中--copy-sysroot-from-dir命令权限问题

- ruyi eclipse 仓库issue
  - [Issue 154](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/154)
    - eclipse中版本检测中升级ruyi包管理器，显示由于不支持utf8报错
  - [Issue 153](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/153)
    - Ruyi-venv名称可以默认设置为ruyi-venv-profile属性
  - [Issue 152](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/152)
    - Ruyi-venv中的vnev path需要手动点击右侧列表，显示项目路径
  - [Issue 151](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/151)
    - Ruyi Venv 没有显示虚拟环境名称，具体名称只会在sysroot路径列表出现
  - [Issue 83](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/83)
    - name和id字节可以正常的顺序或者逆序排列，但是针对variants字节的顺序和逆序排列方式还是乱的
  - [Profiles 列表解析中文 #109](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/109)，[虚拟环境删除后项目目录更新 #99](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/99)等

- ruyi vscode 仓库issue
  - [Issue 144](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/144)
    - Ruyi-venv创建过程中配置sysroot选项中输入非法字符仍可正常配置sysroot
  - [Issue 136](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/136)
    - vscode插件更新后通过.vsix重新安装插件后存在缓存问题，仍是上个版本内容，建议加个重启vscode弹窗
  - [Issue 137](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/137) 
    - vscode插件的build project按钮在启动虚拟环境后会调用系统编译器，编译为x86架构
  - [Issue 115](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/115)
    - 同时安装ruyi最新版和其他版本时，启动旧版ruyi会提示更新ruyi最新版。(貌似需要更新vscode最新版)
  - [Issue 144](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/144)
    - Ruyi-venv创建过程中配置sysroot选项中输入非法字符仍可正常配置sysroot

- eclipse v0.1.3报告[PR 7](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/7)和[v0.1.3 report](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-April/eclipse%E6%B5%8B%E8%AF%95/v0.1.3%20eclipse%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)

- vscode v0.1.3-beta[PR 9](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/9)

#### 1.2 RuyiSDK 开发和测试工具开发

- packages-index 仓库
  - [plugins: specify xthead quirk for milkv-duo profile #182](https://github.com/ruyisdk/packages-index/pull/182)
  - [board-image/armbian-musepipro: add new packages #183](https://github.com/ruyisdk/packages-index/pull/183)
  - [board-image/armbian-orangepirv2-desktop: add new packages #184](https://github.com/ruyisdk/packages-index/pull/184)
  - [board-image/armbian-orangepirv2-minimal: add new packages #185](https://github.com/ruyisdk/packages-index/pull/185)
  - [board-image/armbian-uefi-riscv64-desktop: add new packages #186](https://github.com/ruyisdk/packages-index/pull/186)
  - [board-image/armbian-uefi-riscv64-minimal: add new packages #187](https://github.com/ruyisdk/packages-index/pull/187)
  - [board-image/armbian-visionfive2-desktop: add new packages #188](https://github.com/ruyisdk/packages-index/pull/188)
  - [board-image/armbian-visionfive2-minimal: add new packages #189](https://github.com/ruyisdk/packages-index/pull/189)
  - [board-image/armbian-spacemit-musepipro: add new packages #190](https://github.com/ruyisdk/packages-index/pull/190)

- 迁移 ruyi 的 lit 测试到 pytest [7a2eae0...534d2e4](https://github.com/ruyisdk-test/ruyi-pytest/compare/7a2eae007d1ddc444b7ef4472eb7cc0b83a3c83c...534d2e47412e44a7d2a1a4ef82bdbe7638407b17)
  - 共计 21 个 commit， 2853 行增加

- [新增armbian的新riscv板子](https://github.com/ruyisdk-test/riko-bot/commit/4db35ef400ce70649d72ba69594105ba763a901a)
- 新增了`armbian-musepipro`/`armbian-orangepirv2`/`armbian-visionfive2`/`armbian-uefi-riscv64`三个板子的`riko.py`、`riko.toml`、`riko.yaml`文件
- 在`https://github.com/armbian/community/tags`进行镜像下载
- [将version-sync保存日志](https://github.com/ruyisdk-test/riko-bot/commit/ee278246d6e0e415d951dc5606a25c7c6ddac081)
  - 在 dry-run 模式下，将日志同时输出到 /version-dry-run_docs 文件夹                         
  - 生成带时间戳的日志文件名（如 version-sync-20260424_150949.log）                   
  - 保持 stdout 输出以便实时查看
- [更新版本更新机制](https://github.com/ruyisdk-test/riko-bot/commit/387a050387cb071fff1d51912b3524805a728f20)       
  - 新增 get_cache_versions_info 方法，用于获取本地 cache 中已有版本信息                                 
  - 重构 VersionDiff 类，区分 cache（实际要增删的）和 remote（仅展示参考）两个维度                         
  - 同时计算 cache vs upstream 和 remote vs upstream 的版本差异                                           
  - 修复 git pull 使用 --ff-only 避免 divergent branches 问题                                        
  - 改进 git push 认证方式，使用 token 嵌入 URL 并在 finally 中恢复原始 URL 避免泄露
- [修改freebsd/riko.py的url](https://github.com/ruyisdk-test/riko-bot/commit/293e534aaac6290807f24aa9d5bde95a07619e5b)
  - 原来的`https://mirror.iscas.ac.cn/FreeBSD/releases/riscv/riscv64/ISO-IMAGES/`无法访问，将其riko.toml的url修改成`https://download.freebsd.org/releases/riscv/riscv64/ISO-IMAGES/`
  - `riko.py`按照同样的逻辑进行修改
- [Ruyi镜像源配置逻辑修复](https://github.com/ruyisdk-test/riko-bot/commit/fefe377e6de38f4888140e007fa77dc713d33c95)
 - 修复了镜像源切换失效的问题，现在可以通过环境变量 USE_RUYI_ISCAS_MIRROR=true 正确切换到国内加速源
 - 提高了配置的安全性，避免空值覆盖导致的配置异常
- [将原有单一的 armbian 板卡配置拆分为 minimal 和 desktop](https://github.com/ruyisdk-test/riko-bot/commit/ee278246d6e0e415d951dc5606a25c7c6ddac081)
  - armbian-orangepirv2：拆分为 armbian-orangepirv2-minimal 和  armbian-orangepirv2-desktop             
  - armbian-uefi-riscv64：拆分为 armbian-uefi-riscv64-minimal 和armbian-uefi-riscv64-desktop  
  - armbian-visionfive2：拆分为 minimal 和 desktop 两个版本                      
- [修复-trunk 版本文件名和keep_back 策略空指针问题](https://github.com/ruyisdk-test/riko-bot/commit/3b71a3b6293a514c2fe00bb354d97b70d81bdba9)
 - 修复 keep_back 策略空指针问题：当 pkg_ver 为 None 时，使用占位版本 0.0.0 替代，避免程序崩溃
 - 修复 -trunk 版本文件名问题：对于包含 -trunk 的upstream_version（如 armbian-musepipro），使用完整的upstream_version 作为 manifest 文件名，而非解析后的 semver 版本
- [board-image/armbian-spacemit-musepipro: add new packages](https://github.com/ruyisdk/packages-index/pull/190)
  - 新增armbian-spacemit-musepipro包
- [Add armbian-orangepirv2-desktop manifest](https://github.com/ruyisdk/packages-index/pull/184)
  - 新增 armbian-orangepirv2-desktop 包 
- [Add armbian-orangepirv2-minimal manifest](https://github.com/ruyisdk/packages-index/pull/185)
  - 新增 armbian-orangepirv2-minimal 包
- [Add armbian-visionfive2-desktop manifest](https://github.com/ruyisdk/packages-index/pull/188)
  - 新增 armbian-visionfive2-desktop 包
- [Add armbian-visionfive2-minimal manifest](https://github.com/ruyisdk/packages-index/pull/189)
  - 新增 armbian-visionfive2-minimal 包

#### 1.3 RuyiSDK开发示例库和示例库网站开发

- Licheepi4A 
	- cpufetch
		- 视频链接：[【RuyiSDK示例】使用Ruyi工具链编译cpufetch](https://www.bilibili.com/video/BV1fiw7zBE6F?buvid=Y14C16117DC47F7240DFA9AB49C606069273&is_story_h5=false&mid=7O7lEOQTno7ebx%2FEwA0C1w%3D%3D&plat_id=116&share_from=ugc&share_medium=iphone&share_plat=ios&share_session_id=821B26EC-6E57-4DE1-AD38-1154FCC458E7&share_source=COPY&share_tag=s_i&spmid=united.player-video-detail.0.0&timestamp=1773655425&unique_k=xB64uZq&up_id=179700748)
		- 视频链接：[【RISC-V架构识别】在Licheepi4A上使用cpufetch获取CPU信息](https://www.bilibili.com/video/BV1j8wFzSE2x?vd_source=63f9297bce04de7108868464326f7b22)
	- [使用 Ruyi 工具链在 LicheePi 4A 上编译并运行GStreamer](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/examples/GStreamer_LPi4A.md)
	- [RuyiSDK 计算机视觉示例__LicheePi 4A OpenCV](https://github.com/zhiyao310/board-docs/blob/main/LicheePi4A/OpenCV/README_zh.md)
	- [YOLOX](https://github.com/ruyisdk/board-docs/blob/main/LicheePi4A/YOLOX/README_zh.md)
  - [MobilenetV2](https://github.com/ruyisdk/board-docs/tree/main/LicheePi4A/MobilenetV2)
  - [YOLOV5n](https://github.com/ruyisdk/board-docs/tree/main/LicheePi4A/YOLOV5n)
- VisionFive2Lite
	- 概述： [README.md](https://github.com/zhiyao310/board-docs/tree/main/VisionFive2Lite);[README_zh.md](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/README_zh.md)
	- [HelloWorld](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/HelloWorld/README_zh.md)
	- [Coremark](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/Coremark/README_zh.md)
- Duo256
	- [使用 RuyiSDK 在 Milk-V Duo256m 上编译运行 mailbox-test 教程](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%20mailbox-test%20%E6%95%99%E7%A8%8B.md)
	- [使用 RuyiSDK 在 Milk-V Duo256m 上编译运行 opencv-mobile 教程](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/Duo%20256m/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256M%20%E4%B8%8A%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%20opencv-mobile%20%E6%95%99%E7%A8%8B.md)
- DuoS 
	- [Mailbox-test](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Mailbox-test)
	- [Blink](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Blink)
	- [Dht22](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Dht22)
	- [ADC](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/ADC)
- Mars
	- [Milk-V Mars_2048](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Mars/Milk-V%20Mars_2048.md)
	- [Milk-V Mars_Coremark](https://github.com/feifei-xx/ruyisdk-dev-archive/blob/main/examples/CoreMark/Milk-V%20Mars_CoreMark.md)
—Coremark
  -用户手册：[Milk-V Mars_Coremark](https://github.com/feifei-xx/ruyisdk-dev-archive/blob/main/examples/CoreMark/Milk-V%20Mars_CoreMark.md)
  -Demo:[Demo_Milk-V Mars_Coremark](https://github.com/feifei-xx/ruyisdk-dev-archive/blob/main/examples/CoreMark/Demo_Milk-v%20Mars_coremark.md)
— Mars 2048
  -用户手册：[Milk-V Mars_2048](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Mars/Milk-V%20Mars_2048.md)
  -Demo:[Demo_Milk-V Mars_2048](https://github.com/feifei-xx/plct-works/blob/main/%E5%90%84%E7%A7%8D/2048/Demo_Milk-V%20Mars_2048.md)
— cpufetch
  - 视频链接：[【RuyiSDK示例】使用Ruyi工具链编译cpufetch](https://www.  bilibili.com/video/BV1fiw7zBE6F)
  - 视频链接：[【RISC-V架构识别】在Licheepi4A上使用cpufetch获取CPU信息](https://www.bilibili.com/video/BV1j8wFzSE2x)
- GStreamer
  - 用户手册： [使用 Ruyi 工具链在 LicheePi 4A 上编译并运行GStreamer](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/examples/GStreamer_LPi4A.md)
- OpenCV
  - 用户手册： [RuyiSDK 计算机视觉示例__LicheePi 4A OpenCV](https://github.com/zhiyao310/board-docs/blob/main/LicheePi4A/OpenCV/README_zh.md)
- VisionFive2Lite
  - 概述:[README.md](https://github.com/zhiyao310/board-docs/tree/main/VisionFive2Lite);[README_zh.md](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/README_zh.md)
  - [HelloWorld](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/HelloWorld/README_zh.md)
  - [Coremark](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/Coremark/README_zh.md)
  - [Add VisionFive 2 Lite test cases and docs](https://github.com/ruyisdk/board-docs/pull/4)
- [使用 RuyiSDK 在 Milk-V Duo256m 上编译运行 mailbox-test 教程](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%20mailbox-test%20%E6%95%99%E7%A8%8B.md)
  - 教程：[使用 RuyiSDK 在 Milk-V Duo256M 上编译运行 opencv-mobile 教程](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/Duo%20256m/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256M%20%E4%B8%8A%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%20opencv-mobile%20%E6%95%99%E7%A8%8B.md)
  - [Mailbox-test](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Mailbox-test)
  - [Blink](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Blink)
  - [Dht22](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Dht22)
  - [ADC](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/ADC)
- [wiringX 库对 LicheePi 4A TH1520 平台的 GPIO 支持](https://github.com/ruyisdk/ruyisdk/issues/79)
- [Go Toolchain](https://github.com/ruyisdk/ruyisdk/issues/80)
做出了一个 demo，形成了代码仓库和文档，详见：`https://my.feishu.cn/docx/FvIMdSx1Uo1mbkx8MXscBiPNnsc`

- RuyiSDK开发资源梳理和资源申请
	- [Go Toolchain](https://github.com/ruyisdk/ruyisdk/issues/80)

-  RuyiSDK 示例库文档展示的前端页面
	- 前端仓库： [https://github.com/DuoQilai/board-docs-frontend.git](https://github.com/DuoQilai/board-docs-frontend.git)
	- 前端仓库内容包括：
		- 完成了 2 轮迭代，现已支持BPI-F3、Duo、Duo_256m、Duo_S、Meles、Pioneer、LicheePi3A、LicheePi4A等开发板。
		- 前端网页代码完成了给 VS Code 和 Eclipse 插件团队的消息发送。
		- 针对团队提出的新需求做了 patch。
		- 更新并拉取前端文档仓库和 README。
		- 根据插件侧需求，完善了“仅在 VS Code WebView / Eclipse 内生效”的前端交互：
	    - 通过 userAgent 判断 VS Code（包含 `Code/`）来控制按钮显隐；浏览器环境不展示；Eclipse/VS Code 外也不展示。
	    - 在页面右上角增加按钮「在 VS Code 中使用」；点击后调用 `vscode.postMessage({ type: 'copilot', url, model, profile })` 把当前文档原文 URL 与（从文档属性读取的）开发板型号/示例名称回传给 VS Code。
		- 按要求将网站文档仓库切到 `ruyisdk/board-docs`，并处理目录展示（不显示 `/templates`，用于后续新增模板目录）。
		- 跟进 UI 细节：标签图标替换为 ruyisdk logo。
		- 学习 Electron 桌面开发与 VS Code 插件开发的基本逻辑，更好地理解对方团队需求并协作对齐。
	-  网站连接： https://board-docs-frontend.pages.dev/
	-  文档仓库： https://github.com/ruyisdk/board-docs/

#### 1.4 RuyiSDK 文档编写

- 新的[快速开始](github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month34/quick_start_draft.md)文档
- 增补新的[快速开始](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month34/quick_start_draft2.md)文档，还需要验证一些发行版相关的命令
- [ruyi包管理器](https://github.com/ruyisdk-test/test-working/tree/main/cjh/26-April/Ruyi%E5%8C%85%E7%AE%A1%E7%90%86%E5%99%A8)
- [ruyi-qemu+openruyi](https://github.com/ruyisdk-test/test-working/tree/main/cjh/26-April/blog/ruyi-qemu%2Bopenruyi.md)
  - 介绍了如何通过ruyi-qemu和openRuyi rootfs进行交叉编译
- [ruyi包管理可以接入使用者自制的sysroot](https://github.com/ruyisdk-test/test-working/tree/main/cjh/26-April/blog/ruyi%E5%8C%85%E7%AE%A1%E7%90%86%E5%99%A8%E5%8F%AF%E4%BB%A5%E6%8E%A5%E5%85%A5%E5%A4%96%E6%9D%A5sysroot%E4%BA%86.md)
  - ruyi包管理可以接入使用者自制的sysroot

#### 1.5 RuyiSDK网站

- [pages(index): better terminal scroll #428](https://github.com/ruyisdk/ruyisdk-website/pull/428)
- [pages(navbar): better dropdown menu transform #430](https://github.com/ruyisdk/ruyisdk-website/pull/430)
- [pages(footer): add openRuyi projects to ecosystem section #439](https://github.com/ruyisdk/ruyisdk-website/pull/439)
- [pages(index): add jeandle to partner section and better xuantie logo #440](https://github.com/ruyisdk/ruyisdk-website/pull/440)
- [Downloads page refactor #418](https://github.com/ruyisdk/ruyisdk-website/pull/418)
- [Improved mobile scrolling performance && deleted unused varity #433](https://github.com/ruyisdk/ruyisdk-website/pull/433)
- [I removed the footer link to the data statistics page. #436](https://github.com/ruyisdk/ruyisdk-website/pull/436)
- [pages(footer): add openRuyi projects to ecosystem section #439](https://github.com/ruyisdk/ruyisdk-website/pull/439)

#### 1.6 RuyiSDK.cn 社区

- [利用 RuyiSDK 玩转 RISC-V 版Endless-Sky](https://ruyisdk.cn/t/topic/2599)
- [RuyiSDK 实践指南：基于 RISC-V 架构编译与运行 Busybox](https://ruyisdk.cn/t/topic/2602)

### 2. RuyiAI

- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/773 [ci] Release buddy-cli
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/772 [ci] Update openmp build command for release
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/759 [ci] Enable test-example on riscv64
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/756 [ci] Fix test-example
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/754 [CI] Add example ci test
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/747 [ci] Enable check-buddy on x64
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/746 [ci] Enable pre-commit on new file changes
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/743 [ci] Add arm64-macos
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/741 [package] generate package version from BUDDY_PACKAGE_VERSION
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/740 [package] Add cmake option BUDDY_PACKAGE_VERSION
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/739 [example] Fix stable-diffusion example
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/736 [package] Add runtime cli
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/733 [example] FIx OneDNN example
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/729 [example] Use pretrained model for LeNet

- Release BUDDY MLIR 0.0.3 https://github.com/buddy-compiler/buddy-mlir/releases/tag/release%2Fv0.0.3
      
### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- [#1622](https://github.com/riscv/sail-riscv/pull/1622) : 将当前冗余的 `Memory_Exception` 的处理逻辑合并到 `Trap`的处理逻辑中, 已经解决 review 意见并合并
- [#1665](https://github.com/riscv/sail-riscv/pull/1665) : 提交PR, 在sail-riscv 中实现 smpmpmt 扩展
- [#1672](https://github.com/riscv/sail-riscv/pull/1672) : 提交PR, 简化异常处理逻辑，将xret 的处理流程移动到对应的指令执行函数体，已经合并
- smwid 扩展[https://github.com/riscv/sail-riscv/compare/master...challenger1024:sail-riscv:riscv-world](https://github.com/riscv/sail-riscv/compare/master...challenger1024:sail-riscv:riscv-world)
- 继续推进 IME 扩展

#### 3.2 技术分享

- smwid扩展 [https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2026-04-Smwid.md](https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2026-04-Smwid.md)

#### 3.3 SAIL会议

- 参加 tech-golden-model meeting [`04.13`, `04.20`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 参加东亚双周会 0416，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/143zz3oMxsKFSTsrHmaeLA-cAge8we4yWRt22u_IP3xU/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0430，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1VquRhGyJbqzo3fDxb8seyqxRCtpjxHoXqmm93heHk7I/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

### 4. 2026年RISC-V 欧洲峰会

4篇海报入选2026年欧洲峰会（峰会共入选213篇，期中软件所7篇）
参考：https://riscv-europe.org/summit/2026/posters

- RuyiSDK Package Manager - A Unified Package Management and Development Environment for RISC-V

- An Efficient Approach to Apply the RISC-V Sail Model to Chip Verification

- Sail-RISCV-WASM A Browser-Native RISC-V Toolchain and Debugging Workbench

- From Fragmentation to Systematization: A Standardized Quality Selection and Reconstruction Approach for RISC-V Courses

### 5. 2026年中国科学院公众科学日

团队参加2026年中国科学院公众科学日软件研究所活动，展示RuyiSDK和RuyiAI成果

准备展示物
- RuyiSDK的使用
- RuyiSDK各领域开发实例（嵌入式、操作系统桌面生态、服务器、机器学习、大模型、MPI高性能、机器人）
- RuyiAI的使用
- RuyiAI的应用实例和性能对比

- 用 RISC‑V 开发板（荔枝派 4A）跑 openEuler，现场演示我做的全栈应用 debate_book：在浏览器里一键启动，让两位“学者 AI”（杰维斯 vs 米尔斯海默）围绕固定命题进行 3 轮辩论。
  - 提出了 5 个备选 ideas，形成了文档，详见：`https://my.feishu.cn/docx/XaLgdQEOVoHRmmxMa0Qc1wHZnJg`

- 嵌入式小车
1. 硬件选型与成本控制
主控板选择：倾向于使用 Milk-V 或 VisionFive 2 等 RISC-V 开发板作为主控，替代树莓派以降低成本。
通信模块方案：鉴于开发板自带 WiFi 模块较少，决定采用红外接收模块（约 5-8 元）作为遥控方案，替代复杂的 WiFi/蓝牙配置。
2. 机械结构与驱动
动力方案：计划采用空心杯电机配合简易车体（如纸板或开发板直接作为底盘），实现低成本、轻量化的四轮或两轮驱动。

- RISC-V 硬件下 RuyiAI 编译的Pytorch项目和Pytorch下直接运行体验，感受性能差异

### 6. 职工

#### 6.1 蔡玮霖

- ruyisdk-website 仓库提交 4 个 pr
  - [pages(index): better terminal scroll #428](https://github.com/ruyisdk/ruyisdk-website/pull/428)
  - [pages(navbar): better dropdown menu transform #430](https://github.com/ruyisdk/ruyisdk-website/pull/430)
  - [pages(footer): add openRuyi projects to ecosystem section #439](https://github.com/ruyisdk/ruyisdk-website/pull/439)
  - [pages(index): add jeandle to partner section and better xuantie logo #440](https://github.com/ruyisdk/ruyisdk-website/pull/440)
- ruyisdk-website 仓库审核 4 个 pr
  - [Downloads page refactor #418](https://github.com/ruyisdk/ruyisdk-website/pull/418)
  - [Improved mobile scrolling performance && deleted unused varity #433](https://github.com/ruyisdk/ruyisdk-website/pull/433)
  - [I removed the footer link to the data statistics page. #436](https://github.com/ruyisdk/ruyisdk-website/pull/436)
  - [pages(footer): add openRuyi projects to ecosystem section #439](https://github.com/ruyisdk/ruyisdk-website/pull/439)
- packages-index 仓库提交 1 个 pr
  - [plugins: specify xthead quirk for milkv-duo profile #182](https://github.com/ruyisdk/packages-index/pull/182)
- packages-index 仓库审核 8 个 pr
  - [board-image/armbian-musepipro: add new packages #183](https://github.com/ruyisdk/packages-index/pull/183)
  - [board-image/armbian-orangepirv2-desktop: add new packages #184](https://github.com/ruyisdk/packages-index/pull/184)
  - [board-image/armbian-orangepirv2-minimal: add new packages #185](https://github.com/ruyisdk/packages-index/pull/185)
  - [board-image/armbian-uefi-riscv64-desktop: add new packages #186](https://github.com/ruyisdk/packages-index/pull/186)
  - [board-image/armbian-uefi-riscv64-minimal: add new packages #187](https://github.com/ruyisdk/packages-index/pull/187)
  - [board-image/armbian-visionfive2-desktop: add new packages #188](https://github.com/ruyisdk/packages-index/pull/188)
  - [board-image/armbian-visionfive2-minimal: add new packages #189](https://github.com/ruyisdk/packages-index/pull/189)
  - [board-image/armbian-spacemit-musepipro: add new packages #190](https://github.com/ruyisdk/packages-index/pull/190)
- packages-index 仓库提交 1 个 issue
  - [milkv-duo profile does not specify quirk xthead #181](https://github.com/ruyisdk/packages-index/issues/181)
- ruyi 仓库提交 5 个 issue
  - [ruyi 0.48.0-beta.20260421 cannot run on debian bookworm #447](https://github.com/ruyisdk/ruyi/issues/447)
  - [ruyi 0.48.0-beta.20260421 see RequestsDependencyWarning: Unable to find acceptable character detection dependency #448](https://github.com/ruyisdk/ruyi/issues/448)
  - [bash-completion: not work properly when running ruyi for the first time #452](https://github.com/ruyisdk/ruyi/issues/452)
  - [ruyi version: show welcome message before print ruyi version #453](https://github.com/ruyisdk/ruyi/issues/453)
  - [ruyi extract --extract-without-subdir: does not print destination directory properly #454](https://github.com/ruyisdk/ruyi/issues/454)
- ruyi 快速开始文档
  - 新的[快速开始](github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month34/quick_start_draft.md)文档
  - 增补新的[快速开始](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month34/quick_start_draft2.md)文档，还需要验证一些发行版相关的命令
- 迁移 ruyi 的 lit 测试到 pytest [7a2eae0...534d2e4](https://github.com/ruyisdk-test/ruyi-pytest/compare/7a2eae007d1ddc444b7ef4472eb7cc0b83a3c83c...534d2e47412e44a7d2a1a4ef82bdbe7638407b17)
  - 共计 21 个 commit， 2853 行增加

#### 6.2 阎明铸

##### 6.2.1 Sail

- 继续推进 IME 扩展
- 参加 tech-golden-model meeting [`04.13`, `04.20`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 参加东亚双周会 0416，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/143zz3oMxsKFSTsrHmaeLA-cAge8we4yWRt22u_IP3xU/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0430，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1VquRhGyJbqzo3fDxb8seyqxRCtpjxHoXqmm93heHk7I/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

##### 6.2.2 Ruyi AI

- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/773 [ci] Release buddy-cli
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/772 [ci] Update openmp build command for release
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/759 [ci] Enable test-example on riscv64
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/756 [ci] Fix test-example
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/754 [CI] Add example ci test
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/747 [ci] Enable check-buddy on x64
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/746 [ci] Enable pre-commit on new file changes
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/743 [ci] Add arm64-macos
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/741 [package] generate package version from BUDDY_PACKAGE_VERSION
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/740 [package] Add cmake option BUDDY_PACKAGE_VERSION
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/739 [example] Fix stable-diffusion example
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/736 [package] Add runtime cli
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/733 [example] FIx OneDNN example
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/729 [example] Use pretrained model for LeNet

- Release BUDDY MLIR 0.0.3 https://github.com/buddy-compiler/buddy-mlir/releases/tag/release%2Fv0.0.3

#### 6.3 张馥媛

##### 6.3.1 RuyiSDK 示例代码库建设

设计、参与开发或审核

-  RuyiSDK 示例库文档展示的前端页面
	- 前端仓库： [https://github.com/DuoQilai/board-docs-frontend.git](https://github.com/DuoQilai/board-docs-frontend.git)
	- 前端仓库内容包括：
		- 完成了 2 轮迭代，现已支持BPI-F3、Duo、Duo_256m、Duo_S、Meles、Pioneer、LicheePi3A、LicheePi4A等开发板。
		- 前端网页代码完成了给 VS Code 和 Eclipse 插件团队的消息发送。
		- 针对团队提出的新需求做了 patch。
		- 更新并拉取前端文档仓库和 README。
		- 根据插件侧需求，完善了“仅在 VS Code WebView / Eclipse 内生效”的前端交互：
	    - 通过 userAgent 判断 VS Code（包含 `Code/`）来控制按钮显隐；浏览器环境不展示；Eclipse/VS Code 外也不展示。
	    - 在页面右上角增加按钮「在 VS Code 中使用」；点击后调用 `vscode.postMessage({ type: 'copilot', url, model, profile })` 把当前文档原文 URL 与（从文档属性读取的）开发板型号/示例名称回传给 VS Code。
		- 按要求将网站文档仓库切到 `ruyisdk/board-docs`，并处理目录展示（不显示 `/templates`，用于后续新增模板目录）。
		- 跟进 UI 细节：标签图标替换为 ruyisdk logo。
		- 学习 Electron 桌面开发与 VS Code 插件开发的基本逻辑，更好地理解对方团队需求并协作对齐。
	-  网站连接： https://board-docs-frontend.pages.dev/
	-  文档仓库： https://github.com/ruyisdk/board-docs/

- 开发板示例文档扩充
	- Licheepi4A 
		- cpufetch
			- 视频链接：[【RuyiSDK示例】使用Ruyi工具链编译cpufetch](https://www.bilibili.com/video/BV1fiw7zBE6F?buvid=Y14C16117DC47F7240DFA9AB49C606069273&is_story_h5=false&mid=7O7lEOQTno7ebx%2FEwA0C1w%3D%3D&plat_id=116&share_from=ugc&share_medium=iphone&share_plat=ios&share_session_id=821B26EC-6E57-4DE1-AD38-1154FCC458E7&share_source=COPY&share_tag=s_i&spmid=united.player-video-detail.0.0&timestamp=1773655425&unique_k=xB64uZq&up_id=179700748)
			- 视频链接：[【RISC-V架构识别】在Licheepi4A上使用cpufetch获取CPU信息](https://www.bilibili.com/video/BV1j8wFzSE2x?vd_source=63f9297bce04de7108868464326f7b22)
	- [使用 Ruyi 工具链在 LicheePi 4A 上编译并运行GStreamer](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/examples/GStreamer_LPi4A.md)
	- [RuyiSDK 计算机视觉示例__LicheePi 4A OpenCV](https://github.com/zhiyao310/board-docs/blob/main/LicheePi4A/OpenCV/README_zh.md)
	- VisionFive2Lite
		- 概述： [README.md](https://github.com/zhiyao310/board-docs/tree/main/VisionFive2Lite);[README_zh.md](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/README_zh.md)
		- [HelloWorld](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/HelloWorld/README_zh.md)
		- [Coremark](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/Coremark/README_zh.md)
	- Duo256
		- [使用 RuyiSDK 在 Milk-V Duo256m 上编译运行 mailbox-test 教程](https://github.com/cuiqiyun/ruyisdk-dev-archive/blob/main/examples/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256m%20%E4%B8%8A%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%20mailbox-test%20%E6%95%99%E7%A8%8B.md)
		- [使用 RuyiSDK 在 Milk-V Duo256m 上编译运行 opencv-mobile 教程](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/Duo%20256m/%E4%BD%BF%E7%94%A8%20RuyiSDK%20%E5%9C%A8%20Milk-V%20Duo256M%20%E4%B8%8A%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%20opencv-mobile%20%E6%95%99%E7%A8%8B.md)
	- DuoS 
		- [Mailbox-test](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Mailbox-test)
		- [Blink](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Blink)
		- [Dht22](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/Dht22)
		- [ADC](https://github.com/ruyisdk/board-docs/tree/main/Duo_S/ADC)
	- Mars
		- [Milk-V Mars_2048](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Mars/Milk-V%20Mars_2048.md)
		- [Milk-V Mars_Coremark](https://github.com/feifei-xx/ruyisdk-dev-archive/blob/main/examples/CoreMark/Milk-V%20Mars_CoreMark.md)
- RuyiSDK开发资源梳理和资源申请
	- [Go Toolchain](https://github.com/ruyisdk/ruyisdk/issues/80)
- Licheepi4A示例文档：
  - [YOLOX](https://github.com/ruyisdk/board-docs/blob/main/LicheePi4A/YOLOX/README_zh.md)
  - [MobilenetV2](https://github.com/ruyisdk/board-docs/tree/main/LicheePi4A/MobilenetV2)
  - [YOLOV5n](https://github.com/ruyisdk/board-docs/tree/main/LicheePi4A/YOLOV5n)

##### 6.3.2 2026 RISC-V 欧洲峰会投稿

- 扩展摘要中稿
	- From Fragmentation to Systematization: A Standardized Quality Selection and Reconstruction Approach for RISC-V Courses Sub.  # C3QQBZ. Fuyuan Zhang and Yunxiang Luo.
