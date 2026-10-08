# RISC-V 软件生态进展 · 第 86 期·2026 年 9 月汇总

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

2026年9月，RuyiSDK测试团队完成RuyiSDK 0.53.0-beta.20260917版本在常见Linux发行版操作系统及macOS等系统与x86_64、aarch64、riscv64架构上的包管理器测试，形成29份测试报告，并持续跟踪fastboot文档、镜像源切换、包状态更新、遥测上传等缺陷修复，完成RuyiCode插件备份压缩测试及Eclipse IDE、VSCode IDE延迟发版测试；同时推进RuyiSDK测试工具的持续开发。RuyiSDK示例库和课程方面，board-docs新增了HiFive Premier P550、SpaceMIT K3 CoM260 Kit等板卡的示例及ROS2课程，ROS2 RISC-V课程完成了在K3 Pico-ITX、CoM260 Kit开发板上多章节课程的移植和验证，RISC-V Linux系统与开发板实践课程完成网络与MQTT、线程与协同及K3端侧Agent综合项目并发布到ruyisdk.cn论坛；RuyiSDK网站更新install.sh、下载说明、新闻和合作伙伴，双周报发布第75—77期。RuyiAI方面，buddy-mlir新增PyTorch 2.14的x86/riscv64 CI测试并优化CI耗时，推进Hugging Face模型发布、CLI11参数解析、RISC-V交叉编译简化和BGE-M3 tokenizer改造；triton-riscv更新至最新上游并适配nanobind及join/trans/reshape lowering。操作系统支持矩阵新增或更新HiFive Premier P550、Milk-V Duo S、SpaceMIT K3 CoM260 Kit、CH32V307、CH32V003、ESP32-C3等板卡测试报告，并恢复支持矩阵网站同步；开发板编译工具链测试补充EBC7700/EBC7702、SG2044 EVB、VisionFive 2 Lite、K510、HiFive Premier P550等测试素材和asciinema记录。SAIL/ACT持续向上游提交reserved static rounding modes等PR并审核社区代码，参加东亚双周会。团队共有1个报告和4个海报入选2026年RISC-V中国峰会，并持续协助部分中国企业完成RVI CSC调查填报。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.53.0-beta.20260917 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/README.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260918/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu26.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260918/RUYI_包管理_Ubuntu26.04_x86_64_测试结果.md)
    - [Ubuntu26.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Ubuntu26.04_riscv64_测试结果.md)
    - [Ubuntu26.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Ubuntu26.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Fedora42_x86_64_测试结果.md)
	- [Fedora42 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Fedora42_aarch64_测试结果.md)
	- [Fedora43 x86_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Fedora43_x86_64_测试结果.md)
	- [Fedora43 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Fedora43_aarch64_测试结果.md)
	- [Deepin23 x86_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Deepin23_x86_64_测试结果.md)
	- [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Deepin23_riscv64_测试结果.md)
	- [Deepin25 x86_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Deepin25_x86_64_测试结果.md)
	- [Deepin25 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Deepin25_riscv64_测试结果.md)
	- [Deepin25 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Deepin25_aarch64_测试结果.md)
	- [OpenCloudOS 9.4 x86_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)
	- [OpenCloudOS 9.4 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_OpenCloudOS_aarch64_测试结果.md)
	- [Archlinux x86_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_Archlinux_x86_64_测试结果.md)
	- [macOS aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260918/RUYI_包管理_macOS_arm64_测试结果.md)

    - 缺陷：  
		- 文档测试
		上一版本遗留 2 个缺陷：

		| 缺陷      | 问题等级 | 备注 |
		| ----------- | ----------- | --- |
		| [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，正在修复中 |

		- Ruyi 包管理器测试

		遗留缺陷：

		| 缺陷      | 问题等级 |判定依据 |
		| ----------- | ----------- | --- |
		| [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415) | 一般 | 已有 issue 回复 |

		新增缺陷：

		| 缺陷      | 问题等级 |判定依据 |
		| ----------- | ----------- | --- |
		| [ruyi only try first url in mirror list #498](https://github.com/ruyisdk/ruyi/issues/498) | 严重 | 测试版已修复 |
		| [切换软件源后，已安装的软件包显示为「未安装」，且重新安装被跳过、状态永远无法更新 #501](https://github.com/ruyisdk/ruyi/issues/501) | 一般 | 边缘情况，已修复 |

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

	- RuyiSDK VSCode IDE 延迟发版测试

	| 缺陷 | 问题等级 | 备注 |
	| --- | --- | --- |
	| [包树搜索会将输入强制转为小写 #252](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/252) | 建议 |  |
	| [新闻搜索会将输入强制转为小写 #253](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/253) | 建议 |  |
	| [下载进度显示的软件包大小偏小（单位进制不一致） #254](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/254) | 建议 |  |
	| [版本状态显示错误 正式版被标为预览版，最新预览版被标为旧版 #255](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/255) | 修复 |  |

- [ruyi only try first url in mirror list #498](https://github.com/ruyisdk/ruyi/issues/498)
-[ruyi telemetry upload 经常失败 #117](https://github.com/ruyisdk/ruyi-backend/issues/117)
- https://github.com/ruyisdk-test/riko-bot/pull/1
- https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test/pull/1 
- https://github.com/ruyisdk/ruyi/issues/501 切换软件源后，已安装的软件包显示为「未安装」，且重新安装被跳过、状态永远无法更新

- ruyisdk-vscode 测试
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/252 包树搜索会将输入强制转为小写
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/253 新闻搜索会将输入强制转为小写
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/254 下载进度显示的软件包大小偏小（单位进制不一致）
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/255 版本状态显示错误 正式版被标为预览版，最新预览版被标为旧版
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/225 ruyi存在多个镜像源时，存在软件包安装冲突（状态异常）
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/226 ruyi package 切换镜像源时，需手动刷新当前的软件包状态
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/227 package 版本状态不一致
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/229 虚拟环境创建时工具链列表的中英文状态不一致
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/232 最新版工具链排序问题
	- https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/235 emulator排序意义不明
	- https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/14

- [RuyiCode 插件测试（备份压缩）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Others/RuYiCode插件测试.rar)

#### 1.2 RuyiSDK开发和测试开发

- ruyi
RuyiSDK包管理器 
	- [test(ruyi-pytest): update to latest and fix resources download timeout #494](https://github.com/ruyisdk/ruyi/pull/494)
    - [tests(ruyi-pytest): calculate ruyi install timeout by pkg count #503](https://github.com/ruyisdk/ruyi/pull/503)

- ruyisdk-test/ruyi-pytest 
集成测试套件，用于全面验证 ruyi CLI 的功能正确性。
	- [Fixes for ruyi 0.53.x #21](https://github.com/ruyisdk-test/ruyi-pytest/pull/21)
    - test: switch from gnu-plct to gnu-ruyisdk for macOS tests [fecb7f7](https://github.com/ruyisdk-test/ruyi-pytest/commit/fecb7f7930688495f026bb666e331d13849bd9f9)
    - test: calculate ruyi install timeout by pkg count [94881c0](https://github.com/ruyisdk-test/ruyi-pytest/commit/94881c0bece8ea1c884aca1733b752de3b9f13a0)

- ruyisdk-test/oh-my-ruyi
图形化管理工具，为 ruyi 包管理器的 GUI 前端，提供了版本管理、仓库管理、设备烧录等核心功能的可视化操作界面。
	- fix: validate stable ruyi versions [0527a01](https://github.com/ruyisdk-test/oh-my-ruyi/commit/0527a01ea6931ba1c49f089e8bd1c31b478ff489)
    - test: update ruyi installer expectations [7e9f891](https://github.com/ruyisdk-test/oh-my-ruyi/commit/7e9f89153081abec5638d3c4b7cd7de20af08a9c)
    - ci: keep uv prerelease mode consistent [7e9f891](https://github.com/ruyisdk-test/oh-my-ruyi/commit/7e9f89153081abec5638d3c4b7cd7de20af08a9c)

- ruyisdk-test/ruyi-index-test-bot
packages-index 是 RuyiSDK 的包元数据仓库，为 ruyi 客户端提供包索引和同步数据源，测试团队负责RISC-V开发板镜像测试和集成。
    - [33ccb23...b6b465e](https://github.com/ruyisdk-test/ruyi-index-test-bot/compare/33ccb23824c4e2bb47fa2dc9271db13209c7b58c...b6b465e47301414403a4bce731176ef6eaa69563) 3,169 additions and 1 deletion
    - [bb15827...ecfe986](https://github.com/ruyisdk-test/ruyi-index-test-bot-web/compare/bb15827812058af4ea9836ced1b80473c8d2226d...ecfe986fb95329bf62f04e5f406087e199385ea1) 291 additions and 53 deletions
    - [b8cda9a...dc48bed](https://github.com/ruyisdk-test/ruyi-index-resolve-bot/compare/b8cda9a9abef9dbc9900e396fdb4c8b28d39c27c...dc48bed7c2245fc6beaca8b0d5745a2d1116a198) 2,328 additions and 30 deletions

- https://github.com/qingwan12138/ruyi-telegram-bot  这是从 [`ruyisdk-test/riko-bot`](https://github.com/ruyisdk-test/riko-bot) 拆分出来的独立 Telegram 通知与人工交互传输服务。

#### 1.3 RuyiSDK开发示例库和示例库网站开发

- Ruyi 示例文档库：
	- 仓库：[ruyisdk/board-docs](https://github.com/ruyisdk/board-docs)
	- 开发板示例文档扩充：
		- HiFive Premier P550：新增中英文板卡概述、Hello World 和 CoreMark 示例，覆盖 GCC、LLVM 工具链的编译与运行，见 [PR #46](https://github.com/ruyisdk/board-docs/pull/46)。
		- SpaceMIT K3 CoM260 Kit：新增中英文板卡概述和 Hello World 示例、中文 CoreMark 示例，并补充 ROS 2 第 1—2 章课程入口，见 [PR #47](https://github.com/ruyisdk/board-docs/pull/47)。
	- ROS 2 课程接入：
		- 为 K3 Pico-ITX 新增课程入口及第一章课程元数据，关联 RISC-V 与 x86 版本的教案、实验手册和运行环境，见 [PR #44](https://github.com/ruyisdk/board-docs/pull/44)。
		- 将课程文档来源切换至 GitHub 镜像，完善课程介绍、教案和实验手册的链接，见 [PR #45](https://github.com/ruyisdk/board-docs/pull/45)。
		- 为 K3 Pico-ITX、CoM260 Kit 接入独立课程目录，并增加 CoM260 Kit 第 3—4 章的 RISC-V 与 x86 课程入口，见 [PR #48](https://github.com/ruyisdk/board-docs/pull/48)。
		- 更新 K3 Pico-ITX、CoM260 Kit 的课程元数据，改为引用课程仓库 `course_support` 目录下的板卡课程清单，见 [PR #49](https://github.com/ruyisdk/board-docs/pull/49)。
	- 仓库维护：统一板卡文档、元数据及中英文索引中的 SpaceMIT 厂商名称，见 [PR #43](https://github.com/ruyisdk/board-docs/pull/43)。

- board-docs-frontend：
	- 项目仓库：[DuoQilai/board-docs-frontend](https://github.com/DuoQilai/board-docs-frontend)
	- 在线站点：[中文入口](https://boards.ruyisdk.org/)；[英文入口](https://boards.ruyisdk.org/en/)
	- 新增 ROS 2 课程页面和中英文访问路由，按开发板、章节及 RISC-V／x86 版本组织教案与实验手册；支持远程文档、图片和视频同步，补充首页课程预览、更新提示及统一顶部导航，见 [PR #9](https://github.com/DuoQilai/board-docs-frontend/pull/9)。
	- 优化移动端课程目录和正文显示，调整表格、长链接及代码块在窄屏下的布局，见 [PR #10](https://github.com/DuoQilai/board-docs-frontend/pull/10)。
	- 增加课程上一章／下一章导航，修正当前课程及章节的目录定位，并在首页展示最新课程章节，见 [PR #11](https://github.com/DuoQilai/board-docs-frontend/pull/11)。
	- 从固定版本的课程子模块读取目录、正文和媒体，依据课程目录生成章节路由、导航和最新章节预览；同步失败时保留原有缓存与素材，见 [PR #12](https://github.com/DuoQilai/board-docs-frontend/pull/12)。
	- 同步更新 README 中的课程目录路径示例，与课程仓库的新目录结构保持一致，见 [PR #13](https://github.com/DuoQilai/board-docs-frontend/pull/13)。

- RISC-V ROS 2 机器人操作系统编程课程
	- 项目仓库：[ROS2_RISCV](https://gitee.com/yunxiangluo/ROS2_RISCV)；[GitHub 镜像](https://github.com/DuoQilai/ROS2_RISCV)
	- K3 Pico-ITX 课程移植与验证：
		- 完成第一章独立 C--17 课程源码、教师教案及实验手册，验证环境安装、DDS 通信与域隔离、生命周期节点、IDE 远程调试及 K3 与 x86 Gazebo 联动；整理第 1—4 章的运行证据、截图和连续录像，见 [PR !2](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/2)。
		- 完成第 2—4 章独立源码、教案和实验手册，覆盖节点与命名空间、日志工具、话题与自定义消息、QoS、执行器和服务通信，补充板端运行及 Gazebo 运动、停止验证，见 [Commit 07c86bb](https://gitee.com/chuachuaa/ROS2_RISCV/commit/07c86bbc94aa6cbd3a514b86230de8d167e41d93)。
	- CoM260 Kit 课程移植与验证：
		- 第 1—2 章：基于 Bianbu 4.0.6／ROS 2 Humble 建立板端与 x86 课程环境，完成独立文档和 C--17 示例，验证 DDS、生命周期、建包、命名空间、日志过滤、远程调试和仿真里程计反馈，见 [PR !3](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/3)。
		- 第 3—4 章：完成话题、自定义消息、QoS、执行器和服务通信的教案、实验及源码；验证从空目录建包、方形运动、速度服务、无时钟与中断退出行为，并补充连续录像和运行记录，见 [PR !4](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/4)。
		- 第 5—6 章：完成动作通信、参数与 Launch 的 C--17 示例、教案和实验手册，验证动作反馈与取消、目标拒绝、参数校验、动态调速、巡航配置及独立信号停止；完成与 x86 Gazebo 的运动和停车联调、Nav2 组合启动验证，补齐截图、CAST、MP4、GIF 和实测记录，见 [PR !5](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/5)。
	- 课程目录与镜像维护：
		- 在课程仓库新增 K3 Pico-ITX 和 CoM260 Kit 的板卡课程目录，统一维护章节、教案、实验、编程语言及运行环境，见 [PR #1](https://github.com/DuoQilai/ROS2_RISCV/pull/1)。
		- 补充 `course_support` 目录下的板卡课程清单，保留 K3 Pico-ITX 第一章入口，并将 CoM260 Kit 的 RISC-V／x86 教案及实验入口补齐至第六章，见 [PR !5](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/5)。
		- 改进 Gitee 到 GitHub 的课程镜像同步，保留 GitHub 侧课程目录，并补充冲突、拉取失败及并发更新场景的验证，见 [PR #2](https://github.com/DuoQilai/ROS2_RISCV/pull/2)。

- RISC-V Linux 系统与开发板实践课程
	- 项目仓库：[DuoQilai/ruyi-riscv-linux-book](https://github.com/DuoQilai/ruyi-riscv-linux-book)
	- 第五章“网络与 MQTT”：将实验细化为命令解析、虚拟灯命令环及真实 GPIO／MQTT 远程控灯三个递进环节，补充实机接线、命令与状态联调、非法命令拒绝及板端 tcpdump 抓包证据，见 [PR #8](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/8)。
	- 第六章“线程与协同”：新增成对快照加锁练习，完善 race-demo、snapshot-lock 与 tri-thread 的递进实验；修正并发控制、MQTT 载荷匹配与连接／收发错误处理，补充线程创建和 GPIO 初始化失败检查；完善加锁重编命令、竞态复现、ThreadSanitizer、加锁对照及三线程协同的板端截图、录屏和实物动作录像，见 [PR #9](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/9)。
	- 综合项目：补充 K3 端侧 Agent 与荔枝派的 MQTT 联调工具、部署说明和实物演示，提供状态查询、风扇及 LED 控制接口，整理 Qwen2.5-1.5B Q4_0 本地推理与云端模型调用的运行材料；完善阈值参数格式、上下限关系及板端状态读回校验，明确本轮温湿度为模拟数据、风扇及 LED 为真实 GPIO 控制，见 [PR #11](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/11)。

#### 1.4 RISC-V 操作系统支持矩阵

- [ruyisdk/support-matrix#389](https://github.com/ruyisdk/support-matrix/pull/389)
- [Premier_P550: update Debian test report：ruyisdk/support-matrix#393](https://github.com/ruyisdk/support-matrix/pull/393)
- [Fedora 44 Premier P550 test report：ruyisdk/support-matrix#400](https://github.com/ruyisdk/support-matrix/pull/400)

#### 1.5 RuyiSDK网站

- [pages(news): add RISC-V Summit Europe 2026 article #581](https://github.com/ruyisdk/ruyisdk-website/pull/581)
- [scripts: new install.sh #580](https://github.com/ruyisdk/ruyisdk-website/pull/580)
- [pages(downloads): update instructions to fit the latest install.sh #582](https://github.com/ruyisdk/ruyisdk-website/pull/582)
- [static(install.sh): configure ruyi repo after installation #583](https://github.com/ruyisdk/ruyisdk-website/pull/583)
- [pages(index): add spacemit to index partners #586](https://github.com/ruyisdk/ruyisdk-website/pull/586)

#### 1.6 RuyiSDK双周报

- [第 77 期RuyiSDK测试和系统测试报告、P550／CoM260 Kit 示例和课程](https://github.com/ruyisdk/wechat-articles/blob/main/20260924-ruyisdk-biweekly-77.md)。
- [第 76 期RuyiSDK测试和ROS2课程](https://github.com/ruyisdk/wechat-articles/blob/main/20260924-ruyisdk-biweekly-76.md)。
- [第 75 期RuyiSDK测试和支持矩阵和开发板文档](https://github.com/ruyisdk/wechat-articles/blob/main/20260924-ruyisdk-biweekly-75.md)。

### 2. RuyiAI

- buddy-compiler/buddy-mlir
	- `[ci] Add pytorch 2.14 test for X86` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/887
		- x64/arm64 加测 torch 2.14（PyPI 与 `download.pytorch.org/whl/cpu` 已有，无需换索引）；riscv64 保持 2.13（Ruyi 索引 riscv64 最新仍为 torch-2.13.0）
		- 版本遍历改为「从新到旧」，只有最新版跑完整 `check-buddy`，旧版本跑 `check-buddy-python` - `check-buddy-examples-buddyjit`；循环耗时 x64 8.3→~5min、riscv64 52→~27min
		- 修 lit 目标：`add_lit_testsuites()` 传 BINARY_DIR，让 `check-buddy-*` 能定位生成的 `lit.site.cfg.py`

	- `[ci] Add pytorch 2.14 test for riscv` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/926
		- Ruyi 仓库 pypi 数据里 riscv64 已发布 torch 2.14.0（cp310/312/314，manylinux_2_38_riscv64），据此补上 riscv64 的 2.14 测试

	- `[CI][Models] Publish to huggingface` 🔄 草稿（更新） 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/925
		- 新增 publish-models workflow：为 `models/publish.json` 中每个启用的 spec 交叉编译 riscv64 `.rax` 包，按模型家族推送到对应 Hugging Face 仓库，并用 CLI 版本打 tag
		- `workflow_dispatch` 手动触发，另在 ci 分支挂了临时 push 触发

	- `[deps] Add CLI11 and parse tool arguments with it` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/936
		- 新增 `cmake/deps.cmake`，FetchContent 统一管理 header-only 依赖；CLI11 默认开启，离线构建可用 `BUDDY_DOWNLOAD_CLI11=OFF` 关闭
		- buddy-cli / buddy-server / rax-pack / rax-inspect 的手写 argv 解析全部换成 CLI11（分组选项、类型化解析、`--opt=value`、自动 `--help` 与报错），各工具新增 `--version`

	- `[build] Simplify RISC-V cross compilation` 🔄 草稿 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/937
		- Makefile 一键交叉构建：host 工具 - RISC-V GNU 工具链 - 交叉 MLIR/OpenMP runtime；再按 `models/*/specs/*.json` 生成 per-model riscv64 `.rax` target，默认 target 一并构建 Python 包，README 补充流程
		- `.rax` manifest 注入 release version（新增 `--version`），运行时依赖（libomp、mlir_c_runner_utils、float16/apfloat wrapper）作为 `runtime_dep_*` 打进包内，加载模型前用 `RTLD_GLOBAL` 装载、通过 `$ORIGIN` 解析；buddy-cli 不再静态链接 LLVM
		- 模型插件（serving/embedding/masked-lm/transcription）改为用交叉 clang 编译，配套 EXTRA_SRCS 与 LLVM/MLIR include 路径

	- `[models] Use jsoncons in the BGE-M3 tokenizer` 🔄 草稿 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/938
		- BGE-M3 tokenizer 原用 `llvm::json` - MemoryBuffer 解析 tokenizer.json；该模型是 single_forward，runner plugin 交叉编译时不带 LLVMSupport，导致链接失败
		- 改为引入 header-only jsoncons（v1.8.1），base64 本地解码，去掉对 LLVMSupport 的依赖

- RuyiAI-Stack/triton-riscv
	— `[triton] Update integration for latest upstream` ✅ 合并 🔗 https://github.com/RuyiAI-Stack/triton-riscv/pull/76
	- Triton 升到 58895270 并 rebase CPU-only 集成补丁，只保留上游还未吸收的改动；Buddy 与 LLVM 同步升到匹配版本
	- 插件绑定切换到 nanobind（跟进 Triton PR #10283）；适配 PR #11293 引入的 join/trans/reshape lowering，改造指针拼接，并在 TritonToPtr 里转换其 transpose/collapse 操作

### 3. RISC-V 操作系统支持矩阵

## RuyiSDK Support Matrix

- HiFive Premier P550：
	- 更新 Debian 中英文测试报告，补充镜像烧录、启动与串口登录记录，见 [PR #393](https://github.com/ruyisdk/support-matrix/pull/393)。
	- 新增 Fedora 44 Server 中英文测试报告，补充 Bootchain 更新、启动配置及串口登录验证，见 [PR #400](https://github.com/ruyisdk/support-matrix/pull/400)。
- Milk-V Duo S：
	- 更新 Arch Linux 测试报告，补充新版镜像的安装步骤、启动日志和录屏，见 [PR #394](https://github.com/ruyisdk/support-matrix/pull/394)。
	- 更新 Debian 13 社区镜像 v1.9.6 测试报告，补充系统信息、串口登录结果及启动告警记录，见 [PR #395](https://github.com/ruyisdk/support-matrix/pull/395)。
	- 更新 RT-Thread、RT-Thread Smart 5.2.2 测试报告，完善源码编译、小核与 FIP 打包、启动日志和录屏，见 [PR #396](https://github.com/ruyisdk/support-matrix/pull/396)、[PR #397](https://github.com/ruyisdk/support-matrix/pull/397)。
	- 更新 Ubuntu 24.04 LTS 中英文测试报告，补充镜像安装、系统信息和启动验证，见 [PR #398](https://github.com/ruyisdk/support-matrix/pull/398)。
	- 更新 Zephyr 4.1.99 中英文测试报告，完善构建、固件打包、UART1 接线和 C906 小核 Hello World 运行记录，见 [PR #405](https://github.com/ruyisdk/support-matrix/pull/405)。
	- 更新 xv6 中英文测试报告，补齐镜像准备、启动文件重新打包、烧录及成功启动证据，见 [PR #407](https://github.com/ruyisdk/support-matrix/pull/407)。
- SpaceMIT K3 CoM260 Kit：
	- 新增中英文板卡概述及 Buildroot 1.0.7 测试报告，记录 TITANTOOLS 烧录、串口登录和 Weston 桌面验证，见 [PR #399](https://github.com/ruyisdk/support-matrix/pull/399)。
	- 新增 Bianbu 4.0.6 LXQt 中英文测试报告，补充系统初始化、串口登录、系统信息和桌面截图，见 [PR #401](https://github.com/ruyisdk/support-matrix/pull/401)。
	- 新增 OpenHarmony 6.1 中英文测试报告，记录默认启动因缺少设备树失败的问题，以及临时使用另一设备树进入 shell 和桌面的验证过程，见 [PR #402](https://github.com/ruyisdk/support-matrix/pull/402)。
	- 整理 openEuler 24.03-LTS-SP4 中英文待测文档，覆盖镜像下载与校验、解压烧录、UART 接线及 SD 卡启动步骤，见 [PR #403](https://github.com/ruyisdk/support-matrix/pull/403)。
- CH32V307：更新 RT-Thread 5.3.1 中英文测试报告，改用官方 BSP，补充 SDK 依赖、存储配置、串口命令及板载以太网 DHCP／ping 验证，见 [PR #404](https://github.com/ruyisdk/support-matrix/pull/404)。
- CH32V003：新增基于官方 `ch32v003f4p6-evt` BSP 的 RT-Thread 中英文测试报告，补充 Windows 编译、WCH-LinkE 接线、烧录与 USART1 启动至 msh 的验证记录，实测范围限于串口控制台，见 [PR #408](https://github.com/ruyisdk/support-matrix/pull/408)。
- ESP32-C3：新增 RT-Thread 5.3.1 中英文测试报告，记录编译、烧录、启动至 msh 及基础命令验证，并补充 Windows 链接脚本和芯片版本适配说明，见 [PR #406](https://github.com/ruyisdk/support-matrix/pull/406)。
- 支持矩阵网站：排查并恢复内容同步，核对 CoM260 Kit 四项系统、P550 Fedora 44 和 CH32V307 RT-Thread 5.3.1 的页面更新，见 [CoM260 Kit 页面](https://matrix.ruyisdk.org/zh-CN/boards/CoM260_Kit/)、[P550 页面](https://matrix.ruyisdk.org/boards/Premier_P550/)、[CH32V307 页面](https://matrix.ruyisdk.org/boards/CH32V307/)。
- [Add Zephyr Milk-V Duo S test report](https://github.com/ruyisdk/support-matrix/pull/405)
- [Add Arch Linux Milk-V Duo S test report](https://github.com/ruyisdk/support-matrix/pull/394)
- [Add Debian Milk-V Duo S test report](https://github.com/ruyisdk/support-matrix/pull/395)
- [Add RT-Thread Milk-V Duo S test report](https://github.com/ruyisdk/support-matrix/pull/396)
- [Add Ubuntu Milk-V Duo S test report](https://github.com/ruyisdk/support-matrix/pull/398)
- [Add xv6 Milk-V Duo S test report](https://github.com/ruyisdk/support-matrix/pull/407)
- [Add RT-Thread Smart Milk-V Duo S test report](https://github.com/ruyisdk/support-matrix/pull/397)

### 4. RISC-V 开发板编译工具链测试

- 开发板测试素材：新增 EBC7702 的 2 张、SG2044 EVB 的 1 张测试环境照片，整理 VisionFive 2 Lite 与 K510 已有照片的命名和引用，并更新测试总表中的录制材料说明，见 [PR #5](https://github.com/DuoQilai/asciinema/pull/5)。
- Add HiFive Premier P550 test environment photos：[DuoQilai/asciinema#7](https://github.com/DuoQilai/asciinema/pull/7)
- [HiFive Premier P550 Debian test asciinema](https://asciinema.org/a/1264770)
- [HiFive Premier P550 Fedora 44 Server test asciinema](https://asciinema.org/a/1264802)
- Add Premier P550 documentation：[ruyisdk/board-docs#46](https://github.com/ruyisdk/board-docs/pull/46)
- [Add EBC7700 device photos](https://github.com/DuoQilai/asciinema/pull/6)

### 5. SAIL和ACT

#### 5.1 SAIL和ACT开发

- 软件所与某企业扩展合作项目，产出占本月Sail产出重要比例，不公开
- [`Add configurable behavior for reserved static rounding modes`](https://github.com/riscv/sail-riscv/pull/1987)
- [sail-riscv#1924](https://github.com/riscv/sail-riscv/pull/1924)
- [sail-riscv#1841](https://github.com/riscv/sail-riscv/pull/1841
- [sail-riscv#1856](https://github.com/riscv/sail-riscv/pull/1856)
- [sail-riscv#commit1883](https://github.com/riscv/sail-riscv/pull/1857/changes/1883ce7b1522158c9ecf88a7209c2ccfa3eb1ce2)
- 审核社区提交代码

#### 5.2 SAIL会议

- 厂商合作开发工作(包括SAIL部分)
- 参加东亚双周会 0917，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1m5uf-wuYubk2EecwQ6HhjDBV3k_7TohCoUcKkbb-jto/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0903，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1dDaP28s3ppZUHpYgtIx_ZpUF9NTRNnE9_tyg0Aj12OI/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

### 6. 2026年RISC-V 中国峰会

收到通知以下1个报告和4个海报入选
- [RISC-V课程移植方法与RuyiSDK生态建设（报告）](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/JJPCAAGRQEGEDGWMXHGFHZCBGA97ASGT)
- [Ruyi 包管理器 - 专为 RISC-V 开发者打造的全方位、集成式全功能开发环境](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/L9QA9JTA8JBGGU8CFWXEPPPKHUFBSWMB)
- [AI 驱动的 RISC-V 图形化应用测试（RuyiSDK IDE测试方法，海报）](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/YKGSC8XVWAGA9LE9JKHMRQQUCCHAAKM7)
- [从碎片化到体系化：RISC-V 课程质量评估与系统化重构（海报）](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/KLZWWYCLBYPQHYWYHKHT8CYPHNMGHYSF)
- [一种将 RISC-V Sail 模型高效应用于芯片验证的方法](https://cfp2026.riscv-summit-china.org/rvsc2026/talk/review/JH7LXDC8VBMWUJ9C3UN3YKNDPUEAHWWL)

### 7. RVI CSC 中国客户调查

- 辅助部分中国企业完成调查表
- 联系更多中国企业参与

### 8. 职工

#### 8.1 蔡玮霖

- 测试 Ruyi 0.52.0 测试版本提交测试报告
    - [!101 Add 0.52.0 test result](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/101)
- 测试 Ruyi 0.53.0 测试版本提交测试报告
    - [!102 Update v0.53.0 test report](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/102)
- 更新 Ruyi 0.53.0 测试报告的 VSCode 部分
    - [!103 Update v0.1.7 vscode test result](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/103)
- ruyisdk-website 仓库审核 1 个 pr
    - [pages(news): add RISC-V Summit Europe 2026 article #581](https://github.com/ruyisdk/ruyisdk-website/pull/581)
- ruyisdk-website 仓库提交 4 个 pr
    - [scripts: new install.sh #580](https://github.com/ruyisdk/ruyisdk-website/pull/580)
    - [pages(downloads): update instructions to fit the latest install.sh #582](https://github.com/ruyisdk/ruyisdk-website/pull/582)
    - [static(install.sh): configure ruyi repo after installation #583](https://github.com/ruyisdk/ruyisdk-website/pull/583)
    - [pages(index): add spacemit to index partners #586](https://github.com/ruyisdk/ruyisdk-website/pull/586)
- ruyi 仓库提交 1 个 issue
    - [ruyi only try first url in mirror list #498](https://github.com/ruyisdk/ruyi/issues/498)
- ruyi 仓库提交 1 个 pr
    - [test(ruyi-pytest): update to latest and fix resources download timeout #494](https://github.com/ruyisdk/ruyi/pull/494)
    - [tests(ruyi-pytest): calculate ruyi install timeout by pkg count #503](https://github.com/ruyisdk/ruyi/pull/503)
- ruyi-backend 仓库提交 1 个 issue
    - [ruyi telemetry upload 经常失败 #117](https://github.com/ruyisdk/ruyi-backend/issues/117)
- ruyisdk-test/ruyi-pytest 仓库审核 1 个 pr
    - [Fixes for ruyi 0.53.x #21](https://github.com/ruyisdk-test/ruyi-pytest/pull/21)
- ruyisdk-test/ruyi-pytest 仓库提交 2 个 commit
    - test: switch from gnu-plct to gnu-ruyisdk for macOS tests [fecb7f7](https://github.com/ruyisdk-test/ruyi-pytest/commit/fecb7f7930688495f026bb666e331d13849bd9f9)
    - test: calculate ruyi install timeout by pkg count [94881c0](https://github.com/ruyisdk-test/ruyi-pytest/commit/94881c0bece8ea1c884aca1733b752de3b9f13a0)
- ruyisdk-test/oh-my-ruyi 仓库提交 3 个 commit
    - fix: validate stable ruyi versions [0527a01](https://github.com/ruyisdk-test/oh-my-ruyi/commit/0527a01ea6931ba1c49f089e8bd1c31b478ff489)
    - test: update ruyi installer expectations [7e9f891](https://github.com/ruyisdk-test/oh-my-ruyi/commit/7e9f89153081abec5638d3c4b7cd7de20af08a9c)
    - ci: keep uv prerelease mode consistent [7e9f891](https://github.com/ruyisdk-test/oh-my-ruyi/commit/7e9f89153081abec5638d3c4b7cd7de20af08a9c)
- ruyisdk-test/ruyi-index-test-bot 仓库提交 52 个 commit
    - [33ccb23...b6b465e](https://github.com/ruyisdk-test/ruyi-index-test-bot/compare/33ccb23824c4e2bb47fa2dc9271db13209c7b58c...b6b465e47301414403a4bce731176ef6eaa69563) 3,169 additions and 1 deletion
- ruyisdk-test/ruyi-index-test-bot 仓库提交 8 个 commit
    - [bb15827...ecfe986](https://github.com/ruyisdk-test/ruyi-index-test-bot-web/compare/bb15827812058af4ea9836ced1b80473c8d2226d...ecfe986fb95329bf62f04e5f406087e199385ea1) 291 additions and 53 deletions
- ruyisdk-test/ruyi-index-test-bot 仓库提交 17 个 commit
    - [b8cda9a...dc48bed](https://github.com/ruyisdk-test/ruyi-index-resolve-bot/compare/b8cda9a9abef9dbc9900e396fdb4c8b28d39c27c...dc48bed7c2245fc6beaca8b0d5745a2d1116a198) 2,328 additions and 30 deletions

#### 8.2 阎明铸

##### 8.2.1 Sail

- 厂商合作开发工作(产出不公开,量大)
- `Add configurable behavior for reserved static rounding modes` 🔄 提交
🔗 https://github.com/riscv/sail-riscv/pull/1987
- 审核社区提交代码
- 参加厂商合作开发工作会议
- 参加Sail会议
- 参加东亚双周会 0917，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1m5uf-wuYubk2EecwQ6HhjDBV3k_7TohCoUcKkbb-jto/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0903，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1dDaP28s3ppZUHpYgtIx_ZpUF9NTRNnE9_tyg0Aj12OI/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

##### 8.2.2 Ruyi AI

- buddy-compiler/buddy-mlir

	- `[ci] Add pytorch 2.14 test for X86` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/887
		- x64/arm64 加测 torch 2.14（PyPI 与 `download.pytorch.org/whl/cpu` 已有，无需换索引）；riscv64 保持 2.13（Ruyi 索引 riscv64 最新仍为 torch-2.13.0）
		- 版本遍历改为「从新到旧」，只有最新版跑完整 `check-buddy`，旧版本跑 `check-buddy-python` + `check-buddy-examples-buddyjit`；循环耗时 x64 8.3→~5min、riscv64 52→~27min
		- 修 lit 目标：`add_lit_testsuites()` 传 BINARY_DIR，让 `check-buddy-*` 能定位生成的 `lit.site.cfg.py`

	- `[ci] Add pytorch 2.14 test for riscv` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/926
		- Ruyi 仓库 pypi 数据里 riscv64 已发布 torch 2.14.0（cp310/312/314，manylinux_2_38_riscv64），据此补上 riscv64 的 2.14 测试

	- `[CI][Models] Publish to huggingface` 🔄 草稿（更新） 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/925
		- 新增 publish-models workflow：为 `models/publish.json` 中每个启用的 spec 交叉编译 riscv64 `.rax` 包，按模型家族推送到对应 Hugging Face 仓库，并用 CLI 版本打 tag
		- `workflow_dispatch` 手动触发，另在 ci 分支挂了临时 push 触发

	- `[deps] Add CLI11 and parse tool arguments with it` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/936
		- 新增 `cmake/deps.cmake`，FetchContent 统一管理 header-only 依赖；CLI11 默认开启，离线构建可用 `BUDDY_DOWNLOAD_CLI11=OFF` 关闭
		- buddy-cli / buddy-server / rax-pack / rax-inspect 的手写 argv 解析全部换成 CLI11（分组选项、类型化解析、`--opt=value`、自动 `--help` 与报错），各工具新增 `--version`

	- `[build] Simplify RISC-V cross compilation` 🔄 草稿 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/937
		- Makefile 一键交叉构建：host 工具 + RISC-V GNU 工具链 + 交叉 MLIR/OpenMP runtime；再按 `models/*/specs/*.json` 生成 per-model riscv64 `.rax` target，默认 target 一并构建 Python 包，README 补充流程
		- `.rax` manifest 注入 release version（新增 `--version`），运行时依赖（libomp、mlir_c_runner_utils、float16/apfloat wrapper）作为 `runtime_dep_*` 打进包内，加载模型前用 `RTLD_GLOBAL` 装载、通过 `$ORIGIN` 解析；buddy-cli 不再静态链接 LLVM
		- 模型插件（serving/embedding/masked-lm/transcription）改为用交叉 clang 编译，配套 EXTRA_SRCS 与 LLVM/MLIR include 路径

	- `[models] Use jsoncons in the BGE-M3 tokenizer` 🔄 草稿 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/938
		- BGE-M3 tokenizer 原用 `llvm::json` + MemoryBuffer 解析 tokenizer.json；该模型是 single_forward，runner plugin 交叉编译时不带 LLVMSupport，导致链接失败
		- 改为引入 header-only jsoncons（v1.8.1），base64 本地解码，去掉对 LLVMSupport 的依赖

- RuyiAI-Stack/triton-riscv
		- PR #76 — `[triton] Update integration for latest upstream` ✅ 合并 🔗 https://github.com/RuyiAI-Stack/triton-riscv/pull/76
		- Triton 升到 58895270 并 rebase CPU-only 集成补丁，只保留上游还未吸收的改动；Buddy 与 LLVM 同步升到匹配版本
		- 插件绑定切换到 nanobind（跟进 Triton PR #10283）；适配 PR #11293 引入的 join/trans/reshape lowering，改造指针拼接，并在 TritonToPtr 里转换其 transpose/collapse 操作

#### 8.3 张馥媛

##### 8.3.1 RuyiSDK 示例代码库建设

- Ruyi 示例文档库：
	- 仓库：[ruyisdk/board-docs](https://github.com/ruyisdk/board-docs)
	- 开发板示例文档扩充：
		- HiFive Premier P550：新增中英文板卡概述、Hello World 和 CoreMark 示例，覆盖 GCC、LLVM 工具链的编译与运行，见 [PR #46](https://github.com/ruyisdk/board-docs/pull/46)。
		- SpaceMIT K3 CoM260 Kit：新增中英文板卡概述和 Hello World 示例、中文 CoreMark 示例，并补充 ROS 2 第 1—2 章课程入口，见 [PR #47](https://github.com/ruyisdk/board-docs/pull/47)。
	- ROS 2 课程接入：
		- 为 K3 Pico-ITX 新增课程入口及第一章课程元数据，关联 RISC-V 与 x86 版本的教案、实验手册和运行环境，见 [PR #44](https://github.com/ruyisdk/board-docs/pull/44)。
		- 将课程文档来源切换至 GitHub 镜像，完善课程介绍、教案和实验手册的链接，见 [PR #45](https://github.com/ruyisdk/board-docs/pull/45)。
		- 为 K3 Pico-ITX、CoM260 Kit 接入独立课程目录，并增加 CoM260 Kit 第 3—4 章的 RISC-V 与 x86 课程入口，见 [PR #48](https://github.com/ruyisdk/board-docs/pull/48)。
		- 更新 K3 Pico-ITX、CoM260 Kit 的课程元数据，改为引用课程仓库 `course_support` 目录下的板卡课程清单，见 [PR #49](https://github.com/ruyisdk/board-docs/pull/49)。
	- 仓库维护：统一板卡文档、元数据及中英文索引中的 SpaceMIT 厂商名称，见 [PR #43](https://github.com/ruyisdk/board-docs/pull/43)。
- board-docs-frontend：
	- 项目仓库：[DuoQilai/board-docs-frontend](https://github.com/DuoQilai/board-docs-frontend)
	- 在线站点：[中文入口](https://boards.ruyisdk.org/)；[英文入口](https://boards.ruyisdk.org/en/)
	- 新增 ROS 2 课程页面和中英文访问路由，按开发板、章节及 RISC-V／x86 版本组织教案与实验手册；支持远程文档、图片和视频同步，补充首页课程预览、更新提示及统一顶部导航，见 [PR #9](https://github.com/DuoQilai/board-docs-frontend/pull/9)。
	- 优化移动端课程目录和正文显示，调整表格、长链接及代码块在窄屏下的布局，见 [PR #10](https://github.com/DuoQilai/board-docs-frontend/pull/10)。
	- 增加课程上一章／下一章导航，修正当前课程及章节的目录定位，并在首页展示最新课程章节，见 [PR #11](https://github.com/DuoQilai/board-docs-frontend/pull/11)。
	- 从固定版本的课程子模块读取目录、正文和媒体，依据课程目录生成章节路由、导航和最新章节预览；同步失败时保留原有缓存与素材，见 [PR #12](https://github.com/DuoQilai/board-docs-frontend/pull/12)。
	- 同步更新 README 中的课程目录路径示例，与课程仓库的新目录结构保持一致，见 [PR #13](https://github.com/DuoQilai/board-docs-frontend/pull/13)。

##### 8.3.2 RISC-V Support Matrix

参与或审核

- 仓库：[ruyisdk/support-matrix](https://github.com/ruyisdk/support-matrix)
- 操作系统支持报告更新：
	- HiFive Premier P550：
		- 更新 Debian 中英文测试报告，补充镜像烧录、启动与串口登录记录，见 [PR #393](https://github.com/ruyisdk/support-matrix/pull/393)。
		- 新增 Fedora 44 Server 中英文测试报告，补充 Bootchain 更新、启动配置及串口登录验证，见 [PR #400](https://github.com/ruyisdk/support-matrix/pull/400)。
	- Milk-V Duo S：
		- 更新 Arch Linux 测试报告，补充新版镜像的安装步骤、启动日志和录屏，见 [PR #394](https://github.com/ruyisdk/support-matrix/pull/394)。
		- 更新 Debian 13 社区镜像 v1.9.6 测试报告，补充系统信息、串口登录结果及启动告警记录，见 [PR #395](https://github.com/ruyisdk/support-matrix/pull/395)。
		- 更新 RT-Thread、RT-Thread Smart 5.2.2 测试报告，完善源码编译、小核与 FIP 打包、启动日志和录屏，见 [PR #396](https://github.com/ruyisdk/support-matrix/pull/396)、[PR #397](https://github.com/ruyisdk/support-matrix/pull/397)。
		- 更新 Ubuntu 24.04 LTS 中英文测试报告，补充镜像安装、系统信息和启动验证，见 [PR #398](https://github.com/ruyisdk/support-matrix/pull/398)。
		- 更新 Zephyr 4.1.99 中英文测试报告，完善构建、固件打包、UART1 接线和 C906 小核 Hello World 运行记录，见 [PR #405](https://github.com/ruyisdk/support-matrix/pull/405)。
		- 更新 xv6 中英文测试报告，补齐镜像准备、启动文件重新打包、烧录及成功启动证据，见 [PR #407](https://github.com/ruyisdk/support-matrix/pull/407)。
	- SpaceMIT K3 CoM260 Kit：
		- 新增中英文板卡概述及 Buildroot 1.0.7 测试报告，记录 TITANTOOLS 烧录、串口登录和 Weston 桌面验证，见 [PR #399](https://github.com/ruyisdk/support-matrix/pull/399)。
		- 新增 Bianbu 4.0.6 LXQt 中英文测试报告，补充系统初始化、串口登录、系统信息和桌面截图，见 [PR #401](https://github.com/ruyisdk/support-matrix/pull/401)。
		- 新增 OpenHarmony 6.1 中英文测试报告，记录默认启动因缺少设备树失败的问题，以及临时使用另一设备树进入 shell 和桌面的验证过程，见 [PR #402](https://github.com/ruyisdk/support-matrix/pull/402)。
		- 整理 openEuler 24.03-LTS-SP4 中英文待测文档，覆盖镜像下载与校验、解压烧录、UART 接线及 SD 卡启动步骤，见 [PR #403](https://github.com/ruyisdk/support-matrix/pull/403)。
	- CH32V307：更新 RT-Thread 5.3.1 中英文测试报告，改用官方 BSP，补充 SDK 依赖、存储配置、串口命令及板载以太网 DHCP／ping 验证，见 [PR #404](https://github.com/ruyisdk/support-matrix/pull/404)。
	- CH32V003：新增基于官方 `ch32v003f4p6-evt` BSP 的 RT-Thread 中英文测试报告，补充 Windows 编译、WCH-LinkE 接线、烧录与 USART1 启动至 msh 的验证记录，实测范围限于串口控制台，见 [PR #408](https://github.com/ruyisdk/support-matrix/pull/408)。
	- ESP32-C3：新增 RT-Thread 5.3.1 中英文测试报告，记录编译、烧录、启动至 msh 及基础命令验证，并补充 Windows 链接脚本和芯片版本适配说明，见 [PR #406](https://github.com/ruyisdk/support-matrix/pull/406)。
- 支持矩阵网站：排查并恢复内容同步，核对 CoM260 Kit 四项系统、P550 Fedora 44 和 CH32V307 RT-Thread 5.3.1 的页面更新，见 [CoM260 Kit 页面](https://matrix.ruyisdk.org/zh-CN/boards/CoM260_Kit/)、[P550 页面](https://matrix.ruyisdk.org/boards/Premier_P550/)、[CH32V307 页面](https://matrix.ruyisdk.org/boards/CH32V307/)。

##### 8.3.3 RISC-V ROS 2 机器人操作系统编程课程

移植和验证RISC-V ROS 2 机器人操作系统编程课程

- 项目仓库：[ROS2_RISCV](https://gitee.com/yunxiangluo/ROS2_RISCV)；[GitHub 镜像](https://github.com/DuoQilai/ROS2_RISCV)
- K3 Pico-ITX 课程移植与验证：
	- 完成第一章独立 C++17 课程源码、教师教案及实验手册，验证环境安装、DDS 通信与域隔离、生命周期节点、IDE 远程调试及 K3 与 x86 Gazebo 联动；整理第 1—4 章的运行证据、截图和连续录像，见 [PR !2](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/2)。
	- 完成第 2—4 章独立源码、教案和实验手册，覆盖节点与命名空间、日志工具、话题与自定义消息、QoS、执行器和服务通信，补充板端运行及 Gazebo 运动、停止验证，见 [Commit 07c86bb](https://gitee.com/chuachuaa/ROS2_RISCV/commit/07c86bbc94aa6cbd3a514b86230de8d167e41d93)。
- CoM260 Kit 课程移植与验证：
	- 第 1—2 章：基于 Bianbu 4.0.6／ROS 2 Humble 建立板端与 x86 课程环境，完成独立文档和 C++17 示例，验证 DDS、生命周期、建包、命名空间、日志过滤、远程调试和仿真里程计反馈，见 [PR !3](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/3)。
	- 第 3—4 章：完成话题、自定义消息、QoS、执行器和服务通信的教案、实验及源码；验证从空目录建包、方形运动、速度服务、无时钟与中断退出行为，并补充连续录像和运行记录，见 [PR !4](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/4)。
	- 第 5—6 章：完成动作通信、参数与 Launch 的 C++17 示例、教案和实验手册，验证动作反馈与取消、目标拒绝、参数校验、动态调速、巡航配置及独立信号停止；完成与 x86 Gazebo 的运动和停车联调、Nav2 组合启动验证，补齐截图、CAST、MP4、GIF 和实测记录，见 [PR !5](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/5)。
- 课程目录与镜像维护：
	- 在课程仓库新增 K3 Pico-ITX 和 CoM260 Kit 的板卡课程目录，统一维护章节、教案、实验、编程语言及运行环境，见 [PR #1](https://github.com/DuoQilai/ROS2_RISCV/pull/1)。
	- 补充 `course_support` 目录下的板卡课程清单，保留 K3 Pico-ITX 第一章入口，并将 CoM260 Kit 的 RISC-V／x86 教案及实验入口补齐至第六章，见 [PR !5](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/5)。
	- 改进 Gitee 到 GitHub 的课程镜像同步，保留 GitHub 侧课程目录，并补充冲突、拉取失败及并发更新场景的验证，见 [PR #2](https://github.com/DuoQilai/ROS2_RISCV/pull/2)。

##### 8.3.4 RISC-V Linux 系统与开发板实践课程

审核

- 项目仓库：[DuoQilai/ruyi-riscv-linux-book](https://github.com/DuoQilai/ruyi-riscv-linux-book)
- 第五章“网络与 MQTT”：将实验细化为命令解析、虚拟灯命令环及真实 GPIO／MQTT 远程控灯三个递进环节，补充实机接线、命令与状态联调、非法命令拒绝及板端 tcpdump 抓包证据，见 [PR #8](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/8)。
- 第六章“线程与协同”：新增成对快照加锁练习，完善 race-demo、snapshot-lock 与 tri-thread 的递进实验；修正并发控制、MQTT 载荷匹配与连接／收发错误处理，补充线程创建和 GPIO 初始化失败检查；完善加锁重编命令、竞态复现、ThreadSanitizer、加锁对照及三线程协同的板端截图、录屏和实物动作录像，见 [PR #9](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/9)。
- 综合项目：补充 K3 端侧 Agent 与荔枝派的 MQTT 联调工具、部署说明和实物演示，提供状态查询、风扇及 LED 控制接口，整理 Qwen2.5-1.5B Q4_0 本地推理与云端模型调用的运行材料；完善阈值参数格式、上下限关系及板端状态读回校验，明确本轮温湿度为模拟数据、风扇及 LED 为真实 GPIO 控制，见 [PR #11](https://github.com/DuoQilai/ruyi-riscv-linux-book/pull/11)。

##### 8.3.5 RISC-V 编译工具链-开发板 测试

- 开发板测试素材：新增 EBC7702 的 2 张、SG2044 EVB 的 1 张测试环境照片，整理 VisionFive 2 Lite 与 K510 已有照片的命名和引用，并更新测试总表中的录制材料说明，见 [PR #5](https://github.com/DuoQilai/asciinema/pull/5)。

##### 8.3.6 会议

- 补充第 75 期支持矩阵和开发板文档进展，见 [PR #327](https://github.com/ruyisdk/wechat-articles/pull/327)。
- 补充第 76 期开发板系统测试、ROS 2 课程入口和移动端显示改进，见 [PR #342](https://github.com/ruyisdk/wechat-articles/pull/342)。
- 补充第 77 期系统测试报告、P550／CoM260 Kit 示例和课程导航进展，见 [PR #356](https://github.com/ruyisdk/wechat-articles/pull/356)。
