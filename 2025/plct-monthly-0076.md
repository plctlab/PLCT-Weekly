# PLCT 开源进展·第 76 期·2025 年 11 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

## V8 / Chromium

## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK

## Go

## OpenCV

## GNU Toolchain

## LLVM Team
- Upstream llvm-project 合并的patch:
  - [[DAG] Update canCreateUndefOrPoison to handle ISD::VECTOR_COMPRESS](https://github.com/llvm/llvm-project/pull/168010)
  - [[DAG] Add generic m_TernaryOp() / m_c_TernaryOp() matchers](https://github.com/llvm/llvm-project/pull/165520)
  - [[LLDB][DWARF] Use the same qualified name computation for Rust](https://github.com/llvm/llvm-project/pull/165840)
  - [[LLDB][Editline] empty current line before el_wgets](https://github.com/llvm/llvm-project/pull/165830)
  - [RISCV] Intrinsic Support for XCVelw: https://github.com/llvm/llvm-project/pull/129168
  - [DAGCombiner] Bail out if BitWidthDiff > BitWidth when folding cltz(and) - BitWidthDiff: https://github.com/llvm/llvm-project/pull/166607
  - [WebAssembly][FastISel] Bail out on meeting non-integer type in selectTrunc: https://github.com/llvm/llvm-project/pull/167165
  - [WebAssembly] Truncate extra bits of large elements in BUILD_VECTOR: https://github.com/llvm/llvm-project/pull/167223
  - [GISel][RISCV] Compute CTPOP of small odd-sized integer correctly: https://github.com/llvm/llvm-project/pull/168559
  - [DAGCombiner] Don't optimize insert_vector_elt into shuffle if implicit truncation exists: https://github.com/llvm/llvm-project/pull/169022
  - [Clang] Generalize interp__builtin_ia32_shuffle_generic to handle single op permute shuffles. https://github.com/llvm/llvm-project/pull/167236

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

## [BLDClock](https://github.com/BrokenClient/BLDClock.md) (甲辰计划 J156)

### 完成内容

- 移植 `RT-Thread`, `LVGL`, `SimpleFOC`
- 完成表盘与编码器的协同
- 完成编码器与USB设备的协同
- 完成衍生作品 `LCD2004_Clock` 的电路和测试程序设计

### 目前效果

- 电机定力矩运动，角度闭环运动
- 旋转电机，屏幕表盘计时点移动
- 插入USB电脑时，转动电机，电脑屏幕丝滑滑动

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
