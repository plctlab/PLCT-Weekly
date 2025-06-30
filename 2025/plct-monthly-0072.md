# PLCT 开源进展·第 72 期·2025 年 7 月汇总

## 卷首语

## 本期亮点

PLCT实验室的亮点产出通过「RuyiSDK」微信公众号（ID：RuyiSDK）和英文网站提供更新服务：

- https://plctlab.org/en/news/

为了减少冗余工作量，已经在微信公众号推送的中文信息默认不再搬运。

## RuyiSDK IDE

## RuyiSDK 包管理器

## V8 / Chromium
#### PLCT提交并合入的代码
* 实现struct/array.atomic.rmw.xchg的原子交换操作 | 6633523: [riscv][wasm][shared] Implement struct/array.atomic.rmw.xchg | https://chromium-review.googlesource.com/c/v8/v8/+/6633523  
* 将 suspender 对象迁移到可信空间 | 6637888: [riscv][wasm][jspi] Move suspender object to trusted space | https://chromium-review.googlesource.com/c/v8/v8/+/6637888  
* 引入简单的截断优化pass | 6638821: [riscv][maglev] Simple truncation pass | https://chromium-review.googlesource.com/c/v8/v8/+/6638821  
* 在release模式中在常量池前增加检查 | 6653368: [riscv] Check trampoline before Constant pool in Release mode | https://chromium-review.googlesource.com/c/v8/v8/+/6653368  
* 避免在JSPI内置函数中进行可信写入 | 6656978: [riscv] [wasm][sandbox] Avoid a trusted write in a JSPI builtin | https://chromium-review.googlesource.com/c/v8/v8/+/6656978  
* 在Maglev中加入额外的peephole优化 | 6656979: [riscv][maglev] Add some peephole optimisations | https://chromium-review.googlesource.com/c/v8/v8/+/6656979
* In turbofan, produce non-canonical NaNs as result if input is Nan （6621983: [riscv] Implement non-canonical NaNs fadds in turbofan | https://chromium-review.googlesource.com/c/v8/v8/+/6621983）（6616397: [riscv][turboshaft] Propagate non-canonical NaNs | https://chromium-review.googlesource.com/c/v8/v8/+/6616397 ）
*   In liftoff, support Wasm code coverage （6621984: [riscv][wasm] Wasm code coverage: Support Liftoff | https://chromium-review.googlesource.com/c/v8/v8/+/6621984 ）
*  6605164: [riscv] Optimize Comparezero | https://chromium-review.googlesource.com/c/v8/v8/+/6605164 ）
*  6605718: [riscv] Fix add/sub overflow failed in pointer compression mode | https://chromium-review.googlesource.com/c/v8/v8/+/6605718
*  6588676: [riscv] Adjust TemporaryRegisterScope to release kMaglevFlagsRegister quickly | https://chromium-review.googlesource.com/c/v8/v8/+/6588676 

  
#### 审阅并合入的代码：  
* 修复RISC-V中sew()实现的错误 | 6643633: [riscv] Fix incorrect sew() implementation | https://chromium-review.googlesource.com/c/v8/v8/+/6643633 （来自syntacore）  
* 解决arm64平台模拟器编译问题 | 6651306: Fix riscv64 simulator compilation on arm64 | https://chromium-review.googlesource.com/c/v8/v8/+/6651306（以下均来自RISVOS）  
* 改进 trampoline 池检查方式 | 6650984: [riscv] Use byte-sized margin for trampoline pool checks | https://chromium-review.googlesource.com/c/v8/v8/+/6650984  
* 简化 wasm 转js流程，避免RISCV64平台上使用64bit整数指令处理unsigned 转换过的SMI时发生的符号错误 | 6650985: [wasm] Remove 'Unsigned' call during Js->Wasm conversion | https://chromium-review.googlesource.com/c/v8/v8/+/6650985  
* 更正拼写错误为 BranchLong | 6656518: [riscv] Fix spelling of Brachlong to BranchLong | https://chromium-review.googlesource.com/c/v8/v8/+/6656518  
* 优化常量池发射策略 | 6651735: [riscv] Use constant pool size as block margin when emitting it | https://chromium-review.googlesource.com/c/v8/v8/+/6651735
* Syntacore's 提交了针对 RAS feature的优化 6562942: [riscv] improve calls/jumps to avoid RAS pollution | https://chromium-review.googlesource.com/c/v8/v8/+/6562942 ）
* Syntacore 提交了针对StringCharCodeOrCodePointA内建函数的优化  （6593511: [riscv][maglev] Improve StringCharCodeOrCodePointAt to use sh1add instruction on Zba hardware | https://chromium-review.googlesource.com/c/v8/v8/+/6593511 ）


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
