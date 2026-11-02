# RISC-V 软件生态进展 · 第 87 期·2026 年 10 月汇总

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

2026年10月，RuyiSDK测试团队围绕 RuyiCode VSCode 插件 与 RuyiSDK Imager 开展功能测试，完成 RuyiCode 0.4.10 版本测试报告，累计提交多项缺陷并给出改进建议，同时推进 ruyi-imager 的镜像源、下载策略、刷写策略与界面交互完善。RuyiSDK 示例库和课程方面，board-docs 新增 HiFive Premier P550 的 Dhrystone 与 SiFive SKL 示例、Milk-V Jupiter2 的 llama-server 部署文档，ROS2 RISC-V 课程完成 CoM260 Kit 第 7—10 章及 K3 Pico-ITX 第 2—4 章的移植与验证，RISC-V Linux 系统与开发板实践课程更新网络与 MQTT 章节材料；RuyiSDK 网站更新 Ruyi Imager 介绍、包页面厂商筛选与移动端布局。RuyiAI 方面，buddy-mlir 推进 `.rax` 版本注入、RISC-V 交叉编译简化、运行时依赖加载、Hugging Face 模型发布与 manylinux 构建修复，triton-riscv 适配新版 LLVM 符号与 inline-asm API。RISC-V 操作系统支持矩阵新增或更新 ESP32-C6、RDC2022-D1s、Milk-V Jupiter2、SpaceMIT K3 Pico-ITX、Milk-V Duo S、VisionFive 2 Lite 等板卡测试报告，并补充开发板测试素材。SAIL/ACT 持续向上游提交并审核社区代码，推进 Ztt 扩展与长指令支持，参加 Sail 会议及厂商合作开发会议。团队参加 2026 年 RISC-V 中国峰会，完成报告、海报展示与展台演示，测试团队共有 1 个报告和 4 个海报入选 2026 年 RISC-V 中国峰会。
。完成中国科学院科学节创工坊 RISC-V 展位的科普演示项目准备、布展和第一天活动，展示了12个项目，观众多、评价好，选入中央电视台13套新闻中国科学院科学节新闻。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- RuyiCode VSCode 插件测试：开展 2 轮测试，审核 2 个测试报告 PR
  - [docs：add ruyicode test report #1](https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test/pull/1)
  - [docs：add 0.4.10 test report #2](https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test/pull/2)

- RuyiSDK Imager 测试：针对功能、界面与刷写逻辑开展测试、问题排查与回归验证，提交并合并多个 PR
  - [ruyisdk/ruyi-imager#12](https://github.com/ruyisdk/ruyi-imager/pull/12)
  - [ruyisdk/ruyi-imager#13](https://github.com/ruyisdk/ruyi-imager/pull/13)
  - [ruyisdk/ruyi-imager#14](https://github.com/ruyisdk/ruyi-imager/pull/14)
  - [ruyisdk/ruyi-imager#19](https://github.com/ruyisdk/ruyi-imager/pull/19)
  - [ruyisdk/ruyi-imager#21](https://github.com/ruyisdk/ruyi-imager/pull/21)

- RuyiCode 0.4.10 测试缺陷（详见 [测试报告 #2](https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test/pull/2)）：

  | 缺陷      | 备注 |
  | ----------- | --- |
  | 对话生成过程中切换视图后历史记录丢失，且后续消息发送被锁死 |  |
  | AI 流式生成过程中滚动条被强制拉回底部，无法回看历史内容 |  |
  | Markdown 有序列表序号全部显示为 1，嵌套列表层级丢失 |  |
  | Markdown 代码块解析异常，导致回答正文大面积被误判为代码 |  |
  | 多种编程语言的函数声明无法通过命令面板识别，生成注释入口行为不一致 |  |
  | CodeLens 将注释中的函数声明误识别为真实函数并显示操作入口 |  |

  回归测试通过项：引擎连接状态及状态栏交互正常；AI 对话支持流式输出；取消生成后已输出的回答内容能够保留；内联代码补全功能正常，关闭配置后不再触发。

- RuyiCode 0.4.10 测试材料：
  - [RuyiCode 0.4.10 测试材料（备份压缩）](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Others/0.4.10RuyiCode%E6%B5%8B%E8%AF%95.zip)
  - [RuYiCode 插件测试](https://github.com/ZihanCheng63/PLCT/tree/main/Ruyi/RuYiCode/RuYiCode%E6%8F%92%E4%BB%B6%E6%B5%8B%E8%AF%95)

- RuyiSDK Imager 新增缺陷：

  | 缺陷      | 问题等级 | 备注 |
  | ----------- | ----------- | --- |
  | [中文 Windows 下 CLI 的帮助信息显示乱码 #6](https://github.com/ruyisdk/ruyi-imager/issues/6) | 一般 |  |
  | [子命令不支持 -h/--help，且只打印帮助时退出码为 0 #7](https://github.com/ruyisdk/ruyi-imager/issues/7) | 一般 |  |
  | [镜像同时支持多块板卡时，只在第一块板下显示（MusePi Pro 少了 6 个 Bianbu 镜像）#8](https://github.com/ruyisdk/ruyi-imager/issues/8) | 一般 |  |
  | [Lichee RV（sipeed-licheerv）在界面中完全不可见，镜像只归到 related 的第一块板 #9](https://github.com/ruyisdk/ruyi-imager/issues/9) | 一般 |  |
  | [支持 spacemit-k3-v1 刷写策略 #10](https://github.com/ruyisdk/ruyi-imager/issues/10) | 严重 |  |
  | [GUI 没有“仅下载”入口，慢速网络下必须全程连接设备 #11](https://github.com/ruyisdk/ruyi-imager/issues/11) | 一般 |  |
  | [自定义镜像源的支持 #15](https://github.com/ruyisdk/ruyi-imager/issues/15) | 建议 |  |
  | [自定义下载策略的支持 #16](https://github.com/ruyisdk/ruyi-imager/issues/16) | 建议 |  |
  | [镜像载入速度慢 #17](https://github.com/ruyisdk/ruyi-imager/issues/17) | 一般 |  |
  | [界面和刷写逻辑设计问题 #18](https://github.com/ruyisdk/ruyi-imager/issues/18) | 建议 |  |
  | [搜索无匹配时列表空白，但选择按钮仍可点击，点击后落到默认第一项 #20](https://github.com/ruyisdk/ruyi-imager/issues/20) | 建议 |  |

- RuyiSDK Imager 回归测试缺陷：

  | 缺陷      | 问题等级 | 备注 |
  | ----------- | ----------- | --- |
  | [更新元数据失败 #2](https://github.com/ruyisdk/ruyi-imager/issues/2) | 一般 |  |
  | [窗口相关文字位置偏下 #3](https://github.com/ruyisdk/ruyi-imager/issues/3) | 建议 |  |
  | [设置界面取消和保存按钮不可以 #5](https://github.com/ruyisdk/ruyi-imager/issues/5) | 一般 |  |

#### 1.2 RuyiSDK开发和测试开发

- [ruyi](https://github.com/ruyisdk/ruyi)
RuyiSDK包管理器
	- [docs: update vendor naming list #508](https://github.com/ruyisdk/ruyi/pull/508)

- [ruyisdk/ruyi-imager](https://github.com/ruyisdk/ruyi-imager)
RuyiSDK 镜像下载与烧录工具，提供命令行与图形界面操作。
	- [ruyisdk/ruyi-imager#12](https://github.com/ruyisdk/ruyi-imager/pull/12)
	- [ruyisdk/ruyi-imager#13](https://github.com/ruyisdk/ruyi-imager/pull/13)
	- [ruyisdk/ruyi-imager#14](https://github.com/ruyisdk/ruyi-imager/pull/14)
	- [ruyisdk/ruyi-imager#19](https://github.com/ruyisdk/ruyi-imager/pull/19)
	- [ruyisdk/ruyi-imager#21](https://github.com/ruyisdk/ruyi-imager/pull/21)

- [ruyisdk/packages-index](https://github.com/ruyisdk/packages-index)
packages-index 是 RuyiSDK 的包元数据仓库，为 ruyi 客户端提供包索引和同步数据源。
	- [board-image/ubuntu-server-riscv64-sifive-unmatched: fix ubuntu releases download links #226](https://github.com/ruyisdk/packages-index/pull/226)
	- [ci: keep telemetry upload from failing the workflow #228](https://github.com/ruyisdk/packages-index/pull/228)
	- [board-image/revyos-milkv-meles: bump image and related uboot to version 20260504 #230](https://github.com/ruyisdk/packages-index/pull/230)
	- [board-images/openwrt-sifive-unmatched: bump version to 25.12.6 #231](https://github.com/ruyisdk/packages-index/pull/231)
	- 提交 [ruyisdk/packages-index #229](https://github.com/ruyisdk/packages-index/pull/229)，为 A210 板卡增加 OpenRuyi RVA20 镜像与 `a210-coreboot-v1` 刷写策略（bootstrap / coreboot-ram / emmc0boot0 三段 fastboot）。

- [ruyisdk-test/ruyisdk-codeai-extension-test](https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test)
RuyiCode 插件测试用例与测试报告仓库。
	- [docs：add ruyicode test report #1](https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test/pull/1)
	- [docs：add 0.4.10 test report #2](https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test/pull/2)

- [ruyisdk-test/oh-my-ruyi](https://github.com/ruyisdk-test/oh-my-ruyi)
图形化管理工具，为 ruyi 包管理器的 GUI 前端，提供了版本管理、仓库管理、设备烧录等核心功能的可视化操作界面。
	- fix: keep provisioning usable with cached metadata [eade45e](https://github.com/ruyisdk-test/oh-my-ruyi/commit/eade45e97de75e1be5a133c8d44e70987494499c)

- [ruyisdk-test/ruyi-index-resolve-bot](https://github.com/ruyisdk-test/ruyi-index-resolve-bot)
	- [dc48bed...605c7d8](https://github.com/ruyisdk-test/ruyi-index-resolve-bot/compare/dc48bed7c2245fc6beaca8b0d5745a2d1116a198...605c7d8c9b63689f571b91031f656296016495ca) 10 个 commit，2,282 additions and 15 deletions

#### 1.3 RuyiSDK开发示例库和示例库网站开发

- Ruyi 示例文档库：
	- 仓库：[ruyisdk/board-docs](https://github.com/ruyisdk/board-docs)
	- 开发板示例文档扩充：
		- HiFive Premier P550：新增 Dhrystone 2.1 中文示例，覆盖 Fedora 44 下 RuyiGCC 编译、Linux 兼容调整、一亿次迭代运行及结果校验，见 [PR #51](https://github.com/ruyisdk/board-docs/pull/51)。
		- HiFive Premier P550：新增 SiFive SKL 中文示例，使用 RuyiGCC 编译 FP32 标量参考算子，验证矩阵乘法、Softmax 及大数值输入的计算结果，见 [PR #52](https://github.com/ruyisdk/board-docs/pull/52)。
		- Milk-V Jupiter2：新增 llama-server 中文部署文档，补充 RuyiSDK 编译环境、模型下载、服务启动、健康检查、模型列表和对话 API 调用步骤，见 [PR #55](https://github.com/ruyisdk/board-docs/pull/55)。
	- 课程入口整理：删除 K3 Pico-ITX 板卡介绍中重复的课程标题及第一章链接，由网站课程标签页统一提供章节入口，见 [PR #53](https://github.com/ruyisdk/board-docs/pull/53)。
	- 文档维护：
		- 更新示例文档中的 Ruyi 0.52.0 下载链接及安装命令，见 [PR #50](https://github.com/ruyisdk/board-docs/pull/50)。
		- 清理 83 份 Markdown 文档中的不换行空格、零宽空格及格式问题，修正复制命令时的参数分隔，同时保留元数据、代码块排版和 Markdown 换行语义，见 [PR #54](https://github.com/ruyisdk/board-docs/pull/54)。

- board-docs-frontend：
	- 项目仓库：[DuoQilai/board-docs-frontend](https://github.com/DuoQilai/board-docs-frontend)
	- 在线站点：[中文入口](https://boards.ruyisdk.org/)；[英文入口](https://boards.ruyisdk.org/en/)
	- 完善 CoM260 Kit 课程的章节展示范围，增加第 11—12 章的课程目录、章节导航及页面入口，并补充第 10—15 章共用 SLAM 实验手册的中英文说明，见 [PR #14](https://github.com/DuoQilai/board-docs-frontend/pull/14)。
	- 接入 K3 Pico-ITX 第 2—4 章 RISC-V C-- 与 x86 版本的教案、实验页面，同步整理板卡页面中的课程入口，见 [PR #15](https://github.com/DuoQilai/board-docs-frontend/pull/15)。
	- 将 CoM260 Kit 课程展示范围扩展至第 15 章，补充 gmapping、AMCL 定位和 Cartographer 三章入口，同步首页进度、中英文课程目录及章节导航，见 [PR #16](https://github.com/DuoQilai/board-docs-frontend/pull/16)。

- RISC-V ROS 2 机器人操作系统编程课程
	- 项目仓库：[ROS2_RISCV](https://gitee.com/yunxiangluo/ROS2_RISCV)；[GitHub 镜像](https://github.com/DuoQilai/ROS2_RISCV)
	- CoM260 Kit 课程移植与验证：
		- 第 7—8 章：完成 TF2 坐标变换、URDF／Xacro 机器人建模的独立教案、实验手册与配套代码；验证双端构建、动态／静态变换、历史查询、异常超时、跨机 TF 查询及模型关节操作，补充 RViz、Gazebo 连续录像和实测记录，见 [PR !6](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/6)。
		- 第 9—10 章：完成 Gazebo、ros2_control 与 SLAM 综合实验，验证板端读取仿真传感器、直行／旋转及超时停止，补充 slam_toolbox 建图、地图保存、AMCL 定位、Cartographer 二维建图导出和 rosbag 半速回放记录；配套整理第 10—15 章的 C--17 教案与共用 SLAM 实验手册，见 [PR !7](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/7)。
	- K3 Pico-ITX 课程整合：整理第 1—4 章教案、实验及运行证据入口，并在课程清单中补齐第 2—4 章的 RISC-V C-- 与 x86 版本链接，见 [PR !8](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/8)、[PR #4](https://github.com/DuoQilai/ROS2_RISCV/pull/4)。

- RISC-V Linux 系统与开发板实践课程
	- 项目仓库：[DuoQilai/ruyi-riscv-linux-book](https://github.com/DuoQilai/ruyi-riscv-linux-book)
	- 修复第五章 MQTT 实验终端截图的断行与展示尺寸，更新控灯状态及 tcpdump 抓包图片，见 [Commit dfb8abe](https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/dfb8abe6ae7e90c261b2e780c8fcf470e3f28b37)。

#### 1.4 RISC-V 操作系统支持矩阵

- [ESP32-C6 RT-Thread 测试报告：ruyisdk/support-matrix#409](https://github.com/ruyisdk/support-matrix/pull/409)
- [RDC2022-D1s RT-Thread Smart 5.0.0 测试报告：ruyisdk/support-matrix#410](https://github.com/ruyisdk/support-matrix/pull/410)
- [Milk-V Jupiter2 Bianbu 4.0.1 测试报告：ruyisdk/support-matrix#411](https://github.com/ruyisdk/support-matrix/pull/411)
- [SpaceMIT K3 Pico-ITX Bianbu 4.0.8 测试报告：ruyisdk/support-matrix#412](https://github.com/ruyisdk/support-matrix/pull/412)
- [VisionFive 2 Lite Ubuntu 24.04.5 测试报告：ruyisdk/support-matrix#390](https://github.com/ruyisdk/support-matrix/pull/390)

#### 1.5 RuyiSDK网站

- [docs(Ruyi Imager): update ruyi-imager links #152](https://github.com/ruyisdk/docs/pull/152)
- [docs(Ruyi Imager): update ruyi imager Chinese name #153](https://github.com/ruyisdk/docs/pull/153)
- [docs(Ruyi Imager): Add information about Ruyi Imager #589](https://github.com/ruyisdk/ruyisdk-website/pull/589)
- [pages(packages): align page width with other pages #603](https://github.com/ruyisdk/ruyisdk-website/pull/603)
- [pages(packages): smooth card shadow edge #604](https://github.com/ruyisdk/ruyisdk-website/pull/604)
- [api(packages): add vendor name data #605](https://github.com/ruyisdk/ruyisdk-website/pull/605)
- [pages(packages): filter devices by board vendor #606](https://github.com/ruyisdk/ruyisdk-website/pull/606)
- [pages(packages): add vendor fallback handling #607](https://github.com/ruyisdk/ruyisdk-website/pull/607)
- [pages(packages): improve mobile card layout #608](https://github.com/ruyisdk/ruyisdk-website/pull/608)
- [pages(packages): unify filter scrolling #609](https://github.com/ruyisdk/ruyisdk-website/pull/609)

#### 1.6 RuyiSDK双周报

- 补充第 78 期支持矩阵及 CoM260 Kit ROS 2 课程进展，见 [PR #370](https://github.com/ruyisdk/wechat-articles/pull/370)。
- 补充第 79 期 RDC2022-D1s 测试报告、CoM260 Kit Gazebo／SLAM 课程及前端展示进展，见 [PR #382](https://github.com/ruyisdk/wechat-articles/pull/382)。

### 2. RuyiAI

- buddy-compiler/buddy-mlir
	- `[codegen] Inject the release version into .rax manifests` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/976
		- 通过新增的 `--version` 把 `BUDDY_PACKAGE_VERSION` 传给各 manifest 生成器（generic、Tenstorrent、bge_m3、proteinglm、whisper、qwen3_vl），保证打包出的 `.rax` 版本与 CLI 一致

	- `[build] Simplify RISC-V cross compilation` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/975
		- Makefile 分三档目标：`make host`、`make riscv`、`make riscv-model-<family>-<variant>`；Python 包进默认 target，README 补充完整流程

	- `[buddy-cli] Load RAX runtime dependencies before the model` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/977
		- manifest 声明的 `runtime_dep_*` 共享库用 `RTLD_GLOBAL` 保持加载、通过 `$ORIGIN` 解析；buddy-cli 不再静态链接 LLVM
		- 新增 `test-cli.yml`，在 x86/riscv64 上跑 bge_m3 与 deepseek_r1 f16 验证加载链路

	- `ci: run bge_m3 with buddy-cli on x86 and riscv64` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/983
		- x86 交叉编译 bge_m3、校验每个 staged library 均为 RISC-V ELF 并上传 `.rax`；riscv64 job 原生构建后加载 x86 交叉产物；断言 embedding shape 与 L2 norm

	- `[ci] Check cross-compile` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/937
		- 原「简化交叉编译」PR 拆分为纯 CI 验证：x86 交叉编译 deepseek_r1 w4a16、校验 ELF、上传 `.rax`，riscv64 用原生 buddy-cli 实跑
		- 确认 `RISCV_ZFH_ZVFH=ON` 必须开启，否则 w4 反量化的 f16 数学会被标量化导致推理过慢

	- `[ci] Fix the manylinux release build` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/990
		- 修复 nightly manylinux 双架构失败：x64 容器改为 `--network host`；riscv64 侧 `release.sh` 补齐 Ruyi index；补装 `libsndfile-devel` 解决 `soundfile` 无 riscv64 wheel 的问题

	- `[models] Use jsoncons in the BGE-M3 tokenizer` ⛔ 关闭 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/938
		- 换掉 `llvm::json` 是为绕开交叉编译插件未链接 LLVMSupport 的链接错误；#954 已从插件构建侧解决，故关闭作废

	- `[CI][Models] Publish to huggingface` ✅ 合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/925
		- 新增 publish-models workflow：为 `models/publish.json` 中启用的 spec 交叉编译 riscv64 `.rax`，按模型家族推送到对应 Hugging Face 仓库并用 CLI 版本打 tag

	- `[CI] Add YOLO26 example test` 🔍 评审并合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/808
		- 把 examples 测试纳入默认 CI，新增 BuddyYOLO26 示例与 ctest；修复 importer 与 Python 包的构建依赖、Gemma4 importer 失配、YOLO26 仅 x86/arm 可跑
		- 补充多个提交：示例 job 精简触发与状态步骤、riscv64 只跑 qwen3、DeepSeekR1 W4A16 runner 增加 CLI11 参数、修正 decode 结果布局、ci-common 统一开启 PNG

	- `[examples] Validate Whisper output and enable its x64 CI test` 🔍 评审并合并 🔗 https://github.com/buddy-compiler/buddy-mlir/pull/1012
		- Whisper 示例改为 `check-output.py` 校验退出码、唯一 `[Output]` 与 EOT，并在 x64 示例脚本中构建 `buddy-whisper-run`

- RuyiAI-Stack/triton-riscv
	- `[patches] Support newer LLVM symbol and inline-asm APIs` ✅ 合并 🔗 https://github.com/RuyiAI-Stack/triton-riscv/pull/86
		- 跟进 LLVM 破坏性改动：SymbolOpInterface 不再从 trait 提供符号访问器，`llvm.inline_asm` 新增 `convergent` 属性
		- 新增兼容补丁，在 `triton::FuncOp` 上直接定义符号访问器并编译期探测 inline_asm builder 签名，兼容新旧工具链

- 其他：
	- ruyisdk/sail-riscv、ruyisdk/riscv-isa-sim 新建 [`ztt` 分支](https://github.com/ruyisdk/sail-riscv/tree/ztt) 推进 Ztt 扩展：sail 侧完成 bf16 融合舍入、float logexp 语义、generator cases 与文档英文化、AME 配置统一；isa-sim 侧实现 Ztt、RV32 零扩展测试及 AME/Ztt 存储原子性等修正，见 [ruyisdk/riscv-isa-sim `ztt` 分支](https://github.com/ruyisdk/riscv-isa-sim/tree/ztt)
	- 提交 [ruyisdk/packages-index #229](https://github.com/ruyisdk/packages-index/pull/229)，为 A210 板卡增加 OpenRuyi RVA20 镜像与 `a210-coreboot-v1` 刷写策略
	- 指导新人接入 Whisper 示例 CI，见 [buddy-mlir #757](https://github.com/buddy-compiler/buddy-mlir/pull/757)，给出 x86 测试与 rax 打包、交叉编译、板端验证的三步口径

- 其他重要产出（无公开链接，单列）：
	- 反馈 ruyirepo 安装包偶发 404 问题，定位为前置代理规则异常。

### 3. RISC-V 操作系统支持矩阵

## RuyiSDK Support Matrix

- ESP32-C6：新增基于官方 BSP 的 RT-Thread 中英文测试报告，固定源码与 ESP-IDF 依赖版本，整理编译烧录、串口 shell、GPIO 和 ADC 的测试结果，并记录 SPI 回环异常及无线功能的限制，见 [PR #409](https://github.com/ruyisdk/support-matrix/pull/409)。
- RDC2022-D1s：新增板卡资料及 RT-Thread Smart 5.0.0 出厂固件中英文测试报告，补充 SD NAND 分块烧写、回读校验及串口交互记录，并记录自编 5.3.1 固件无串口输出的问题，见 [PR #410](https://github.com/ruyisdk/support-matrix/pull/410)。
- Milk-V Jupiter2：新增板卡信息及 Bianbu 4.0.1 中英文测试报告，记录出厂预装系统的首次设置、图形登录和桌面启动，补充录屏及桌面截图，见 [PR #411](https://github.com/ruyisdk/support-matrix/pull/411)。
- SpaceMIT K3 Pico-ITX：新增中英文板卡概述及 Bianbu 4.0.8 测试报告，补充 Type-C 烧录说明、串口及图形登录记录、系统信息和 LXQt 桌面截图，见 [PR #412](https://github.com/ruyisdk/support-matrix/pull/412)。
- Milk-V Duo S：
	- 完善 RT-Thread Smart 的 ELF 工具链、小核配置与自动打包步骤，修正产物路径，更新启动记录和录屏引用，见 [PR #397](https://github.com/ruyisdk/support-matrix/pull/397)。
	- 完善 Zephyr 报告中的工具链下载、U-Boot 板级配置同步及构建检查，固定 Zephyr 实测源码版本，见 [PR #405](https://github.com/ruyisdk/support-matrix/pull/405)。
- VisionFive 2 Lite：将 Ubuntu 中英文报告更新至 24.04.5，调整镜像来源和安装说明，更新串口登录、内核及 CPU 信息，见 [PR #390](https://github.com/ruyisdk/support-matrix/pull/390)。

### 4. RISC-V 开发板编译工具链测试

- 开发板测试素材：补充 K3 Pico-ITX 的 2 张测试环境照片，并完善测试总表中 EBC7700 已有照片的入口，见 [PR #8](https://github.com/DuoQilai/asciinema/pull/8)、[PR #6](https://github.com/DuoQilai/asciinema/pull/6)。

### 5. SAIL和ACT

#### 5.1 SAIL和ACT开发

- [`Add configurable behavior for reserved static rounding modes` #1987](https://github.com/riscv/sail-riscv/pull/1987)：审核社区提交，确认保留编码（reserved static rm）的行为应通过 platform config 暴露，并对配置项与实现位置给出意见。
- [Add support for local counter-overflow interrupts #1122](https://github.com/riscv/sail-riscv/pull/1122)：对应功能已由 #1520 实现，10/08 关闭，避免长期挂起。
- [sail-riscv#2051](https://github.com/riscv/sail-riscv/pull/2051)：提交，修复 Sail 在 VS-Mode 下写入 CSR（H 扩展虚拟模式专用 CSR）的日志显示问题。
- [sail-riscv#1990](https://github.com/riscv/sail-riscv/pull/1990)：合并，修复 Sail 在 V 扩展单点存储／加载时只计算当前块合法性而忽略整体合法性的问题。
- [sail-riscv commit 01ca6a](https://github.com/riscv/sail-riscv/pull/1924/changes/01ca6aafabe40e649a25f8ebab36da50ad48b13f)、[sail-riscv commit 0be1233](https://github.com/KotorinMinami/sail-riscv/commit/0be1233c86e2c3531d9120d610c82ae5ca855a3f)

其他重要产出（无公开链接，单列）：

- 软件所与某企业扩展合作项目，产出占本月 Sail 产出重要比例，不公开。
- riscv-long-instruction 在 Sail 下的实现方案调研与初版长指令支持（支持 `L.lui` 等更长立即数指令），不公开。
- 审核社区提交代码。

#### 5.2 SAIL会议

- 厂商合作开发工作会议（包括 SAIL 部分）：进行 spike、sail、qemu 综合测试并比对 spec，重构代码风格（共修改 87 文件，增添 6372 行，删去 3376 行），不公开。
- 参加 Sail 黄金模型开发社区周会。

### 6. 2026年RISC-V 中国峰会

测试团队参加 2026 年 RISC-V 中国峰会，完成报告、海报展示与展台演示：

- 海报展示：展示入选海报《从碎片化到体系化：RISC-V 课程质量评估与系统化重构》，介绍课程筛选、质量评估、标签化重构及远程硬件实践方法，见 [峰会报道](https://ruyisdk.cn/t/topic/2893)。
- 报告材料：协作完成《RISC-V 课程移植方法与 RuyiSDK 生态建设》报告材料及配套海报，介绍双端协同、分阶段移植验证，以及开发示例和支持矩阵在课程建设中的应用，支撑嵌入式、物联网与智能硬件分论坛的专题分享，见 [大会议程](https://riscv-summit-china.org/agenda/)。
- 展台演示：在 RuyiSDK 展台展示 RISC-V ROS 2 机器人开发课堂，使用 CoM260 Kit 运行控制节点，配合 Ubuntu 上的 Gazebo、RViz 和 Nav2，演示仿真机器人的方形运动与八点巡回；完成网线直连、一键启停、复位重跑及现场操作讲解稿准备，见 [展台报道](https://ruyisdk.cn/t/topic/2893)。
- 演示复现包：整理源码、固定运行镜像、地图模型、依赖安装脚本、直连配置及验收记录，形成联网准备版交付包；在两端独立目录验证源码构建、跨机通信、方形运动、整圈巡回、停车与复位重跑，见 [rvsc.md](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month40/rvsc.md)。
- 展台展品介绍与海报展示记录见 [rvsc.md](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month40/rvsc.md)。

### 7. RVI CSC 中国客户调查

- 本月协助RVI和进迭时空，完成了进迭时空的RISC-V 认证问卷调查。

### 8. 科普与演示

- [中国科学院科学节日，创工坊B区 RISC-V 展位(小架构、大神通)](https://content-static.cctvnews.cctv.com/snow-book/video.html?item_id=5982553481273996242&t=1793486314849&toc_style_id=video_default&track_id=A6FEAC69-1757-488E-96BD-EDAB5C814222_815186749994&share_to=wechat)，项目包括
1. 认识 RuyiSDK和RuyiAI
2. RISC-V 知识问答（大模型，思维和语音模拟）
3. RuyiSDK RISC-V 手势识别 
4. RuyiSDK RISC-V 机器人开发课堂
5. RuyiSDK RISC-V OpenCV RVV 加速
6. RuyiSDK RISC-V 应用开发课堂
7. RISC-V ROS 移动机器人小车
8. RuyiAI 系统软件栈 AI 推理
9. RuyiAI与RISC-V机器狗（人体姿态命令识别）
10. RISC-V 无人机（静态展示）
11. 如意BOOK
12. 如意PAD

### 9. 职工

#### 9.1 蔡玮霖

- 针对 RuyiCode VSCode 插件开展 2 轮测试， ruyisdk-test/ruyisdk-codeai-extension-test 仓库审核 2 个测试报告 pr
    - [docs：add ruyicode test report #1](https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test/pull/1)
    - [docs：add 0.4.10 test report #2](https://github.com/ruyisdk-test/ruyisdk-codeai-extension-test/pull/2)
- 针对 ruyi-imager 开展测试， ruyi-imager 仓库提交  个 issue
    - [自定义镜像源的支持 #15](https://github.com/ruyisdk/ruyi-imager/issues/15)
    - [自定义下载策略的支持 #16](https://github.com/ruyisdk/ruyi-imager/issues/16)
    - [镜像载入速度慢 #17](https://github.com/ruyisdk/ruyi-imager/issues/17)
    - [界面和刷写逻辑设计问题 #18](https://github.com/ruyisdk/ruyi-imager/issues/18)
- ruyi 仓库提交 1 个 pr
    - [docs: update vendor naming list #508](https://github.com/ruyisdk/ruyi/pull/508)
- docs 仓库提交 2 个 pr
    - [docs(Ruyi Imager): update ruyi-imager links 152](https://github.com/ruyisdk/docs/pull/152)
    - [docs(Ruyi Imager): update ruyi imager Chinese name #153](https://github.com/ruyisdk/docs/pull/153)
- ruyisdk-website 仓库合作 1 个 pr
    - [docs(Ruyi Imager): Add information about Ruyi Imager #589](https://github.com/ruyisdk/ruyisdk-website/pull/589)
- ruyisdk-website 仓库提交 7 个 pr
    - [pages(packages): align page width with other pages #603](https://github.com/ruyisdk/ruyisdk-website/pull/603)
    - [pages(packages): smooth card shadow edge #604](https://github.com/ruyisdk/ruyisdk-website/pull/604)
    - [api(packages): add vendor name data #605](https://github.com/ruyisdk/ruyisdk-website/pull/605)
    - [pages(packages): filter devices by board vendor #606](https://github.com/ruyisdk/ruyisdk-website/pull/606)
    - [pages(packages): add vendor fallback handling #607](https://github.com/ruyisdk/ruyisdk-website/pull/607)
    - [pages(packages): improve mobile card layout #608](https://github.com/ruyisdk/ruyisdk-website/pull/608)
    - [pages(packages): unify filter scrolling #609](https://github.com/ruyisdk/ruyisdk-website/pull/609)
- packages-index 仓库提交 4 个 pr
    - [board-image/ubuntu-server-riscv64-sifive-unmatched: fix ubuntu releases download links #226](https://github.com/ruyisdk/packages-index/pull/226)
    - [ci: keep telemetry upload from failing the workflow #228](https://github.com/ruyisdk/packages-index/pull/228)
    - [board-image/revyos-milkv-meles: bump image and related uboot to version 20260504 #230](https://github.com/ruyisdk/packages-index/pull/230)
    - [board-images/openwrt-sifive-unmatched: bump version to 25.12.6 #231](https://github.com/ruyisdk/packages-index/pull/231)
- ruyisdk-test/oh-my-ruyi 仓库提交 1 个 commit
    - fix: keep provisioning usable with cached metadata [eade45e](https://github.com/ruyisdk-test/oh-my-ruyi/commit/eade45e97de75e1be5a133c8d44e70987494499c)
- ruyisdk-test/ruyi-index-resolve-bot 仓库提交 10 个 commit
    - [dc48bed...605c7d8](https://github.com/ruyisdk-test/ruyi-index-resolve-bot/compare/dc48bed7c2245fc6beaca8b0d5745a2d1116a198...605c7d8c9b63689f571b91031f656296016495ca) 2,282 additions and 15 deletions
- 参加 RVSC 2026 并做展台展品介绍和海报展示 [rvsc.md](https://github.com/ruyisdk-test/test-working/blob/main/weilinfox/Month40/rvsc.md)

#### 9.2 阎明铸

##### 9.2.1 Sail

- 厂商合作开发工作(产出不公开,量大)
- PR #1987 — `Add configurable behavior for reserved static rounding modes` 🔍 review
🔗 https://github.com/riscv/sail-riscv/pull/1987
- 审核社区提交，确认保留编码（reserved static rm）的行为应通过 platform config 暴露，并对配置项与实现位置给出意见

- PR #1122 — `Add support for local counter-overflow interrupts` ⛔ 关闭
🔗 https://github.com/riscv/sail-riscv/pull/1122
- 2025 年提交的 LCOFI 支持，经 maintainer 确认对应功能已由 #1520 实现，10/08 关闭，避免长期挂起

##### 9.2.2 Ruyi AI

- buddy-compiler/buddy-mlir

	**PR #976** — `[codegen] Inject the release version into .rax manifests` ✅ 合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/976
	- 通过新增的 `--version` 把 `BUDDY_PACKAGE_VERSION` 传给各 manifest 生成器（generic、Tenstorrent、bge_m3、proteinglm、whisper、qwen3_vl），保证打包出的 `.rax` 版本与 CLI 一致

	**PR #975** — `[build] Simplify RISC-V cross compilation` ✅ 合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/975
	- Makefile 分三档目标：`make host` 构建 host LLVM/Buddy，`make riscv` 构建 RISC-V GNU 工具链 + 交叉 MLIR/OpenMP runtime，`make riscv-model-<family>-<variant>` 按 spec 生成 riscv64 `.rax`；Python 包进默认 target，README 补充完整流程

	**PR #977** — `[buddy-cli] Load RAX runtime dependencies before the model` ✅ 合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/977
	- manifest 声明的 `runtime_dep_*` 共享库在 runner 与 model 存活期间用 `RTLD_GLOBAL` 保持加载，通过 `$ORIGIN` 解析；buddy-cli 不再静态链接 LLVM
	- 原生构建同样打包运行时库；新增 `test-cli.yml`，在 x86/riscv64 上跑 bge_m3 与 deepseek_r1 f16 验证加载链路

	**PR #983** — `ci: run bge_m3 with buddy-cli on x86 and riscv64` ✅ 合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/983
	- x86 上交叉编译 bge_m3、校验每个 staged library 均为 RISC-V ELF 并上传 `.rax`；riscv64 job 原生构建后加载 x86 交叉产物，等价于板端加载 riscv64 插件
	- 断言 embedding shape 与 L2 norm，而非只看退出码

	**PR #937** — `[ci] Check cross-compile` ✅ 合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/937
	- 原「简化交叉编译」PR 拆分后收窄为纯 CI 验证：x86 交叉编译 deepseek_r1 w4a16、校验 ELF、上传 `.rax`，riscv64 用原生 buddy-cli 实跑
	- 确认 `RISCV_ZFH_ZVFH=ON` 必须开启，否则 w4 反量化的 f16 数学会被标量化（`fadd.s` 112k vs 462），推理无法在合理时间内出 token

	**PR #990** — `[ci] Fix the manylinux release build` ✅ 合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/990
	- 修复 nightly manylinux 双架构失败：x64 runner 所在节点的 raw 表关闭 UDP conntrack 导致容器内 `dnf` 解析失败，改 `--network host`；riscv64 侧 `release.sh` 补齐 Ruyi index；补装 `libsndfile-devel` 解决 `soundfile` 无 riscv64 wheel 的问题

	**PR #938** — `[models] Use jsoncons in the BGE-M3 tokenizer` ⛔ 关闭
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/938
	- 换掉 `llvm::json` 是为绕开交叉编译插件未链接 LLVMSupport 的链接错误；#954 已从插件构建侧解决，故关闭作废

	**PR #925** — `[CI][Models] Publish to huggingface` ✅ 合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/925
	- 新增 publish-models workflow：为 `models/publish.json` 中启用的 spec 交叉编译 riscv64 `.rax`，按模型家族推送到对应 Hugging Face 仓库并用 CLI 版本打 tag

	**PR #808** — `[CI] Add YOLO26 example test` 🔍 评审并合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/808
	- 把 examples 测试纳入默认 CI，新增 BuddyYOLO26 示例与 ctest；修复 importer 与 Python 包的构建依赖、Gemma4 importer 失配、YOLO26 仅 x86/arm 可跑（riscv64 无 torchvision wheel）
	- 本人补 7 个提交：example job 去掉冗余触发与状态步骤、riscv64 只跑 qwen3、DeepSeekR1 W4A16 runner 增加 CLI11 参数、修正 decode 结果布局（dummy memref 交错导致段错误）、ci-common 统一开启 PNG

	**PR #1012** — `[examples] Validate Whisper output and enable its x64 CI test` 🔍 评审并合并
	🔗 https://github.com/buddy-compiler/buddy-mlir/pull/1012
	- Whisper 示例 CTest 原断言输出含 `www`，正确转写反而失败；改为 `check-output.py` 校验退出码、唯一 `[Output]` 与 EOT，并在 x64 示例脚本中构建 `buddy-whisper-run`

- RuyiAI-Stack/triton-riscv

	**PR #86** — `[patches] Support newer LLVM symbol and inline-asm APIs` ✅ 合并
	🔗 https://github.com/RuyiAI-Stack/triton-riscv/pull/86
	- 跟进 LLVM 破坏性改动：SymbolOpInterface 不再从 trait 提供符号访问器，`llvm.inline_asm` 新增 `convergent` 属性
	- 新增兼容补丁，在 `triton::FuncOp` 上直接定义符号访问器并编译期探测 inline_asm builder 签名，兼容新旧工具链；升级 PR 随后顺利合入

##### 9.2.3 其他

- ruyisdk/sail-riscv、ruyisdk/riscv-isa-sim 新建 `ztt` 分支推进 Ztt 扩展：sail 侧完成 bf16 融合舍入、float logexp 语义、generator cases 与文档英文化、AME 配置统一；isa-sim 侧实现 Ztt、RV32 零扩展测试及 AME/Ztt 存储原子性等一批修正
- 提交 ruyisdk/packages-index #229，为 A210 板卡增加 OpenRuyi RVA20 镜像与 `a210-coreboot-v1` 刷写策略（bootstrap / coreboot-ram / emmc0boot0 三段 fastboot）
- 指导新人接入 Whisper 示例 CI（buddy-mlir #757），给出 x86 测试与 rax 打包、交叉编译、板端验证的三步口径
- 反馈 ruyirepo 安装包偶发 404 问题，定位为前置代理规则异常
- 厂商合作开发工作

#### 9.3 张馥媛

##### 9.3.1 RuyiSDK 示例代码库建设

- Ruyi 示例文档库：
	- 仓库：[ruyisdk/board-docs](https://github.com/ruyisdk/board-docs)
	- 开发板示例文档扩充：
		- HiFive Premier P550：新增 Dhrystone 2.1 中文示例，覆盖 Fedora 44 下 RuyiGCC 编译、Linux 兼容调整、一亿次迭代运行及结果校验，见 [PR #51](https://github.com/ruyisdk/board-docs/pull/51)。
		- HiFive Premier P550：新增 SiFive SKL 中文示例，使用 RuyiGCC 编译 FP32 标量参考算子，验证矩阵乘法、Softmax 及大数值输入的计算结果，见 [PR #52](https://github.com/ruyisdk/board-docs/pull/52)。
		- Milk-V Jupiter2：新增 llama-server 中文部署文档，补充 RuyiSDK 编译环境、模型下载、服务启动、健康检查、模型列表和对话 API 调用步骤，见 [PR #55](https://github.com/ruyisdk/board-docs/pull/55)。
	- 课程入口整理：删除 K3 Pico-ITX 板卡介绍中重复的课程标题及第一章链接，由网站课程标签页统一提供章节入口，见 [PR #53](https://github.com/ruyisdk/board-docs/pull/53)。
	- 文档维护：
		- 更新示例文档中的 Ruyi 0.52.0 下载链接及安装命令，见 [PR #50](https://github.com/ruyisdk/board-docs/pull/50)。
		- 清理 83 份 Markdown 文档中的不换行空格、零宽空格及格式问题，修正复制命令时的参数分隔，同时保留元数据、代码块排版和 Markdown 换行语义，见 [PR #54](https://github.com/ruyisdk/board-docs/pull/54)。
- board-docs-frontend：
	- 项目仓库：[DuoQilai/board-docs-frontend](https://github.com/DuoQilai/board-docs-frontend)
	- 在线站点：[中文入口](https://boards.ruyisdk.org/)；[英文入口](https://boards.ruyisdk.org/en/)
	- 完善 CoM260 Kit 课程的章节展示范围，增加第 11—12 章的课程目录、章节导航及页面入口，并补充第 10—15 章共用 SLAM 实验手册的中英文说明，见 [PR #14](https://github.com/DuoQilai/board-docs-frontend/pull/14)。
	- 接入 K3 Pico-ITX 第 2—4 章 RISC-V C++ 与 x86 版本的教案、实验页面，同步整理板卡页面中的课程入口，见 [PR #15](https://github.com/DuoQilai/board-docs-frontend/pull/15)。
	- 将 CoM260 Kit 课程展示范围扩展至第 15 章，补充 gmapping、AMCL 定位和 Cartographer 三章入口，同步首页进度、中英文课程目录及章节导航，见 [PR #16](https://github.com/DuoQilai/board-docs-frontend/pull/16)。

##### 9.3.2 RISC-V Support Matrix

- 仓库：[ruyisdk/support-matrix](https://github.com/ruyisdk/support-matrix)
- 操作系统支持报告更新：
	- ESP32-C6：新增基于官方 BSP 的 RT-Thread 中英文测试报告，固定源码与 ESP-IDF 依赖版本，整理编译烧录、串口 shell、GPIO 和 ADC 的测试结果，并记录 SPI 回环异常及无线功能的限制，见 [PR #409](https://github.com/ruyisdk/support-matrix/pull/409)。
	- RDC2022-D1s：新增板卡资料及 RT-Thread Smart 5.0.0 出厂固件中英文测试报告，补充 SD NAND 分块烧写、回读校验及串口交互记录，并记录自编 5.3.1 固件无串口输出的问题，见 [PR #410](https://github.com/ruyisdk/support-matrix/pull/410)。
	- Milk-V Jupiter2：新增板卡信息及 Bianbu 4.0.1 中英文测试报告，记录出厂预装系统的首次设置、图形登录和桌面启动，补充录屏及桌面截图，见 [PR #411](https://github.com/ruyisdk/support-matrix/pull/411)。
	- SpaceMIT K3 Pico-ITX：新增中英文板卡概述及 Bianbu 4.0.8 测试报告，补充 Type-C 烧录说明、串口及图形登录记录、系统信息和 LXQt 桌面截图，见 [PR #412](https://github.com/ruyisdk/support-matrix/pull/412)。
	- Milk-V Duo S：
		- 完善 RT-Thread Smart 的 ELF 工具链、小核配置与自动打包步骤，修正产物路径，更新启动记录和录屏引用，见 [PR #397](https://github.com/ruyisdk/support-matrix/pull/397)。
		- 完善 Zephyr 报告中的工具链下载、U-Boot 板级配置同步及构建检查，固定 Zephyr 实测源码版本，见 [PR #405](https://github.com/ruyisdk/support-matrix/pull/405)。
	- VisionFive 2 Lite：将 Ubuntu 中英文报告更新至 24.04.5，调整镜像来源和安装说明，更新串口登录、内核及 CPU 信息，见 [PR #390](https://github.com/ruyisdk/support-matrix/pull/390)。

##### 9.3.3 RISC-V ROS2 机器人操作系统编程课程

- 项目仓库：[ROS2_RISCV](https://gitee.com/yunxiangluo/ROS2_RISCV)；[GitHub 镜像](https://github.com/DuoQilai/ROS2_RISCV)
- CoM260 Kit 课程移植与验证：
	- 第 7—8 章：完成 TF2 坐标变换、URDF／Xacro 机器人建模的独立教案、实验手册与配套代码；验证双端构建、动态／静态变换、历史查询、异常超时、跨机 TF 查询及模型关节操作，补充 RViz、Gazebo 连续录像和实测记录，见 [PR !6](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/6)。
	- 第 9—10 章：完成 Gazebo、ros2_control 与 SLAM 综合实验，验证板端读取仿真传感器、直行／旋转及超时停止，补充 slam_toolbox 建图、地图保存、AMCL 定位、Cartographer 二维建图导出和 rosbag 半速回放记录；配套整理第 10—15 章的 C++17 教案与共用 SLAM 实验手册，见 [PR !7](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/7)。
- K3 Pico-ITX 课程整合：整理第 1—4 章教案、实验及运行证据入口，并在课程清单中补齐第 2—4 章的 RISC-V C++ 与 x86 版本链接，见 [PR !8](https://gitee.com/yunxiangluo/ROS2_RISCV/pulls/8)、[PR #4](https://github.com/DuoQilai/ROS2_RISCV/pull/4)。

##### 9.3.4 RISC-V Linux 系统与开发板实践课程

审核

- 项目仓库：[DuoQilai/ruyi-riscv-linux-book](https://github.com/DuoQilai/ruyi-riscv-linux-book)
- 修复第五章 MQTT 实验终端截图的断行与展示尺寸，更新控灯状态及 tcpdump 抓包图片，见 [Commit dfb8abe](https://github.com/DuoQilai/ruyi-riscv-linux-book/commit/dfb8abe6ae7e90c261b2e780c8fcf470e3f28b37)。

##### 9.3.5 RISC-V 中国峰会

- 海报展示：展示入选海报《从碎片化到体系化：RISC-V 课程质量评估与系统化重构》，介绍课程筛选、质量评估、标签化重构及远程硬件实践方法，见 [峰会报道](https://ruyisdk.cn/t/topic/2893)。
- 报告材料：协作完成《RISC-V 课程移植方法与 RuyiSDK 生态建设》报告材料及配套海报，介绍双端协同、分阶段移植验证，以及开发示例和支持矩阵在课程建设中的应用，支撑嵌入式、物联网与智能硬件分论坛的专题分享，见 [大会议程](https://riscv-summit-china.org/agenda/)。
- 展台演示：在 RuyiSDK 展台展示 RISC-V ROS 2 机器人开发课堂，使用 CoM260 Kit 运行控制节点，配合 Ubuntu 上的 Gazebo、RViz 和 Nav2，演示仿真机器人的方形运动与八点巡回；完成网线直连、一键启停、复位重跑及现场操作讲解稿准备，见 [展台报道](https://ruyisdk.cn/t/topic/2893)。
- 演示复现包：整理源码、固定运行镜像、地图模型、依赖安装脚本、直连配置及验收记录，形成联网准备版交付包；在两端独立目录验证源码构建、跨机通信、方形运动、整圈巡回、停车与复位重跑。

##### 9.3.6 其他

- 开发板测试素材：补充 K3 Pico-ITX 的 2 张测试环境照片，并完善测试总表中 EBC7700 已有照片的入口，见 [PR #8](https://github.com/DuoQilai/asciinema/pull/8)、[PR #6](https://github.com/DuoQilai/asciinema/pull/6)。
- RuyiSDK 双周报材料：
	- 补充第 78 期支持矩阵及 CoM260 Kit ROS 2 课程进展，见 [PR #370](https://github.com/ruyisdk/wechat-articles/pull/370)。
	- 补充第 79 期 RDC2022-D1s 测试报告、CoM260 Kit Gazebo／SLAM 课程及前端展示进展，见 [PR #382](https://github.com/ruyisdk/wechat-articles/pull/382)。
