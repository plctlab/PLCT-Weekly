# RISC-V 软件生态进展 · 第 77 期·2025 年 12 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium

Update by PLCT（Lu Yahan): 
- 7206634: [frames] Track stack frame iteration depth in StackFrameIterator | https://chromium-review.googlesource.com/c/v8/v8/+/7206634
Fix meaglev  overflow check failed about SMI
- 7202584: [riscv][maglev] Fix  an issue where SMI values do not overflow correctly | https://chromium-review.googlesource.com/c/v8/v8/+/7202584
- 7149198: [riscv] Enable v8_enable_external_code_space | https://chromium-review.googlesource.com/c/v8/v8/+/7149198 
修复 位转换FP32->UINT64时没有正确NanBox,此外减少arm64多余的指令
IR中ChangeUint32ToUint64(BitcastFloat32ToUint32)会将fp32零扩展到uint64不符合RISC-V spec
- 7271804: [Turbofan] optimize ChangeUint32ToUint64(BitcastFloat32ToUint32) | https://chromium-review.googlesource.com/c/v8/v8/+/7271804
支持Zicfiss
- 7039660: [riscv64] Protect return addresses stored on stack. | https://chromium-review.googlesource.com/c/v8/v8/+/7039660
- 7274581: [riscv] [builtins] Refactor CallApiGetter builtin | https://chromium-review.googlesource.com/c/v8/v8/+/7274581
- 7271945: [riscv][heap] Make read-only MemoryChunk field conditionally optional | https://chromium-review.googlesource.com/c/v8/v8/+/7271945
- 7259655: [riscv][api] Flatten v8::FunctionCallbackInfo<T> | https://chromium-review.googlesource.com/c/v8/v8/+/7259655
- 7255074: [riscv][wasmfx] Support return values in stack wrapper | https://chromium-review.googlesource.com/c/v8/v8/+/7255074
- 7252469: [riscv][maglev] Materialize undefined for undefined nan on exception | https://chromium-review.googlesource.com/c/v8/v8/+/7252469
- 7220250: [riscv] rename x0 to tmp1 in ByteSwap | https://chromium-review.googlesource.com/c/v8/v8/+/7220250
- 7221190: [riscv] Enable wasm-deopt flag | https://chromium-review.googlesource.com/c/v8/v8/+/7221190
- 7214846: [riscv][codegen] Remove IsolateAddressId in favour of IsolateFieldId | https://chromium-review.googlesource.com/c/v8/v8/+/7214846
- 7202304: [riscv][wasmfx] Implement tag parameters and returns | https://chromium-review.googlesource.com/c/v8/v8/+/7202304 


Review:
优化开启Zba时多余的指令
- 7255075: [riscv] Change 'zextw + add' to 'add.uw'  | https://chromium-review.googlesource.com/c/v8/v8/+/7255075
- 7171091: [riscv] Save and restore simd128 registers when deopting | https://chromium-review.googlesource.com/c/v8/v8/+/7171091
- 7157374: [riscv] Add compilation flags to control code-related alignment | https://chromium-review.googlesource.com/c/chromium/src/+/7157374 


## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/27676 (8369296: Add fast class init checks in interpreter for resolving ConstantPool entries for static field)
- https://github.com/openjdk/jdk/pull/27728 (8369505: jhsdb jstack --mixed cannot handle continuation stub on Linux)
- https://github.com/openjdk/jdk/pull/27885 (8370176: Mixed mode jhsdb jstack cannot unwind call stack with -Xcomp)
- https://github.com/openjdk/jdk/pull/27802 (8369238: Allow virtual thread preemption on some common class initialization paths)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/27557 (8368893: RISC-V: crash after JDK-8352673 on fastdebug version)
- https://github.com/openjdk/jdk/pull/27562 (8368897: RISC-V: Cleanup RV_EXT_FEATURE_FLAGS & RV_NON_EXT_FEATURE_FLAGS)
- https://github.com/openjdk/jdk/pull/27570 (8367601: Remove held_monitor_count)
- https://github.com/openjdk/jdk/pull/27757 (8369616: JavaFrameAnchor on RISC-V has unnecessary barriers and wrong store order in MacroAssembler)
- https://github.com/openjdk/jdk/pull/27572 (8368950: RISC-V: fail to catch out of order declarations among dependent cpu extensions/flags)
- https://github.com/openjdk/jdk/pull/27771 (8369685: RISC-V: refactor code related to RVFeatureValue::enabled)
- https://github.com/openjdk/jdk/pull/27850 (8369947: Bytecode rewriting causes Java heap corruption on RISC-V)
- https://github.com/openjdk/jdk/pull/27894 (8370225: RISC-V: move verify_frame_setup into ASSERT)
- https://github.com/openjdk/jdk/pull/27915 (8367982: Unify ObjectSynchronizer and LightweightSynchronizer)
- https://github.com/openjdk/jdk/pull/28005 (8370708: RISC-V: Add VerifyStackAtCalls)

3. Reviewed JDK-21u/25u mainline PRs:
- https://github.com/openjdk/jdk25u/pull/252 (8368732: RISC-V: Detect support for misaligned vector access via hwprobe)
- https://github.com/openjdk/jdk21u-dev/pull/2417 (8369947: Bytecode rewriting causes Java heap corruption on RISC-V)

## Go

Fixing https://github.com/golang/go/issues/76816 for RVA22U64 builder

1. Authored/Co-authored Go-mainline CLs:
- 647596: runtime: unify C -> Go ABI transitions on riscv64 | https://go-review.googlesource.com/c/go/+/647596
- 659175: cmd/link: generate proper attributes for riscv profile | https://go-review.googlesource.com/c/go/+/659175
- 657036: internal/bytealg: vector implementation of count 1 byte for riscv64 | https://go-review.googlesource.com/c/go/+/657036 
- 663778: cmd/asm, cmd/internal/obj: add zvbb/zvbc/zvkb for riscv64 | https://go-review.googlesource.com/c/go/+/663778
- 664155: cmd/asm, cmd/internal/obj: add crypto algorithm suites for riscv64 | https://go-review.googlesource.com/c/go/+/664155
- 663675: cmd/internal/obj: add crypto extension for riscv64 | https://go-review.googlesource.com/c/go/+/663675
- 702695: cmd/internal/obj: add zfh extensions for riscv64 | https://go-review.googlesource.com/c/go/+/702695
- 711075: chacha20: improve performance for riscv64 | https://go-review.googlesource.com/c/crypto/+/711075
- 719880: math/big: use vector for addVV on riscv64 | https://go-review.googlesource.com/c/go/+/719880
- 728940: runtime/secret: enable secret on riscv64 | https://go-review.googlesource.com/c/go/+/728940
- 728901: cmd/compile: update ABI document for riscv64 | https://go-review.googlesource.com/c/go/+/728901 [merged]
- 732540: runtime: reduce stack size of gcWriteBarrier on riscv64 | https://go-review.googlesource.com/c/go/+/732540 [Abondon]

2. Reviewed Go-mainline CLs:
- 652717: doc, cmd/internal/obj/riscv: document the riscv64 assembler | https://go-review.googlesource.com/c/go/+/652717 
- 646736: internal/bytealg: vector implementation of equal for riscv64 | https://go-review.googlesource.com/c/go/+/646736
- 646737: internal/bytealg: vector implementation of compare for riscv64 | https://go-review.googlesource.com/c/go/+/646737
- 670875: riscv64: fix the path to the RISC-V extensions in spec.go | https://go-review.googlesource.com/c/arch/+/670875
- 670875: riscv64: fix the path to the RISC-V extensions in spec.go | https://go-review.googlesource.com/c/arch/+/670875
- 690495: runtime: identify virtual memory layout for riscv64 | https://go-review.googlesource.com/c/go/+/690495
- 703715: cmd/compile/internal/ssa: add codegen for Zicond extension on riscv64 | https://go-review.googlesource.com/c/go/+/703715
- 717560: cmd/compile: use FCLASSD for subnormal checks on riscv64 | https://go-review.googlesource.com/c/go/+/717560
- 705996: cmd/compile/internal/ssa: add codegen for Zicond extension on riscv64 | https://go-review.googlesource.com/c/go/+/705996
- 732180: test/codegen: codify bit related code generation for riscv64 | https://go-review.googlesource.com/c/go/+/732180 [merged]
- 731921: cmd/asm/internal/asm: run riscv64 end-to-end tests for each profile | https://go-review.googlesource.com/c/go/+/731921 [merged]

## GNU Toolchain

## LLVM Team

## MLIR / Buddy Compiler

- Buddy Compiler 主页地址 - https://buddy-compiler.github.io/
- Buddy Compiler As A Service (Buddy CAAS) - https://buddy.isrc.ac.cn/

**buddy-mlir**

- [examples] Add instructions to build DeepSeekR1 on RISC-V.
- [Frontend] Eliminate weight transpose node.
- [midend] Add assume tight memref layout pass.
- [midend] Add matmul vectorization for decode phase.
- [Midend] Optimize BatchMatMul TransposeB Vectorization.
- [midend] Add batch matmul vectorization and simplification passes.
- [Frontend] Fuse Transpose into Reshape to Remove Redundant Operations.
- [Frontend] Add KV cache for DeepSeekR1 f16 model.
- [examples] Add metrics and streaming CLI in DeepSeekR1 example.
- [examples] Add shift context mechanism for handling token overflow.
- [examples] Update README for DeepSeek on RVV.
- [examples] Remove affine parallel pass for decode phase.
- [Frontend] Apply FlashAttention for DeepSeekR1 Prefill Phase.
- [LLVM] Integrate LLVM at llvmorg-22-init
- [Frontend] Implement GQA–Attention Fusion and Integrate into DeepSeek Decode Phase
- [examples] Add MLIR files to analyze performance.
- [midend] Add pass to staticize memref layout.

## opensbi

## RT-Thread

## PLCT罗云翔测试团队

（包含 SAIL 和 ACT 测试部分）

1. RuyiSDK 多版本测试与测试工具开发
  - 完成了 **RuyiSDK v0.44.0-beta.20251222** 在 Debian、Ubuntu、openEuler、Fedora、Deepin、openKylin、OpenCloudOS、ArchLinux 等多个系统与架构（x86_64、aarch64、riscv64）的全面测试，并发布详细测试报告。  
  - 记录并跟踪了多个遗留缺陷与新增问题，包括文档、packages-index、IDE（Eclipse/VSCode 插件）等方面的改进建议与一般性缺陷。  
  - 测试资源与工具更新，使用 `ruyi-litester` 进行自动化测试支持。  
  - 在 `packages-index` 提交多个 PR，更新多款开发板镜像至最新版本（如 OpenBSD、FreeBSD、OpenWRT、RevyOS 等），新增 Laptop 4A 等支持。  
  - 在 `ruyi-packaging` 中更新镜像设置，优化包管理流程。  
  - 在 `ruyi-litester` 中新增对 aarch64 和 riscv64 架构的测试支持。

2. RuyiSDK 网站开发与文档优化  
  - 网站前端优化：统一页面尺寸、代码块高亮修复、移动端适配、新闻展示逻辑调整、新增下载页面。  
  - 文档更新：修复 pipx 安装问题、更新 IDE 使用指南、同步测试状态至微信公众号文章。  
  - 多语言支持与社区页面建设。

3. RISC-V 编译工具链测试  
- 设计了针对 20 款 RISC-V 开发板的自动化测试方法
- 开发测试脚本并集成至验收流程，提升测试过程录制与验收回放的效率。

4. Sail/ACT 
  - 提交多项 PR，支持 Hypervisor 扩展、重构异常处理、CSR 访问检查、TLB 与地址转换机制。  
  - 增强模型配置灵活性，支持物理地址位可配置、状态字段保护等。  
  - 修复测试用例中的编译器优化问题与指令测试覆盖。
  - 提交 PR 优化饱和减法指令 lowering、寄存器分配与格式转换问题修复。
  - 发布 Sail 代码风格检查等技术分享视频与文档。  
  - 参与 Sail 双周会并整理会议纪要。

5. RuyiSDK和RISC-V 推广短视频设计  
  - 制作并发布多期 RuyiSDK 使用教程与开发板演示视频，涵盖烧录、编译、游戏运行、模型推理等场景。  
  - 文档与素材整理，包括游戏移植、模拟器运行、驱动问题排查等实战内容。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.44.0-beta.20251222 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251222/README.md)
    - [Debian12 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Debian12 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251222/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu22.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Ubuntu22.04_riscv64_测试结果.md)
    - [Ubuntu22.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251222/RUYI_包管理_Ubuntu22.04_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20251222/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu24.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Ubuntu24.04_aarch64_测试结果.md)
    - [RevyOS riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora42 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Fedora42_aarch64_测试结果.md)
    - [Fedora43 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Fedora43_x86_64_测试结果.md)  
    - [Fedora43 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Fedora43_aarch64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Deepin25 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Deepin25_x86_64_测试结果.md)
    - [Deepin25 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Deepin25_riscv64_测试结果.md)
    - [Deepin25 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Deepin25_aarch64_测试结果.md)
    - [openKylin2.0 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openKylin_x86_64_测试结果.md)
    - [openKylin2.0 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openKylin_riscv64_测试结果.md)
    - [openKylin2.0 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_openKylin_aarch64_测试结果.md)
    - [OpenCloudOS 9.4 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)
    - [OpenCloudOS 9.4 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_OpenCloudOS_aarch64_测试结果.md)
    - [Archlinux x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20251222/RUYI_包管理_Archlinux_x86_64_测试结果.md)

    - 缺陷：
      
      上一版本遗留 2 个缺陷：

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，修复已经延后  |
      
      - 文档测试

        上一版本遗留 2 个缺陷：

        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，修复已经延后  |

      - packages-index 测试

        新增 1 个缺陷：

        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [Duplicate manual profile on plugins/internal-riscv-profile-data #149](https://github.com/ruyisdk/packages-index/issues/149)     | 一般| 软件自带修复功能 |

      - RuyiSDK IDE 测试

        本版本测试基于 ruyisdk-eclipse-plugins [v0.1.0](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/releases/tag/v0.1.0) 开展手动测试。

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

        本版本测试基于 ruyisdk-vscode-extension [0.1.0](https://github.com/ruyisdk/ruyisdk-vscode-extension/releases/tag/0.1.0) 开展手动测试。

        | 缺陷 | 问题等级 | 备注 |
        | ----- | ----- | ----- |
        | [没有News的树状视图 #89](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/89) | 修复 |  |
        | [激活虚拟环境时图标未正确显示 #94](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/94) | 建议 |  |
        | [安装包时弹窗中的进度条不动 #95](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/95) | 建议 |  |
        | [新闻的搜索功能中的使用ID搜索应如何使用？ #96](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/96) | 建议 |  |

      - Ruyi 包管理器测试

        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415) | 一般 | 已有 issue 回复 |

    - 修复情况
    	新增缺陷遗留 1 个一般缺陷，将在下个开发周期修复。简单修复合格。
      
    - 资源
      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/aacca1f0f3a65b6565121e526f526ec14bc63398)
      - [ruyisdk-eclipse-plugins 参考测试报告](https://github.com/Cyl18/plct_working/blob/main/month-next-1/1_eclipse-plugin-test/README.md)

- ruyi 仓库缺陷 issue
  - [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415)

- ruyisdk-vscode-extension 缺陷 issue 
  - [解压项目模板在选择目录界面取消仍会解压 #82](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/82)

- ruyisdk-eclipse-plugins 缺陷 issue
  - [命令执行提示框可以任意关闭且无法重新打开 #82](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/82)
  - [开发板选择框中开发板型号未排序 #83](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/83)
  - [虚拟环境建立的项目绑定问题 #84](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/84)
  - [安装插件时 Eclipse 提示未签名 #85](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/85)
  - [打开 Ruyi Package Explorer 时必须选择某款开发板 #86](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/86)
  - [虚拟环境建立的 quirks 过滤问题 #87](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/87)
  - [虚拟环境建立的 ruyi update 错误处理问题 #88](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/88)
  - [虚拟环境建立的 profile 排序问题 #89](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/89)
- 在 Ubuntu 25.04 上，避开 snap， Eclipse Plugin 在 Eclipse for C/C-- 25-12 的测试，基于版本 [4019d74](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/commit/4019d74407718d8c77f8dc56741ea6794e5a847e) [测试报告](https://github.com/Cyl18/plct_working/blob/main/month-next-1/1_eclipse-plugin-test/README.md)

#### 1.2 RuyiSDK 开发和测试工具开发

- packages-index 仓库
  - [board-image/openbsd-riscv64-live: bump to latest version 7.8 #134](https://github.com/ruyisdk/packages-index/pull/134)
  - [board-image/freebsd-riscv64-mini-live: bump to latest version 15.0 #135](https://github.com/ruyisdk/packages-index/pull/135)
  - [board-image/openwrt-sifive-unmatched: bump to latest version 24.10.4 #136](https://github.com/ruyisdk/packages-index/pull/136)
  - [board-image/revyos-sipeed-lpi4a: bump to latest version 20251115 #137](https://github.com/ruyisdk/packages-index/pull/137)
  - [board-image/revyos-sipeed-meles: bump to latest version 20251115 #138](https://github.com/ruyisdk/packages-index/pull/138)
  - [board-image/revyos-sipeed-pioneer: bump to latest version 20251115 #139](https://github.com/ruyisdk/packages-index/pull/139)
  - [board-image/revyos-sipeed-laptop4a: bump to latest version 20251115 #140](https://github.com/ruyisdk/packages-index/pull/140)
  - [board-image/revyos-sipeed-lcon4a: bump to latest version 20251115 #141](https://github.com/ruyisdk/packages-index/pull/141)
  - [board-image/buildroot-sdk-sipeed-licheervnano: bump to latest version 20251202 #142](https://github.com/ruyisdk/packages-index/pull/142)
  
- ruyi-packaging 仓库
  - [ruyi_packages: update freebsd/openbsd riko.py mirror setting](https://github.com/ruyisdk/ruyi-packaging/commit/4daabb1c2ced5d1914c9204ec3d6ed076ca25f51)

- ruyi-litester 仓库
  - [Implement testing for the aarch64 architecture #14](https://github.com/weilinfox/ruyi-litester/pull/14)

- ruyi-litester 仓库
  - [Implement testing for the riscv64 architecture #15](https://github.com/weilinfox/ruyi-litester/pull/15)

#### 1.3 RuyiSDK网站

- [docs: update English version #317](https://github.com/ruyisdk/ruyisdk-website/pull/317)

- [Homepage NewsShowcase logics finetune #318](https://github.com/ruyisdk/ruyisdk-website/pull/318)

- [ci: deploy with build-noupdate and check with build #308](https://github.com/ruyisdk/ruyisdk-website/pull/308)

- [pages: release /Community/contributors #309](https://github.com/ruyisdk/ruyisdk-website/pull/309)

- [pages: update blogs and biweekly #313](https://github.com/ruyisdk/ruyisdk-website/pull/313)

- [docs: update pipx installation venv issue #316](https://github.com/ruyisdk/ruyisdk-website/pull/316)

- [docs: update IDE docs #319](https://github.com/ruyisdk/ruyisdk-website/pull/319)

- [Unify homepage sizing #283](https://github.com/ruyisdk/ruyisdk-website/pull/283)

- [Code block v3: Fixed the code highlighting issue and removed the filename attribute. #294](https://github.com/ruyisdk/ruyisdk-website/pull/294)

- [Unify page width #303](https://github.com/ruyisdk/ruyisdk-website/pull/303)

- [Optimize /about page #304](https://github.com/ruyisdk/ruyisdk-website/pull/304)

- [Optimize news #305](https://github.com/ruyisdk/ruyisdk-website/pull/305)

- [New /downloads page #311](https://github.com/ruyisdk/ruyisdk-website/pull/311)

- [Improve hints and text on /downloads page #314](https://github.com/ruyisdk/ruyisdk-website/pull/314)

#### 1.4 RuyiSDK文档

- docs 仓库提交 1 个 pr
  - [docs: update pipx installation venv issue #121](https://github.com/ruyisdk/docs/pull/121)

- wechat-articles 仓库提交 1 个 pr
  - [Update test status for 0.44.0 #218](https://github.com/ruyisdk/wechat-articles/pull/218)

#### 1.5 RuyiSDK实习生招募

编写多个考核题目

- [P119_yxi.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_yxi.md)

- [P119_jxy.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_jxy.md)

- [P119_ijh.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_ijh.md)

- [P119_vjw.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_vjw.md)

- [P119_dky.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_dky.md)
  
- [P119_vh.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_vh.md)
  
#### 1.5 RuyiSDK会议和技术分享

- RuyiSDK双周报
  
### 2. RISC-V 工具链测试

设计自动化测试方法，并测试开发板 20 个
  
  - 测试脚本 https://gitee.com/yan-mingzhu/yanshou
  
  - 为 asciinema-automation 自动化工具支持了标记点 https://github.com/trdthg/asciinema_automation/commit/8d51d104b54795ffa400fbba9d9b4de2395625cc
  
### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- SAIL
  - [sail-riscv#1419](https://github.com/riscv/sail-riscv/pull/1419) Add Hypervisor Extension, 提交了 Hypervisor 虚拟机扩展实现，共包含五个部分
    - Exception 重构，扩展了虚拟机扩展新增的多种错误信息传递
    - trap_handler 重构，陷入 VS/VU 状态的陷入除了
    - CSR 寄存器控制访问状态重构
    - TLB 支持了 VS/VU 模式下的地址缓存
    - 支持了两步地址转换
	- [sail-riscv#1437](https://github.com/riscv/sail-riscv/pull/1437)
  - [sail-riscv#1459](https://github.com/riscv/sail-riscv/pull/1459)
  - [sail-riscv#1415](https://github.com/riscv/sail-riscv/pull/1415)
  - [sail-riscv#1395](https://github.com/riscv/sail-riscv/pull/1395)
  - [sail-riscv#1424](https://github.com/riscv/sail-riscv/pull/1424)
  - [sail-riscv#1436](https://github.com/riscv/sail-riscv/pull/1436)
  - [sail-riscv#1571](https://github.com/rems-project/sail/pull/1571)
  - [sail-riscv#1402](https://github.com/riscv/sail-riscv/pull/1402) 更新 PR Enhance CSR access result granularity and report illegal access reasons
  - [sail-riscv#1451](https://github.com/riscv/sail-riscv/pull/1451): 提交PR，为H扩展需要将trap信息进行更加细致的上下文描述进行重构
  - [sail-riscv#1412](https://github.com/riscv/sail-riscv/pull/1412): 针对当前physaddr 的所有bits 都被实现的情况, 添加配置选项, 使得physaddr 的实现位可配置, 同时保证高位为只读零
  - [sail-riscv#1413](https://github.com/riscv/sail-riscv/pull/1413): 针对spec中提出的`mstatus`中`FS`, `VS`字段在某些扩展的配置关闭的情况下,须为只读的问题, 添加可配置选项, 并修改字段写入guard.
  
- riscv-hypervisor-tests
  - 修复了一个测试用例可能因为编译器优化导致失败 <https://github.com/trdthg/riscv-hyp-tests/commit/531e4e0020bb940c45685fb4d77e450cb1ebc518>
  - 修复了一个 hlvx 测试 <https://github.com/trdthg/riscv-hyp-tests/commit/725d7d8bc28d9ef8961cceff7999a5b03b9cc060>

- LLVM
	- [Lowering usub.sat(a, 1) to a - (a != 0)](https://github.com/llvm/llvm-project/pull/170076) 
	- [优化寄存器序列](https://github.com/llvm/llvm-project/pull/163047)
  - [在nchw格式转nhwc格式转换的时候会crash](https://github.com/llvm/llvm-project/pull/171122)

- Issues
  - [Cannot unify Int expression 'xxx#foo with 'foo](https://github.com/rems-project/sail/issues/1566)
  - 研究 [#956](https://github.com/riscv/sail-riscv/pull/956)
  - [#1390](https://github.com/riscv/sail-riscv/issues/1390)
  - 排查修复BUG [#1392](https://github.com/rems-project/sail/issues/1392)

#### 3.2 知识储备和技术分享

- [技术分享——为RISC-V形式化验证工具Sail添加代码风格检查](https://www.bilibili.com/video/BV1CBBEB9EoK)
  
- https://github.com/ibvqeibob/plct-works/blob/main/outcome_list/2025/m12_w2.md

- https://github.com/ibvqeibob/plct-works/blob/main/outcome_list/2025/m12_w3.md

- https://github.com/ibvqeibob/plct-works/blob/main/m12_w1.md

- [clang/gcc 测试方法](https://github.com/trdthg/llvm-tools)

#### 3.3 SAIL会议

- 参加 SAIL 双周会，产出会议记录

### 4. RISC-V教育和短视频

#### 4.1 RuyiSDK等短视频制作

- [使用RuyiSDK烧录Milk-V Duo](https://www.bilibili.com/video/BV1LYSYBCE1e/)
- [使用 RuyiSDK 在 Milk-V-Duo 编译环境构建 coremark](https://www.bilibili.com/video/BV11H2zBeEn9/)
- [丁真教你玩转荔枝派 (二)](https://www.bilibili.com/video/BV1vfSsBXEbx/)
- [LicheePi 4A平台CoreMark基准测试](https://www.bilibili.com/video/BV1Ub2LBrEvM/)
- [使用 RuyiSDK 烧录 LicheePi 4A](https://www.bilibili.com/video/BV13mSWBGEJe/)
- [LicheePi 4A平台运行Deepseek- R1(1.5B)模型](https://www.bilibili.com/video/BV1zpmEBTEii/)
- [LicheePi4A运行我的世界](https://github.com/DuoQilai/Games_Docs/blob/main/LicheePi4A/LicheePi4A_Luanti.md)
- [LicheePi 4A平台运行SuperTuxKart赛车游戏](https://www.bilibili.com/video/BV1i8BKB6EKo/)

#### 4.2 短视频剧本和文档、素材

- Luanti 开源我的世界游戏移植运行
    - 解决之前显卡驱动问题，具体定位为使用apt安装SDL2相关包时导致显卡驱动更新，解决方式参考[链接](https://gitee.com/huizhang_chen/game_doc/blob/master/sdl2_config.md)
    - 为了不干扰包版本，游戏已编译上传，可以直接下载编译好的版本运行。编译好的仓库[链接](https://gitee.com/huizhang_chen/luanti)
- Half-Life 半条命 WineCE 方式启动，游戏运行[文档](https://gitee.com/huizhang_chen/game_doc/blob/master/LicheePi_Half-Life.md)
- LaiNES 开源NES红白机模拟器移植运行，游戏运行[文档](https://gitee.com/huizhang_chen/game_doc/blob/master/LaiNES.md)
- picodrive 开源世嘉模拟器移植运行，游戏编译好的仓库[链接](https://gitee.com/huizhang_chen/picodrive)
- vkQuake 开源Quake雷神之锤游戏引擎移植运行，游戏编译好的仓库[链接](https://gitee.com/huizhang_chen/vk-quake)
- 参考[官网案例](https://wiki.sipeed.com/hardware/zh/lichee/th1520/lpi4a/8_application.html)尝试安装PSP游戏，结果失败。原因：RuyiSDK开发者论坛[帖子](http://ruyisdk.cn/t/topic/543/10)，发现显卡驱动有问题
- 参考[官网案例](https://docs.revyos.dev/docs/npu/lpi4a/pose-estimation/rtmpose_1/)尝试执行 RTMPose 模型。发现的问题已RuyiSDK开发者论坛[帖子](https://ruyisdk.cn/t/topic/2249)
- 配合维护展厅及实验室设备运行状态，定期排查开发板连通性与系统环境稳定性
- 跟踪 RISCV- Lab 建设进度，协助完善展厅视频内容与展示方案
- 教学视频[PPT](https://github.com/DuoQilai/PLCT-Works/tree/main/Notes/RISCVLab/PPT)
- 发布Licheepi 4A环境搭建、ruyi虚拟环境运行示例程序和游戏文档和视频

### 5. 职工

#### 5.1 蔡玮霖

##### 5.1.1 RuyiSDK测试和开发

- 测试 Ruyi 0.44.0-beta.20251219、 RuyiSDK IDE VSCode 0.1.0 和 RuyiSDK IDE Eclipse v0.1.0，提交测试报告
    - [!86 Add 0.44.0 test report](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/86)
    - [!87 Update 0.44.0 IDE test report](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/87)
- ruyi 仓库提出 1 个 issue
    - [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415)
- docs 仓库提交 1 个 pr
    - [docs: update pipx installation venv issue #121](https://github.com/ruyisdk/docs/pull/121)
- wechat-articles 仓库提交 1 个 pr
    - [Update test status for 0.44.0 #218](https://github.com/ruyisdk/wechat-articles/pull/218)
- packages-index 仓库提交 9 个 pr
    - [board-image/openbsd-riscv64-live: bump to latest version 7.8 #134](https://github.com/ruyisdk/packages-index/pull/134)
    - [board-image/freebsd-riscv64-mini-live: bump to latest version 15.0 #135](https://github.com/ruyisdk/packages-index/pull/135)
    - [board-image/openwrt-sifive-unmatched: bump to latest version 24.10.4 #136](https://github.com/ruyisdk/packages-index/pull/136)
    - [board-image/revyos-sipeed-lpi4a: bump to latest version 20251115 #137](https://github.com/ruyisdk/packages-index/pull/137)
    - [board-image/revyos-sipeed-meles: bump to latest version 20251115 #138](https://github.com/ruyisdk/packages-index/pull/138)
    - [board-image/revyos-sipeed-pioneer: bump to latest version 20251115 #139](https://github.com/ruyisdk/packages-index/pull/139)
    - [board-image/revyos-sipeed-laptop4a: bump to latest version 20251115 #140](https://github.com/ruyisdk/packages-index/pull/140)
    - [board-image/revyos-sipeed-lcon4a: bump to latest version 20251115 #141](https://github.com/ruyisdk/packages-index/pull/141)
    - [board-image/buildroot-sdk-sipeed-licheervnano: bump to latest version 20251202 #142](https://github.com/ruyisdk/packages-index/pull/142)
- ruyi-packaging 仓库提交 1 个 commit
    - [ruyi_packages: update freebsd/openbsd riko.py mirror setting](https://github.com/ruyisdk/ruyi-packaging/commit/4daabb1c2ced5d1914c9204ec3d6ed076ca25f51)
- ruyi-litester 仓库合作 1 个 pr
    - [Implement testing for the aarch64 architecture #14](https://github.com/weilinfox/ruyi-litester/pull/14)
- ruyi-litester 仓库审核 1 个 pr
    - [Implement testing for the riscv64 architecture #15](https://github.com/weilinfox/ruyi-litester/pull/15)
- ruyisdk-website 仓库审核 2 个 pr
    - [docs: update English version #317](https://github.com/ruyisdk/ruyisdk-website/pull/317)
    - [Homepage NewsShowcase logics finetune #318](https://github.com/ruyisdk/ruyisdk-website/pull/318)
- ruyisdk-website 仓库提交 5 个 pr
    - [ci: deploy with build-noupdate and check with build #308](https://github.com/ruyisdk/ruyisdk-website/pull/308)
    - [pages: release /Community/contributors #309](https://github.com/ruyisdk/ruyisdk-website/pull/309)
    - [pages: update blogs and biweekly #313](https://github.com/ruyisdk/ruyisdk-website/pull/313)
    - [docs: update pipx installation venv issue #316](https://github.com/ruyisdk/ruyisdk-website/pull/316)
    - [docs: update IDE docs #319](https://github.com/ruyisdk/ruyisdk-website/pull/319)
- ruyisdk-website 仓库审核 7 个 pr
    - [Unify homepage sizing #283](https://github.com/ruyisdk/ruyisdk-website/pull/283)
    - [Code block v3: Fixed the code highlighting issue and removed the filename attribute. #294](https://github.com/ruyisdk/ruyisdk-website/pull/294)
    - [Unify page width #303](https://github.com/ruyisdk/ruyisdk-website/pull/303)
    - [Optimize /about page #304](https://github.com/ruyisdk/ruyisdk-website/pull/304)
    - [Optimize news #305](https://github.com/ruyisdk/ruyisdk-website/pull/305)
    - [New /downloads page #311](https://github.com/ruyisdk/ruyisdk-website/pull/311)
    - [Improve hints and text on /downloads page #314](https://github.com/ruyisdk/ruyisdk-website/pull/314)
- ruyisdk-vscode-extension 仓库提出 1 个 issue
    - [解压项目模板在选择目录界面取消仍会解压 #82](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/82)
- ruyisdk-eclipse-plugins 仓库提出 8 个 issue
    - [命令执行提示框可以任意关闭且无法重新打开 #82](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/82)
    - [开发板选择框中开发板型号未排序 #83](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/83)
    - [虚拟环境建立的项目绑定问题 #84](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/84)
    - [安装插件时 Eclipse 提示未签名 #85](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/85)
    - [打开 Ruyi Package Explorer 时必须选择某款开发板 #86](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/86)
    - [虚拟环境建立的 quirks 过滤问题 #87](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/87)
    - [虚拟环境建立的 ruyi update 错误处理问题 #88](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/88)
    - [虚拟环境建立的 profile 排序问题 #89](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/89)
  
##### 5.2.2 RuyiSDK 新实习生面试
- [P119_yxi.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_yxi.md)
- [P119_jxy.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_jxy.md)
- [P119_ijh.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_ijh.md)
- [P119_vjw.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_vjw.md)
- [P119_dky.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_dky.md)
- [P119_vh.md](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month30/P119_vh.md)
  
#### 5.2 阎明铸

##### 5.2.1 Sail

- \[PR\] <https://github.com/riscv/sail-riscv/pull/1419> Add Hypervisor Extension, 提交了 Hypervisor 虚拟机扩展实现，共包含五个部分
    - Exception 重构，扩展了虚拟机扩展新增的多种错误信息传递
    - trap_handler 重构，陷入 VS/VU 状态的陷入除了
    - CSR 寄存器控制访问状态重构
    - TLB 支持了 VS/VU 模式下的地址缓存
    - 支持了两步地址转换
- riscv-hypervisor-tests
    - 修复了一个测试用例可能因为编译器优化导致失败 <https://github.com/trdthg/riscv-hyp-tests/commit/531e4e0020bb940c45685fb4d77e450cb1ebc518>
    - 修复了一个 hlvx 测试 <https://github.com/trdthg/riscv-hyp-tests/commit/725d7d8bc28d9ef8961cceff7999a5b03b9cc060>

- \[ISSUE\] <https://github.com/rems-project/sail/issues/1566> Cannot unify Int expression 'xxx#foo with 'foo
- 更新 PR <https://github.com/riscv/sail-riscv/pull/1402> Enhance CSR access result granularity and report illegal access reasons
- clang/gcc 测试方法 <https://github.com/trdthg/llvm-tools>

##### 5.2.3 RISC-V 工具链测试

- 设计自动化测试方法，并测试开发板 20 个
    - 测试脚本 https://gitee.com/yan-mingzhu/yanshou
    - 为 asciinema-automation 自动化工具支持了标记点 https://github.com/trdthg/asciinema_automation/commit/8d51d104b54795ffa400fbba9d9b4de2395625cc

#### 5.3 张馥媛

##### 5.3.1 RuyiSDK等短视频
- [丁真教你玩转荔枝派 (二)](https://www.bilibili.com/video/BV1vfSsBXEbx/)
- [LicheePi 4A平台CoreMark基准测试](https://www.bilibili.com/video/BV1Ub2LBrEvM/)
- [使用 RuyiSDK 烧录 LicheePi 4A](https://www.bilibili.com/video/BV13mSWBGEJe/)
- [LicheePi 4A平台运行Deepseek- R1(1.5B)模型](https://www.bilibili.com/video/BV1zpmEBTEii/)
- [LicheePi4A运行我的世界](https://github.com/DuoQilai/Games_Docs/blob/main/LicheePi4A/LicheePi4A_Luanti.md)
- [LicheePi 4A平台运行SuperTuxKart赛车游戏](https://www.bilibili.com/video/BV1i8BKB6EKo/)

##### 5.3.2 RISC-V 测试

- 发布RuyiSDK Licheepi 4A环境搭建、ruyi虚拟环境运行示例程序和游戏文档和视频
- Luanti 开源我的世界游戏移植运行
    - 解决之前显卡驱动问题，具体定位为使用apt安装SDL2相关包时导致显卡驱动更新，解决方式参考[链接](https://gitee.com/huizhang_chen/game_doc/blob/master/sdl2_config.md)
    - 为了不干扰包版本，游戏已编译上传，可以直接下载编译好的版本运行。编译好的仓库[链接](https://gitee.com/huizhang_chen/luanti)
- Half-Life 半条命 WineCE 方式启动，游戏运行[文档](https://gitee.com/huizhang_chen/game_doc/blob/master/LicheePi_Half-Life.md)
- LaiNES 开源NES红白机模拟器移植运行，游戏运行[文档](https://gitee.com/huizhang_chen/game_doc/blob/master/LaiNES.md)
- picodrive 开源世嘉模拟器移植运行，游戏编译好的仓库[链接](https://gitee.com/huizhang_chen/picodrive)
- vkQuake 开源Quake雷神之锤游戏引擎移植运行，游戏编译好的仓库[链接](https://gitee.com/huizhang_chen/vk-quake)
-  [使用RuyiSDK烧录Milk-V Duo](https://www.bilibili.com/video/BV1LYSYBCE1e/)
- [使用 RuyiSDK 在 Milk-V-Duo 编译环境构建 coremark](https://www.bilibili.com/video/BV11H2zBeEn9/)
- 参考[官网案例](https://wiki.sipeed.com/hardware/zh/lichee/th1520/lpi4a/8_application.html)尝试安装PSP游戏，结果失败。原因：RuyiSDK开发者论坛[帖子](http://ruyisdk.cn/t/topic/543/10)，发现显卡驱动有问题
- 参考[官网案例](https://docs.revyos.dev/docs/npu/lpi4a/pose-estimation/rtmpose_1/)尝试执行 RTMPose 模型。发现的问题已RuyiSDK开发者论坛[帖子](https://ruyisdk.cn/t/topic/2249)
- 配合维护展厅及实验室设备运行状态，定期排查开发板连通性与系统环境稳定性
- 跟踪 RISCV- Lab 建设进度，协助完善展厅视频内容与展示方案
- 教学视频[PPT](https://github.com/DuoQilai/PLCT-Works/tree/main/Notes/RISCVLab/PPT)

## LuaJIT

## Jeandle

### 实习生

#### 邓冲之

- \[PR\] <https://github.com/jeandle/jeandle-jdk/pull/265> enhancement: Add LLVM fatal error handler
- \[PR\] <https://github.com/jeandle/jeandle-jdk/pull/268> Fix compiler debugging assertion macro spelling case error and correct some typos

## 参考链接
