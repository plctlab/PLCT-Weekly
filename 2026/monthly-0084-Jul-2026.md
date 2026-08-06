# RISC-V 软件生态进展 · 第 84 期·2026 年 7 月汇总

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

2026年7月测试团队完成了RuyiSDK 0.51.0-beta版本在Debian、Ubuntu、openEuler、Fedora等4种发行版及多架构（x86_64/aarch64/riscv64）上的包管理器测试，发布19份测试报告；Eclipse插件v0.1.6-beta.2完成发版测试与回归，新增及遗留缺陷均已跟踪；自动化测试框架ruyi-pytest新增多个测试用例。RuyiSDK开发示例新增Jupiter2、VisionFive 2 Lite、K510等开发板示例文档，完善board-docs仓库贡献规范与模板，官网完成下载页重构、首页优化等7项更新。packages-index新增A210-SODIMM设备并更新多款开发板镜像。RuyiAI方面，为buddy-mlir贡献PyTorch 2.13支持及CI改进，推进triton-riscv和llvm-project的优化。开发板工具链测试覆盖14款以上RISC-V板卡，编写自动化测试脚本并录制演示视频。SAIL提交2个上游PR，修复模型缺陷并增强ACT支持。RuyiSDK嵌入式课程发布大纲、评估标准及初步完成前3章实验。此外辅助完成了RVI CSC RISC-V 认证方面中国厂商问卷材料的翻译，同时协助了部分中国厂商完成填报。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.51.0-beta.20260714 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/README.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260715/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu26.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260715/RUYI_包管理_Ubuntu26.04_x86_64_测试结果.md)
    - [Ubuntu26.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Ubuntu26.04_riscv64_测试结果.md)
    - [Ubuntu26.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Ubuntu26.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260715/RUYI_包管理_Fedora42_x86_64_测试结果.md)

    - 缺陷：  
      - 文档测试上一版本遗留 2 个缺陷：

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，修复已经延后  |

      - Ruyi 包管理器测试

        遗留缺陷：

        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415) | 一般 | 已有 issue 回复 |

      - RuyiSDK Eclipse IDE 发版测试

        v0.1.6-beta.1 测试有严重缺陷，已经重新发布新 beta 版本 v0.1.6-beta.2 重新测试。

        本版本发布的 Eclipse 插件测试[报告](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/tree/v0.1.6-beta.2)。

        遗留缺陷：

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [命令执行提示框可以任意关闭且无法重新打开 #82](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/82)   | 建议 |   |
        | [虚拟环境建立的项目绑定问题 #84](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/84) | 建议 |  |
        | [安装插件时 Eclipse 提示未签名 #85](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/85) | 建议 |  |
        | [New Virtual environment添加虚拟环境时响应时间过长 #177](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/177) | 建议 |  |
        | [在使用不包含 sysroot 的工具链 （例如 xscc） 时，可通过指定其他工具链，此时仍包含xscc #179](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/179) | 建议 |  |

        新增缺陷：

        | 缺陷 | 问题等级 | 备注 |
        | --- | --- | --- |
        | [用户无法直观获知项目当前启用的虚拟环境 #191](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/191) | 建议 |  |
        | [select package 不可用 #196](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/196) | 建议 |  |

    - 更新 Ruyi 0.50.0 测试报告的 IDE 和 VSCode 部分
      - [!98 Update reports](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/98)
      - [!99 Update 0.50.0 IDE test status](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/99)

- https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/11 
- https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/12
- ruyisdk-eclipse-plugins 
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/179 在使用不包含 sysroot 的工具链 （例如 xscc） 时，可通过指定其他工具链，此时仍包含xscc
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/191 用户无法直观获知项目当前启用的虚拟环境
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/192 目前问卷弹窗关闭方式未知
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/196 select package 不可用
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/98  UI：新闻界面切换仅未读“勾号”不明显
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/90  venv 文件夹中有一些可以自动获取的东西，不需要手动填写
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/152 Ruyi-venv中的vnev path需要手动点击右侧列表，显示项目路径
- ruyisdk-vscode-extension
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/204 Ruyi软件包列表i18n
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/205 在使用不包含 sysroot 的工具链 （例如 xscc） 时，可通过指定其他工具链，此时仍包含xscc
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/206 项目构建i18n
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/211 工具链列表未排序
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/212 工具链全选按钮无意义
- [#480 repo add ruyisdk 报错信息在非 Rich 终端下缺失关键词 repo](https://github.com/ruyisdk/ruyi/issues/480)

#### 1.2 RuyiSDK测试开发

- packages-index
  - [device/zhihe-a210-sodimm: new device #208](https://github.com/ruyisdk/packages-index/pull/208)
  - [#201 board-image/armbian-spacemit-musepipro-xfce: add new package](https://github.com/ruyisdk/packages-index/pull/201)
  - [#202 board-image/freebsd-riscv64-mini-live: bump to latest version 15.1](https://github.com/ruyisdk/packages-index/pull/202)
  - [#203 board-image/revyos-sipeed-lpi4a: bump to latest version 20260504](https://github.com/ruyisdk/packages-index/pull/203)
  - [#204 board-image/revyos-sipeed-lcon4a: bump to latest version 20260504](https://github.com/ruyisdk/packages-index/pull/204)
  - [#205 board-image/revyos-sipeed-laptop4a: bump to latest version 20260504](https://github.com/ruyisdk/packages-index/pull/205)
  - [#207 board-image/openbsd-riscv64-live: bump to version 7.9](https://github.com/ruyisdk/packages-index/pull/207)
  - [#184 board-image/armbian-orangepi-rv2-xfce: add new packages](https://github.com/ruyisdk/packages-index/pull/184)
  - [#185 board-image/armbian-orangepi-rv2-minimal: add new packages](https://github.com/ruyisdk/packages-index/pull/185)
  - [#188 board-image/armbian-starfive-visionfive2-xfce: add new packages](https://github.com/ruyisdk/packages-index/pull/188)
  - [#189 board-image/armbian-starfive-visionfive2-minimal:add new packages](https://github.com/ruyisdk/packages-index/pull/189)
  - [#201 board-image/armbian-spacemit-musepipro-xfce: add new package](https://github.com/ruyisdk/packages-index/pull/201)
  - [#202 board-image/freebsd-riscv64-mini-live: bump to latest version 15.1](https://github.com/ruyisdk/packages-index/pull/202) 备注：非直接从pr中合并，从commit中和并入仓库
  - [#203 board-image/revyos-sipeed-lpi4a: bump to latest version 20260504](https://github.com/ruyisdk/packages-index/pull/203)
  - [#204 board-image/revyos-sipeed-lcon4a: bump to latest version 20260504](https://github.com/ruyisdk/packages-index/pull/204)
  - [#205 board-image/revyos-sipeed-laptop4a: bump to latest version 20260504](https://github.com/ruyisdk/packages-index/pull/205)
  - [#207 board-image/openbsd-riscv64-live: bump to version 7.9](https://github.com/ruyisdk/packages-index/pull/207)
  - [#202 board-image/freebsd-riscv64-mini-live: bump to latest version 15.1](https://github.com/ruyisdk/packages-index/pull/202)
- ruyi-backend
  - [/releases/latest-pm 将 macOS 架构二进制显示为 linux/macos-arm64 #113](https://github.com/ruyisdk/ruyi-backend/issues/113)
- ruyisdk-test/ruyi-pytest
  - [New test cases based on ruyi v0.50.0 #13](https://github.com/ruyisdk-test/ruyi-pytest/pull/13)
  - [ruyi: update dev dep ruyi version to v0.50.0 #14](https://github.com/ruyisdk-test/ruyi-pytest/pull/14)
  - [misc: revert for test failure caused by #9 #15](https://github.com/ruyisdk-test/ruyi-pytest/pull/15)
  - [tests: fix codebase mixture #16](https://github.com/ruyisdk-test/ruyi-pytest/pull/16)  
  - [#10 tests: add repo test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/10)
  - [#11 tests: add update test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/11)
  - [#6 tests: add self test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/6)
  - [ruyi: update testcases for v0.51.0b20260714 #17](https://github.com/ruyisdk-test/ruyi-pytest/pull/17)
- ruyisdk-test/ruyi-pytest 仓库审核 4 个 pr
  - [tests: add pytest-html for visual test reports #9](https://github.com/ruyisdk-test/ruyi-pytest/pull/9)
  - [tests: add repo test cases #10](https://github.com/ruyisdk-test/ruyi-pytest/pull/10)
  - [tests: add update test cases #11](https://github.com/ruyisdk-test/ruyi-pytest/pull/11)
  - [tests: add telemetry test cases #12](https://github.com/ruyisdk-test/ruyi-pytest/pull/12)
- ruyi 本地管理 GUI [oh-my-ruyi](https://github.com/ruyisdk-test/oh-my-ruyi)
  - [57d801e...44efe7f](https://github.com/ruyisdk-test/oh-my-ruyi/compare/57d801ee9c63e389b7fe1c297a573c9febc62117...44efe7feb0ccf407412709fb757a21fbb64f4f97) 共计 71 commits，16099 行增加 2009 行删除
- [https://github.com/a1gorhythm7/oh-my-ruyi](https://github.com/a1gorhythm7/oh-my-ruyi)

#### 1.3 RuyiSDK开发示例库和示例库网站开发

- 开发板示例文档
	- VisionFive 2 Lite
		- [RuyiSDK 外设示例：基础按键检测](https://github.com/ruyisdk/board-docs/blob/add-documents-K510-VF2Lite/VisionFive2Lite/Button/README_zh.md)
	- Canaan K510-CRB-V1.2 KIT
		- [RuyiSDK 外设示例：通信测试](https://github.com/ruyisdk/board-docs/blob/add-documents-K510-VF2Lite/K510/UART/README.md)
	- Milk-V Jupiter2
		- 概述：[README.md](https://github.com/ruyisdk/board-docs/blob/main/Jupiter2/README.md)；[README_zh.md](https://github.com/ruyisdk/board-docs/blob/main/Jupiter2/README_zh.md)
		- [RuyiSDK 基础示例：HelloWorld](https://github.com/ruyisdk/board-docs/blob/main/Jupiter2/HelloWorld/README_zh.md)
		- [RuyiSDK 基础示例：Coremark](https://github.com/ruyisdk/board-docs/blob/main/Jupiter2/Coremark/README_zh.md)
- board-docs-frontend website
	- 在线站点：[board-docs-frontend](https://board-docs-frontend.pages.dev/)
	- Commit：[fix(ci): replace git submodule update --remote with explicit fetch/checkout](https://github.com/DuoQilai/board-docs-frontend/commit/3295c3f)
	- Commit：[docs: remove dev setup and manual trigger, keep essentials](https://github.com/DuoQilai/board-docs-frontend/commit/38a8fc9)
- board-docs仓库维护
	- 仓库配置：
		- [.gitignore](https://github.com/ruyisdk/board-docs/blob/main/.gitignore)
	- 贡献规范：
		- [CONTRIBUTING.md](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/CONTRIBUTING.md)
		- [CONTRIBUTING_zh.md](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/CONTRIBUTING_zh.md)
	- board-doc 模板
		- [.github/ISSUE_TEMPLATE/content-bug.yml](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/.github/ISSUE_TEMPLATE/content-bug.yml)
		- [.github/ISSUE_TEMPLATE/content-new.yml](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/.github/ISSUE_TEMPLATE/content-new.yml)
		- [.github/ISSUE_TEMPLATE/content-outdated.yml](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/.github/ISSUE_TEMPLATE/content-outdated.yml)
		- [.github/PULL_REQUEST_TEMPLATE.md](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/.github/PULL_REQUEST_TEMPLATE.md)
	- 文档模板更新：
		- [templates/](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/templates/%5Bboard-name%5D/%5Bexample-name%5D/README_zh.md)
- [VisionFive 2 Lite 基础按键检测](https://github.com/zhiyao310/board-docs/blob/add-documents-K510-VF2Lite/VisionFive2Lite/Button/README_zh.md)
- [Canaan K510 CRB-V1.2 KIT UART通信测试](https://github.com/zhiyao310/board-docs/blob/add-documents-K510-VF2Lite/K510/UART/README.md)
- [Add testing documents for K510 and VF2Lite](https://github.com/ruyisdk/board-docs/pull/23)
- 站点 https://board-docs-frontend.pages.dev/
- https://github.com/DuoQilai/board-docs-frontend/commit/3295c3f fix(ci): replace git submodule update --remote with explicit fetch/checkout
- https://github.com/DuoQilai/board-docs-frontend/commit/2568a6e feat(ci): add deploy hook + change logging to sync workflow
- https://github.com/DuoQilai/board-docs-frontend/commit/38a8fc9 docs: remove dev setup and manual trigger, keep essentials

#### 1.4 RISC-V 操作系统支持矩阵

- Update Premier P550 Ubuntu 24.04.3 LTS report.
- Add EBC7702 Ubuntu 24.04.4 LTS report.
- Update LicheePi4A RevyOS test report to 20251226.
- PR：[ruyisdk/support-matrix#389](https://github.com/ruyisdk/support-matrix/pull/389)

#### 1.5 RuyiSDK网站

- [Add package-index-web to official site #545](https://github.com/ruyisdk/ruyisdk-website/pull/545)
- [Optimize the layouts of homepage onboarding component. #549](https://github.com/ruyisdk/ruyisdk-website/pull/549)
- [pages(downloads): release new download page #540](https://github.com/ruyisdk/ruyisdk-website/pull/540)
- [pages(issue): release issue page #541](https://github.com/ruyisdk/ruyisdk-website/pull/541)
- [Improve layout for installation script #544](https://github.com/ruyisdk/ruyisdk-website/pull/544)
- [pages(about): add ruyisdk survey qr code #550](https://github.com/ruyisdk/ruyisdk-website/pull/550)
- [misc: add cloudflare web analytics beacon #553](https://github.com/ruyisdk/ruyisdk-website/pull/553)
- [ruyisdk/ruyisdk-website#544](https://github.com/ruyisdk/ruyisdk-website/pull/544)
- [ruyisdk/ruyisdk-website#545](https://github.com/ruyisdk/ruyisdk-website/pull/545)
- [ruyisdk/ruyisdk-website#549](https://github.com/ruyisdk/ruyisdk-website/pull/549)
- [ruyisdk/ruyisdk-website#551](https://github.com/ruyisdk/ruyisdk-website/pull/551)
- [ruyisdk-test/oh-my-ruyi#1](https://github.com/ruyisdk-test/oh-my-ruyi/pull/1)
- [ruyisdk/ruyisdk-website#544](https://github.com/ruyisdk/ruyisdk-website/pull/544)
- [ruyisdk/ruyisdk-website#545](https://github.com/ruyisdk/ruyisdk-website/pull/545)
- [ruyisdk/ruyisdk-website#549](https://github.com/ruyisdk/ruyisdk-website/pull/549)

#### 1.6 RuyiSDK技术分享

- 每周三技术分享，实习生实习总结

### 2. RuyiAI

- buddy-compiler/buddy-mlir
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/852 [ci] Enable torch 212/213 tests on riscv
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/840 [ci] Use abi3 for release
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/831 [frontend] Add pytorch 2.13 support

- RuyiAI-Stack/triton-riscv
  - 提交 PR https://github.com/RuyiAI-Stack/triton-riscv/pull/36 [compiler] Use +xsmtime instead of +buddyext

- RuyiAI-Stack/llvm-project
  - 提交 PR https://github.com/RuyiAI-Stack/llvm-project/pull/19 [ci] Use pull_request instead of pull_request_target

### 3. RISC-V 开发板编译工具链测试

- [编写 RISC-V 开发板 GCC/LLVM 工具链测试脚本，并录制测试过程](https://github.com/DuoQilai/asciinema)
- 测试用例
	- [board-compiler-test-cases.md](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md)
	- [10种开发板+编译器测试用例.docx](https://github.com/DuoQilai/asciinema/blob/develop/202607/10%E7%A7%8D%E5%BC%80%E5%8F%91%E6%9D%BF%2B%E7%BC%96%E8%AF%91%E5%99%A8%E6%B5%8B%E8%AF%95%E7%94%A8%E4%BE%8B.docx)
- 测试流程和结果
	- 测试说明：[202607/README.md](https://github.com/DuoQilai/asciinema/blob/develop/202607/README.md)
	- 测试用例：[board-compiler-test-cases.md](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md)
	- 测试脚本：[examples/](https://github.com/DuoQilai/asciinema/tree/develop/examples)
	- 测试截图和视频录制：[board-compiler-test-cases_media/](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media)
- ESWIN EBC7700：
	- 测试用例：[GCC和LLVM对EBC7700的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L34)
	- 测试脚本：[01-ebc7700.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/01-ebc7700.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/1.ebc7700)
- HiFive Premier P550：
	- 测试用例：[GCC和LLVM对SiFive HiFive Premier P550的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L63)
	- 测试脚本：[02-p550.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/02-p550.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/2.p550)
- ESWIN EBC7702：
	- 测试用例：[GCC和LLVM对ESWIN EBC7702的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L92)
	- 测试脚本：[03-ebc7702.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/03-ebc7702.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/3.ebc7702)
- SG2044 EVB：
	- 测试用例：[GCC和LLVM对SG2044的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L122)
	- 测试脚本：[04-sg2044.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/04-sg2044.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/4.Sg2044)
- A210 SODIMM V2：
	- 测试用例：[GCC和LLVM对A210 SODIMM V2的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L151)
	- 测试脚本：[05-a210-v2.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/05-a210-v2.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/5.a210-v2)
- VisionFive 2 Lite：
	- 测试用例：[GCC和LLVM对VisionFive 2 Lite的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L180)
	- 测试脚本：[06-vf2-lite.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/06-vf2-lite.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/6.VisionFive2Lite)
- Canaan K510 CRB-V1.2 KIT：
	- 测试用例：[GCC和LLVM对Canaan K510 CRB-V1.2 KIT的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L209)
	- 测试脚本：[07-k510.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/07-k510.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/7.K510)
- Milk-V Megrez：
	- 测试用例：[GCC和LLVM对Milk-V Megrez的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L248)
	- 测试脚本：[08-megrez.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/08-megrez.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/8.Megrez)
- RISC-V Book（如意笔记本甲辰版）：
	- 测试用例：[GCC和LLVM对RISC-V Book（如意笔记本甲辰版）的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L277)
	- 测试脚本：[09-rvbook.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/09-rvbook.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/9.ruyibook)
- RISC-V Book 2（如意二代笔记本）：
	- 测试用例：[GCC和LLVM对RISC-V Book 2（如意二代笔记本）的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L306)
	- 测试脚本：[10-rvbook2.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/10-rvbook2.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/10.rvbook2)
- SpacemiT K3 Pico-ITX：
	- 测试用例：[GCC和LLVM对SpacemiT K3 Pico-ITX的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L335)
	- 测试脚本：[11-k3.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/11-k3.sh)
- Milk-V Jupiter2 Dev Kit：
	- 测试用例：[GCC和LLVM对Milk-V Jupiter2 Dev Kit的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L385)
- K3 CoM260 Kit 16G：
	- 测试用例：[GCC和LLVM对K3 CoM260 Kit 16G的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L414)
- K3 Pico-ITX 32G：
	- 测试用例：[GCC和LLVM对K3 Pico-ITX 32G的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L443)
- [GCC和LLVM对EBC7700的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L34)
- VisionFive2Lite:
  - 视频录制：[https://asciinema.org/a/1260556](https://asciinema.org/a/1260556)
  - 测试截图：[board-compiler-test-cases_media/6.VisionFive2Lite](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/6.VisionFive2Lite)
- Canaan K510-CRB-V1.2 KIT:
  - 视频录制：[https://asciinema.org/a/1260823](https://asciinema.org/a/1260823)
  - 测试截图：[board-compiler-test-cases_media/7.K510](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/7.K510)
  - 脚本修正：[GCC and LLVM compiler test for Canaan K510 CRB-V1.2 KIT](https://github.com/DuoQilai/asciinema/blob/develop/examples/07-k510.sh)
- [Update the K510 script file](https://github.com/DuoQilai/asciinema/pull/1)
- [开发板调研](https://github.com/ZihanCheng63/my-repo/blob/main/ruyi/%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94.md)
- [Milk-V Jupiter2 Dev Kit 、K3 CoM260 Kit 16G、K3 Pico-ITX 32G 测试用例](https://github.com/DuoQilai/asciinema/pull/2)

### 4. SAIL和ACT

#### 4.1 SAIL和ACT开发

- [#1412](https://github.com/riscv/sail-riscv/pull/1412) : 支持sail-riscv模型的物理地址的有效位配置, 以支持ACT的测试需求
— [#1786](https://github.com/riscv/sail-riscv/pull/1786) : 修复sail-riscv模型实现的bug, spec 声明的合法情况由于控制流问题会造成 panic, 并编写first party test 测试有效性

#### 4.2 SAIL会议

- 参加 tech-golden-model meeting [`07.06`, `07.13`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 参加东亚双周会 0724，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1hzlhQkyYgxk4-9FeXY44fmC3HxrywoYgUPTB7JMCtLU/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

### 5. RISC-V Linux 嵌入式课程开发

- CourseOutline.html https://enzoding-rgb.github.io/ruyi-riscv-book/CourseOutline.html
- intro.md https://enzoding-rgb.github.io/ruyi-riscv-book/intro.md
- course-evaluation-standard.md https://enzoding-rgb.github.io/ruyi-riscv-book/course-evaluation-standard.md
- misc/boards/riscv-ai-boards-2025-2026.md https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/enzo/misc/boards/riscv-ai-boards-2025-2026.md
- chapters/ch03/lab.html https://enzoding-rgb.github.io/ruyi-riscv-book/chapters/ch03/lab.html
- commit https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/2a8e65f docs: ship ch01–ch06 lecture/lab pages and scaffolds
- commit https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/3c4694c docs: add course evaluation standard (CIPP+OBE fused)
- commit https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/a157f5e ch03: zero-to-assembly temp-fan lab + LPi4A gpiochip1 pin defaults
- [ruyi-riscv-linux-book](https://enzoding-rgb.github.io/ruyi-riscv-book/)
- [CourseOutline.html](https://enzoding-rgb.github.io/ruyi-riscv-book/CourseOutline.html)
- [intro.md](https://enzoding-rgb.github.io/ruyi-riscv-book/intro.md)
- [course-evaluation-standard.md](https://enzoding-rgb.github.io/ruyi-riscv-book/course-evaluation-standard.md)
- [misc/boards/riscv-ai-boards-2025-2026.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/enzo/misc/boards/riscv-ai-boards-2025-2026.md)
- [chapters/ch03/lab.html](https://enzoding-rgb.github.io/ruyi-riscv-book/chapters/ch03/lab.html)
- [docs: ship ch01–ch06 lecture/lab pages and scaffolds](https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/2a8e65f)
- [docs: add course evaluation standard (CIPP+OBE fused)](https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/3c4694c)
- [ch03: zero-to-assembly temp-fan lab + LPi4A gpiochip1 pin defaults](https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/a157f5e)

### 6. 2026年RISC-V 欧洲峰会

- 欧洲峰会宣传稿编写（审核中）

### 7. RVI CSC 中国客户调查

- 完成RVI CSC中国客户调查计划、相关材料（PPT、表格）的中文版翻译
- 辅助部分中国企业完成调查表

### 8. 职工

#### 8.1 蔡玮霖

- 更新 Ruyi 0.50.0 测试报告的 IDE 和 VSCode 部分
  - [!98 Update reports](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/98)
  - [!99 Update 0.50.0 IDE test status](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/99)
- 测试 Ruyi 0.51.0 测试版本提交测试报告
  - [!100 v0.51.0 report](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/100)
- ruyisdk-website 仓库审核 2 个 pr
  - [Add package-index-web to official site #545](https://github.com/ruyisdk/ruyisdk-website/pull/545)
  - [Optimize the layouts of homepage onboarding component. #549](https://github.com/ruyisdk/ruyisdk-website/pull/549)
- ruyisdk-website 仓库提交 26 个 pr
  - [pages(downloads): release new download page #540](https://github.com/ruyisdk/ruyisdk-website/pull/540)
  - [pages(issue): release issue page #541](https://github.com/ruyisdk/ruyisdk-website/pull/541)
  - [Improve layout for installation script #544](https://github.com/ruyisdk/ruyisdk-website/pull/544)
  - [pages(about): add ruyisdk survey qr code #550](https://github.com/ruyisdk/ruyisdk-website/pull/550)
  - [misc: add cloudflare web analytics beacon #553](https://github.com/ruyisdk/ruyisdk-website/pull/553)
- packages-index 仓库提交 1 个 pr
  - [device/zhihe-a210-sodimm: new device #208](https://github.com/ruyisdk/packages-index/pull/208)
- ruyi-backend 仓库提交 1 个 issue
  - [/releases/latest-pm 将 macOS 架构二进制显示为 linux/macos-arm64 #113](https://github.com/ruyisdk/ruyi-backend/issues/113)
- ruyisdk-test/ruyi-pytest 仓库提交  个 pr
  - [New test cases based on ruyi v0.50.0 #13](https://github.com/ruyisdk-test/ruyi-pytest/pull/13)
  - [ruyi: update dev dep ruyi version to v0.50.0 #14](https://github.com/ruyisdk-test/ruyi-pytest/pull/14)
  - [misc: revert for test failure caused by #9 #15](https://github.com/ruyisdk-test/ruyi-pytest/pull/15)
  - [tests: fix codebase mixture #16](https://github.com/ruyisdk-test/ruyi-pytest/pull/16)
  - [ruyi: update testcases for v0.51.0b20260714 #17](https://github.com/ruyisdk-test/ruyi-pytest/pull/17)
- ruyisdk-test/ruyi-pytest 仓库审核 4 个 pr
  - [tests: add pytest-html for visual test reports #9](https://github.com/ruyisdk-test/ruyi-pytest/pull/9)
  - [tests: add repo test cases #10](https://github.com/ruyisdk-test/ruyi-pytest/pull/10)
  - [tests: add update test cases #11](https://github.com/ruyisdk-test/ruyi-pytest/pull/11)
  - [tests: add telemetry test cases #12](https://github.com/ruyisdk-test/ruyi-pytest/pull/12)
- ruyi 本地管理 GUI [oh-my-ruyi](https://github.com/ruyisdk-test/oh-my-ruyi)
    + [57d801e...44efe7f](https://github.com/ruyisdk-test/oh-my-ruyi/compare/57d801ee9c63e389b7fe1c297a573c9febc62117...44efe7feb0ccf407412709fb757a21fbb64f4f97) 共计 71 commits，16099 行增加 2009 行删除

#### 8.2 阎明铸

##### 8.2.1 Sail

- 参加 tech-golden-model meeting [`07.06`, `07.13`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 参加东亚双周会 0724，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1hzlhQkyYgxk4-9FeXY44fmC3HxrywoYgUPTB7JMCtLU/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

##### 8.2.2 Ruyi AI

- buddy-compiler/buddy-mlir
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/852 [ci] Enable torch 212/213 tests on riscv
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/840 [ci] Use abi3 for release
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/831 [frontend] Add pytorch 2.13 support
- RuyiAI-Stack/triton-riscv
  - 提交 PR https://github.com/RuyiAI-Stack/triton-riscv/pull/36 [compiler] Use +xsmtime instead of +buddyext
- RuyiAI-Stack/llvm-project
  - 提交 PR https://github.com/RuyiAI-Stack/llvm-project/pull/19 [ci] Use pull_request instead of pull_request_target

#### 8.3 张馥媛

##### 8.3.1 RuyiSDK 示例代码库建设

- 审核或参与开发板示例文档扩充
	- VisionFive 2 Lite
		- [RuyiSDK 外设示例：基础按键检测](https://github.com/ruyisdk/board-docs/blob/add-documents-K510-VF2Lite/VisionFive2Lite/Button/README_zh.md)
	- Canaan K510-CRB-V1.2 KIT
		- [RuyiSDK 外设示例：通信测试](https://github.com/ruyisdk/board-docs/blob/add-documents-K510-VF2Lite/K510/UART/README.md)
	- Milk-V Jupiter2
		- 概述：[README.md](https://github.com/ruyisdk/board-docs/blob/main/Jupiter2/README.md)；[README_zh.md](https://github.com/ruyisdk/board-docs/blob/main/Jupiter2/README_zh.md)
		- [RuyiSDK 基础示例：HelloWorld](https://github.com/ruyisdk/board-docs/blob/main/Jupiter2/HelloWorld/README_zh.md)
		- [RuyiSDK 基础示例：Coremark](https://github.com/ruyisdk/board-docs/blob/main/Jupiter2/Coremark/README_zh.md)
- board-docs-frontend：
	- 在线站点：[board-docs-frontend](https://board-docs-frontend.pages.dev/)
	- Commit：[fix(ci): replace git submodule update --remote with explicit fetch/checkout](https://github.com/DuoQilai/board-docs-frontend/commit/3295c3f)
	- Commit：[docs: remove dev setup and manual trigger, keep essentials](https://github.com/DuoQilai/board-docs-frontend/commit/38a8fc9)
- 仓库维护：
	- 仓库配置：
		- [.gitignore](https://github.com/ruyisdk/board-docs/blob/main/.gitignore)
	- 贡献规范：
		- [CONTRIBUTING.md](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/CONTRIBUTING.md)
		- [CONTRIBUTING_zh.md](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/CONTRIBUTING_zh.md)
	- GitHub 模板：
		- [.github/ISSUE_TEMPLATE/content-bug.yml](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/.github/ISSUE_TEMPLATE/content-bug.yml)
		- [.github/ISSUE_TEMPLATE/content-new.yml](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/.github/ISSUE_TEMPLATE/content-new.yml)
		- [.github/ISSUE_TEMPLATE/content-outdated.yml](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/.github/ISSUE_TEMPLATE/content-outdated.yml)
		- [.github/PULL_REQUEST_TEMPLATE.md](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/.github/PULL_REQUEST_TEMPLATE.md)
	- 文档模板更新：
		- [templates/](https://github.com/ruyisdk/board-docs/blob/ospp-readiness/templates/%5Bboard-name%5D/%5Bexample-name%5D/README_zh.md)

##### 8.3.2 编译工具链测试

参与或审核
- Fork [trdthg/asciinema](https://github.com/trdthg/asciinema)，并在自己的 Fork 仓库 [DuoQilai/asciinema](https://github.com/DuoQilai/asciinema) 中，基于其中的 `asciinema expect` 功能编写 RISC-V 开发板 GCC/LLVM 工具链测试脚本，并录制测试过程。
- 测试用例文档：
	- [board-compiler-test-cases.md](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md)
	- [10种开发板+编译器测试用例.docx](https://github.com/DuoQilai/asciinema/blob/develop/202607/10%E7%A7%8D%E5%BC%80%E5%8F%91%E6%9D%BF%2B%E7%BC%96%E8%AF%91%E5%99%A8%E6%B5%8B%E8%AF%95%E7%94%A8%E4%BE%8B.docx)
- 测试流程和结果整理：
	- 测试说明：[202607/README.md](https://github.com/DuoQilai/asciinema/blob/develop/202607/README.md)
	- 测试用例：[board-compiler-test-cases.md](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md)
	- 测试脚本：[examples/](https://github.com/DuoQilai/asciinema/tree/develop/examples)
	- 测试截图和视频录制：[board-compiler-test-cases_media/](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media)
- ESWIN EBC7700：
	- 测试用例：[GCC和LLVM对EBC7700的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L34)
	- 测试脚本：[01-ebc7700.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/01-ebc7700.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/1.ebc7700)
- HiFive Premier P550：
	- 测试用例：[GCC和LLVM对SiFive HiFive Premier P550的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L63)
	- 测试脚本：[02-p550.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/02-p550.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/2.p550)
- ESWIN EBC7702：
	- 测试用例：[GCC和LLVM对ESWIN EBC7702的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L92)
	- 测试脚本：[03-ebc7702.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/03-ebc7702.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/3.ebc7702)
- SG2044 EVB：
	- 测试用例：[GCC和LLVM对SG2044的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L122)
	- 测试脚本：[04-sg2044.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/04-sg2044.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/4.Sg2044)
- A210 SODIMM V2：
	- 测试用例：[GCC和LLVM对A210 SODIMM V2的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L151)
	- 测试脚本：[05-a210-v2.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/05-a210-v2.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/5.a210-v2)
- VisionFive 2 Lite：
	- 测试用例：[GCC和LLVM对VisionFive 2 Lite的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L180)
	- 测试脚本：[06-vf2-lite.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/06-vf2-lite.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/6.VisionFive2Lite)
- Canaan K510 CRB-V1.2 KIT：
	- 测试用例：[GCC和LLVM对Canaan K510 CRB-V1.2 KIT的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L209)
	- 测试脚本：[07-k510.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/07-k510.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/7.K510)
- Milk-V Megrez：
	- 测试用例：[GCC和LLVM对Milk-V Megrez的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L248)
	- 测试脚本：[08-megrez.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/08-megrez.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/8.Megrez)
- RISC-V Book（如意笔记本甲辰版）：
	- 测试用例：[GCC和LLVM对RISC-V Book（如意笔记本甲辰版）的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L277)
	- 测试脚本：[09-rvbook.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/09-rvbook.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/9.ruyibook)
- RISC-V Book 2（如意二代笔记本）：
	- 测试用例：[GCC和LLVM对RISC-V Book 2（如意二代笔记本）的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L306)
	- 测试脚本：[10-rvbook2.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/10-rvbook2.sh)
	- 测试截图和视频录制：[测试素材](https://github.com/DuoQilai/asciinema/tree/develop/202607/board-compiler-test-cases_media/10.rvbook2)
- SpacemiT K3 Pico-ITX：
	- 测试用例：[GCC和LLVM对SpacemiT K3 Pico-ITX的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L335)
	- 测试脚本：[11-k3.sh](https://github.com/DuoQilai/asciinema/blob/develop/examples/11-k3.sh)
- Milk-V Jupiter2 Dev Kit：
	- 测试用例：[GCC和LLVM对Milk-V Jupiter2 Dev Kit的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L385)
- K3 CoM260 Kit 16G：
	- 测试用例：[GCC和LLVM对K3 CoM260 Kit 16G的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L414)
- K3 Pico-ITX 32G：
	- 测试用例：[GCC和LLVM对K3 Pico-ITX 32G的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L443)
- [GCC和LLVM对EBC7700的支持测试](https://github.com/DuoQilai/asciinema/blob/develop/202607/board-compiler-test-cases.md#L34)
- [SitongZhang](https://github.com/DuoQilai/ruyisdk-dev-archive/tree/main/reports/SitongZhang)

##### 8.3.3 RISC-V 开发板操作系统支持矩阵

- [ruyisdk/support-matrix#389](https://github.com/ruyisdk/support-matrix/pull/389)
  - Update Premier P550 Ubuntu 24.04.3 LTS report.
  - Add EBC7702 Ubuntu 24.04.4 LTS report.
  - Update LicheePi4A RevyOS test report to 20251226.

##### 8.3.4 RISC-V Linux系统与开发板实践课程

- 审核ruyi-riscv-linux-book
	- 在线预览：[ruyi-riscv-linux-book](https://enzoding-rgb.github.io/ruyi-riscv-book/)
	- [CourseOutline.html](https://enzoding-rgb.github.io/ruyi-riscv-book/CourseOutline.html)
	- [intro.md](https://enzoding-rgb.github.io/ruyi-riscv-book/intro.md)
	- [course-evaluation-standard.md](https://enzoding-rgb.github.io/ruyi-riscv-book/course-evaluation-standard.md)
	- [misc/boards/riscv-ai-boards-2025-2026.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/enzo/misc/boards/riscv-ai-boards-2025-2026.md)
	- [chapters/ch03/lab.html](https://enzoding-rgb.github.io/ruyi-riscv-book/chapters/ch03/lab.html)
	- [docs: ship ch01–ch06 lecture/lab pages and scaffolds](https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/2a8e65f)
	- [docs: add course evaluation standard (CIPP+OBE fused)](https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/3c4694c)
	- [ch03: zero-to-assembly temp-fan lab + LPi4A gpiochip1 pin defaults](https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/a157f5e)
