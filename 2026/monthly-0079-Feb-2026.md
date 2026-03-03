# RISC-V 软件生态进展 · 第 79 期·2026 年 2 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium
#### Update：
- 7508964: [riscv] Eliminate -Wexit-time-destructors warnings | https://chromium-review.googlesource.com/c/v8/v8/+/7508964
- 7502457: [riscv] Implement AssembleArchSelect | https://chromium-review.googlesource.com/c/v8/v8/+/7502457
- 7484947: [riscv] Fix  incorrect code gen | https://chromium-review.googlesource.com/c/v8/v8/+/7484947
- Fix random crashes  (by wangruikang@iscas.ac.cn)
7540554: [riscv] Fix sp handling in MacroAssembler::LeaveFrame | https://chromium-review.googlesource.com/c/v8/v8/+/7540554
- Add stack pointer validation for memory access in simulator
7543083: [riscv] Add check stack pointer when access memory |https://chromium-review.googlesource.com/c/v8/v8/+/7543083 
- Implement instruction selection for Select IR
7515447: [riscv] Implement word64/word32 Select for Tst/CmpZero operations | https://chromium-review.googlesource.com/c/v8/v8/+/7515447  
- Fix illegal instruction errors caused by unsupported SEW/LMUL configurations（Zhijin Zeng zhijin.zeng@spacemit.com）
7502635: [riscv] Fix illegal instruction caused by unsupported SEW and LMUL configuration | https://chromium-review.googlesource.com/c/v8/v8/+/7502635   
#### Upstream Port：
- 7495671: [riscv][sandbox] Migrate TrustedPointerTable to range-based type checks | https://chromium-review.googlesource.com/c/v8/v8/7495671 
- 7489051: [riscv][acqrel] Added atomic acquire load and release store instructions | https://chromium-review.googlesource.com/c/v8/v8/7489051 
- 7417239: [riscv][wasmfx] Fix cmp width in WasmFXResumeThrow | https://chromium-review.googlesource.com/c/v8/v8/+/7417239 
- 7543084: [riscv][baseline] Inline fast ToBoolean checks for Smis and static roots | https://chromium-review.googlesource.com/c/v8/v8/7543084 
- 7540545: [riscv][ic] Introduce CallNamedInterceptorSetter builtin | https://chromium-review.googlesource.com/c/v8/v8/+/7540545 
- 7538513: [riscv][wasmfx] Implement cont.bind. | https://chromium-review.googlesource.com/c/v8/v8/+/7538513 
- 7529664: [riscv][cleanup] Use EnumSet<CpuFeature> in multiple places | https://chromium-review.googlesource.com/c/v8/v8/+/7529664
- 7608971: [riscv][jspi] Clear EPT entry on stack return | https://chromium-review.googlesource.com/c/v8/v8/+/7608971
- 7599842: [riscv][maglev] Handle equal inputs in Float64Max/Min | https://chromium-review.googlesource.com/c/v8/v8/+/7599842
- 7599840: [riscv][wasm] Improve write-barrier treatment | https://chromium-review.googlesource.com/c/v8/v8/+/7599840
- 7566742: [riscv]Add WasmCodePointer bounds masking | https://chromium-review.googlesource.com/c/v8/v8/+/7566742

## Spidermonkey / Firefox

## OpenJDK

## Go

## GNU Toolchain

## LLVM Team

## RuyiAI 系统软件栈

### Ruyi Buddy Compiler

- [examples] Add Qwen3-0.6B E2E Inference.
- [Example] Enable gqa attention for Qwen3-0.6B
- [Frontend] Enhance parent tracking for nested container arguments and add flexible shape handling in reshape_op
- [examples] Add features to support Gemmini examples E2E deployments on FPGA.
- [frontend] Add MLIR result checking and JIT encapsulation.
- [Frontend] restore operator index input to previous implementation due to performance regression.
- [Frontend] Add quantisation pass.
- [Frontend] correct parameter data packing order in eliminate_weight_transpose.
- [examples] Fix DeepSeek fp16 pipeline.
- [frontend] Restore index_put broadcast semantics without redundant alloc/copy.
- [examples] Add yolo26n e2e model support.

### triton-riscv

- 知乎文章：让 Triton 跑在 RISC-V 平台上 - [Link](https://zhuanlan.zhihu.com/p/2010281222484554437)
- [backend] Remove Nvidia and AMD requirement.
- [setup] Avoid Nvidia and AMD environment download.
- [cmake] Add riscv64 CodeGen and AsmParser configuration.
- [proton] Set TRITON_BUILD_PROTON=OFF
- [compiler] Add -mattr configuration for RISC-V.
- [compiler] Add platform package.
- [driver] Append libgcc_s to provide soft-float runtime helpers.
- [examples] Resolve pytest warnings.

## opensbi

## 罗云翔测试团队
（包含 SAIL 和 ACT 测试部分）

RuyiSDK 0.46.0完成在多发行版、多架构下的测试及IDE插件评测，持续开发自动化测试工具和测试用例，网站与文档不断优化。测试团队正常推进RuyiAI项目2026年Q1的工作任务，本月提交5个PR。在SAIL方向提交10余个PR并参与多个PR的评审，完成多次技术分享。此外，完成了对多款RISC-V开发板的编译工具链测试，夯实了2026年底项目验收基础。

1. RuyiSDK

1.1 RuyiSDK `0.46.0-beta.20260206` 测试
- 测试覆盖了8种主流Linux发行版（Debian, Ubuntu, openEuler, Fedora, Deepin, openKylin, OpenCloudOS, Archlinux）的20多个版本。
- 在x86_64、aarch64、riscv64三种CPU架构上进行了全面验证。
- 对RuyiSDK Eclipse插件（v0.1.2）和VSCode插件（v0.1.2-beta.1）进行了系统性手动测试，并建立RuyiSDK IDE测试用例库。
- 发现并推动修复了包管理器严重缺陷（`rich`模块缺失），确保版本质量；VSCode插件新增测试点（新闻状态、插件引导等）并反馈中文解析等问题。

1.2 RuyiSDK测试工具开发
- 为`ruyi-litester`测试框架贡献代码，新增`ruyi-list`和`ruyi-venv`命令的测试用例，并修复匹配逻辑。
- 在`ruyi-packaging`仓库中实现自动化PR创建机制、定时任务调度、数据库记录和Web查询接口，显著提升包管理的自动化水平和运维效率。
- 完成Telegram Bot集成，实现上游更新目录的定时推送；重构系统配置和三层架构体系，提升代码可维护性。

1.3 RuyiSDK示例代码与开发指南建设
- 创建并维护`riscv-board-custom-dev`项目，为Milk-V Duo/Duo S、LicheePi 4A等多款RISC-V开发板编写从入门到应用开发的系列指南（Hello World、Coremark、外设应用如ADC、DHT22、SSD1306等）。
- 在LicheePi 4A上实践了Allegro迁移测试、LED闪烁、OpenCV构建、Qwen2.5模型部署、Luanti/Chocolate-Doom等游戏编译，并制作配套视频和文档。
- 完成teeworlds、2048、Snake-Game、OpenTTD、Yolo_Label等项目的RuyiSDK构建及在openEuler QEMU环境下的运行验证。

1.4 RuyiSDK网站与文档
- 在`ruyisdk-website`仓库提交多个PR，涉及统计页面优化、从UnoCSS迁移至Tailwind CSS、移除Ant Design依赖等，提升网站性能和可维护性。
- 修复文档链接、更新微信文章测试状态，确保信息一致性。

2. RuyiAI
- 提交5个PR至`buddy-mlir`仓库，包括Python包构建脚本、GitHub CI支持、前端性能分析指令注入等。

3. SAIL/ACT

3.1 `sail-riscv`代码贡献
- 提交10余个PR，主要内容包括：
  - 新增扩展支持：`Zilsd/Zclsd`、向量浮点指令集、`Zicclsm`、`Zibi`等。
  - 增强配置与合规性：添加多种配置选项（如Mtvec、保留行为处理），使模型行为更符合标准。
  - 提升模型精度与调试能力：细化CSR访问结果、修复模拟器CLI输出、处理取址对齐异常等。
- 审核多个PR（如Hypervisor扩展、Zvabd扩展），确保代码质量。

3.2 活跃的社区参与与知识分享
- 定期参加RISC-V技术黄金模型会议和东亚区双周会，同步项目进展。
- 技术分享：包括Zibi扩展原理、Sail语言存在类型修复等。

4. RISC-V 操作系统与工具链测试
- 工具链测试覆盖RevyOS、Buildroot、Debian、Fedora、bianbu等多种操作系统，在BPI-F3、Milk-V Jupiter、MUSE Book/Box/Pi Pro、Milk-V Mars、Unmatched、香山笔记本等近10款主流RISC-V开发板上完成测试并输出报告。
- 持续维护RISC-V操作系统支持矩阵，完成前端部署并上线`matrix.ruyisdk.org`，为生态治理提供数据支撑。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.46.0-beta.20260206 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260207/README.md)
    - [Debian12 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Debian12 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260207/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu22.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260207/RUYI_包管理_Ubuntu22.04_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260207/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu24.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Ubuntu24.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora42 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Fedora42_aarch64_测试结果.md)
    - [Fedora43 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Fedora43_x86_64_测试结果.md)  
    - [Fedora43 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Fedora43_aarch64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Deepin25 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Deepin25_x86_64_测试结果.md)
    - [Deepin25 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Deepin25_riscv64_测试结果.md)
    - [Deepin25 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Deepin25_aarch64_测试结果.md)
    - [openKylin2.0 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openKylin_x86_64_测试结果.md)
    - [openKylin2.0 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openKylin_riscv64_测试结果.md)
    - [openKylin2.0 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_openKylin_aarch64_测试结果.md)
    - [OpenCloudOS 9.4 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)
    - [OpenCloudOS 9.4 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_OpenCloudOS_aarch64_测试结果.md)
    - [Archlinux x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260207/RUYI_包管理_Archlinux_x86_64_测试结果.md)

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
        本版本测试基于 ruyisdk-eclipse-plugins [v0.1.2](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/releases/tag/v0.1.2) 开展手动测试。

        测试报告见 [针对 RuyiSDK Eclipse 插件的测试](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/blob/v0.1.2/README.md)

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
        本版本无同步发布的新版本。

        遗留缺陷：

        | 缺陷 | 问题等级 | 备注 |
        | ----- | ----- | ----- |
        | [新闻UI界面已读状态未更新 #108](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/108) | 一般 | 已有 issue 回复 |
        | [查看未读新闻命令失效 #106](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/106) | 一般 | 与 #108 为同一缺陷 |

      - Ruyi 包管理器测试
        遗留缺陷：

        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415) | 一般 | 已有 issue 回复 |

        基于 v0.46.0-beta.20260203 版本的测试发现无法简单修复的缺陷，修复后重发新版本 v0.46.0-beta.20260206 后重新执行测试，缺陷已修复：

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [Many commands failed: ModuleNotFoundError: No module named 'rich._unicode_data.unicode17-0-0' #428](https://github.com/ruyisdk/ruyi/issues/428)   | 严重 |   |
      - 本版本包含遗留的严重缺陷，均按照修复时间表修复中；
    
    - 测试结论
      本版本新增严重缺陷，需要修复；
      RuyiSDK v0.46.0-beta.20260203 版本需要修 1 个严重缺陷并重新发测试版。

    - 修复情况
    	重发新版本 v0.46.0-beta.20260206 后重新执行测试，缺陷已修复：

      | 缺陷      | 问题等级 | 备注 |
      | ----------- | ----------- | --- |
      | [Many commands failed: ModuleNotFoundError: No module named 'rich._unicode_data.unicode17-0-0' #428](https://github.com/ruyisdk/ruyi/issues/428)   | 修复 |   |

    - 资源
      - [本版本 litester 测试程序](https://github.com/ruyisdk-test/ruyi-litester/tree/0f6c010632aadc177afe98e100ebd833e601a8d0)

- [Many commands failed: ModuleNotFoundError: No module named 'rich.\_unicode\_data.unicode17-0-0' #428](https://github.com/ruyisdk/ruyi/issues/428)
- [ruyi admin format-manifest automatically remove distfiles[].strip_components < 2 #430](https://github.com/ruyisdk/ruyi/issues/430)

- [ruyisdk-vscode-extension（v0.1.2-beta.1）测试](https://github.com/qingwan12138/ruyisdk-vscode-extension-test)
  - 补充新闻读取状态、插件引导、虚拟环境图形化引导以及旧版本ruyi包管理器添加提示的测试结果
  - [Pull Request #7](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/7)
      - 补充新闻读取状态、插件引导、虚拟环境图形化引导以及旧版本ruyi包管理器添加提示的测试结果
      - 替换过期测试截图，保证报告准确性
  - Issues
    - [Issue #115](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/115)
      - 旧版本ruyi提示更新冲突
    - [Issue #122](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/122)
      - 反馈 Profiles 列表解析中文
    
- [ruyisdk-eclipse-plugins-test](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/5)
  - [ruyisdk-eclipse-plugins（v0.1.2）测试用例报告](https://github.com/jxy687/ruyisdk-eclipse-plugins-test/tree/v0.1.2)
  - [ci: update dependent actions](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/commit/6b9d4a21833e5d7cd3eb1f1bd6c54513abc99c32)
  - [ruyisdk-test/ruyisdk-eclipse-plugins-test#6](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/6)
    - 更新测试文档，关联对应缺陷报告
    - 替换过期测试截图，保证报告准确性
  - [ruyisdk/ruyisdk-eclipse-plugins/issues#107](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/107)
  - Issues
    - [ruyisdk/ruyisdk-eclipse-plugins#109](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/109)
  
#### 1.2 RuyiSDK 开发和测试工具开发

- ruyi-packaging ruyisdk 包管理器创建二进制安装文件
  - [实现了系统的配置系统的重构](https://github.com/ruyisdk/ruyi-packaging/commit/b43ce1c9cb6d9b38a29b3dac26e12331dc98f189)
    - 修复数据库初始化问题，实现表自动创建机制
    - 完善配置模板文件，补充所有缺失的配置项和环境变量
    - 保持向后兼容性，支持旧配置文件格式

  -[建立 core/services/interfaces 三层架构体系](https://github.com/ruyisdk/ruyi-packaging/commit/40c829998b12688dde880e242fc9d211251d83a3)
    - 架构分层：建立核心层、服务层、接口层三层架构，从rikoriko.py、api.py 提取业务模型到 core/，将接口层 (CLI/API)与业务逻辑解耦 
    - 服务层抽取：将 CLI 命令的业务逻辑抽取为 4 个独立服务类（CheckService、ManifestService、PRService、SchedulerService），CLI 和 API共享服务层方法，避免代码重复
    - 接口层重构：CLI 移至 interfaces/cli/ 仅保留参数解析；API 拆分为 4 个路由模块，提取 Pydantic 模型到独立文件，统一使用相对导入规范化依赖关系

  - [实现TelegramBot定时发送上游更新目录](https://github.com/ruyisdk/ruyi-packaging/commit/b42e36d244dc4a34f1bbe93f0975a31e76827c7a)
    - Telegram Bot 服务新增：创建 telegramBot_service.py 实现完整的 Bot 服务层，支持消息发送
    - CLI 命令扩展：在 riko 主程序中新增 telegram-bot 子命令，将Telegram Bot 启动功能集成到 CLI 工具链，用户可通过 python3 -m riko telegram-bot 直接启动机器人

  -[实现自动对比上游版型与Ruyi-packaging仓库版型对比并更新](https://github.com/ruyisdk/ruyi-packaging/commit/34ff64365461e0d8cb7bbf14fe395f640225985c)
    - 完成对上游版型号的整体对比，筛选出新增与删除的型号文件。通过调用manifests的版型下载和pr功能中的生成pr来协助完成version_sync功能的实现

  - [修改manifests中获取size与哈希值逻辑](https://github.com/ruyisdk/ruyi-packaging/commit/72c4815e2c92d199f7c1b7cd27b40caa0eb33082)
    - 修改了manifests_r9函数的功能，在下载完成之后计算size与哈希值之后立即删除该文件，防止过多占用磁盘空间，而导致功能无法正常实施

  - [将version-sync进行CLi命令扩展以及api扩展](https://github.com/ruyisdk/ruyi-packaging/commit/6d84a25de355f712f2c34c578311af8cef9d633a)
    - CLI 命令扩展：在 riko 主程序中新增 versions-sync 子命令，将 versions-sync 启动功能集成到 CLI 工具链，用户可通过 python3 -m riko  versions-sync 直接调用该功能
    - 创建 versions-sync 接口，在服务端可以直接调用接口来使用该功能

- [ruyisdk provision命令可视化GUI demo设计实现](https://gitee.com/huizhang_chen/ruyi_provision_gui)
  - 调研ruyisdk provision命令跨平台系统镜像sd卡烧录方案设计

- ruyisdk-eclipse-plugins
  - 修复了[#82](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/82#issuecomment-3837909308)中第一个问题：安装ruyi时按钮未被disable
  
- packages-index 仓库
  - [board-image/buildroot-sdk-sipeed-licheervnano: fix version 20260114 #166](https://github.com/ruyisdk/packages-index/pull/166)
  - [board-image/buildroot-sdk-sipeed-licheervnano: bump to 20260114 #164](https://github.com/ruyisdk/packages-index/pull/164)
  - [board-image/openwrt-sifive-unmatched: bump to latest version 2410.5 #165](https://github.com/ruyisdk/packages-index/pull/165)

- [自动化 PR 提交和 Telegram bot 实现](https://github.com/ruyisdk-test/riko-bot/compare/fd91054f09d7a720ff05bdc60402f6e35b3b7884...96f8ead93c3cb46082cc47eaff6756e3841a2a66)

#### 1.3 RuyiSDK Sample Codes 开发和文档编写

- Licheepi4A 示例库扩充
	-  [Ruyi SDK GLES/SDL 中 Allegro 迁移测试及核心问题总结（基于Licheepi4A)](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Allegro/Ruyi_Allegro_test.md)
	-  [LicheePi4A LED 闪烁功能测试文档](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/LED_flashing/Ruyi_LED_flashing.md)
		- [LED flashing Example视频](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/LED_flashing/images/LED_Example.rar)
- Duo256 示例库扩充
	- [使用RuyiSDK 编译 Milk-V Duo256m 示例程序教程（以2048为例）](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/2026/m02_w01.md)

- DuoS 示例库扩充
	- [使用 RuyiSDK 构建 Pico-8SEG-LED 驱动程序（以 Milk-V Duo S 为例）](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_Pico_8SEG_RuyiSDK.md)
	- [使用 RuyiSDK 构建 Pico-ePaper-2.13 驱动程序（以 Milk-V Duo S 为例）](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_Pico_ePaper_RuyiSDK.md)
	- WiringX示例的RuyiSDK版本：
		- [使用 RuyiSDK 编译 Milk-V DuoS 示例程序教程](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_RuyiSDK_DuoS.md)
		- [ADC 读取：采集模拟信号](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_ADC_DuoS.md)
		- [传感器：读取 DHT22 温湿度数据](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_DHT22_DuoS.md)
		- [通信：驱动 SSD1306 OLED 屏幕](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_I2C_SSD1306_DuoS.md)
		- [PWM 控制：呼吸灯效果](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_PWM_DuoS.md)
		- [SPI 通信：读取 MAX6675 温度](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_SPI_MAX6675_DuoS.md)
	
- [Ruyi SDK GLES/SDL 中 Allegro 迁移测试及核心问题总结（基于Licheepi4A)](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Allegro/Ruyi_Allegro_test.md)

—LED flashing:
  - [LicheePi4A LED 闪烁功能文档](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/LED_flashing/Ruyi_LED_flashing.md)
  - [LED flashing Example 运行视频](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/LED_flashing/images/LED_Example.rar)

- [teeworlds构建文档](https://github.com/qingwan12138/PLCT-WORK/blob/main/February/blog/ruyisdk%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91teeworlds.md)
  - 使用 RuyiSDK 创建虚拟环境并构建项目，成功运行

- 在 openEuler的qemu模拟器下构建项目
  - [teeworlds构建文档](https://github.com/qingwan12138/PLCT-WORK/blob/main/February/blog/teeworlds.md)
    - 详细说明了如何在运行RISC-V架构 OpenEuler 系统的 qemu 虚拟机上从源代码编译和运行 teeworlds 开源游戏
  - [TranslateGemma-4b-it.Q4_K_M构建文档](https://github.com/qingwan12138/PLCT-WORK/blob/main/February/blog/translategemma-4b-it.Q4_K_M.md)
    - 详细说明了如何在运行RISC-V架构 OpenEuler 系统的 qemu 虚拟机上从源代码构建 TranslateGemma-4b-it.Q4_K_M
  - [Chocolate-Doom构建文档](https://github.com/qingwan12138/PLCT-WORK/blob/main/February/blog/Chocolate-Doom%E5%BC%80%E6%BA%90%E6%B8%B8%E6%88%8F.md)
    - 详细说明了如何在运行RISC-V架构 OpenEuler 系统的 qemu 虚拟机上从源代码编译和运行 Chocolate-Doom 开源游戏

- 使用qemu的OpenEuler构建项目
	- OpenTTD:[构建文档](https://github.com/YXCZS/plct_working/blob/main/blog/OpenTTD.md)
	- Yolo_Label:[构建文档](https://github.com/YXCZS/plct_working/blob/main/blog/Yolo_Label.md)
	- supertux:[构建文档](https://github.com/YXCZS/plct_working/blob/main/blog/supertux.md)

- [2048构建文档](https://github.com/jxy687/Docs/tree/main/2048)
  - 使用 RuyiSDK 创建虚拟环境并构建项目，成功运行
  - 项目源代码 [2048.c](https://github.com/mevdschee/2048.c)

- [Snake-Game构建文档](https://github.com/jxy687/Docs/tree/main/Snake)
  - 使用 RuyiSDK 创建虚拟环境，并向 sysroot 添加 SDL 依赖，成功构建项目
  - 项目源代码 [CppND-Capstone-Snake-Game](https://github.com/udacity/CppND-Capstone-Snake-Game)

- 使用 qemu 里面的 openEuler 构建项目
  - [2048构建文档](https://github.com/jxy687/Net-word/blob/main/Games/2048.md)
    - 使用 openEuler，成功运行
    - 项目源代码 [2048.c](https://github.com/mevdschee/2048.c)

  - [Snake-Game构建文档](https://github.com/jxy687/Net-word/blob/main/Games/snake.md)
    - 使用 openEuler，成功运行
    - 项目源代码 [CppND-Capstone-Snake-Game](https://github.com/udacity/CppND-Capstone-Snake-Game)

#### 1.4 RuyiSDK网站

- [ci: fix audo submodule update #347](https://github.com/ruyisdk/ruyisdk-website/pull/347)
- [ci: submodule update action will create PR #351](https://github.com/ruyisdk/ruyisdk-website/pull/351)
- [ci: add automat label for ci audo PR #352](https://github.com/ruyisdk/ruyisdk-website/pull/352)
- [ci: check trigger for auto PRs #355](https://github.com/ruyisdk/ruyisdk-website/pull/355)
- [ci: check pnpm build after auto submodule update PR #357](https://github.com/ruyisdk/ruyisdk-website/pull/357)
- [ci: add action run url in auto PRs body #359](https://github.com/ruyisdk/ruyisdk-website/pull/359)
- [ci: deploy gh page on gh-pages branch #360](https://github.com/ruyisdk/ruyisdk-website/pull/360)
- [ci: audo update api data #362](https://github.com/ruyisdk/ruyisdk-website/pull/362)
- [pages: release /news page #366](https://github.com/ruyisdk/ruyisdk-website/pull/366)
- [pages(dashboard): remove github status p #367](https://github.com/ruyisdk/ruyisdk-website/pull/367)
- [docs: update README to pnpm version #374](https://github.com/ruyisdk/ruyisdk-website/pull/374)
- [ci: retry on 202 for stats/contributors #375](https://github.com/ruyisdk/ruyisdk-website/pull/375)
- [ci: fix runtime error #376](https://github.com/ruyisdk/ruyisdk-website/pull/376)
- [ci: fix runtime error #377](https://github.com/ruyisdk/ruyisdk-website/pull/377)

- [Pull #348](https://github.com/ruyisdk/ruyisdk-website/pull/348)
  - Revert the stats/dashboard page to the previous design while keeping updated functionality.
  - Replace CSS-module based styles with Tailwind utility classes and minimal custom CSS for charts and orbit layout.
  - Adjust statistics, charts, and mobile install sections to use simpler card layouts with updated typography and spacing.
  - Extract complex FlipCounter styles into a standalone CSS file and update its usage.
  - Integrate a reusable PageBackground component and simplify the page container styling.
  - Status: merged (merged_at: 2026-02-02).

- [Pull #354](https://github.com/ruyisdk/ruyisdk-website/pull/354)
  - Migrate the site styling pipeline from UnoCSS to Tailwind CSS.
  - Add Tailwind configuration, PostCSS setup (autoprefixer), and Tailwind entry CSS; remove UnoCSS plugin and related files.
  - Introduce new shared visual pieces (e.g., AnimatedBlobs background component) and tune homepage/card typography and button styles.
  - Update Docusaurus configuration to load Tailwind styles.
  - Status: open (work-in-progress; active Tailwind migration and style tuning).

- [Pull #371](https://github.com/ruyisdk/ruyisdk-website/pull/371)
  - Remove remaining Ant Design (antd) components and @ant-design/icons usages across the UI.
  - Replace antd layout/components (Tabs, Card, Tag, Button, modal close icon, Progress, etc.) with lightweight custom HTML/CSS equivalents and lucide-react icons.
  - Implement a custom progress bar for category statistics and update FlipCounter/empty states to use lucide-react icons.
  - Remove antd and @ant-design/icons from package.json and clean up unused imports (dashboard, QRCode, etc.).
  - Adjust responsive styles for stats and charts to match new grid-based layouts and custom cards/buttons.
  - Status: open (major UI/dependency removal in progress).

- [Update RuyiSDK Website section #1274](https://github.com/plctlab/PLCT-Weekly/pull/1274)

#### 1.5 RuyiSDK 视频教程

- [【LicheePi 4A 下使用 RuyiSDK 编译 TryQuake 3D游戏～】 ](https://www.bilibili.com/video/BV1k5F6zNEUy/)
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/TyrQuake.md)
  
#### 1.6 RuyiSDK实习生招募

RuyiSDK 测试开发实习生：

- [P119\_cyu.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month31/P119_cyu.md)
- [P119\_luz.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month31/P119_luz.md)

RuyiSDK Sample Codes和开发视频：

- [实习生技术报告面试题目](https://github.com/DuoQilai/PLCT-Works/blob/main/RISC-V_short_video/Intern_Report_Title.md)

#### 1.7 RuyiSDK双周报

- RuyiSDK双周报2份

#### 1.8 RISC-V 欧洲峰会

- [扩展摘要 From Fragmentation to Systematization A Standardized Quality Selection and Systematic Reconstruction Approach for RISC-V Courses](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/From%20Fragmentation%20to%20Systematization%20A%20Standardized%20Quality%20Selection%20and%20Systematic%20Reconstruction%20Approach%20for%20RISC-V%20Courses.pdf)

- [RuyiSDK Package Manager - A Unified Package Management and Development Environment for RISC-V](https://cfp.riscv-europe.org/eu-summit-2026/talk/review/GXE9CB8EZPTVJTKQKNZDHH3VUMKLTBM9)

### 2. RuyiAI

#### 2.1 RuyiAI 开发

- 更新 PR <https://github.com/buddy-compiler/buddy-mlir/pull/681> \[package\] Add package scripts and github ci support

#### 2.2 RuyiAI 会议和技术分析

- 技术分享，onnx 格式介绍 [PPT](https://github.com/trdthg/plct/blob/main/doc/ai/onnx/onnx.pdf)
- 参加 RuyiAI 会议和完成任务分配

### 3. RISC-V 编译工具链测试

- [bianbu (v3) BPI-F3工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/BPI-F3/Report_bianbu_v3_BPI_F3.md)
- [bianbu (v3) Milk-V Jupiter 工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Jupiter/Report_bianbu_v3_Milk-V_Jupiter.md)
- [bianbu (v3) MUSE Book 工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/MUSE_Book/Report_bianbu_v3_MUSE_Book.md)
- [bianbu (v3) MUSE Box 工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/MUSE_Box/Report_bianbu_v3_MUSE_Box.md)
- [bianbu (v3) MUSE Pi Pro 工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Muse_Pi_Pro/Report_bianbu_v3_MUSE_Pi_Pro.md)
- [Ubuntu Milk-V Mras 工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Mars/Report_Milk-V%20Mars.md)
- [Ubuntu Unmatched 工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Unmatched/Re_port_Unmatched.md)
- [Debian 香山笔记本（Xiangshan Nanhu） 工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/%E9%A6%99%E5%B1%B1%E7%AC%94%E8%AE%B0%E6%9C%AC%EF%BC%88Xiangshan%20Nanhu%EF%BC%89/Re_port_%E9%A6%99%E5%B1%B1%E7%AC%94%E8%AE%B0%E6%9C%AC%EF%BC%88Xiangshan%20Nanhu%EF%BC%89.md)
- [Milk-V Mars 工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Mars/Report_Milk-V%20Mars.md)
- [HiFive Unmatched 工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Unmatched/Re_port_Unmatched.md)
- [香山笔记本（Xiangshan Nanhu）工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/%E9%A6%99%E5%B1%B1%E7%AC%94%E8%AE%B0%E6%9C%AC%EF%BC%88Xiangshan%20Nanhu%EF%BC%89/Re_port_%E9%A6%99%E5%B1%B1%E7%AC%94%E8%AE%B0%E6%9C%AC%EF%BC%88Xiangshan%20Nanhu%EF%BC%89.md)

### 4. RISC-V 操作系统支持矩阵

- 交接前端部署，已成功展示  matrix.ruyisdk.org

- 新实习生知识储备

  - [RISC-V 操作系统支持矩阵（Knowledge Matrix）](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/%E4%B8%80%E3%80%81%E7%9F%A5%E8%AF%86%E7%9F%A9%E9%98%B5%EF%BC%88Knowledge%20Matrix%EF%BC%89%E7%9A%84%E4%BB%8B%E7%BB%8D.md)

  - [RISC-V 知识矩阵管理框架：构建生态治理新范式](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/RISC-V%20%E7%9F%A5%E8%AF%86%E7%9F%A9%E9%98%B5%E7%AE%A1%E7%90%86%E6%A1%86%E6%9E%B6%EF%BC%9A%E6%9E%84%E5%BB%BA%E7%94%9F%E6%80%81%E6%B2%BB%E7%90%86%E6%96%B0%E8%8C%83%E5%BC%8F.md)

  - 操作系统
    - [Debian 操作系统调研报告](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/Debian_Operating%20System%20Research%20Report.md)
    - [Zephyr 操作系统调研报告](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/Zephyr_Operating%20System%20Research%20Report.md)
    - [FreeRTOS 操作系统调研报告](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/FreeRTOS_Operating%20System%20Research%20Report.md)
    - [xv6 操作系统调研报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/xv6%20%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
    - [RT-Thread操作系统调研报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/RT-Thread%20%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
    - [主流操作系统维调研报告](https://github.com/feifei-xx/plct-works/blob/main/%E5%90%84%E7%A7%8D/%E8%B0%83%E7%A0%94/%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%A0%94.md)

  - 开发板
      - RISC-V开发板对照社区调研
        - [Lichee Pi 4A, Milk-V Mars, Milk-V Duo, 香橙派 (Orange Pi) 系列开发板调研报告](https://github.com/feifei-xx/plct-works/blob/main/%E5%90%84%E7%A7%8D/%E8%B0%83%E7%A0%94/%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94.md)
      - 其它架构开发板对照社区调研
        - [ESP32 系列开发板调研报告（以ESP32 DevKitC为例）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/ESP32%20%E7%B3%BB%E5%88%97%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A%EF%BC%88%E4%BB%A5ESP32%20DevKitC%E4%B8%BA%E4%BE%8B%EF%BC%89.md)
        - [NVIDIA Jetson系列开发板调研报告（以NVIDIA Jetson Nano为例）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/NVIDIA%20Jetson%E7%B3%BB%E5%88%97%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A%EF%BC%88%E4%BB%A5NVIDIA%20Jetson%20Nano%E4%B8%BA%E4%BE%8B%EF%BC%89.md)
        - [Arduino系列开发板调研报告（以Arduino Uno为例）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/Arduino%E7%B3%BB%E5%88%97%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A%EF%BC%88%E4%BB%A5Arduino%20Uno%E4%B8%BA%E4%BE%8B%EF%BC%89.md)
        - [M5Stack系列发板调研报告（以M5Stack Core2为例）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/M5Stack%E7%B3%BB%E5%88%97%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A%EF%BC%88%E4%BB%A5M5Stack%20Core2%E4%B8%BA%E4%BE%8B%EF%BC%89.md)
        - [Orange Pi 5（香橙派5）开发板调研报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/Orange%20Pi%205%EF%BC%88%E9%A6%99%E6%A9%99%E6%B4%BE5%EF%BC%89%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
        - [Raspberry Pi 5（树莓派5）开发板调研报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/Raspberry%20Pi%205%EF%BC%88%E6%A0%91%E8%8E%93%E6%B4%BE5%EF%BC%89%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
      
### 5. SAIL和ACT

#### 5.1 SAIL和ACT开发

- SAIL
  - 提交 PR <https://github.com/riscv/sail-riscv/pull/1534> Support custom configs for first-party tests
  - 更新 PR <https://github.com/riscv/sail-riscv/pull/765> Add Zilsd/Zclsd Support
  - 提交 PR https://github.com/riscv/sail-riscv/pull/1581

    *注：本扩展涉及指令较多，以下为具体指令：*

    | 指令类别 | 涉及指令 |
    |----------|----------|
    | 向量浮点基本算术类 | vfadd.vv, vfadd.vf, vfsub.vv, vfsub.vf, vfrsub.vf, vfmul.vv, vfmul.vf, vfdiv.vv, vfdiv.vf, vfsqrt.v |
    | 向量 FMA（乘加融合）类 | vfmacc.vv, vfmacc.vf, vfnmacc.vv, vfnmacc.vf, vfmsac.vv, vfmsac.vf, vfnmsac.vv, vfnmsac.vf, vfmadd.vv, vfmadd.vf, vfnmadd.vv, vfnmadd.vf, vfmsub.vv, vfmsub.vf, vfnmsub.vv, vfnmsub.vf |
    | 浮点最值与符号处理类 | vfmin.vv, vfmax.vv, vfsgnj.vv, vfsgnjn.vv, vfsgnjx.vv |
    | 浮点比较类 | vmfeq.vv, vmfne.vv, vmflt.vv, vmfle.vv, vmfgt.vf, vmfge.vf |
    | 浮点转换与扩展类 | vfwcvt.f.f.v, vfncvt.f.f.w, vfncvt.rod.f.f.w, vfcvt.f.x.v, vfcvt.f.xu.v, vfcvt.x.f.v, vfcvt.xu.f.v |
  - Merged PR https://github.com/riscv/sail-riscv/pull/1478
  - 修改sail-riscv 模拟器 cli 逻辑,修复模拟器无参数输入时输出打印信息不全问题,产出链接: [https://github.com/riscv/sail-riscv/pull/1576](https://github.com/riscv/sail-riscv/pull/1576)
  - 修改sail-riscv 寄存器字段行为,如果Zca 扩展开启的情况下取址对齐异常应无法触发,根据WARL原则应为只读0. 产出链接: [https://github.com/riscv/sail-riscv/pull/1550](https://github.com/riscv/sail-riscv/pull/1550)
  - 向sail-riscv 提交PR, 鉴于memory.misalign字段具有一定迷惑性,需要进行澄清修改.产出链接:[https://github.com/riscv/sail-riscv/pull/1548](https://github.com/riscv/sail-riscv/pull/1548)
  - 向sail 提交PR, 修复BUG, 针对mapping 映射时无法处理对应函数执行的问题进行修复,并提供测试用例.产出链接:[https://github.com/rems-project/sail/pull/1622](https://github.com/rems-project/sail/pull/1622)
  - pr#1533 [add configuration option for Mtvec](https://github.com/riscv/sail-riscv/pull/1533)
  - pr#1573 [add configuration option for reserved behavior vsew >= 100.](https://github.com/riscv/sail-riscv/pull/1573)
  - 审核 PR <https://github.com/riscv/sail-riscv/pull/1417> Add unratified Zvabd

#### 5.2 技术分享和知识储备

技术分享：
  - [Zibi扩展](https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2026-02-Zibi%E6%89%A9%E5%B1%95.md)
  - [存在主义危机:修复Sail语言的存在类型在Lean4后端的代码生成](https://www.bilibili.com/video/BV1nxctzAEMD)

#### 5.3 SAIL会议

- 参加 tech-golden-model meeting [`02.02`, `02.09`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 2026年 RISC-V 欧洲峰会 
  - 扩展摘要 An Efficient Approach to Apply the RISC-V Sail Model to Chip Verification [PDF](https://github.com/trdthg/plct/blob/main/doc/sail/europe-summit-2026/An%20Efficient%20Approach%20to%20Apply%20the%20RISC-V%20Sail%20Model%20to%20Chip%20Verification.pdf)
  - 扩展摘要 Sail-RISCV-WASM A Browser-Native RISC-V Toolchain and Debugging Workbench [PDF](https://github.com/trdthg/plct/blob/main/doc/sail/europe-summit-2026/Sail-RISCV-WASM%20A%20Browser-Native%20RISC-V%20Toolchain%20and%20Debugging%20Workbench.pdf)

### 6. 职工

#### 6.1 蔡玮霖

##### 6.1.1 RuyiSDk

- ruyi v0.46.0-beta.20260203 测试，发现 1 个缺陷，仓库提交 1 个 issue
  - [Many commands failed: ModuleNotFoundError: No module named 'rich.\_unicode\_data.unicode17-0-0' #428](https://github.com/ruyisdk/ruyi/issues/428
- ruyi 仓库提交 1 个 issue
  - [ruyi admin format-manifest automatically remove distfiles[].strip_components < 2 #430](https://github.com/ruyisdk/ruyi/issues/430)
- ruyisdk-website 仓库提交 14 个 pr
  - [ci: fix audo submodule update #347](https://github.com/ruyisdk/ruyisdk-website/pull/347)
  - [ci: submodule update action will create PR #351](https://github.com/ruyisdk/ruyisdk-website/pull/351)
  - [ci: add automat label for ci audo PR #352](https://github.com/ruyisdk/ruyisdk-website/pull/352)
  - [ci: check trigger for auto PRs #355](https://github.com/ruyisdk/ruyisdk-website/pull/355)
  - [ci: check pnpm build after auto submodule update PR #357](https://github.com/ruyisdk/ruyisdk-website/pull/357)
  - [ci: add action run url in auto PRs body #359](https://github.com/ruyisdk/ruyisdk-website/pull/359)
  - [ci: deploy gh page on gh-pages branch #360](https://github.com/ruyisdk/ruyisdk-website/pull/360)
  - [ci: audo update api data #362](https://github.com/ruyisdk/ruyisdk-website/pull/362)
  - [pages: release /news page #366](https://github.com/ruyisdk/ruyisdk-website/pull/366)
  - [pages(dashboard): remove github status p #367](https://github.com/ruyisdk/ruyisdk-website/pull/367)
  - [docs: update README to pnpm version #374](https://github.com/ruyisdk/ruyisdk-website/pull/374)
  - [ci: retry on 202 for stats/contributors #375](https://github.com/ruyisdk/ruyisdk-website/pull/375)
  - [ci: fix runtime error #376](https://github.com/ruyisdk/ruyisdk-website/pull/376)
  - [ci: fix runtime error #377](https://github.com/ruyisdk/ruyisdk-website/pull/377)
- packages-index 仓库提交 1 个 pr
  - [board-image/buildroot-sdk-sipeed-licheervnano: fix version 20260114 #166](https://github.com/ruyisdk/packages-index/pull/166)
- PLCT-Weekly 仓库提交 1 个 pr
  - [Update RuyiSDK Website section #1274](https://github.com/plctlab/PLCT-Weekly/pull/1274)

##### 6.1.2 实习生 packages-index/board-image 自动化更新工具

- packages-index 仓库提交 2 个 pr
  - [board-image/buildroot-sdk-sipeed-licheervnano: bump to 20260114 #164](https://github.com/ruyisdk/packages-index/pull/164)
  - [board-image/openwrt-sifive-unmatched: bump to latest version 2410.5 #165](https://github.com/ruyisdk/packages-index/pull/165)
- [自动化 PR 提交和 Telegram bot 实现](https://github.com/ruyisdk-test/riko-bot/compare/fd91054f09d7a720ff05bdc60402f6e35b3b7884...96f8ead93c3cb46082cc47eaff6756e3841a2a66)
  
#### 6.2 阎明铸

##### 6.2.1 Sail

- 提交 PR <https://github.com/riscv/sail-riscv/pull/1534> Support custom configs for first-party tests
- 更新 PR <https://github.com/riscv/sail-riscv/pull/765> Add Zilsd/Zclsd Support
- 审核 PR <https://github.com/riscv/sail-riscv/pull/1417> Add unratified Zvabd
- 审核 PR <https://github.com/riscv/sail-riscv/pull/1476> plic mvp
- Sail-RISCV-WASM https://github.com/trdthg/sail-riscv-wasm

##### 6.2.2 Ruyi AI

- 更新 PR <https://github.com/buddy-compiler/buddy-mlir/pull/681> \[package\] Add package scripts and github ci support

##### 6.1.3 会议

- 参加 tech-golden-model meeting [`02.02`, `02.09`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 2026年RISC-V欧洲峰会投稿准备
  - 扩展摘要 An Efficient Approach to Apply the RISC-V Sail Model to Chip Verification [PDF](https://github.com/trdthg/plct/blob/main/doc/sail/europe-summit-2026/An%20Efficient%20Approach%20to%20Apply%20the%20RISC-V%20Sail%20Model%20to%20Chip%20Verification.pdf)
  - 扩展摘要 Sail-RISCV-WASM A Browser-Native RISC-V Toolchain and Debugging Workbench [PDF](https://github.com/trdthg/plct/blob/main/doc/sail/europe-summit-2026/Sail-RISCV-WASM%20A%20Browser-Native%20RISC-V%20Toolchain%20and%20Debugging%20Workbench.pdf)

#### 6.3 张馥媛

##### 6.3.1 RuyiSDK

- RuyiSDK 开发板开发代码示例库建设审核
	- Licheepi4A 示例库扩充
		-  [Ruyi SDK GLES/SDL 中 Allegro 迁移测试及核心问题总结（基于Licheepi4A)](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Allegro/Ruyi_Allegro_test.md)
		-  [LicheePi4A LED 闪烁功能测试文档](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/LED_flashing/Ruyi_LED_flashing.md)
			- [LED flashing Example视频](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/LED_flashing/images/LED_Example.rar)
	- Duo256 示例库扩充
		- [使用RuyiSDK 编译 Milk-V Duo256m 示例程序教程（以2048为例）](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/2026/m02_w01.md)
	- DuoS 示例库扩充
		- [使用 RuyiSDK 构建 Pico-8SEG-LED 驱动程序（以 Milk-V Duo S 为例）](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_Pico_8SEG_RuyiSDK.md)
		- [使用 RuyiSDK 构建 Pico-ePaper-2.13 驱动程序（以 Milk-V Duo S 为例）](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_Pico_ePaper_RuyiSDK.md)
		- WiringX示例的RuyiSDK版本：
			-  [使用 RuyiSDK 编译 Milk-V DuoS 示例程序教程](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_RuyiSDK_DuoS.md)
			- [ADC 读取：采集模拟信号](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_ADC_DuoS.md)
			- [传感器：读取 DHT22 温湿度数据](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_DHT22_DuoS.md)
			- [通信：驱动 SSD1306 OLED 屏幕](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_I2C_SSD1306_DuoS.md)
			- [PWM 控制：呼吸灯效果](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_PWM_DuoS.md)
			- [SPI 通信：读取 MAX6675 温度](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Tutorial_SPI_MAX6675_DuoS.md)
	- 操作系统和工具链测试文档
		-  [bianbu (v3) BPI-F3 系统版本和工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/BPI-F3/Report_bianbu_v3_BPI_F3.md)
		-  [bianbu (v3) Milk-V Jupiter 系统版本和工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Jupiter/Report_bianbu_v3_Milk-V_Jupiter.md)
		-  [bianbu (v3) MUSE Book 系统版本和工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/MUSE_Book/Report_bianbu_v3_MUSE_Book.md)
		-  [bianbu (v3) MUSE Box 系统版本和工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/MUSE_Box/Report_bianbu_v3_MUSE_Box.md)
		-  [bianbu (v3) MUSE Pi Pro 系统版本和工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Muse_Pi_Pro/Report_bianbu_v3_MUSE_Pi_Pro.md)
		- [Ubuntu Milk-V Mras 系统版本和工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Mars/Report_Milk-V%20Mars.md)
		- [Ubuntu Unmatched 系统版本和工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/Unmatched/Re_port_Unmatched.md)
		- [Debian 香山笔记本（Xiangshan Nanhu） 系统版本和工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/%E9%A6%99%E5%B1%B1%E7%AC%94%E8%AE%B0%E6%9C%AC%EF%BC%88Xiangshan%20Nanhu%EF%BC%89/Re_port_%E9%A6%99%E5%B1%B1%E7%AC%94%E8%AE%B0%E6%9C%AC%EF%BC%88Xiangshan%20Nanhu%EF%BC%89.md)

##### 6.3.2 支持矩阵
- 交接前端部署，已成功展示  matrix.ruyisdk.org

##### 6.3.3 2026 RISC-V 欧洲峰会投稿准备
- 调研报告
	- 操作系统：
		- [Debian 操作系统调研报告](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/Debian_Operating%20System%20Research%20Report.md)
		- [Zephyr 操作系统调研报告](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/Zephyr_Operating%20System%20Research%20Report.md)
		- [FreeRTOS 操作系统调研报告](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/FreeRTOS_Operating%20System%20Research%20Report.md)
		- [xv6 操作系统调研报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/xv6%20%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
		- [RT-Thread操作系统调研报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/RT-Thread%20%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
		- [主流操作系统维调研报告](https://github.com/feifei-xx/plct-works/blob/main/%E5%90%84%E7%A7%8D/%E8%B0%83%E7%A0%94/%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%A0%94.md)
	- 开发板：
		- [ESP32 系列开发板调研报告（以ESP32 DevKitC为例）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/ESP32%20%E7%B3%BB%E5%88%97%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A%EF%BC%88%E4%BB%A5ESP32%20DevKitC%E4%B8%BA%E4%BE%8B%EF%BC%89.md)
		- [NVIDIA Jetson系列开发板调研报告（以NVIDIA Jetson Nano为例）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/NVIDIA%20Jetson%E7%B3%BB%E5%88%97%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A%EF%BC%88%E4%BB%A5NVIDIA%20Jetson%20Nano%E4%B8%BA%E4%BE%8B%EF%BC%89.md)
		- [Arduino系列开发板调研报告（以Arduino Uno为例）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/Arduino%E7%B3%BB%E5%88%97%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A%EF%BC%88%E4%BB%A5Arduino%20Uno%E4%B8%BA%E4%BE%8B%EF%BC%89.md)
		- [M5Stack系列发板调研报告（以M5Stack Core2为例）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/M5Stack%E7%B3%BB%E5%88%97%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A%EF%BC%88%E4%BB%A5M5Stack%20Core2%E4%B8%BA%E4%BE%8B%EF%BC%89.md)
		- [Orange Pi 5（香橙派5）开发板调研报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/Orange%20Pi%205%EF%BC%88%E9%A6%99%E6%A9%99%E6%B4%BE5%EF%BC%89%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
		- [Raspberry Pi 5（树莓派5）开发板调研报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/Raspberry%20Pi%205%EF%BC%88%E6%A0%91%E8%8E%93%E6%B4%BE5%EF%BC%89%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
		- [Lichee Pi 4A, Milk-V Mars, Milk-V Duo, 香橙派 (Orange Pi) 系列开发板调研报告](https://github.com/feifei-xx/plct-works/blob/main/%E5%90%84%E7%A7%8D/%E8%B0%83%E7%A0%94/%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94.md)
	- 支持矩阵
		- [知识矩阵（Knowledge Matrix）的介绍](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/%E4%B8%80%E3%80%81%E7%9F%A5%E8%AF%86%E7%9F%A9%E9%98%B5%EF%BC%88Knowledge%20Matrix%EF%BC%89%E7%9A%84%E4%BB%8B%E7%BB%8D.md)
		- [RISC-V 知识矩阵管理框架：构建生态治理新范式](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/RISC-V%20%E7%9F%A5%E8%AF%86%E7%9F%A9%E9%98%B5%E7%AE%A1%E7%90%86%E6%A1%86%E6%9E%B6%EF%BC%9A%E6%9E%84%E5%BB%BA%E7%94%9F%E6%80%81%E6%B2%BB%E7%90%86%E6%96%B0%E8%8C%83%E5%BC%8F.md)
- [扩展摘要 From Fragmentation to Systematization A Standardized Quality Selection and Systematic Reconstruction Approach for RISC-V Courses](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RVDay/From%20Fragmentation%20to%20Systematization%20A%20Standardized%20Quality%20Selection%20and%20Systematic%20Reconstruction%20Approach%20for%20RISC-V%20Courses.pdf)

##### 6.3.4 其它

- RuyiSDK 开发示例短视频
  - [【LicheePi 4A 运行 TryQuake 3D游戏～】 ](https://www.bilibili.com/video/BV1k5F6zNEUy/)
    - [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/TyrQuake.md)

- [实习生技术报告面试题目](https://github.com/DuoQilai/PLCT-Works/blob/main/RISC-V_short_video/Intern_Report_Title.md)

## 参考链接
