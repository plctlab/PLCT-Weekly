# PLCT 开源进展·第 73 期·2025 年 8 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

## V8 / Chromium

-  优化StackPointerGreaterThanOp指令生成，现在会直接使用branch指令进行判断和跳转  
6862026: [riscv] Optimize StackPointerGreaterThanOp Compare and Branch | https://chromium-review.googlesource.com/c/v8/v8/+/6862026--  合并add/sub; sext.w指令成addw/subw  
6861481: [riscv] Optimize addi and signextend into addiw | https://chromium-review.googlesource.com/c/v8/v8/+/6861481
-  6838685: [riscv][turboshaft] Direct call for known functions | https://chromium-review.googlesource.com/c/v8/v8/+/6838685
-  6808522: [riscv][wasm][jspi][sandbox] Avoid writes to StackMemory from sandboxed code | https://chromium-review.googlesource.com/c/v8/v8/+/6808522
-  6726075: [risc-v] Use sign-extension (via `sext.w`) to replace `slliw` when the shift amount is zero (i.e., `slliw rd, rs, 0`). | https://chromium-review.googlesource.com/c/v8/v8/+/6726075
-  6808523: [riscv][wasm][growable-stacks] Record missing safepoint entry | https://chromium-review.googlesource.com/c/v8/v8/+/6808523

### Review:
- 6760111: [riscv] Implement register constraints for more operations | https://chromium-review.googlesource.com/c/v8/v8/+/6760111
- 6818294: [riscv] Improve ifdef guards. | https://chromium-review.googlesource.com/c/v8/v8/+/6818294
- 6820271: [riscv] Remove broken optimization in i8x16ReplaceLane | https://chromium-review.googlesource.com/c/v8/v8/+/6820271
- 6824703: [riscv] Fix xnor simulator and test. | https://chromium-review.googlesource.com/c/v8/v8/+/6824703
- 6818339: [riscv] Clean up MacroAssembler::StoreReturnAddressAndCall | https://chromium-review.googlesource.com/c/v8/v8/+/6818339
- 6818368: [riscv] Handle indirect pointer slots when recording writes | https://chromium-review.googlesource.com/c/v8/v8/+/6818368
- 6831542: [riscv][maglev] Fix compilation | https://chromium-review.googlesource.com/c/v8/v8/+/6831542
- 6813493: [riscv] Fix alignment of jump table entries in assembler tests | https://chromium-review.googlesource.com/c/v8/v8/+/6813493
- 6842298: [riscv] Allow trampoline blocking to generate code in jump table tests | https://chromium-review.googlesource.com/c/v8/v8/+/6842298
- 6859316: [riscv][liftoff] Block trampoline pool in OOL stack frame setup | https://chromium-review.googlesource.com/c/v8/v8/+/6859316
- 6760071: [riscv] Move forward declarations of Set{Hi20|Lo12}Offset | https://chromium-review.googlesource.com/c/v8/v8/+/6760071
- 6760110: [riscv] Add register constraints | https://chromium-review.googlesource.com/c/v8/v8/+/6760110
- 6760116: [riscv] Avoid temp and unique registers for ExtAddPairwise | https://chromium-review.googlesource.com/c/v8/v8/+/6760116
- 6760117: [riscv] Use register constraints for I8x16Shuffle | https://chromium-review.googlesource.com/c/v8/v8/+/6760117
- 6760118: [riscv] Avoid unnecessary moves | https://chromium-review.googlesource.com/c/v8/v8/+/6760118



## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK

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
