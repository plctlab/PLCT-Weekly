# PLCT 开源进展·第 72 期·2025 年 7 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

## V8 / Chromium
- 6702989: [riscv] Delete Unnecessary margin in liftoff | https://chromium-review.googlesource.com/c/v8/v8/+/6702989
- 6702434: [riscv] Remove g_thread_in_wasm_code flag | https://chromium-review.googlesource.com/c/v8/v8/+/6702434
- 6715698: [riscv][simulator][arm64] Add missing ProbeMemory calls | https://chromium-review.googlesource.com/c/v8/v8/+/6715698
- 6715563: [riscv][builtins] Additional checks when computing baseline osr offsets | https://chromium-review.googlesource.com/c/v8/v8/+/6715563
- 6718872: [riscv] Remove the zicond optimization in builtins | https://chromium-review.googlesource.com/c/v8/v8/+/6718872
- 6726075: [risc-v] Use sign-extension (via `sext.w`) to replace `slliw` when the shift amount is zero (i.e., `slliw rd, rs, 0`). | https://chromium-review.googlesource.com/c/v8/v8/+/6726075
- 6731441: [riscv][turbolev] Implement Math.sqrt turbolev | https://chromium-review.googlesource.com/c/v8/v8/+/6731441
- 6731860: [riscv] Fix Smi to Word bitcast | https://chromium-review.googlesource.com/c/v8/v8/+/6731860
- 6731441: [riscv][turbolev] Implement Math.sqrt turbolev | https://chromium-review.googlesource.com/c/v8/v8/+/6731441
- 6734118: [riscv] Revert change-6605718 | https://chromium-review.googlesource.com/c/v8/v8/+/6734118
- 优化sext.w的弹出 6774564: [riscv] Optimize SignExtend Opcode emit | https://chromium-review.googlesource.com/c/v8/v8/+/6774564
- maglev中实现优化 6656979: [riscv][maglev] Add some peephole optimisations | https://chromium-review.googlesource.com/c/v8/v8/+/6656979
- 开启wasm deopt测试用例 6652018: [riscv][deoptimizer][wasm] Enable wasm deopt tests | https://chromium-review.googlesource.com/c/v8/v8/+/6652018

#### Reviewed:
- 6700768: [riscv] Use `Emit(...)` instead of `this->Emit(...)` | https://chromium-review.googlesource.com/c/v8/v8/+/6700768
- 6700767: [riscv] Remove incorrect debug check in riscv32 | https://chromium-review.googlesource.com/c/v8/v8/+/6700767
- 6718414: [riscv] Avoid unnecessary register move in SmiToInt32(dst, src) | https://chromium-review.googlesource.com/c/v8/v8/+/6718414
- 6731345: [riscv] Implement 'PatchInHeapNumberRequest' | https://chromium-review.googlesource.com/c/v8/v8/+/6731345
- 6767336: [riscv] Fix test expectations for floating point operations | https://chromium-review.googlesource.com/c/v8/v8/+/6767336
- 重构lane-size编码方式，直接在opcode中实现 6699489: [riscv] Refactor lane-size encoding | https://chromium-review.googlesource.com/c/v8/v8/+/6699489
- 正确记录Call函数的pc_offset 
6652837: [riscv] Use pc_offset_for_safepoint instead of blocking trampolines | https://chromium-review.googlesource.com/c/v8/v8/+/6652837
- 为了避免DEBUG模式下，向量寄存器检查失败的问题，重构部分向量IR实现方式
6668634: [riscv] Move F32x4 comp functions to code generator | https://chromium-review.googlesource.com/c/v8/v8/+/6668634
- 在编译阶段增加对RVV寄存器限制的检查  6760110: [riscv] Add register constraints | https://chromium-review.googlesource.com/c/v8/v8/+/6760110


## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/24909 (8355667: RISC-V: Add backend implementation for unsigned vector Min / Max operations)
- https://github.com/openjdk/jdk/pull/24296 (8352251: Implement JEP 518: JFR Cooperative Sampling)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/25158 (8356192: Enable AOT code caching only on supported platforms)
- https://github.com/openjdk/jdk/pull/25272 (8357143: New test AOTCodeCompressedOopsTest.java fails on platforms without AOT Code Cache support)
- https://github.com/openjdk/jdk/pull/24910 (8355668: RISC-V: jdk/incubator/vector/Int256VectorTests.java fails when using RVV)
- https://github.com/openjdk/jdk/pull/24918 (8355796: RISC-V: compiler/vectorapi/AllBitsSetVectorMatchRuleTest.java fails after JDK-8355657)
- https://github.com/openjdk/jdk/pull/24943 (8355878: RISC-V: jdk/incubator/vector/DoubleMaxVectorTests.java fails when using RVV)
- https://github.com/openjdk/jdk/pull/24950 (8355913: RISC-V: improve hotspot/jtreg/compiler/vectorization/runner/BasicFloatOpTest.java)
- https://github.com/openjdk/jdk/pull/24968 (8355980: RISC-V: remove vmclr_m before vmsXX and vmfXX)
- https://github.com/openjdk/jdk/pull/24983 (8356030: RISC-V: enable (part of) BasicDoubleOpTest.java)
- https://github.com/openjdk/jdk/pull/25005 (8355699: RISC-V: support SUADD/SADD/SUSUB/SSUB)
- https://github.com/openjdk/jdk/pull/25055 (8356188: RISC-V: Cleanup effect of vmaskcmp_fp)
- https://github.com/openjdk/jdk/pull/25135 (8356593: RISC-V: Small improvement to array fill stub)
- https://github.com/openjdk/jdk/pull/25145 (8356642: RISC-V: enable hotspot/jtreg/compiler/vectorapi/VectorFusedMultiplyAddSubTest.java)
- https://github.com/openjdk/jdk/pull/25172 (8356700: RISC-V: Declare incompressible scope in fill_words / zero_memory assembler routines)
- https://github.com/openjdk/jdk/pull/25181 (8350960: RISC-V: Add riscv backend for Float16 operations - vectorization)
- https://github.com/openjdk/jdk/pull/25210 (8356869: RISC-V: Improve tail handling of array fill stub)
- https://github.com/openjdk/jdk/pull/25213 (8356875: RISC-V: extension flag UseZvfh should depends on UseZfh)
- https://github.com/openjdk/jdk/pull/25221 (8356924: RISC-V: Clean up cost for vector instructions)

## Go

## OpenCV

## GNU Toolchain

## LLVM Team

## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

## DynamoRIO

## llama.cpp

## coreboot for riscv

## openocd

## opensbi

## u-boot

## RevyOS (Debian for Xuantie)

### Debian

## RT-Thread

## PLCT罗云翔测试团队

## SG2042/SG2044 Upstream

## Milk-V Duo Upstream

## TPU-MLIR （甲辰计划 J123）

默认无更新。本项目 RISC-V 支持由实习生提供。

## LuaJIT

默认无更新。本项目 RISC-V 支持由实习生提供。

## gem5

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## Spike

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## QEMU

默认无更新。目前无员工或实习生投入，欢迎投递简历继续做 RISC-V 支持。

## RustSBI 小队

全实习生小队，独立宣传渠道。

## Nixpkgs

默认无更新。目前无员工或实习生投入。

## Fedora

全实习生小队，独立宣传渠道。

## The Aya Theorem Prover

默认无更新。目前无员工或实习生投入。

## Arch Linux

全实习生小队，独立宣传渠道。

## 参考链接

- [PLCT 实验室的开放职位（实习生）](https://github.com/plctlab/weloveinterns/blob/master/open-internships.md)
- [PLCT 开源进展 (PLCT Weekly)](https://github.com/plctlab/PLCT-Weekly)
- [PLCT 公开报告幻灯片（选集）](https://github.com/plctlab/PLCT-Open-Reports)
