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

## 参考链接
