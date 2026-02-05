# RISC-V 软件生态进展 · 第 78 期·2026 年 1 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

Reviewed PRs:
- [fix: sync read status with ruyi CLI using porcelain mode](https://github.com/ruyisdk/ruyisdk-vscode-extension/pull/112)
- [docs: add VSCode Marketplace links; adjust screenshot to correct preview](https://github.com/ruyisdk/ruyisdk-vscode-extension/pull/111)
- [refactor(venv): streamline venv creation and detection by removing unnecessary prompts and simplifying name handling](https://github.com/ruyisdk/ruyisdk-vscode-extension/pull/101)
- [fix: improve extraction folder selection logic to use suggested direc…](https://github.com/ruyisdk/ruyisdk-vscode-extension/pull/98)
- [refactor(venv): split switch command and implement centralized state management](https://github.com/ruyisdk/ruyisdk-vscode-extension/pull/93)

Authored PRs:
- [feat(extract): add current folder option in extract picker](https://github.com/ruyisdk/ruyisdk-vscode-extension/pull/103)
- [fix: use local screenshot files to avoid external links](https://github.com/ruyisdk/ruyisdk-vscode-extension/pull/102)

## RuyiSDK 包管理器

## RuyiSDK 网站更新

项目更新

+ 重构用于“贡献者”和“数据统计”页面数据获取的 cjs 脚本
+ 新增 /data/api 路由，作为站外 api 不可用时的后备
+ 规范项目结构，其中本应在 src/components 下的源码从 src/pages 移出、 CommonJS 源码从 js 后缀重命名为 cjs
+ 规范模块命名，其中 /StatisticalDataPages 页面改为 /dashboard、 /community/contributors 页面改为 /contributors 一级
+ 规范模块化设计，拆分功能模块（进行中）
+ 修复 /docs 中不规范的站内 URL
+ 修复 submodule 的自动更新 workflow
+ 修复 packages.json 中缺失的依赖和可能发生的依赖版本不一致问题
+ 依赖管理工具从 npm 改为 pnpm

页面更新

+ 修复文档页面侧栏带底色的箭头图标
+ 修复不同分辨率下“新闻”页面（未公开）的新闻头图显示问题
+ 更新的“下载”页面和“感谢下载”页面（未公开）
+ 更新“文档”和“双周报”页面，同步 Ruyi 包管理器新闻到“博客”页面
+ “数据统计”页面增加 IDE 相关统计数据

PR 列表

+ [fix docs menu-list arrow's bug #315](https://github.com/ruyisdk/ruyisdk-website/pull/315)
+ [docs: add English section content for RuyiSDK VSCode extension #320](https://github.com/ruyisdk/ruyisdk-website/pull/320)
+ [pages: modify some words and i18n #322](https://github.com/ruyisdk/ruyisdk-website/pull/322)
+ [pages: update news #323](https://github.com/ruyisdk/ruyisdk-website/pull/323)
+ [Fix layout issue for pictures in different H-W ratio in news page #326](https://github.com/ruyisdk/ruyisdk-website/pull/326)
+ [pages(about): fix about page RuyiSDK toolchain #328](https://github.com/ruyisdk/ruyisdk-website/pull/328)
+ [Optimize mobile news page #329](https://github.com/ruyisdk/ruyisdk-website/pull/329)
+ [Improve subscribe button #330](https://github.com/ruyisdk/ruyisdk-website/pull/330)
+ [CI behaviour fix for contributor json file #331](https://github.com/ruyisdk/ruyisdk-website/pull/331)
+ [pages: update statistical page labels #332](https://github.com/ruyisdk/ruyisdk-website/pull/332)
+ [docs: fix broken img links #333](https://github.com/ruyisdk/ruyisdk-website/pull/333)
+ [pages(StatisticalDataPages): update ruyi download count text #334](https://github.com/ruyisdk/ruyisdk-website/pull/334)
+ [misc: modify project structure #335](https://github.com/ruyisdk/ruyisdk-website/pull/335)
+ [New vscode plugin download data #336](https://github.com/ruyisdk/ruyisdk-website/pull/336)
+ [pages(dashboard): modify overview data order #337](https://github.com/ruyisdk/ruyisdk-website/pull/337)
+ [pages(dashboard): fix crash #338](https://github.com/ruyisdk/ruyisdk-website/pull/338)
+ [pages(dashboard): really fix mobile crash #340](https://github.com/ruyisdk/ruyisdk-website/pull/340)
+ [Download page direct link and thank-you page #341](https://github.com/ruyisdk/ruyisdk-website/pull/341)
+ [misc: use tailwind instead of unocss #342](https://github.com/ruyisdk/ruyisdk-website/pull/342)（Draft）
+ [Split common components & New downloads page #343](https://github.com/ruyisdk/ruyisdk-website/pull/343)（Reverted）
+ [misc: fix dependency issue and move json files to static/data #345](https://github.com/ruyisdk/ruyisdk-website/pull/345)
+ [misc: auto api data update scripts #346](https://github.com/ruyisdk/ruyisdk-website/pull/346)

## V8 / Chromium
提交的patch如下：
1. **[riscv] Fix incorrect code gen**  
   [RISC-V] 修复不正确的ZBA指令代码生成逻辑（https://chromium-review.googlesource.com/c/7484947）
2. **[deoptimizer] fix comment**  
   [反优化器] 修复注释错误（https://chromium-review.googlesource.com/c/7459395）
3. **[riscv][maglev] Materialize undefined for undefined nan on exception**  
   [RISC-V][Maglev编译器] 针对异常场景下未定义的NaN，显式生成undefined值（https://chromium-review.googlesource.com/c/7484969）
4. **[riscv][acqrel] Added atomic acquire load and release store instructions**  
   [RISC-V][内存屏障] 添加原子获取加载（acquire load）和释放存储（release store）指令（https://chromium-review.googlesource.com/c/7489051）
5. **[riscv][wasmfx] Retire empty target stack for resume_throw**  
   [RISC-V][wasmfx] 清理resume_throw流程中空的目标栈（https://chromium-review.googlesource.com/c/7484970）
6. **[riscv][sandbox] Migrate TrustedPointerTable to range-based type checks**  
   [RISC-V][沙箱] 将TrustedPointerTable迁移为基于范围的类型检查机制（https://chromium-review.googlesource.com/c/7495671）
7. **[riscv] Implement AssembleArchSelect**  
   [RISC-V] 实现AssembleArchSelect功能（https://chromium-review.googlesource.com/c/7502457）
8. **[riscv] Skip pop simd128 in DeoptimizationEntry**  
   [RISC-V] 在反优化入口（DeoptimizationEntry）中跳过simd128的出栈操作（https://chromium-review.googlesource.com/c/7498990）
9. **[riscv] Eliminate -Wexit-time-destructors warnings**  
   [RISC-V] 消除-Wexit-time-destructors编译警告（https://chromium-review.googlesource.com/c/7508964）
10. **[riscv] Implement FP16 in simulator**  
    [RISC-V] 在模拟器中实现FP16（半精度浮点）功能（https://chromium-review.googlesource.com/c/7266607）
11. **[riscv][wasmfx] Implement resume_throw** [RISC-V][wasmfx] 实现 resume_throw 功能（https://chromium-review.googlesource.com/c/7412876） 
12. **[riscv][wasmfx] Fix cmp width in WasmFXResumeThrow** [RISC-V][wasmfx] 修复 WasmFXResumeThrow 中比较指令的位宽问题（https://chromium-review.googlesource.com/c/7417239） 
13. **[riscv] Support Wasm interpreter drumbrake** [RISC-V] 为Wasm解释器提供调试断点（drumbrake）支持（https://chromium-review.googlesource.com/c/7364683） 
14. **[riscv] Enable trap handling for memory64** [RISC-V] 为 memory64 启用内存陷阱处理机制（https://chromium-review.googlesource.com/c/7365201）

## Spidermonkey / Firefox

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/28171 (8371385: compiler/escapeAnalysis/TestRematerializeObjects.java fails in case of -XX:-UseUnalignedAccesses)
- https://github.com/openjdk/jdk/pull/28279 (8371753: compiler/c2/cr7200264/TestIntVect.java fails IR verification)
- https://github.com/openjdk/jdk/pull/28340 (8371869: RISC-V: too many warnings when build on BPI-F3 SBC)
- https://github.com/openjdk/jdk/pull/28364 (8372046: compiler/floatingpoint/TestSubNodeFloatDoubleNegation.java fails IR verification)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/25281 (8365732: RISC-V: implement AES CTR intrinsics)
- https://github.com/openjdk/jdk/pull/28320 (8371968: RISC-V: implement AES CBC intrinsics)
- https://github.com/openjdk/jdk/pull/28343 (8371966: RISC-V: Incorrect pointer dereference in TemplateInterpreterGenerator::generate_native_entry)
- https://github.com/openjdk/jdk/pull/28309 (8357551: RISC-V: support CMoveF/D vectorization)

3. Proposed JDK-25u backport PRs:
- https://github.com/openjdk/jdk25u/pull/222 (8362972: C2 fails with unexpected node in SuperWord truncation: IsFiniteF, IsFiniteD)
- https://github.com/openjdk/jdk25u/pull/238 (8368366: RISC-V: AlignVector is mistakenly set to AvoidUnalignedAccesses)
- https://github.com/openjdk/jdk25u/pull/281 (8367692: RISC-V: Align post call nop)
- https://github.com/openjdk/jdk25u-dev/pull/5 (8370708: RISC-V: Add VerifyStackAtCalls)
- https://github.com/openjdk/jdk25u-dev/pull/20 (8371966: RISC-V: Incorrect pointer dereference in TemplateInterpreterGenerator::generate_native_entry)
- https://github.com/openjdk/jdk25u-dev/pull/22 (8372046: compiler/floatingpoint/TestSubNodeFloatDoubleNegation.java fails IR verification)
- https://github.com/openjdk/jdk25u-dev/pull/38 (8366747: RISC-V: Improve VerifyMethodHandles for method handle linkers)
- https://github.com/openjdk/jdk25u-dev/pull/41 (8362284: RISC-V: cleanup NativeMovRegMem)

4. OpenJDK committer nomination:
- https://mail.openjdk.org/pipermail/jdk-dev/2025-December/010642.html (New JDK Committer: Dingli Zhang)
- https://mail.openjdk.org/pipermail/jdk-dev/2025-December/010643.html (New JDK Committer: Anjian Wen)

## Go

## GNU Toolchain
- 添加了Zalasr扩展支持：
  https://patchwork.sourceware.org/project/gcc/patch/20260128075607.343141-1-jiawei@iscas.ac.cn/
  https://patchwork.sourceware.org/project/binutils/patch/20260121162309.3466952-1-jiawei@iscas.ac.cn/
- 发布了p扩展spec 012版本，同步更新了p扩展仓库版本信息
  https://github.com/riscv/riscv-p-spec/blob/master/P-ext-proposal%3Dv0.12.adoc
  https://github.com/riscv/riscv-p-spec/commit/5f24f2a0b2e5afae343b0f9851263509c8a0a0c2
- 协助review了xsmtvdot扩展的binutils实现
  https://sourceware.org/pipermail/binutils/2026-January/148006.html

## LLVM Team
 ## LLVM Team
- Upstream llvm-project 合并的patch:
  - [RISCV]Remove experimental from Zalasr  https://github.com/llvm/llvm-project/pull/177120 
  - [DAG]Add ISD::SPLAT_VECTOR to TargetLowering::getNegatedExpression https://github.com/llvm/llvm-project/pull/173967
  - [RISCV] Fold (fma (splat (fneg X)), Y, Z) -> (fma (fneg (splat X)), Y, Z) https://github.com/llvm/llvm-project/pull/173808

- ruyisdk llvm-project
  - [LLVM][Clang][MC][XTHeadVector] add missing vncvt.x.x.w ：https://github.com/ruyisdk/llvm-project/pull/167

## MLIR / Buddy Compiler

- Buddy Compiler 主页地址 - https://buddy-compiler.github.io/
- Buddy Compiler As A Service (Buddy CAAS) - https://buddy.isrc.ac.cn/

**buddy-mlir**

- [midend] Add eliminate-memref-copy pass to eliminate redundant memref.copy operations.
- [frontend/tests] Add aten ops coverage.
- [midend] Fix MatMulParallelVectorization tail detection.
- [examples] Optimize allocation liveness.
- [Frontend] Optimize GQA attention operator for the decode phase.
- [Frontend] Vectorize index_put_ operations for KV cache updates.
- [examples] Add tiered kv cache prefill for DeepSeek-R1.
- [examples] Add Qwen3-0.6B E2E Inference.


## opensbi

## 罗云翔测试团队
## PLCT罗云翔测试团队

（包含 SAIL 和 ACT 测试部分）
测试团队阎明铸当选RISC-V SAIL项目Collaborator，体现了团队在该领域的技术贡献和社区影响力。明确了测试团队RuyiAI项目2026年Q1的工作任务，本月提交5个PR。RuyiSDK 0.44.0完成在多发行版、多架构下、多硬件环境下的测试及IDE插件评测，继续开发了自动化测试工具和测试用例，网站文档持续优化。在SAIL方向提交10个PR并参与2个PR的评审，完成多次技术分享。此外，完成了对近10款RISC-V开发板的编译工具链测试，夯实了2026年底项目验收基础。

1. RuyiSDK
1.1 RuyiSDK `0.44.0-beta.20260120` 测试
  - 测试覆盖了 8种主流Linux发行版（Debian, Ubuntu, openEuler, Fedora, Deepin, openKylin, OpenCloudOS, Archlinux）的 20多个版本。
  - 在 x86_64, aarch64, riscv64 三种CPU架构上进行了验证。
  - 对 RuyiSDK Eclipse插件 (v0.1.0 & v0.1.1) 和 VSCode插件 (v0.1.0 & 0.1.1-beta.1) 进行了系统性的手动测试。
  - 建立RuyiSDK IDE 测试用例库
    
1.2.  RuyiSDK 测试工具开发
  - 为 `ruyi-litester` 测试框架贡献代码，新增了针对 `ruyi-list` 和 `ruyi-venv` 命令的测试用例。
  - 在 `ruyi-packaging` 仓库中，实现了自动化的PR创建机制、定时任务调度、数据库记录和Web查询接口，显著提升了包管理的自动化水平和运维效率。

1.3.  RuyiSDK示例代码与开发指南建设
  - 创建并维护了 `riscv-board-custom-dev` 项目，为多款RISC-V开发板（Milk-V Duo/Duo S, LicheePi 4A等）编写了从入门到应用开发指南（Hello World, Coremark, 外设应用等）。
  - 在LicheePi 4A上实践了OpenCV构建、Qwen2.5模型部署、Luanti/Chocolate-Doom等游戏编译、WordPress部署等，制作了配套视频和文档。

1.4.  RuyiSDK网站与文档
  - 在 `ruyisdk-website` 仓库提交了超过20个PR，涉及功能新增、国际化(i18n)、UI/UX优化、移动端适配、构建流程改进等多个方面。
  - 实现了下载页面的架构自动检测与直链、优化了新闻订阅功能、修复了文档链接、重构了公共组件，并完成了从UnoCSS到Tailwind CSS的技术栈迁移，提升了网站性能和可维护性。
  - 同步更新了主文档和微信文章，确保信息的一致性。

2. RuyiAI

- 完成了2026 第一季度工作承担分工
- 提交了5个PR

3. SAIL/ACT

3.1  阎明铸当选RISC-V SAIL项目Collaborator，体现了团队在该领域的技术贡献和社区影响力。

3.2  `sail-riscv` 仓库提交了十余个PR：
  - 新增扩展支持：如 `Zicclsm`、`Zibi`、`Zvabd`（非批准）等。
  - 增强配置与合规性：添加了多种配置选项，使模型行为更符合标准，并处理了多种“保留行为”。
  - 提升模型精度与调试能力：细化CSR访问结果、增加非法访问原因报告、优化异常处理等。

3.3 活跃的社区参与与知识分享**：
  - 参加RISC-V技术黄金模型会议，作为RISC-V SAIL项项目审核者完成多个PR的审核，参加东亚区双周会同步进展。
  - 多次参加技术分享：主题包括ONNX格式、RISC-V模拟器运行模式、H扩展中断异常、浮点指令在整数寄存器中的实现机制等。

4. RISC-V 操作系统与工具链测试

- 工具链测试，覆盖RevyOS、Buildroot、Debian、Fedora、bianbu等多种操作系统，在LicheePi 4A/3A、Milk-V Duo/Duo S/Pioneer、VisionFive2、OrangePi RV2等近10款主流RISC-V开发板上进行了测试。
- 维护 RISC-V 操作系统支持矩阵 

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.44.0-beta.20260120 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260120/README.md)
    - [Debian12 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Debian12 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260120/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu22.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260120/RUYI_包管理_Ubuntu22.04_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260120/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu24.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Ubuntu24.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora42 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Fedora42_aarch64_测试结果.md)
    - [Fedora43 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Fedora43_x86_64_测试结果.md)  
    - [Fedora43 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Fedora43_aarch64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Deepin25 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Deepin25_x86_64_测试结果.md)
    - [Deepin25 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Deepin25_riscv64_测试结果.md)
    - [Deepin25 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Deepin25_aarch64_测试结果.md)
    - [openKylin2.0 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openKylin_x86_64_测试结果.md)
    - [openKylin2.0 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openKylin_riscv64_测试结果.md)
    - [openKylin2.0 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_openKylin_aarch64_测试结果.md)
    - [OpenCloudOS 9.4 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)
    - [OpenCloudOS 9.4 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_OpenCloudOS_aarch64_测试结果.md)
    - [Archlinux x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260120/RUYI_包管理_Archlinux_x86_64_测试结果.md)

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
        本版本测试基于 ruyisdk-eclipse-plugins [v0.1.1](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/releases/tag/v0.1.1) 开展手动测试。
        测试报告见 [针对 RuyiSDK Eclipse 插件的测试](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/blob/v0.1.1/README.md)
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
      - RuyiSDK VSCode IDE 测试
        本版本测试基于 ruyisdk-vscode-extension [0.1.1-beta.1](https://github.com/ruyisdk/ruyisdk-vscode-extension/releases/tag/0.1.1-beta.1) 开展手动测试。
        测试报告见 [针对 RuyiSDK VSCode 插件的测试](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/blob/v0.1.1/README.md)
        新增缺陷：
        | 缺陷 | 问题等级 | 备注 |
        | ----- | ----- | ----- |
        | [新闻UI界面已读状态未更新 #108](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/108) | 一般 | 已有 issue 回复 |
        | [查看未读新闻命令失效 #106](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/106) | 一般 | 与 #108 为同一缺陷 |
        | [不能在命令行中很好的检测虚拟环境的当前状态 #107](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/107) | 修复 | 暂不提供相关支持 |
      - Ruyi 包管理器测试
        遗留缺陷：
        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415) | 一般 | 已有 issue 回复 |
    - 修复情况
    	Ruyi 包管理器、 IDE 相关一般缺陷均简单修复合格。
    - 资源
      - [本版本 litester 测试程序](https://github.com/ruyisdk-test/ruyi-litester/tree/0f6c010632aadc177afe98e100ebd833e601a8d0)
  
- [ruyisdk-test/ruyisdk-vscode-extension-test#1](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/1)
  - Add the test case report for ruyisdk-vscode-extension-0.1.0.
    - RuyiSDK Management
    - News
    - Virtual Environment Management
    - Package Management
    - Source Package Extraction and Compilation
- [ruyisdk-test/ruyisdk-vscode-extension-test#3](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/3)
  - Improved the test case report of vscode-extension
    - Modified the directory structure
    - Modified some details in the content
- [ruyisdk-test/ruyisdk-eclipse-plugins-test#2](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/2) 
  - Improved the test case report of eclipse-plugin
    - Added use cases
    - Added images corresponding to each use case
- [ruyisdk-test/ruyisdk-vscode-extension-test#4](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/4)
  - Add v0.1.1 test report
    - News: Manual command input don't work
    - Virtual environment management: Virtual environment functionality restructured
    - Extracting source packages and compiling: Added one-click path selection feature
  (https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/95)
- [ruyisdk/ruyisdk-vscode-extension#95](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/95)
  - 安装包时弹窗中的进度条不动
- [ruyisdk/ruyisdk-vscode-extension#96](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/96)
  - 新闻的搜索功能中的使用ID搜索应如何使用？
- [ruyisdk/ruyisdk-vscode-extension#99](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/99)
  - 手动创建虚拟环境后左侧视图不能显示出名称
- [ruyisdk/ruyisdk-vscode-extension#105](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/105)
  - 手动退出虚拟环境后左侧视图不能同步 
- [ruyisdk/ruyisdk-vscode-extension#106](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/106)
  - 查看未读新闻命令失效
- Completed test case reports for ruyisdk-eclipse-plugins (v0.1.0 & v0.1.1)
  - [v0.1.0 Test Document](https://github.com/jxy687/ruyisdk-eclipse-plugins-test-v0.1.0/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3.md)
	  - Added test results for RuyiSDK Management, Package Management, and core plugin functions.
	  - Based on commit [7cd298b](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/commit/7cd298ba0b7dfb557898560f59ecf027423577be).
  - [v0.1.1 Test Document](https://github.com/jxy687/ruyisdk-eclipse-plugins-test-v0.1.1)
    - Conducted manual testing for 12 cases across News Feed and Virtual Environments.
    - Based on commit [3e669eb](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/commit/3e669ebb3961b948a4dd242fe9a404ad7bb1306f).
- [ruyisdk/ruyisdk-eclipse-plugins#92](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/92)
  - Reported initial bugs and optimization feedback found during v0.1.0 testing.
- [ruyisdk/ruyisdk-eclipse-plugins#98](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/98)
  - Reported a UI usability issue where the "Unread Only" checkmark is nearly invisible under the light theme.
- [ruyisdk/ruyisdk-eclipse-plugins#99](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/99)
  - Reported a synchronization bug where deleted virtual environment directories persist in the project list until manual refresh.
- [ruyisdk-test/ruyisdk-eclipse-plugins-test#4](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/4)
  - Updated test documentation by linking relevant bug reports.
  - Replaced outdated test screenshots to ensure report accuracy.
- Completed test case reports for ruyisdk-vscode-extension (v0.1.0 & v0.1.1-beta.1)
  - [v0.1.0 Test Document](https://github.com/qingwan12138/PLCT-WORK/blob/main/January/ruyisdk-vscode-extension-test%20report/%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A0108/%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)
	  - Added test results for Package Management and Virtual Environment Management.
  - [v0.1.1 Test Document](https://github.com/qingwan12138/PLCT-WORK/blob/main/January/ruyisdk-vscode-extension-test%20report/%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A0120/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3.md)
	  - Added test results for news and Virtual Environment Management.
  - [v0.1.1 Test Document](https://github.com/qingwan12138/PLCT-WORK/blob/main/January/ruyisdk-vscode-extension-test%20report/%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A0128/%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)
    - Added test results for RuyiSDK
- Issue [#100](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/100)
  - Reported a UI  issue where the virtual environment icon to the left of the name fails to switch upon activation.
- Issue [#107](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/107)
  - Reported a synchronization issue where the UI  fails to update accordingly when activating or deactivating the virtual environment within the terminal.
- Issue [#108](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/108)
  - Reported a version detection issue where the system incorrectly prompts for an update when a newer version of ruyi is already installed alongside an older one.
- [ruyisdk-test/ruyisdk-vscode-extension-test#5](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/5)
  - Added a failure test managed by Ruyisdk.
  - Corrected several issues regarding the number of test cases in the readme.md file.
- [ruyisdk-eclipse-plugins-test#1](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/1)：整理了 ruyisdk eclipse plugin 的手动测试用例
  - ruyisdk/.github#1：GitHub 介绍有死链
- [eclipse 插件测试更新](https://github.com/Cyl18/ruyisdk-eclipse-plugins-test/commit/57a918893ea5cd1e56e652ecb6cf7e632ce1f949)
- [ruyisdk-eclipse-plugins-test#3 v0.1.1 测试报告](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/3)
- [ruyisdk-eclipse-plugins-test#1](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/1)：已合并，新增手动测试文档，多文件被添加（含 `01-基础测试`、`03-包管理器` 等）。
  - ruyisdk/.github#1：条目保留（页面无可抓取的具体补充内容）。
- [eclipse 插件测试更新 (commit 57a9188)](https://github.com/Cyl18/ruyisdk-eclipse-plugins-test/commit/57a918893ea5cd1e56e652ecb6cf7e632ce1f949)：文档更新，Files changed: 3，改动体现在安装步骤与预期结果说明（+8 −3）。

#### 1.2 RuyiSDK 开发和测试工具开发

- packages-index 仓库
  - [board-image/buildroot-sdk-sipeed-licheervnano: bump to version 20251230 #153](https://github.com/ruyisdk/packages-index/pull/153)
  - [board-image/revyos-milkv-pioneer: bump to version 20251226 #154](https://github.com/ruyisdk/packages-index/pull/154)
  - [board-image/revyos-sipeed-lpi4a: bump to version 20251226 #155](https://github.com/ruyisdk/packages-index/pull/155)
  - [board-image/revyos-milkv-meles: bump to version 20251226 #156](https://github.com/ruyisdk/packages-index/pull/156)
  - [board-image/revyos-sipeed-laptop4a: bump to version 20251226 #157](https://github.com/ruyisdk/packages-index/pull/157)
  - [board-image/revyos-sipeed-lcon4a: bump to version 20251226 #158](https://github.com/ruyisdk/packages-index/pull/158)

- ruyi-litester 仓库
  - [feat: Add new ruyi-list test cases #17](https://github.com/weilinfox/ruyi-litester/pull/17)
  - [fix: rit.bash match does not match single element #18](https://github.com/weilinfox/ruyi-litester/pull/18)
  - [ruyi-litester#19](https://github.com/weilinfox/ruyi-litester/pull/19)：添加了 ruyi-venv 的测试用例
  - [ruyi-litester#17](https://github.com/weilinfox/ruyi-litester/pull/17)：feat: Add new ruyi-list test cases
  - [ruyi-litester#18](https://github.com/weilinfox/ruyi-litester/pull/18)：fix: rit.bash match does not match single element
  - [ruyi-litester#17](https://github.com/weilinfox/ruyi-litester/pull/17)：已合并，新增/修改 `testcases/ruyi-basic/ruyi-list.bash`（约 26 行新增），增加对 `ruyi list` 的检查（install/uninstall、过滤、category/profile 相关检查点）。
  - [ruyi-litester#18](https://github.com/weilinfox/ruyi-litester/pull/18)：已合并，对 `driver/utils/libs.bash` 做小修复（修正 `EXPR_MATCH` 的匹配/返回行为）。
  - [ruyisdk-eclipse-plugins-test#3 v0.1.1 测试报告](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/3)：已合并，报告中记录测试汇总：共 11 个测试用例，成功 8 个，失败 3 个；报告表格列出了具体失败项（例如虚拟环境创建、包管理器、自动检测与安装）。
  - [ruyi-litester#19](https://github.com/weilinfox/ruyi-litester/pull/19)：Draft（草稿），`testcases/ruyi-basic/ruyi-venv.bash` 有大量变更（+80 −7），新增多种 `ruyi venv` 场景的检查点（创建、带/不带 sysroot、多工具链、sysroot 存在性、激活后 gcc 版本等）。

- RuyiSDK IDE 手动测试用例
  - [Add manual test documentation for RuyiSDK Eclipse plugin #1](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/1)

- RuyiSDK IDE 手动测试用例
  - [update test report #2](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/2)
  - [v0.1.1 test report #3](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/3)
  - [merge and add issues link #4](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/4)

- RuyiSDK VSCode 插件手动测试用例
  - [ruyisdk-vscode-extension-0.1.0 test report #1](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/1)

- RuyiSDK VSCode 插件手动测试用例
  - [remove root directory and add tag #3](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/3)
  - [v0.1.1 test report #4](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/4)

- 开发文档
  - [实现自动PR创建机制](https://github.com/ruyisdk/ruyi-packaging/commit/afb69ab2b586f33bae369c4a11e0ec8063b3727e)
    - 在riko/cli/pr.py中实现自动化PR创建逻辑
    - 集成GitHub API，支持自动创建分支和提交PR
    - 支持批量处理多个包的版本更新
    - 实现错误处理和重试机制，确保PR创建的可靠性
    - 添加自动生成PR标题和描述的功

- [实现定时任务功能](https://github.com/ruyisdk/ruyi-packaging/commit/13a452ef864bbcd2bc933f727180d25c3930e97d)
  - 集成APScheduler库实现基于cron的任务调度
  - 配置每日凌晨2:00执行版本检查和PR创建任务
  - 实现任务状态查询功能（scheduler_status）
  - 添加手动任务触发接口（scheduler_trigger）
  - 完成任务生命周期管理：启动、停止和状态监控

- [数据库模块实现](https://github.com/ruyisdk/ruyi-packaging/commit/824034fccbf8caf0c21635b1990761e13c29b740)
  - 设计并实现用于任务历史记录的SQLite数据库架构
  - 创建recorder模块，全面记录扫描过程
  - 支持嵌套调用记录机制（在check/manifests/pr中自动处理）
  - 记录关键信息：扫描状态、包更新、成功/失败统计
  - 实现错误追踪和失败步骤记录功能

- [添加pyproject.toml配置](https://github.com/ruyisdk/ruyi-packaging/commit/ffc1fbdcf10ff257375e1c6510b635554fbecd55)
  - 选择Poetry作为项目的依赖管理工具
  - 编写完整的pyproject.toml配置文件
  - 定义项目依赖：APScheduler、FastAPI、SQLite相关库
  - 配置构建系统和项目元数据
  - 统一开发环境配置，简化团队协作

- [实现Web接口](https://github.com/ruyisdk/ruyi-packaging/commit/88e4b7e4eda6e0fa19be0943cf8bf22ac78400bf)
  - 基于FastAPI框架构建RESTful API服务
  - 提供数据库查询端点，用于获取历史记录
  - 实现调度器状态查询端点

#### 1.3 RuyiSDK Sample Codes 开发和文档编写

- [RuyiSDK Sample Codes计划](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RuyiSDK/RuyiSDK_2030.pptx)
- [使用 VSCode 上的 RuyiSDK 插件示例](https://www.bilibili.com/video/BV1xxktBtEgu/)
	- [文档](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/RuyiSDK%20VSCode%E6%8F%92%E4%BB%B6%E4%BD%BF%E7%94%A8%E6%8A%A5%E5%91%8A.md)
- 创建[开发板定制开发项目](https://github.com/DuoQilai/riscv-board-custom-dev)项目
- [Ruyi 示例库调研文档](https://github.com/DuoQilai/PLCT-Works/tree/main/riscv-board-custom-dev/Research_Document)
- [Ruyi 示例库扩充调研报告和待测示例库列表](https://github.com/DuoQilai/PLCT-Works/blob/main/riscv-board-custom-dev/Research_Document/Research_sample_lib.md)
- [Milk-V Duo x RuyiSDK 极速开发指南](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/index_tutorial_Duo.md)
	- [Milk-V Duo 概述](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/overview_Duo.md)
	- [环境准备](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/boot_Duo.md)
	- [RuyiSDK 示例 01：Hello World](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/HelloWorld_Duo.md)
	- [RuyiSDK 示例 02：Coremark](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/Coremark_Duo.md)
	- [常用库支持](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/Library-Support_Duo.md)
	- [使用 wiringX 在 Duo 上开发应用](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/application-development_Duo.md)
	- [LicheePi 4A x RuyiSDK 极速开发指南](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Licheepi4A/index_tutorial_LPi4A.md)
	-  [Lichee Pi 4A 概述](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/overview%20LPi4A.md)
	- [环境准备](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/boot_LPi4A.md)
	- [RuyiSDK 示例 01：Hello World](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/HelloWorld_LPi4A.md)
	- [RuyiSDK 示例 02：Coremark](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/Coremark_LPi4A.md)
- Duo S
	- [在 Duo S 上使用 Pico-8SEG-LED 数码管](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Application_Pico-8SEG-LED_Duo_S.md)
	- [在 Duo S 上使用 Pico-ePaper-2.13 显示屏](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Application_Pico-ePaper-2.13_Duo_S.md)
	- [LicheePi4A（RISC-V 架构）平台 RuyiSDK 配置及 Luanti 游戏编译运行](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/LicheePi_4A/LicheePi4A%EF%BC%88RISC-V%20%E6%9E%B6%E6%9E%84%EF%BC%89%E5%B9%B3%E5%8F%B0%20RuyiSDK%20%E9%85%8D%E7%BD%AE%E5%8F%8A%20Luanti%20%E6%B8%B8%E6%88%8F%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)
-  [RuyiSDK 下 GCC 对 LicheePi 4A（RevyOS） 的支持](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Ruyi_Luanti.md)
	- [PPT](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/P118.rar)
- [RuyiSDK新手入门实战](https://b23.tv/qE1mHzB)
- [LicheePi 4A运行cave-story-md游戏](https://www.bilibili.com/video/BV1k3iWBfErt/) 
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/Cave-Story-MD.md)
-  [LicheePi 4A运行Chocolate-Doom游戏～](https://www.bilibili.com/video/BV1u1rBBhEfc/) 
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/Chocolate-Doom.md)
-  [Licheepi 4A平台基于RuyiSDK构建openCV](https://www.bilibili.com/video/BV1j4zdBSEJZ/) 
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/openCV.md)
- [LicheePi 4A平台基于RuyiSDK构建Qwen2.5](https://www.bilibili.com/video/BV1WsrkBhEQQ/)
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/Qwen2.5(7B).md)
-  [LicheePi 4A平台运行WordPress个人博客](https://www.bilibili.com/video/BV1Qw6aBkEtD/)
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/WordPress.md)
-  [MilkV Duo性能测试：QEMU 模拟器 + LLVM 工具链编译 Coremark](https://www.bilibili.com/video/BV1HWvYBUEyW/)
	- [参考文档](https://github.com/Jiangxy-daisy/yq-resport/blob/main/MilkV%20Duo%20性能测试：QEMU%20模拟器%20%2B%20LLVM%20工具链编译%20Coremark.md)
-  [Milk-VDuoS部署轻量级MineCraft服务器 Cuberite](https://www.bilibili.com/video/BV1u1rBBhEfc)
- [Ruyi基础功能技术分享](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/PPT/Ruyi%E8%B5%8B%E8%83%BD.pptx)
- [Ruyi包管理器构建milkv-duo-examples示例程序](https://www.bilibili.com/video/BV1WyrEB8EWi/)
-  [使用 Ruyi 虚拟环境编译 duo-examples](https://gitee.com/huizhang_chen/writex)
- [RuyiSDKVSCode插件使用](https://github.com/jason-hue/plct/blob/main/测试文档/RuyiSDK VSCode插件使用报告.md)
- https://ruyisdk.cn/t/topic/2382/6
- [RuyiSDK 扩充示例库项目汇总表](https://github.com/jason-hue/plct/blob/main/%E6%9D%82%E9%A1%B9/%E4%B8%80%E3%80%81%20RuyiSDK%20%E6%89%A9%E5%85%85%E7%A4%BA%E4%BE%8B%E5%BA%93%E9%A1%B9%E7%9B%AE%E6%B1%87%E6%80%BB%E8%A1%A8.md)
- [在 Duo S 上使用 Pico-8SEG-LED 数码管](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Application_Pico-8SEG-LED_Duo_S.md)
- [在 Duo S 上使用 Pico-ePaper-2.13 显示屏](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Application_Pico-ePaper-2.13_Duo_S.md)
- [Ruyi SDK示例库扩充调研](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/Ruyi_Sample_Expansion.md)
- [Allegro 示例迁移至 RuyiSDK 环境实践指南](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/Ruyi_sample_Allergo.md)
- [RuyiSDK示例库调研](https://github.com/feifei-xx/plct-works/blob/5f83a734fa7442a710a856ed4061a372b3ee2a60/%E5%90%84%E7%A7%8D/RuyiSDK%E7%A4%BA%E4%BE%8B%E5%BA%93%E6%89%A9%E5%85%85)
- [OrangePi_RV2](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/OrangePi_RV2/Report_OrangePi_RV2.md)
- [VisionFive2](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/VisionFive2/Report_VisionFive2.md)
- [RuyiSDK 下 GCC 对 LicheePi 4A（RevyOS） 的支持](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Ruyi_Luanti.md)
- [LicheePi4A（RISC-V 架构）平台 RuyiSDK 配置及 Luanti 游戏编译运行](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/LicheePi_4A/LicheePi4A%EF%BC%88RISC-V%20%E6%9E%B6%E6%9E%84%EF%BC%89%E5%B9%B3%E5%8F%B0%20RuyiSDK%20%E9%85%8D%E7%BD%AE%E5%8F%8A%20Luanti%20%E6%B8%B8%E6%88%8F%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)
- LicheePi 4A x RuyiSDK 极速开发指南
  - [Lichee Pi 4A 概述](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/overview%20LPi4A.md)
  - [环境准备](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/boot_LPi4A.md)
  - [RuyiSDK 示例 01：Hello World](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/HelloWorld_LPi4A.md)
  - [RuyiSDK 示例 02：Coremark](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/Coremark_LPi4A.md)
- [RuyiSDK示例库扩充调研](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/Ruyi%20SDK%E7%A4%BA%E4%BE%8B%E5%BA%93%E6%89%A9%E5%85%85%E8%B0%83%E7%A0%94%E8%A1%A5%E5%85%85.md)
- [RuyiSDK实例](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/sundry/Milk-V%20Duo%E4%BA%BA%E8%84%B8%E6%A3%80%E6%B5%8B%E8%BF%81%E7%A7%BBRuyiSDK%E7%BC%96%E8%AF%91%E6%95%99%E7%A8%8B.md)

#### 1.4 RuyiSDK网站

- [pages: modify some words and i18n #322](https://github.com/ruyisdk/ruyisdk-website/pull/322)  
- [pages: update news #323](https://github.com/ruyisdk/ruyisdk-website/pull/323)
- [pages(about): fix about page RuyiSDK toolchain #328](https://github.com/ruyisdk/ruyisdk-website/pull/328)
- [pages: update statistical page labels #332](https://github.com/ruyisdk/ruyisdk-website/pull/332)
- [docs: fix broken img links #333](https://github.com/ruyisdk/ruyisdk-website/pull/333)
- [pages(StatisticalDataPages): update ruyi download count text #334](https://github.com/ruyisdk/ruyisdk-website/pull/334)
- [misc: modify project structure #335](https://github.com/ruyisdk/ruyisdk-website/pull/335)
- [New vscode plugin download data #336](https://github.com/ruyisdk/ruyisdk-website/pull/336)
- [pages(dashboard): modify overview data order #337](https://github.com/ruyisdk/ruyisdk-website/pull/337)
- [pages(dashboard): fix crash #338](https://github.com/ruyisdk/ruyisdk-website/pull/338)
- [pages(dashboard): really fix mobile crash #340](https://github.com/ruyisdk/ruyisdk-website/pull/340)
- [misc: use tailwind instead of unocss #342](https://github.com/ruyisdk/ruyisdk-website/pull/342)
- [misc: fix dependency issue and move json files to static/data #345](https://github.com/ruyisdk/ruyisdk-website/pull/345)
- [misc: auto api data update scripts #346](https://github.com/ruyisdk/ruyisdk-website/pull/346)
- [fix docs menu-list arrow's bug #315](https://github.com/ruyisdk/ruyisdk-website/pull/315)
- [Fix layout issue for pictures in different H-W ratio in news page #326](https://github.com/ruyisdk/ruyisdk-website/pull/326)
- [docs: add English section content for RuyiSDK VSCode extension #320](https://github.com/ruyisdk/ruyisdk-website/pull/320)
- [Optimize mobile news page #329](https://github.com/ruyisdk/ruyisdk-website/pull/329)
- [Improve subscribe button #330](https://github.com/ruyisdk/ruyisdk-website/pull/330)
- [Download page direct link and thank-you page #341](https://github.com/ruyisdk/ruyisdk-website/pull/341)
- [CI behaviour fix for contributor json file #331](https://github.com/ruyisdk/ruyisdk-website/pull/331)
- [Split common components & New downloads page #343](https://github.com/ruyisdk/ruyisdk-website/pull/343)
- [Pull #326](https://github.com/ruyisdk/ruyisdk-website/pull/326) 
  - Fix layout issues when news pictures have different height/width ratios.
  - Adjust article and skeleton layouts so text and thumbnails stretch consistently across aspect ratios.
  - Add a `check-news-images` validation script for news image existence and basic size/aspect constraints.
  - Wire the image validation script into package.json for optional strict checking.
- [Pull #329](https://github.com/ruyisdk/ruyisdk-website/pull/329)
  - Optimize the mobile news page: refine typography, title/date/summary layout for better small-screen readability.
  - Ensure article images render as block elements while keeping existing hover scaling behavior.
  - Improve responsive behavior of news cards to reduce layout shifts on narrow viewports.
- [Pull #330](https://github.com/ruyisdk/ruyisdk-website/pull/330)
  - Improve the subscribe form and button with consistent, responsive layout and localized copy.
  - Add internationalization support for labels, placeholders, and status messages.
  - Refresh visual design (gradients, shadows, focus/hover states) and replace inline styles with CSS module classes for maintainability and consistent layout across viewports.
- [Pull #331](https://github.com/ruyisdk/ruyisdk-website/pull/331)
  - CI behaviour fix for contributor JSON file: add a CI step to detect changes to the generated contributors JSON and only run the diff check when that file changed.
  - Prevent unnecessary CI failures by skipping the generated_contributors.json diff check when no relevant generation changes exist.
- [Pull #341](https://github.com/ruyisdk/ruyisdk-website/pull/341)
  - Add a richer downloads experience with direct architecture-aware links and thank-you redirect.
  - Switch to a fast mirror as the primary source for package manager releases.
  - Introduce an internal slide deck at `/slide` for the website revamp with keyboard navigation and local route previewing.
  - Downloads selector includes CPU architecture detection, source/architecture choice, and localized thank-you redirection.
  - Metadata enhancements: scrape the fast mirror for latest packages, synthesize per-architecture URLs, and improve fallbacks and robustness.
  - Update localized documentation to support the new downloads flow and labels.
- [Pull #343](https://github.com/ruyisdk/ruyisdk-website/pull/343)
  - Extract shared UI elements into reusable components under the `common` directory.
  - Introduce the `PageBackground` component, unify card/avatars/statistics icon layouts.
  - Refactor contributors, about, and news pages to consume these shared components.
  - Export new shared components for site-wide usage.
- [Pull #344](https://github.com/ruyisdk/ruyisdk-website/pull/344)
  - Migrate the site styling pipeline from UnoCSS to Tailwind CSS.
  - Configure Tailwind CSS and Autoprefixer as part of the Docusaurus and PostCSS build.
  - Unify color, typography, layout, and shadow settings with a shared Tailwind configuration.
  - Replace UnoCSS plugin and stylesheet with Tailwind equivalents, integrate with existing Sass styles.
  - Update package dependencies and build processes accordingly.

#### 1.5 RuyiSDK文档

- docs 仓库
  - [docs(VSCode-Plugins): fix broken links #126](https://github.com/ruyisdk/docs/pull/126)
  - [intro: replace old link #127](https://github.com/ruyisdk/docs/pull/127)
  - [feat: venv issue under pipx fixed at v0.45.0 #128](https://github.com/ruyisdk/docs/pull/128)
- wechat-articles 仓库
  - [Update test status for 0.45.0 #228](https://github.com/ruyisdk/wechat-articles/pull/228)

#### 1.6 RuyiSDK 视频教程

视频
- [RuyiSDK 下 GCC 对 LicheePi 4A（RevyOS） 的支持](https://www.bilibili.com/video/BV19s6vBWEAf)
- [在VSCode上使用RuyiSDK插件](https://www.bilibili.com/video/BV1xxktBtEgu)
- [RuyiSDK 下 GCC 对 LicheePi 4A（RevyOS） 的支持测试](https://www.bilibili.com/video/BV19s6vBWEAf)
- [RuyiSDK新手入门实战](https://b23.tv/qE1mHzB)

口播搞和PPT
- [RuyiSDK 下 GCC 对 LicheePi 4A（RevyOS） 的支持测试](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/P118.rar)
- [在VSCode上使用RuyiSDK 插件口播搞1](https://github.com/jason-hue/plct/blob/main/%E5%8F%A3%E6%92%AD%E7%A8%BF/）
- [在VSCode上使用RuyiSDK 插件口播搞2](https://github.com/jason-hue/plct/blob/main/口播稿/在VSCode上使用RuyiSDK插件示例口播稿.md)

#### 1.7 RuyiSDK实习生招募

RuyiSDK 测试开发实习生：

- [P119\_cyu.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month31/P119_cyu.md)
- [P119\_luz.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month31/P119_luz.md)

RuyiSDK Sample Codes和开发视频：

- [实习生技术报告面试题目](https://github.com/DuoQilai/PLCT-Works/blob/main/RISC-V_short_video/Intern_Report_Title.md)

#### 1.8 RuyiSDK双周报

- RuyiSDK双周报2份

### 2. RuyiAI

#### 2.1 RuyiAI 开发

- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/665> [frontend]: automatically inject profiling instructions in DynamoComiler
- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/664> [example] Fix BuddyTransformer build
- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/666> [build] Use custom target for python package building
- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/669> [build] Support build python wheel with scikit-build-core
- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/681> [package] Add package scripts and github ci support

#### 2.2 RuyiAI 会议和技术分析

- 技术分享，onnx 格式介绍 [PPT](https://github.com/trdthg/plct/blob/main/doc/ai/onnx/onnx.pdf)
- 参加 RuyiAI 会议和完成任务分配

### 3. RISC-V 操作系统和编译工具链测试

- 课题项目验收展示准备和现场部署2次
- [RevyOS LPi4A 系统版本和工具链测试](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Licheepi4A/Report_RevyOS_LPi4A.md)
- [Buildroot (v2) Milk-V Duo 系统版本和工具链测试](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/Report_Buildroot_v2_Duo.md)
- [BuildRoot (v2) Milk-V Duo 256M 系统版本和工具链测试](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo_256m/Report_Buildroot_v2_Duo_256m.md)
- [Debian Milk-V Duo S系统版本和工具链测试](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo_S/Report_Debian_Duo_S.md)
- [Debian LicheeRV Nano 系统版本和工具链测试](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/LicheeRV_Nano/Report_Debian_LPiNano.md)
- [RevyOS Meles 系统版本和工具链测试](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Meles/Report_RevyOS_Meles.md)
- [Fedora 38 Milk-V Pioneer系统版本和工具链测试](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Pioneer/Report_Buildroot_v2_Pioneer.md)
- [Debian CanMV K230 系统版本和工具链测试](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/K230/Report_Debian_CanMV_K230.md)
- [bianbu (v3) Lichee Pi 3A 系统版本和工具链测试](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Licheepi3A/Report_bianbu_v3_Licheepi_3A.md)
- [VisionFive2 系统版本和工具链测试](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/VisionFive2/Report_VisionFive2.md)
- [OrangePi_RV2 系统版本和工具链测试](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/OrangePi_RV2/Report_OrangePi_RV2.md)
- [Fedora 38 Milk-V Pioneer系统版本和工具链测试](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Pioneer/Report_Buildroot_v2_Pioneer.md)
- [Debian CanMV K230 系统版本和工具链测试](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/K230/Report_Debian_CanMV_K230.md)
- [bianbu (v3) Lichee Pi 3A 系统版本和工具链测试](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Licheepi3A/Report_bianbu_v3_Licheepi_3A.md)
- [链接](https://github.com/DuoQilai/support-matrix/pull/3)
	- Space-ROS BeagleV-Fire 测试报告
	- OpenWrt Banana Pi BPI-RV2 测试报告
	- Ubuntu ESWIN EBC7702 测试报告
	- pache NuttX on StarPro64 (EIC7700X) 测试报告

### 4. SAIL和ACT

#### 4.1 SAIL和ACT开发

- 阎明铸当选SAIL项目Collaborator，完成[新闻稿](https://mp.weixin.qq.com/s/eKkQ2y8TuNmp6WJ9alP8iA)

- SAIL
  - [Simplify translationException](https://github.com/riscv/sail-riscv/pull/1502)
  - [Enhance CSR access result granularity and report illegal access reasons](https://github.com/riscv/sail-riscv/pull/1402)
  - [Add Hypervisor Extension 删除在移除N扩展支持时遗漏的Interrupt支持,将其改为Reserve, 现已合并](https://github.com/riscv/sail-riscv/pull/1419)
  - [#1492](https://github.com/riscv/sail-riscv/pull/1492) : 
  - [#1412](https://github.com/riscv/sail-riscv/pull/1412): 针对当前physaddr 的所有bits 都被实现的情况, 添加配置选项, 使得physaddr 的实现位可配置, 同时保证高位为只读零
  - [#1413](https://github.com/riscv/sail-riscv/pull/1413): 针对spec中提出的`mstatus`中`FS`, `VS`字段在某些扩展的配置关闭的情况下,须为只读的问题, 添加可配置选项, 并修改字段写入guard.
  - pr#1468: [add Zicclsm extension](https://github.com/riscv/sail-riscv/pull/1468)
  - pr#1491 [add configuration option for dynamic rounding mode.](https://github.com/riscv/sail-riscv/pull/1491)
  - pr#1507 [add zibi extension](https://github.com/riscv/sail-riscv/pull/1507)
  - pr#1510 [print register number for amocas use odd-number register.](https://github.com/riscv/sail-riscv/pull/1510)
  - 合并pr#1422: [Add configuration option for reserved behavior  pmpcfg with r=0, w=1](https://github.com/riscv/sail-riscv/pull/1422)
  - 合并pr#1447 [Add configuration option for reserved behavior xenvcfg.CBIE = 0b10](https://github.com/riscv/sail-riscv/pull/1447)
  - 合并pr#1462 [Add configuration option for reserved behavior: odd number register for RV32Zdinx](https://github.com/riscv/sail-riscv/pull/1462)
  - [priscv/sail-riscv#1476](https://github.com/riscv/sail-riscv/pull/1476)
  - [#1571](https://github.com/rems-project/sail/pull/1571)
  - [#1478](https://github.com/riscv/sail-riscv/pull/1478)
  - review PR <https://github.com/riscv/sail-riscv/pull/1110> Add Hypervisor CSR and virtual Supervisor CSR handling
  - review PR <https://github.com/riscv/sail-riscv/pull/1478> Add unratified Zvabd extension

- ACT
  - 编写文档竞选ACT项目副主席

#### 4.2 技术分享和知识储备

技术分享：
- 技术分享，RISC-V 模拟器运行用户程序的几种方法 [PPT](https://github.com/trdthg/plct/blob/main/doc/sail/sail-user-mode/main.pdf)
- 完成技术分享,讲述H扩展为处理guest与host之间关系的问题扩展的中断与异常类型, [bilibili](https://www.bilibili.com/video/BV1nizaBxEXo)
- 浮点指令在整数寄存器中的实现(https://github.com/challenger1024/plct-works/blob/main/tech-sharing/2026-01-RISC-V%E6%9E%B6%E6%9E%84%E4%B8%8B-%E6%B5%AE%E7%82%B9%E6%8C%87%E4%BB%A4%E5%9C%A8%E6%95%B4%E6%95%B0%E5%AF%84%E5%AD%98%E5%99%A8%E4%B8%AD%E7%9A%84%E5%AE%9E%E7%8E%B0%E6%9C%BA%E5%88%B6.md)
- Sail RISC-V PLIC 实现
- [SIMD,RVVandZvabd.pdf](https://raw.githubusercontent.com/TinyuengKwan/plct_works/refs/heads/main/monthly/26jan.md)

知识储备：
- https://github.com/ibvqeibob/plct-works/blob/main/outcome_list/2025/m1_w1.md
- https://github.com/ibvqeibob/plct-works/blob/main/outcome_list/2025/m1_w2.md

#### 4.3 SAIL会议

- tech-golden-model meeting [`01.05`, `01.12`, `01.19`, `01.26`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 主持东亚双周会，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1bOQUzb7bvoDQ98NO8wCHwfSGRACG4MxhMjZmfml3aE0/edit?slide=id.g3b2949c6564_6_63#slide=id.g3b2949c6564_6_63)

### 5. 职工

#### 5.1 蔡玮霖

- 测试 Ruyi 0.45.0-beta.20260119、 RuyiSDK IDE VSCode 0.1.1-beta.1  和 RuyiSDK IDE Eclipse v0.1.1，提交测试报告
  - [!88 Add 0.45.0-beta.20260119 report](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/88)
- docs 仓库提交 3 个 pr
  - [docs(VSCode-Plugins): fix broken links #126](https://github.com/ruyisdk/docs/pull/126)
  - [intro: replace old link #127](https://github.com/ruyisdk/docs/pull/127)
  - [feat: venv issue under pipx fixed at v0.45.0 #128](https://github.com/ruyisdk/docs/pull/128)
- wechat-articles 仓库提交 1 个 pr
  - [Update test status for 0.45.0 #228](https://github.com/ruyisdk/wechat-articles/pull/228)
- ruyisdk-website 仓库审核 8 个 pr
  - [fix docs menu-list arrow's bug #315](https://github.com/ruyisdk/ruyisdk-website/pull/315)
  - [Fix layout issue for pictures in different H-W ratio in news page #326](https://github.com/ruyisdk/ruyisdk-website/pull/326)
  - [docs: add English section content for RuyiSDK VSCode extension #320](https://github.com/ruyisdk/ruyisdk-website/pull/320)
  - [Optimize mobile news page #329](https://github.com/ruyisdk/ruyisdk-website/pull/329)
  - [Improve subscribe button #330](https://github.com/ruyisdk/ruyisdk-website/pull/330)
  - [Download page direct link and thank-you page #341](https://github.com/ruyisdk/ruyisdk-website/pull/341)
  - [CI behaviour fix for contributor json file #331](https://github.com/ruyisdk/ruyisdk-website/pull/331)
  - [Split common components & New downloads page #343](https://github.com/ruyisdk/ruyisdk-website/pull/343)
- ruyisdk-website 仓库提交 13 个 pr
  - [pages: modify some words and i18n #322](https://github.com/ruyisdk/ruyisdk-website/pull/322)
  - [pages: update news #323](https://github.com/ruyisdk/ruyisdk-website/pull/323)
  - [pages(about): fix about page RuyiSDK toolchain #328](https://github.com/ruyisdk/ruyisdk-website/pull/328)
  - [pages: update statistical page labels #332](https://github.com/ruyisdk/ruyisdk-website/pull/332)
  - [docs: fix broken img links #333](https://github.com/ruyisdk/ruyisdk-website/pull/333)
  - [pages(StatisticalDataPages): update ruyi download count text #334](https://github.com/ruyisdk/ruyisdk-website/pull/334)
  - [misc: modify project structure #335](https://github.com/ruyisdk/ruyisdk-website/pull/335)
  - [New vscode plugin download data #336](https://github.com/ruyisdk/ruyisdk-website/pull/336)
  - [pages(dashboard): modify overview data order #337](https://github.com/ruyisdk/ruyisdk-website/pull/337)
  - [pages(dashboard): fix crash #338](https://github.com/ruyisdk/ruyisdk-website/pull/338)
  - [pages(dashboard): really fix mobile crash #340](https://github.com/ruyisdk/ruyisdk-website/pull/340)
  - [misc: use tailwind instead of unocss #342](https://github.com/ruyisdk/ruyisdk-website/pull/342)
  - [misc: fix dependency issue and move json files to static/data #345](https://github.com/ruyisdk/ruyisdk-website/pull/345)
  - [misc: auto api data update scripts #346](https://github.com/ruyisdk/ruyisdk-website/pull/346)
- packages-index 仓库提交 6 个 pr
  - [board-image/buildroot-sdk-sipeed-licheervnano: bump to version 20251230 #153](https://github.com/ruyisdk/packages-index/pull/153)
  - [board-image/revyos-milkv-pioneer: bump to version 20251226 #154](https://github.com/ruyisdk/packages-index/pull/154)
  - [board-image/revyos-sipeed-lpi4a: bump to version 20251226 #155](https://github.com/ruyisdk/packages-index/pull/155)
  - [board-image/revyos-milkv-meles: bump to version 20251226 #156](https://github.com/ruyisdk/packages-index/pull/156)
  - [board-image/revyos-sipeed-laptop4a: bump to version 20251226 #157](https://github.com/ruyisdk/packages-index/pull/157)
  - [board-image/revyos-sipeed-lcon4a: bump to version 20251226 #158](https://github.com/ruyisdk/packages-index/pull/158)
- ruyi-litester 仓库审核 2 个 pr
  - [feat: Add new ruyi-list test cases #17](https://github.com/weilinfox/ruyi-litester/pull/17)
  - [fix: rit.bash match does not match single element #18](https://github.com/weilinfox/ruyi-litester/pull/18)
- RuyiSDK IDE 手动测试用例提交 1 个 pr
  - [Add manual test documentation for RuyiSDK Eclipse plugin #1](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/1)
- RuyiSDK IDE 手动测试用例审核 3 个 pr
  - [update test report #2](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/2)
  - [v0.1.1 test report #3](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/3)
  - [merge and add issues link #4](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/4)
- RuyiSDK VSCode 插件手动测试用例提交 1 个 pr
  - [ruyisdk-vscode-extension-0.1.0 test report #1](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/1)
- RuyiSDK VSCode 插件手动测试用例审核 2 个 pr
  - [remove root directory and add tag #3](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/3)
  - [v0.1.1 test report #4](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/4)
- P119 新实习生面试
  - [P119\_cyu.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month31/P119_cyu.md)
  - [P119\_luz.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month31/P119_luz.md)
  
#### 5.2 阎明铸

##### 5.2.1 Sail

- submit PR <https://github.com/riscv/sail-riscv/pull/1502> Simplify translationException
- update PR <https://github.com/riscv/sail-riscv/pull/1402> Enhance CSR access result granularity and report illegal access reasons
- update PR <https://github.com/riscv/sail-riscv/pull/1419> Add Hypervisor Extension
- review PR <https://github.com/riscv/sail-riscv/pull/1110> Add Hypervisor CSR and virtual Supervisor CSR handling
- review PR <https://github.com/riscv/sail-riscv/pull/1478> Add unratified Zvabd extension

##### 5.2.2 RuyiAI

- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/665> [frontend]: automatically inject profiling instructions in DynamoComiler
- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/664> [example] Fix BuddyTransformer build
- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/666> [build] Use custom target for python package building
- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/669> [build] Support build python wheel with scikit-build-core
- submit PR <https://github.com/buddy-compiler/buddy-mlir/pull/681> [package] Add package scripts and github ci support

##### 5.2.3 技术分享和会议

- 技术分享，onnx 格式介绍 [PPT](https://github.com/trdthg/plct/blob/main/doc/ai/onnx/onnx.pdf)
- 技术分享，RISC-V 模拟器运行用户程序的几种方法 [PPT](https://github.com/trdthg/plct/blob/main/doc/sail/sail-user-mode/main.pdf)
- tech-golden-model meeting [`01.05`, `01.12`, `01.19`, `01.26`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 主持东亚双周会，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1bOQUzb7bvoDQ98NO8wCHwfSGRACG4MxhMjZmfml3aE0/edit?slide=id.g3b2949c6564_6_63#slide=id.g3b2949c6564_6_63)

#### 5.3 张馥媛

##### 5.3.1 英麒RISC-V Lab
- [LicheePi 4A运行cave- story-md游戏](https://www.bilibili.com/video/BV1k3iWBfErt/) 
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/Cave-Story-MD.md)
-  [LicheePi 4A运行Chocolate-Doom游戏～](https://www.bilibili.com/video/BV1u1rBBhEfc/) 
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/Chocolate-Doom.md)
-  [Licheepi 4A平台  基于RuyiSDK构建openCV](https://www.bilibili.com/video/BV1j4zdBSEJZ/) 
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/openCV.md)
- [LicheePi 4A平台 基于RuyiSDK构建Qwen2.5](https://www.bilibili.com/video/BV1WsrkBhEQQ/)
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/Qwen2.5(7B).md)
-  [LicheePi 4A平台 运行WordPress个人博客](https://www.bilibili.com/video/BV1Qw6aBkEtD/)
	- [参考文档](https://gitee.com/zjx_666/lichee-pi_4-a/blob/master/WordPress.md)
-  [MilkV Duo性能测试：QEMU 模拟器 + LLVM 工具链编译 Coremark](https://www.bilibili.com/video/BV1HWvYBUEyW/)
	- [参考文档](https://github.com/Jiangxy-daisy/yq-resport/blob/main/MilkV%20Duo%20性能测试：QEMU%20模拟器%20%2B%20LLVM%20工具链编译%20Coremark.md)
-  [Milk-VDuoS部署轻量级MineCraft服务器 Cuberite](https://www.bilibili.com/video/BV1u1rBBhEfc)
- [Ruyi基础功能技术分享](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/PPT/Ruyi%E8%B5%8B%E8%83%BD.pptx)
- [Ruyi包管理器构建milkv-duo-examples示例程序](https://www.bilibili.com/video/BV1WyrEB8EWi/)
-  [使用 Ruyi 虚拟环境编译 duo-examples](https://gitee.com/huizhang_chen/writex)

##### 5.3.2 RuyiSDK
- [使用 VSCode 上的 RuyiSDK 插件示例](https://www.bilibili.com/video/BV1xxktBtEgu/)
	- [文档](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/RuyiSDK%20VSCode%E6%8F%92%E4%BB%B6%E4%BD%BF%E7%94%A8%E6%8A%A5%E5%91%8A.md)
	- [口播稿](https://github.com/jason-hue/plct/blob/main/%E5%8F%A3%E6%92%AD%E7%A8%BF/%E5%9C%A8VSCode%E4%B8%8A%E4%BD%BF%E7%94%A8RuyiSDK%E6%8F%92%E4%BB%B6%E7%A4%BA%E4%BE%8B%E5%8F%A3%E6%92%AD%E7%A8%BF.md)
- [2030目标设想](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RuyiSDK/RuyiSDK_2030.pptx)
- 创建[开发板定制开发项目](https://github.com/DuoQilai/riscv-board-custom-dev)项目
	- 示例库调研
		- [收集多篇Ruyi 示例库调研文档](https://github.com/DuoQilai/PLCT-Works/tree/main/riscv-board-custom-dev/Research_Document)
		- [Ruyi 示例库扩充调研报告和待测示例库列表](https://github.com/DuoQilai/PLCT-Works/blob/main/riscv-board-custom-dev/Research_Document/Research_sample_lib.md)
	- 操作系统和工具链测试文档
		- [RevyOS LPi4A 系统版本和工具链测试报告](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Licheepi4A/Report_RevyOS_LPi4A.md)
		- [Buildroot (v2) Milk-V Duo 系统版本和工具链测试报告](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/Report_Buildroot_v2_Duo.md)
		- [BuildRoot (v2) Milk-V Duo 256M 系统版本和工具链测试报告](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo_256m/Report_Buildroot_v2_Duo_256m.md)
		- [Debian Milk-V Duo S系统版本和工具链测试报告](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo_S/Report_Debian_Duo_S.md)
		- [Debian LicheeRV Nano 系统版本和工具链测试报告](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/LicheeRV_Nano/Report_Debian_LPiNano.md)
		- [RevyOS Meles 系统版本和工具链测试报告](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Meles/Report_RevyOS_Meles.md)
		- [Fedora 38 Milk-V Pioneer系统版本和工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Pioneer/Report_Buildroot_v2_Pioneer.md)
		- [Debian CanMV K230 系统版本和工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/K230/Report_Debian_CanMV_K230.md)
		- [bianbu (v3) Lichee Pi 3A 系统版本和工具链测试报告](https://github.com/zhiyao310/riscv-board-custom-dev/blob/main/Licheepi3A/Report_bianbu_v3_Licheepi_3A.md)
		- [VisionFive2 系统版本和工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/VisionFive2/Report_VisionFive2.md)
		- [OrangePi_RV2 系统版本和工具链测试报告](https://github.com/feifei-xx/riscv-board-custom-dev/blob/main/OrangePi_RV2/Report_OrangePi_RV2.md)
	- [Milk-V Duo x RuyiSDK 极速开发指南](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/index_tutorial_Duo.md)
		- [Milk-V Duo 概述](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/overview_Duo.md)
		- [环境准备](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/boot_Duo.md)
		- [RuyiSDK 示例 01：Hello World](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/HelloWorld_Duo.md)
		- [RuyiSDK 示例 02：Coremark](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/Coremark_Duo.md)
		- [常用库支持](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/Library-Support_Duo.md)
		- [使用 wiringX 在 Duo 上开发应用](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Duo/application-development_Duo.md)
	- [LicheePi 4A x RuyiSDK 极速开发指南](https://github.com/DuoQilai/riscv-board-custom-dev/blob/main/Licheepi4A/index_tutorial_LPi4A.md)
		-  [Lichee Pi 4A 概述](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/overview%20LPi4A.md)
		- [环境准备](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/boot_LPi4A.md)
		- [RuyiSDK 示例 01：Hello World](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/HelloWorld_LPi4A.md)
		- [RuyiSDK 示例 02：Coremark](https://github.com/cuiqiyun/riscv-board-custom-dev/blob/main/Licheepi4A/Coremark_LPi4A.md)
	- Duo S
		- [在 Duo S 上使用 Pico-8SEG-LED 数码管](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Application_Pico-8SEG-LED_Duo_S.md)
		- [在 Duo S 上使用 Pico-ePaper-2.13 显示屏](https://github.com/jason-hue/riscv-board-custom-dev/blob/main/Duo_S/Application_Pico-ePaper-2.13_Duo_S.md)

##### 5.3.3 RISC-V short video项目
- [实习生技术报告面试题目](https://github.com/DuoQilai/PLCT-Works/blob/main/RISC-V_short_video/Intern_Report_Title.md)
- 面试产出
	- [LicheePi4A（RISC-V 架构）平台 RuyiSDK 配置及 Luanti 游戏编译运行测试报告](https://github.com/cuiqiyun/outcome_list_cqy/blob/main/LicheePi_4A/LicheePi4A%EF%BC%88RISC-V%20%E6%9E%B6%E6%9E%84%EF%BC%89%E5%B9%B3%E5%8F%B0%20RuyiSDK%20%E9%85%8D%E7%BD%AE%E5%8F%8A%20Luanti%20%E6%B8%B8%E6%88%8F%E7%BC%96%E8%AF%91%E8%BF%90%E8%A1%8C%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A.md)
	-  [RuyiSDK 下 GCC 对 LicheePi 4A（RevyOS） 的支持测试](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Licheepi4A/Ruyi_Luanti.md)
		- [视频](https://www.bilibili.com/video/BV19s6vBWEAf)
		- [PPT](https://github.com/zhiyao310/plct_works/blob/main/outcome_list/Search/P118.rar)
	- [RuyiSDK新手入门实战](https://b23.tv/qE1mHzB)

##### 5.3.4 支持矩阵
- [链接](https://github.com/DuoQilai/support-matrix/pull/3)
	- Space-ROS BeagleV-Fire 测试报告
	- OpenWrt Banana Pi BPI-RV2 测试报告
	- Ubuntu ESWIN EBC7702 测试报告
	- pache NuttX on StarPro64 (EIC7700X) 测试报告

## LuaJIT

## The Aya Theorem Prover

默认无更新。目前无员工或实习生投入。

## 参考链接
