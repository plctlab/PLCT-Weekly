# RISC-V 软件生态进展 · 第 85 期·2026 年 8 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium

## Spidermonkey / Firefox

## OpenJDK

## Go

## GNU Toolchain

## LLVM Team

## MLIR / Buddy Compiler

## opensbi

## 罗云翔测试团队
（包含 SAIL 和 ACT 测试部分）

2026年8月，RuyiSDK测试团队完成RuyiSDK 0.51.0-beta版本在Debian、Ubuntu、openEuler、Fedora等8种操作系统及x86_64、aarch64、riscv64多架构上的包管理器测试，发布30份测试报告，并持续跟踪缺陷修复；自动化测试框架ruyi-pytest新增多项测试用例，增强了跨平台(MacOS)适配的覆盖。RuyiSDK开发示例库新增SpacemiT K3 Pico-ITX、Canaan K510等多款开发板文档。RuyiAI方面，为buddy-mlir修复CI和发布流程问题，并在triton-riscv中引入Renovate自动化依赖更新，扩展riscv64 CI规格以优化编译性能。操作系统支持矩阵新增VisionFive2 Lite、EBC7702等多款板卡测试报告。SAIL团队向上游提交Sscpuutil扩展等PR，为某合作项目持续提交大量扩展SAIL实现（不公开产出）。团队共有6个议题投稿2026年RISC-V中国峰会报告和海报，并协助部分中国企业完成RVI CSC调查填报。RISC-V Linux应用编程技术课程（RuyiSDK为开发工具）完成第1至6章建设，覆盖环境搭建、GPIO、网络通信等实践内容；RISC-V ROS2机器人操作系统编程技术课程（RuyiSDK为开发工具）完成ROS2不涉及ISA部分的建设和验证。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.51.0-beta.20260714 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/README.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260901/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu26.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260901/RUYI_包管理_Ubuntu26.04_x86_64_测试结果.md)
    - [Ubuntu26.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Ubuntu26.04_riscv64_测试结果.md)
    - [Ubuntu26.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Ubuntu26.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Fedora42_x86_64_测试结果.md)
	- [Fedora42 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Fedora42_aarch64_测试结果.md)
	- [Fedora43 x86_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Fedora43_x86_64_测试结果.md)
	- [Fedora43 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Fedora43_aarch64_测试结果.md)
	- [Deepin23 x86_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Deepin23_x86_64_测试结果.md)
	- [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Deepin23_riscv64_测试结果.md)
	- [Deepin25 x86_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Deepin25_x86_64_测试结果.md)
	- [Deepin25 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Deepin25_riscv64_测试结果.md)
	- [Deepin25 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Deepin25_aarch64_测试结果.md)
	- [OpenCloudOS 9.4 x86_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)
	- [OpenCloudOS 9.4 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_OpenCloudOS_aarch64_测试结果.md)
	- [Archlinux x86_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_Archlinux_x86_64_测试结果.md)
	- [macOS aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260901/RUYI_包管理_macOS_arm64_测试结果.md)

    - 缺陷：  
		- 文档测试
		上一版本遗留 2 个缺陷：

		| 缺陷      | 问题等级 | 备注 |
		| ----------- | ----------- | --- |
		| [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，修复已经延后  |

		- Ruyi 包管理器测试

		遗留缺陷：

		| 缺陷      | 问题等级 |判定依据 |
		| ----------- | ----------- | --- |
		| [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415) | 一般 | 已有 issue 回复 |

		新增缺陷：

		| 缺陷      | 问题等级 |判定依据 |
		| ----------- | ----------- | --- |
		| [ruyi entity list 传入多个 -t 参数时只消费其中一个 #492](https://github.com/ruyisdk/ruyi/issues/492) | 一般 | 下一版本修复 |

		- RuyiSDK Eclipse IDE 发版测试

		本版本没有同步发版的版本。

		遗留缺陷：

		| 缺陷      | 问题等级 | 备注 |
		| ----------- | ----------- | --- |
		| [命令执行提示框可以任意关闭且无法重新打开 #82](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/82)   | 建议 |   |
		| [虚拟环境建立的项目绑定问题 #84](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/84) | 建议 |  |
		| [安装插件时 Eclipse 提示未签名 #85](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/85) | 建议 |  |
		| [New Virtual environment添加虚拟环境时响应时间过长 #177](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/177) | 建议 |  |
		| [用户无法直观获知项目当前启用的虚拟环境 #191](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/191) | 建议 |  |
		| [select package 不可用 #196](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/196) | 建议 |  |

	- RuyiSDK VSCode IDE 发版测试

		本版本延迟测试发布的 VSCode 插件测试[报告](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/tree/v0.1.6)。

		遗留缺陷：

		| 缺陷      | 问题等级 | 备注 |
		| ----------- | ----------- | --- |
		| [版本切换过程中中英文切换不灵活 #231](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/231)   | 建议 |   |

- ruyi 仓库提交 1 个 issue
	- [ruyi entity list 传入多个 -t 参数时只消费其中一个 #492](https://github.com/ruyisdk/ruyi/issues/492)

- ruyi-backend 仓库提交 1 个 issue
    - [ruyi telemetry upload 经常失败 #117](https://github.com/ruyisdk/ruyi-backend/issues/117)

- ruyisdk-vscode-extension 仓库
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/225 ruyi存在多个镜像源时，存在软件包安装冲突（状态异常）
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/226 ruyi package 切换镜像源时，需手动刷新当前的软件包状态
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/227 package 版本状态不一致
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/229 虚拟环境创建时工具链列表的中英文状态不一致
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/231 版本切换过程中中英文切换不灵活
  	- 衍生出来的i18n汉化Issue[223](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/223),[224](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/224),[228](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/228),[230](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/230)
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/232 最新版工具链排序问题
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/235 emulator排序意义不明
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/204 Ruyi软件包列表i18n
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/205 在使用不包含 sysroot 的工具链 （例如 xscc） 时，可通过指定其他工具链，此时仍包含xscc
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/206 项目构建i18n
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/211 工具链列表未排序
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/212 工具链全选按钮无意义

- ruyisdk-imager 仓库
	- https://github.com/Glavo/ruyi-imager/issues/1 检查更新失败
	- https://github.com/Glavo/ruyi-imager/issues/2 更新元数据失败
	- https://github.com/Glavo/ruyi-imager/issues/3 窗口相关文字位置偏下
	- https://github.com/Glavo/ruyi-imager/issues/4 设置界面文字重叠
	- https://github.com/Glavo/ruyi-imager/issues/5 设置界面取消和保存按钮不可以

#### 1.2 RuyiSDK开发和测试开发

- packages-index
packages-index 是 RuyiSDK 的包元数据仓库，为 ruyi 客户端提供包索引和同步数据源，测试团队负责RISC-V开发板镜像测试和集成。
	- [#211 board-image/ubuntu-server-riscv64-sifive-unmatched: use old-releases URL for 25.04 image](https://github.com/ruyisdk/packages-index/pull/211)
	- [#212 board-image/revyos-sg2042: bump to latest version 20260504](https://github.com/ruyisdk/packages-index/pull/212)
	- [#213 board-image/armbian-spacemit-musepipro-minimal: update versions](https://github.com/ruyisdk/packages-index/pull/213)
	- [#214 board-image/armbian-starfive-visionfive2-minimal: update versions](https://github.com/ruyisdk/packages-index/pull/214)
	- [#215 board-image/armbian-orangepi-rv2-minimal: update versions](https://github.com/ruyisdk/packages-index/pull/215)
	- [#190 board-image/armbian-spacemit-musepipro-minimal: add new packages](https://github.com/ruyisdk/packages-index/pull/190)

- ruyisdk-test/riko-bot
RuyiSDK 自动化版本检查与打包工具，用于为 ruyisdk/packages-index 仓库自动生成和更新包清单
	- [#c7e6d7b riko: resolve regex upstream versions by file_exists_regex](https://github.com/ruyisdk-test/riko-bot/commit/c7e6d7b7413ef4cc3b629cf1e5c7546279259313)
	- [#930541e ruyi_packages: switch ubuntu-cdimage source to cdimage.ubuntu.com and gate on file_exists_regex](https://github.com/ruyisdk-test/riko-bot/commit/930541ead25889012c385190fe749445c790fea6)
	- [#5900512 rci: translate workflow comments to English](https://github.com/ruyisdk-test/riko-bot/commit/590051268cd089edeb3c9259186f184772d3c9c8)
	- [#7f186a6 riko(cli): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/7f186a6f7bb6f3ec9db81bc55a66079d4bbe28c9)
	- [#94942eb riko(packages_index): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/94942ebf8ac4ee4a76293bd82690c42f4205b30c)
	- [#e42ac71riko(upstreams): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/e42ac7141ff81efd0ca2981d076b78af7c0604b3)
	- [#6b63494 riko(services): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/6b634941ab5fd0606c12585bf68cfdf487991223)
	- [#a36fb25 riko(nvchecker): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/a36fb25b1e90f8ad2542c05aacb08167e373cc72)
	- [#05d78db riko(utils): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/05d78dbb8caafdc0541c4c3e3f62a18ea5caa6da)
	- [#55a4cf9 riko(ruyi_packages): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/55a4cf97019f2d90aa968c48e929673232532733)
	- [#9f4d10b riko(interfaces): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/9f4d10bfda7b3f6534615ba6b89290a1593a7d7e)
	- [#ba7cbbf riko(database): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/ba7cbbf013e4041d485be3aa98d45b5096afe156)
	- [#47365b9 riko(core): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/47365b96aa7794a1af7a69f949952c9308a67164)
	- [#e92432a riko(config): Remove Chinese characters and redundant comments](https://github.com/ruyisdk-test/riko-bot/commit/e92432a8f3038eed24dde40ebafd245431ac3f9e)
	- [#cddbead Update README.md](https://github.com/ruyisdk-test/riko-bot/commit/cddbead64a6bbcb3aa492ce2dccac412844b5974)
	- [#e921db2 riko(core): riko(version-sync): generate dry-run Markdown report and pair it with log file](https://github.com/ruyisdk-test/riko-bot/commit/e921db23bc060771d81bef094d8fa4a4efed59d2)
	- [#95fdd05 riko(config): riko(check): resolve actual ruyi packages-index repo path and sync it to Riko](https://github.com/ruyisdk-test/riko-bot/commit/95fdd054fcc723f842e8bc9142c45103d9e9baf6)

- ruyisdk-test/ruyi-pytest 
集成测试套件，用于全面验证 ruyi CLI 的功能正确性。
    - misc: add test point count script [eb7ab5e](https://github.com/ruyisdk-test/ruyi-pytest/commit/eb7ab5e72d1001d28cfd9a70b36e6186e13c4ca9)
    - tests: add and harden self-management coverage [b054d1b](https://github.com/ruyisdk-test/ruyi-pytest/commit/b054d1b37b3d4c098f223203a5ae3f6a95d9549e)
    - tests: cover experimental entity commands [db451f6](https://github.com/ruyisdk-test/ruyi-pytest/commit/db451f603302c41dc1964c9729706cf74090e23c)
    - test: update Ruyi dependency and entity coverage [9f32e45](https://github.com/ruyisdk-test/ruyi-pytest/commit/9f32e456e23a54ef5e585296848a4dc5176c1eaf)
    - test: mark entity filter defect in 0.52 beta [6d0d335](https://github.com/ruyisdk-test/ruyi-pytest/commit/6d0d335985e2e7c0bc79ce1f632a5c213e884c04)
    - test: extend package download timeouts [a9659f7](https://github.com/ruyisdk-test/ruyi-pytest/commit/a9659f793f15f9b01b0e71baf29bbdb9451877f0)
    - test: expose Ruyi version fixture [c9c91d4](https://github.com/ruyisdk-test/ruyi-pytest/commit/c9c91d4fbc07e5ba4814d4ae43640165a8c0137f)
    - test: honor mirror choice for standalone download [9f6f390](https://github.com/ruyisdk-test/ruyi-pytest/commit/9f6f3901d4e1e393541379feefcb963d985ca594)
    - test: skip Linux-only package tests on macOS [2175dcc](https://github.com/ruyisdk-test/ruyi-pytest/commit/2175dcc6a30b6ff2d165f8faf76c3479b5418261)
    - test: isolate LC_CTYPE in test environment [a0824eb](https://github.com/ruyisdk-test/ruyi-pytest/commit/a0824ebe3575c14b2b47027e531e3e0919e665a9)
    - test: switch from gnu-plct to gnu-ruyisdk for macOS tests [fecb7f7](https://github.com/ruyisdk-test/ruyi-pytest/commit/fecb7f7930688495f026bb666e331d13849bd9f9)
	- https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/13 
	- [#6 tests: add self test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/6)

- ruyisdk-test/oh-my-ruyi 仓库提交 46 个 commit
图形化管理工具，为 ruyi 包管理器的 GUI 前端，提供了版本管理、仓库管理、设备烧录等核心功能的可视化操作界面。
	- [44efe7f...bf5e8fb](https://github.com/ruyisdk-test/oh-my-ruyi/compare/44efe7feb0ccf407412709fb757a21fbb64f4f97...bf5e8fb8192648a6a03b00d52918d88cc2aacb33)

#### 1.3 RuyiSDK开发示例库和示例库网站开发

- Ruyi 示例文档库：
	- 仓库：[ruyisdk/board-docs](https://github.com/ruyisdk/board-docs)
	- 开发板示例文档扩充：
		- SpacemiT K3 Pico-ITX：新增中英文板卡概述及 CoreMark、HelloWorld、llama-server 中文示例文档，见 [PR #33](https://github.com/ruyisdk/board-docs/pull/33)。
		- HelloWorld 英文文档：补充 BPI-F3、Duo、Duo S、EBC7700、Jupiter2、K3 Pico-ITX、LicheePi 4A 等开发板的英文文档，见 [PR #36](https://github.com/ruyisdk/board-docs/pull/36)。
		- Canaan K510：整理 CoreMark 与 HelloWorld 的中英文文档和示例目录，见 [PR #37](https://github.com/ruyisdk/board-docs/pull/37)。
		- BPI-CANMV-K230D-Zero（原 K230D）：新增板卡概述与系统安装文档，文档见 [PR #41](https://github.com/ruyisdk/board-docs/pull/41)，命名更新见 [PR #42](https://github.com/ruyisdk/board-docs/pull/42)。
	- 仓库维护：
		- 将示例分类元数据统一为 `category`，见 [PR #27](https://github.com/ruyisdk/board-docs/pull/27)。
		- 完善中英文示例文档模板，见 [PR #28](https://github.com/ruyisdk/board-docs/pull/28)。
		- 新增元数据检查及配套工作流，见 [PR #30](https://github.com/ruyisdk/board-docs/pull/30)。
		- 新增 DCO 检查并改进 Pull Request 模板，见 [PR #31](https://github.com/ruyisdk/board-docs/pull/31)。
		- 将 `board-docs` 的文档站入口更新为 [boards.ruyisdk.org](https://boards.ruyisdk.org/)，见 [PR #32](https://github.com/ruyisdk/board-docs/pull/32)。
		- 新增 README 支持矩阵自动生成与一致性检查，见 [PR #34](https://github.com/ruyisdk/board-docs/pull/34)。
		- 补充板卡与示例命名、版本记录和中英文文档规范，见 [PR #35](https://github.com/ruyisdk/board-docs/pull/35)。
		- 统一 Ruyi 安装章节和版本化下载路径，新增版本更新脚本及每月版本更新工作流，见 [PR #38](https://github.com/ruyisdk/board-docs/pull/38)。
		- 新增示例级中英文覆盖率检查，支持报告模式和严格模式，见 [PR #40](https://github.com/ruyisdk/board-docs/pull/40)。

- board-docs-frontend：
	- 项目仓库：[DuoQilai/board-docs-frontend](https://github.com/DuoQilai/board-docs-frontend)
	- 在线站点：[中文入口](https://boards.ruyisdk.org/)；[英文入口](https://boards.ruyisdk.org/en/)
	- 完善示例分类读取和展示逻辑，支持 `category` 元数据、扩充分类体系并统一入门分类标签，见 [PR #1](https://github.com/DuoQilai/board-docs-frontend/pull/1)、[PR #2](https://github.com/DuoQilai/board-docs-frontend/pull/2) 和 [PR #3](https://github.com/DuoQilai/board-docs-frontend/pull/3)。
	- 配置正式站点地址、站点地图和中英文语言配置，新增 Pull Request 与 `main` 分支构建检查，见 [PR #5](https://github.com/DuoQilai/board-docs-frontend/pull/5)。
	- 完成中英文界面、共享页面组件、英文路由和语言切换，见 [PR #6](https://github.com/DuoQilai/board-docs-frontend/pull/6)。
	- 新增前端分类与 `board-docs` 元数据的双向一致性检查；未知分类回退到“其他”，并可发现跨仓库分类不一致，见 [PR #7](https://github.com/DuoQilai/board-docs-frontend/pull/7)。
	- 按页面语言选择 `README.md`、`README_zh.md` 或旧版示例文档；缺少对应语言时显示回退提示，见 [PR #8](https://github.com/DuoQilai/board-docs-frontend/pull/8)。

- K3 Pico-ITX AI 服务与设备中控（准备中，完成后提交ruyisdk/board-docs）
	- 仓库：[DuoQilai/k3-agent-server](https://github.com/DuoQilai/k3-agent-server)
	- 建立可复现的 K3 AI 服务部署基线，整理 DSH Agent、llama-server、本地模型、systemd 用户服务及日常启停与日志文档，见 [Commit 3bc2926](https://github.com/DuoQilai/k3-agent-server/commit/3bc29267401823a65c2ff6a0a180b1615349e3b2)。
	- 完成 fleet 设备中控 MVP：提供设备清单、SSH/scp 操作、CLI、stdio MCP 服务和审计约束，见 [PR #1](https://github.com/DuoQilai/k3-agent-server/pull/1)。
	- 编写 OpenClaw 部署与运维文档，见 [PR #2](https://github.com/DuoQilai/k3-agent-server/pull/2)。

#### 1.4 RISC-V 操作系统支持矩阵

- Update Premier P550 Ubuntu 24.04.3 LTS report.
- Add EBC7702 Ubuntu 24.04.4 LTS report.
- Update LicheePi4A RevyOS test report to 20251226.
- PR：[ruyisdk/support-matrix#389](https://github.com/ruyisdk/support-matrix/pull/389)

#### 1.5 RuyiSDK网站

- [Packages index fine-tuning #556](https://github.com/ruyisdk/ruyisdk-website/pull/556)
- [Delete orphaned files & improve code quality #567](https://github.com/ruyisdk/ruyisdk-website/pull/567)
- [misc: add cloudflare web analytics beacon #553](https://github.com/ruyisdk/ruyisdk-website/pull/553)
- [refactor(packages): relocate generated API data #559](https://github.com/ruyisdk/ruyisdk-website/pull/559)
- [ci: deploy website to Cloudflare Pages #562](https://github.com/ruyisdk/ruyisdk-website/pull/562)
- [ci: fix environment secret parsing #563](https://github.com/ruyisdk/ruyisdk-website/pull/563)
- [misc: convert 2024-07-30-video_20240730_182451.mp4 to webm #564](https://github.com/ruyisdk/ruyisdk-website/pull/564)
- [fix(packages): sort packages by id and version #568](https://github.com/ruyisdk/ruyisdk-website/pull/568)
- [fix(packages): compare semver identifiers safely #569](https://github.com/ruyisdk/ruyisdk-website/pull/569)
- [fix(packages): generate stable API ordering #570](https://github.com/ruyisdk/ruyisdk-website/pull/570)
- [ci: deploy website to GitHub Pages #571](https://github.com/ruyisdk/ruyisdk-website/pull/571)
- [pages: release packages page #573](https://github.com/ruyisdk/ruyisdk-website/pull/573)
- [Revert "misc: delete orphaned files & improve code quality (#567)" #574](https://github.com/ruyisdk/ruyisdk-website/pull/574)
- [ruyisdk/ruyisdk-website#576](https://github.com/ruyisdk/ruyisdk-website/pull/576)
- [ruyisdk/ruyisdk-website#567](https://github.com/ruyisdk/ruyisdk-website/pull/567)
- [ruyisdk/ruyisdk-website#549](https://github.com/ruyisdk/ruyisdk-website/pull/549)
- [ruyisdk/ruyisdk-website#567](https://github.com/ruyisdk/ruyisdk-website/pull/567)
- [ruyisdk-test/oh-my-ruyi#1](https://github.com/ruyisdk-test/oh-my-ruyi/pull/1)

#### 1.6 RuyiSDK技术分享

- 每周三技术分享，实习生（2人）实习总结
- PPT：https://github.com/DuoQilai/ruyi-riscv-linux-book/tree/enzo/deck


### 2. RuyiAI

- buddy-compiler/buddy-mlir
	- [PR #871 — `docs Fix prepare python env steps`](https://github.com/buddy-compiler/buddy-mlir/pull/871)
	修正 README 中 prepare python env 步骤的说明，修复文档中的错误或过时内容
	- [PR #879 — `ci Fix schedule timezone`](https://github.com/buddy-compiler/buddy-mlir/pull/879)
	修复 CI 定时任务的时区配置问题
	- [PR #875 — `ci Fix release publishing and dependency fetches`](https://github.com/buddy-compiler/buddy-mlir/pull/875)
	修复 release 发布流程和依赖获取问题
	- [PR #874 — `ci Simplify Buddy MLIR releases`](https://github.com/buddy-compiler/buddy-mlir/pull/874)
	简化 Buddy MLIR 的 release 发布流程

- RuyiAI-Stack/triton-riscv
	- [PR #65 — `ci Configure renovate to update buddy-mlir automatically`](https://github.com/RuyiAI-Stack/triton-riscv/pull/65) 
	配置 Renovate 自动化工具，自动追踪并更新 buddy-mlir 依赖，减少手动维护成本
	- [PR #68 — `ci Configure renovate to update buddy-hash.txt`](https://github.com/RuyiAI-Stack/triton-riscv/pull/68)
	配置 Renovate 自动更新 buddy-hash.txt 依赖版本文件
	- [PR #62 — `ci Use V100`](https://github.com/RuyiAI-Stack/triton-riscv/pull/62)
	扩展 riscv64 CI 机器规格选项，新增 rva23 和 xlarge（V100 机型）两种 runner；针对 riscv64 架构限制并行构建任务数为一倍 CPU，避免大编译任务内存耗尽
	- [PR #69 — `ci Add Renovate dependencyDashboard`](https://github.com/RuyiAI-Stack/triton-riscv/pull/69)
	添加 Renovate 依赖仪表盘，方便查看依赖更新状态

### 3. RISC-V 操作系统支持矩阵

- VisionFive2_Lite: add Ubuntu test report：[ruyisdk/support-matrix#390](https://github.com/ruyisdk/support-matrix/pull/390)
- VisionFive2_Lite: add Debian test report：[ruyisdk/support-matrix#391](https://github.com/ruyisdk/support-matrix/pull/391)
- K510: update BuildRoot test report：[ruyisdk/support-matrix#392](https://github.com/ruyisdk/support-matrix/pull/392)

### 4. RISC-V 开发板编译工具链测试

- 补充 A210 SODIMM V2、RISC-V Book 和 RISC-V Book 2 的 5 张测试环境照片及拍摄说明，见 [PR #3](https://github.com/DuoQilai/asciinema/pull/3)。
- 完成[《RuyiSDK 支持矩阵与开发板文档》汇报材料](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RuyiSDK/RuyiSDK%E6%94%AF%E6%8C%81%E7%9F%A9%E9%98%B5%E4%B8%8E%E5%BC%80%E5%8F%91%E6%9D%BF%E6%96%87%E6%A1%A3-%E6%B1%87%E6%8A%A5.pptx) 。
- Add VisionFive2 Lite and K510 test environment photos：[DuoQilai/asciinema#4](https://github.com/DuoQilai/asciinema/pull/4)

### 5. SAIL和ACT

#### 5.1 SAIL和ACT开发

- 软件所与某企业扩展合作项目，产出占本月Sail产出重要比例，不公开
- [PR #1867 — `Add Sscpuutil extension`](https://github.com/riscv/sail-riscv/pull/1867)
新增 Sscpuutil（CPU Utilization Counter）扩展支持，用于监控和读取 CPU 利用率计数器。涉及 CSR 寄存器定义、stateen 访问控制检查、stateen 寄存器扩展、step 钩子注入，以及配套的汇编测试用例
- [PR #1886 - `update zvabd encodings`](https://github.com/riscv/sail-riscv/pull/1886) 
审核了相关代码，提供了修改意见
- [sail-riscv#1924](https://github.com/riscv/sail-riscv/pull/1924)
- [sail-riscv#commit7d19](https://github.com/riscv/sail-riscv/pull/1841/changes/7d197e2caa7c6be543f779eb99a71e474e1ef8db)
- [sail-riscv#commit39e9](https://github.com/riscv/sail-riscv/pull/1857/changes/39e9d23121b0c4ab9fbbb8d937ac6dbea2ed1d8e)
- [sail-riscv#1856](https://github.com/riscv/sail-riscv/pull/1856)

#### 5.2 SAIL会议

- 参加东亚双周会 0806，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1UGGidiiyV1_mzS89JuBL9QcHliCZu-6Q4P8owSYHJ7s/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0820，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1inb7yaX-olnRCd_BAQcQORD1U5vEcUYL97pYdi6gsBI/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

### 6. RISC-V Linux 课程开发

- ruyi-riscv-linux-book
使用RuyiSDK在RISC-V开发板下实现GCC GPIO和AI编程
	- 项目仓库：[DuoQilai/ruyi-riscv-linux-book](https://github.com/DuoQilai/ruyi-riscv-linux-book)
	- 课程修改方案：
		- [《课程内容更新汇报（第 1–4 章）》](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/enzo/MISC/course-updates-report.md)：汇总 8 月 20—26 日的课程调整，包括 RuyiSDK 安装、虚拟环境、系统烧录和交叉编译流程，以及 C 语言、GPIO、继电器、`select` 和命令解析示例的补充与结构优化。
	- 第 1—6 章课程内容建设：
		- [PR #4](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/4)：完成课程首页、大纲、课程说明、评价标准和导航等课程框架，以及第一章“环境与工具链”的讲义、实验和 CoreMark 上板通道验收内容。
		- [PR #5](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/5)：完成第二章“够用的 C 语言基础”的讲义与实验，补充多文件构建、命令表、滞回温控等可运行示例和学生练习脚手架。
		- [PR #6](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/6)：完成第三章“GPIO 与执行器”的讲义与继电器控制风扇实验，提供 GPIO 示例、温控程序和 LicheePi 4A 相关参考资料。
		- [PR #7](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/7)：完成第四章“串口对话与温控”的讲义与实验，覆盖 DHT22、TXS 电平转换、命令分发和基于 `select` 的采样控制主循环。
		- [PR #8](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/8)：完成第五章“网络与 MQTT”的讲义与远程控灯实验，覆盖 Broker、主题、发布订阅、状态上报和 TCP/IP 分层抓包，并提供 `mqtt-led` 项目脚手架。
		- [PR #9](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/9)：完成第六章“线程与协同”的讲义与实验，提供 `race-demo` 和 `tri-thread` 示例，讲解数据竞争、ThreadSanitizer、互斥锁和安全退出。
		- 课程大纲：https://duoqilai.github.io/ruyi-riscv-linux-book/docs/CourseOutline.html
		- ch01 lab：https://duoqilai.github.io/ruyi-riscv-linux-book/chapters/ch01/lab.html
		- ch02 lab：https://duoqilai.github.io/ruyi-riscv-linux-book/chapters/ch02/lab.html
		- ch03 lab：https://duoqilai.github.io/ruyi-riscv-linux-book/chapters/ch03/lab.html
		- ch04 lab：https://duoqilai.github.io/ruyi-riscv-linux-book/chapters/ch04/lab.html

- [RISC-V ROS2 机器人操作系统编程技术](https://gitee.com/yunxiangluo/ROS2_RISCV)
本课程以 RISC-V 开源硬件平台（openEuler 24.03 LTS）为硬件基础，以 ROS2（Robot Operating System 2）Humble 为技术平台，系统讲授机器人的软件开发框架、分布式通信机制、实时控制系统以及智能终端装调技术。课程 ROS2 程序运行在RISC-V 板卡上，Gazebo、RViz2 等仿真与可视化环境运行在 Windows x86 主机上，两端通过局域网内同一 DDS 域互联。目前完成了ROS2课程建设，正在在RISC-V环境下移植和验证

### 7. 2026年RISC-V 中国峰会

- [Ruyi 包管理器 - 专为 RISC-V 开发者打造的全方位、集成式全功能开发环境](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/L9QA9JTA8JBGGU8CFWXEPPPKHUFBSWMB)
- [AI 驱动的 RISC-V 图形化应用测试（RuyiSDK IDE测试方法，海报）](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/YKGSC8XVWAGA9LE9JKHMRQQUCCHAAKM7)
- [RISC-V课程移植方法与RuyiSDK生态建设（报告）](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/JJPCAAGRQEGEDGWMXHGFHZCBGA97ASGT)
- [从碎片化到体系化：RISC-V 课程质量评估与系统化重构（海报）](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/KLZWWYCLBYPQHYWYHKHT8CYPHNMGHYSF)
- [一种将 RISC-V Sail 模型高效应用于芯片验证的方法](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/JH7LXDC8VBMWUJ9C3UN3YKNDPUEAHWWL)
- [从碎片化到体系化：RISC-V 课程质量评估与系统化重构（海报）](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/KLZWWYCLBYPQHYWYHKHT8CYPHNMGHYSF)
- [Sail-RISCV-WASM：浏览器原生 RISC-V 工具链与调试工作台](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/WBHTH7Q9338NF7UYM7E87FX8HG37M9XJ)
- [从碎片化到体系化：RISC-V 课程质量评估与系统化重构（海报）](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/KLZWWYCLBYPQHYWYHKHT8CYPHNMGHYSF)

### 8. RVI CSC 中国客户调查

- 辅助部分中国企业完成调查表
- 联系更多中国企业参与

### 9. 职工

#### 9.1 蔡玮霖

- ruyisdk-website 仓库审核 2 个 pr
    - [Packages index fine-tuning #556](https://github.com/ruyisdk/ruyisdk-website/pull/556)
    - [Delete orphaned files & improve code quality #567](https://github.com/ruyisdk/ruyisdk-website/pull/567)

- ruyisdk-website 仓库提交 11 个 pr
    - [misc: add cloudflare web analytics beacon #553](https://github.com/ruyisdk/ruyisdk-website/pull/553)
    - [refactor(packages): relocate generated API data #559](https://github.com/ruyisdk/ruyisdk-website/pull/559)
    - [ci: deploy website to Cloudflare Pages #562](https://github.com/ruyisdk/ruyisdk-website/pull/562)
    - [ci: fix environment secret parsing #563](https://github.com/ruyisdk/ruyisdk-website/pull/563)
    - [misc: convert 2024-07-30-video_20240730_182451.mp4 to webm #564](https://github.com/ruyisdk/ruyisdk-website/pull/564)
    - [fix(packages): sort packages by id and version #568](https://github.com/ruyisdk/ruyisdk-website/pull/568)
    - [fix(packages): compare semver identifiers safely #569](https://github.com/ruyisdk/ruyisdk-website/pull/569)
    - [fix(packages): generate stable API ordering #570](https://github.com/ruyisdk/ruyisdk-website/pull/570)
    - [ci: deploy website to GitHub Pages #571](https://github.com/ruyisdk/ruyisdk-website/pull/571)
    - [pages: release packages page #573](https://github.com/ruyisdk/ruyisdk-website/pull/573)
    - [Revert "misc: delete orphaned files & improve code quality (#567)" #574](https://github.com/ruyisdk/ruyisdk-website/pull/574)

- ruyi 仓库提交 1 个 issue
    - [ruyi entity list 传入多个 -t 参数时只消费其中一个 #492](https://github.com/ruyisdk/ruyi/issues/492)

- ruyi-backend 仓库提交 1 个 issue
    - [ruyi telemetry upload 经常失败 #117](https://github.com/ruyisdk/ruyi-backend/issues/117)

- ruyisdk-test/ruyi-pytest 仓库提交 11 个 commit
    - misc: add test point count script [eb7ab5e](https://github.com/ruyisdk-test/ruyi-pytest/commit/eb7ab5e72d1001d28cfd9a70b36e6186e13c4ca9)
    - tests: add and harden self-management coverage [b054d1b](https://github.com/ruyisdk-test/ruyi-pytest/commit/b054d1b37b3d4c098f223203a5ae3f6a95d9549e)
    - tests: cover experimental entity commands [db451f6](https://github.com/ruyisdk-test/ruyi-pytest/commit/db451f603302c41dc1964c9729706cf74090e23c)
    - test: update Ruyi dependency and entity coverage [9f32e45](https://github.com/ruyisdk-test/ruyi-pytest/commit/9f32e456e23a54ef5e585296848a4dc5176c1eaf)
    - test: mark entity filter defect in 0.52 beta [6d0d335](https://github.com/ruyisdk-test/ruyi-pytest/commit/6d0d335985e2e7c0bc79ce1f632a5c213e884c04)
    - test: extend package download timeouts [a9659f7](https://github.com/ruyisdk-test/ruyi-pytest/commit/a9659f793f15f9b01b0e71baf29bbdb9451877f0)
    - test: expose Ruyi version fixture [c9c91d4](https://github.com/ruyisdk-test/ruyi-pytest/commit/c9c91d4fbc07e5ba4814d4ae43640165a8c0137f)
    - test: honor mirror choice for standalone download [9f6f390](https://github.com/ruyisdk-test/ruyi-pytest/commit/9f6f3901d4e1e393541379feefcb963d985ca594)
    - test: skip Linux-only package tests on macOS [2175dcc](https://github.com/ruyisdk-test/ruyi-pytest/commit/2175dcc6a30b6ff2d165f8faf76c3479b5418261)
    - test: isolate LC_CTYPE in test environment [a0824eb](https://github.com/ruyisdk-test/ruyi-pytest/commit/a0824ebe3575c14b2b47027e531e3e0919e665a9)
    - test: switch from gnu-plct to gnu-ruyisdk for macOS tests [fecb7f7](https://github.com/ruyisdk-test/ruyi-pytest/commit/fecb7f7930688495f026bb666e331d13849bd9f9)

- ruyisdk-test/oh-my-ruyi 仓库提交 46 个 commit

#### 9.2 阎明铸

##### 9.2.1 Sail

- 厂商合作开发工作(产出不公开,量大)

- PR #1867 — `Add Sscpuutil extension`  https://github.com/riscv/sail-riscv/pull/1867
	- 新增 Sscpuutil（CPU Utilization Counter）扩展支持，用于监控和读取 CPU 利用率计数器。涉及 CSR 寄存器定义、stateen 访问控制检查、stateen 寄存器扩展、step 钩子注入，以及配套的汇编测试用例

- PR #1886 - `update zvabd encodings` https://github.com/riscv/sail-riscv/pull/1886
	- 审核了相关代码，提供了修改意见

- 参加SAIL周会和东亚双周会 0806，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1UGGidiiyV1_mzS89JuBL9QcHliCZu-6Q4P8owSYHJ7s/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

- 参加SAIL周会和东亚双周会 0820，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1inb7yaX-olnRCd_BAQcQORD1U5vEcUYL97pYdi6gsBI/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

##### 9.2.2 Ruyi AI

- buddy-compiler/buddy-mlir

	- PR #871 `[docs] Fix prepare python env steps`  https://github.com/buddy-compiler/buddy-mlir/pull/871
		- 修正 README 中 prepare python env 步骤的说明，修复文档中的错误或过时内容

	- PR #879 `[ci] Fix schedule timezone`  https://github.com/buddy-compiler/buddy-mlir/pull/879
	- 修复 CI 定时任务的时区配置问题

	- PR #875 `[ci] Fix release publishing and dependency fetches`  https://github.com/buddy-compiler/buddy-mlir/pull/875
		- 修复 release 发布流程和依赖获取问题

	- PR #874**  `[ci] Simplify Buddy MLIR releases`  https://github.com/buddy-compiler/buddy-mlir/pull/874
		- 简化 Buddy MLIR 的 release 发布流程

- RuyiAI-Stack/triton-riscv

	- PR #65 `[ci] Configure renovate to update buddy-mlir automatically`  https://github.com/RuyiAI-Stack/triton-riscv/pull/65
		- 配置 Renovate 自动化工具，自动追踪并更新 buddy-mlir 依赖，减少手动维护成本

	- PR #68 `[ci] Configure renovate to update buddy-hash.txt` https://github.com/RuyiAI-Stack/triton-riscv/pull/68
		- 配置 Renovate 自动更新 buddy-hash.txt 依赖版本文件
	
	- PR #62 `[ci] Use V100` https://github.com/RuyiAI-Stack/triton-riscv/pull/62
		- 扩展 riscv64 CI 机器规格选项，新增 rva23 和 xlarge（V100 机型）两种 runner；针对 riscv64 架构限制并行构建任务数为一倍 CPU，避免大编译任务内存耗尽

	- PR #69 `[ci] Add Renovate dependencyDashboard` https://github.com/RuyiAI-Stack/triton-riscv/pull/69
		- 添加 Renovate 依赖仪表盘，方便查看依赖更新状态

#### 9.3 张馥媛

##### 9.3.1 RuyiSDK 示例代码库建设

- 审核或参与开发板示例文档扩充
	- 开发板示例文档扩充：
		- SpacemiT K3 Pico-ITX：新增中英文板卡概述及 CoreMark、HelloWorld、llama-server 中文示例文档，见 [PR #33](https://github.com/ruyisdk/board-docs/pull/33)。
		- HelloWorld 英文文档：补充 BPI-F3、Duo、Duo S、EBC7700、Jupiter2、K3 Pico-ITX、LicheePi 4A 等开发板的英文文档，见 [PR #36](https://github.com/ruyisdk/board-docs/pull/36)。
		- Canaan K510：整理 CoreMark 与 HelloWorld 的中英文文档和示例目录，见 [PR #37](https://github.com/ruyisdk/board-docs/pull/37)。
		- BPI-CANMV-K230D-Zero（原 K230D）：新增板卡概述与系统安装文档，文档见 [PR #41](https://github.com/ruyisdk/board-docs/pull/41)，命名更新见 [PR #42](https://github.com/ruyisdk/board-docs/pull/42)。
	- 仓库维护：
		- 将示例分类元数据统一为 `category`，见 [PR #27](https://github.com/ruyisdk/board-docs/pull/27)。
		- 完善中英文示例文档模板，见 [PR #28](https://github.com/ruyisdk/board-docs/pull/28)。
		- 新增元数据检查及配套工作流，见 [PR #30](https://github.com/ruyisdk/board-docs/pull/30)。
		- 新增 DCO 检查并改进 Pull Request 模板，见 [PR #31](https://github.com/ruyisdk/board-docs/pull/31)。
		- 将 `board-docs` 的文档站入口更新为 [boards.ruyisdk.org](https://boards.ruyisdk.org/)，见 [PR #32](https://github.com/ruyisdk/board-docs/pull/32)。
		- 新增 README 支持矩阵自动生成与一致性检查，见 [PR #34](https://github.com/ruyisdk/board-docs/pull/34)。
		- 补充板卡与示例命名、版本记录和中英文文档规范，见 [PR #35](https://github.com/ruyisdk/board-docs/pull/35)。
		- 统一 Ruyi 安装章节和版本化下载路径，新增版本更新脚本及每月版本更新工作流，见 [PR #38](https://github.com/ruyisdk/board-docs/pull/38)。
		- 新增示例级中英文覆盖率检查，支持报告模式和严格模式，见 [PR #40](https://github.com/ruyisdk/board-docs/pull/40)。
- board-docs-frontend：
	- 项目仓库：[DuoQilai/board-docs-frontend](https://github.com/DuoQilai/board-docs-frontend)
	- 在线站点：[中文入口](https://boards.ruyisdk.org/)；[英文入口](https://boards.ruyisdk.org/en/)
	- 完善示例分类读取和展示逻辑，支持 `category` 元数据、扩充分类体系并统一入门分类标签，见 [PR #1](https://github.com/DuoQilai/board-docs-frontend/pull/1)、[PR #2](https://github.com/DuoQilai/board-docs-frontend/pull/2) 和 [PR #3](https://github.com/DuoQilai/board-docs-frontend/pull/3)。
	- 配置正式站点地址、站点地图和中英文语言配置，新增 Pull Request 与 `main` 分支构建检查，见 [PR #5](https://github.com/DuoQilai/board-docs-frontend/pull/5)。
	- 完成中英文界面、共享页面组件、英文路由和语言切换，见 [PR #6](https://github.com/DuoQilai/board-docs-frontend/pull/6)。
	- 新增前端分类与 `board-docs` 元数据的双向一致性检查；未知分类回退到“其他”，并可发现跨仓库分类不一致，见 [PR #7](https://github.com/DuoQilai/board-docs-frontend/pull/7)。
	- 按页面语言选择 `README.md`、`README_zh.md` 或旧版示例文档；缺少对应语言时显示回退提示，见 [PR #8](https://github.com/DuoQilai/board-docs-frontend/pull/8)。

##### 9.3.2 RISC-V Support Matrix

- 审核或参与操作系统支持报告更新
	- VisionFive 2 Lite：
		- 新增中英文 Ubuntu 测试报告：[PR #390](https://github.com/ruyisdk/support-matrix/pull/390)。
		- 新增中英文 Debian 测试报告：[PR #391](https://github.com/ruyisdk/support-matrix/pull/391)。
	- Canaan K510：
		- 更新中英文 BuildRoot 测试报告：[PR #392](https://github.com/ruyisdk/support-matrix/pull/392)。

##### 9.3.3 K3 Pico-ITX AI 服务与设备中控

- 仓库：[DuoQilai/k3-agent-server](https://github.com/DuoQilai/k3-agent-server)
- 建立可复现的 K3 AI 服务部署基线，整理 DSH Agent、llama-server、本地模型、systemd 用户服务及日常启停与日志文档，见 [Commit 3bc2926](https://github.com/DuoQilai/k3-agent-server/commit/3bc29267401823a65c2ff6a0a180b1615349e3b2)。
- 完成 fleet 设备中控 MVP：提供设备清单、SSH/scp 操作、CLI、stdio MCP 服务和审计约束，见 [PR #1](https://github.com/DuoQilai/k3-agent-server/pull/1)。
- 编写 OpenClaw 部署与运维文档，见 [PR #2](https://github.com/DuoQilai/k3-agent-server/pull/2)。

##### 9.3.4 RISC-V Linux 系统与开发板实践课程

- 审核ruyi-riscv-linux-book
	- 项目仓库：[DuoQilai/ruyi-riscv-linux-book](https://github.com/DuoQilai/ruyi-riscv-linux-book)
	- 课程修改方案：
		- [《课程内容更新汇报（第 1–4 章）》](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/enzo/MISC/course-updates-report.md)：汇总 8 月 20—26 日的课程调整，包括 RuyiSDK 安装、虚拟环境、系统烧录和交叉编译流程，以及 C 语言、GPIO、继电器、`select` 和命令解析示例的补充与结构优化。
	- 第 1—6 章课程内容建设：
		- [PR #4](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/4)：完成课程首页、大纲、课程说明、评价标准和导航等课程框架，以及第一章“环境与工具链”的讲义、实验和 CoreMark 上板通道验收内容。
		- [PR #5](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/5)：完成第二章“够用的 C 语言基础”的讲义与实验，补充多文件构建、命令表、滞回温控等可运行示例和学生练习脚手架。
		- [PR #6](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/6)：完成第三章“GPIO 与执行器”的讲义与继电器控制风扇实验，提供 GPIO 示例、温控程序和 LicheePi 4A 相关参考资料。
		- [PR #7](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/7)：完成第四章“串口对话与温控”的讲义与实验，覆盖 DHT22、TXS 电平转换、命令分发和基于 `select` 的采样控制主循环。
		- [PR #8](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/8)：完成第五章“网络与 MQTT”的讲义与远程控灯实验，覆盖 Broker、主题、发布订阅、状态上报和 TCP/IP 分层抓包，并提供 `mqtt-led` 项目脚手架。
		- [PR #9](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/9)：完成第六章“线程与协同”的讲义与实验，提供 `race-demo` 和 `tri-thread` 示例，讲解数据竞争、ThreadSanitizer、互斥锁和安全退出。

##### 9.3.5 RISC-V 编译工具链+开发板 测试

- 开发板测试素材：
	- 补充 A210 SODIMM V2、RISC-V Book 和 RISC-V Book 2 的 5 张测试环境照片及拍摄说明，见 [PR #3](https://github.com/DuoQilai/asciinema/pull/3)。
	- 补充 VisionFive 2 Lite 和 K510 的 4 张测试环境照片，见 [PR #4](https://github.com/DuoQilai/asciinema/pull/4)。
- RuyiSDK 汇报材料：
	- 完成[《RuyiSDK 支持矩阵与开发板文档》汇报材料](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RuyiSDK/RuyiSDK%E6%94%AF%E6%8C%81%E7%9F%A9%E9%98%B5%E4%B8%8E%E5%BC%80%E5%8F%91%E6%9D%BF%E6%96%87%E6%A1%A3-%E6%B1%87%E6%8A%A5.pptx) 。

##### 9.3.6 RISC-V 中国峰会投稿

- [RISC-V课程移植方法与RuyiSDK生态建设](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/JJPCAAGRQEGEDGWMXHGFHZCBGA97ASGT)
- [从碎片化到体系化：RISC-V 课程质量评估与系统化重构](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/KLZWWYCLBYPQHYWYHKHT8CYPHNMGHYSF)
