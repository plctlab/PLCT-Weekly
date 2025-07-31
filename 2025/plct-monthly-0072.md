# PLCT 开源进展·第 72 期·2025 年 7 月汇总

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
1. Authored/Co-authored Go-mainline CLs:
- 688635: cmd/internal/obj: enable got pcrel itype in fips140 for riscv64 | https://go-review.googlesource.com/c/go/+/688635 [merged]
- x/build: gotip-freebsd-riscv64 builder is missing | https://github.com/golang/go/issues/73568 [resolved]
2. Reviewed Go-mainline CLs:
- 688975: runtime: fix asan wrapper for riscv64 | https://go-review.googlesource.com/c/go/+/688975 [merged]
- cmd/compile: line number debug info regression in go1.25 around literal rewriting | https://github.com/golang/go/issues/74576
- 665655: internal/buildcfg: add ability to get GORISCV64 variable in GOGOARCH | https://go-review.googlesource.com/c/go/+/665655 


## OpenCV

## GNU Toolchain
实现了p扩展最新草案015版本在Binutils上的支持：
- https://github.com/ruyisdk/riscv-binutils/tree/p-dev

拟定了p扩展intrinsic文档草案，正在进行GCC部分的开发中：
- https://github.com/pz9115/rvp-intrinsic-doc/blob/main/source/simd.md

Rebase了p扩展0.9.11版本的GCC与Bintuils支持：
- https://github.com/ruyisdk/riscv-gcc/pull/5
- https://github.com/ruyisdk/riscv-binutils/pull/6

更新了riscv-gnu-toolchain configure文件中关于--with-tune的配置
- https://github.com/riscv-collab/riscv-gnu-toolchain/pull/1735

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

## Aya Prover

本月合入的 PR 都不是工作重心，主力在搞 <https://github.com/aya-prover/aya-dev/pull/1362>。

[Watch Aya Prover](https://github.com/aya-prover/aya-dev)

+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Cherry-pick context-related changes from psi-based-completion [PR-1365](https://github.com/aya-prover/aya-dev/pull/1365) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) Publish to maven portal instead [PR-1363](https://github.com/aya-prover/aya-dev/pull/1363) opened by [ice1000](https://github.com/ice1000)
+ [v0.39](https://github.com/aya-prover/aya-dev/milestone/31) doc: add init project step in "Developing in IntelliJ IDEA" [PR-1364](https://github.com/aya-prover/aya-dev/pull/1364) opened by [illusory0x0](https://github.com/illusory0x0)

## u-boot

## RevyOS (Debian for Xuantie)

### Debian

### FreeBSD
- libunwind: https://github.com/libunwind/libunwind/issues/857
- lang/go*,devel/go-perf: update default website to go.dev: https://reviews.freebsd.org/D50595
- sqlite3@default：https://sqlite.org/forum/forumpost/a92e06fc8fa3ac99
- devel/zapcc: RISC-V support? https://github.com/yrnkrn/zapcc/issues/53  
- devel/cxxtools: build failure https://github.com/maekitalo/cxxtools/issues/36 
- devel/hpx: can't link against boost-libs [WIP]
- audio/vsound: Enable riscv64 build https://github.com/freebsd/freebsd-ports/pull/423 
- devel/gn: enable riscv64 build https://github.com/freebsd/freebsd-ports/pull/421 
- devel/critcl: enable riscv64 build https://github.com/freebsd/freebsd-ports/pull/420 
- x11/virglrenderer: enable riscv64 build   https://github.com/freebsd/freebsd-ports/pull/418
- chinese/ibus-table-chinese: Update to 1.8.13 https://github.com/freebsd/freebsd-ports/pull/419 [merged]
- net/usockets: Enable riscv64 build https://reviews.freebsd.org/D51271 [merged]
- irc/undernet-ircu: enable riscv64 build https://reviews.freebsd.org/D51270

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
