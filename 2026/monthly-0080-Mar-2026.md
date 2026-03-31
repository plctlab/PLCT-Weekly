# RISC-V 软件生态进展 · 第 80 期·2026 年 3 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium
#### Update:
1. 在liftoff中独立分配simd registers而不是绑定浮点寄存的分配  
   7658971: [riscv][liftoff] Separate floating-point and simd registers | https://chromium-review.googlesource.com/c/v8/v8/+/7658971
3. 7699576: [riscv] Fix build for cross compile | https://chromium-review.googlesource.com/c/v8/v8/+/7699576
4. 7695091: [riscv] Add simd in LiftoffAssembler::Push/Pop | https://chromium-review.googlesource.com/c/v8/v8/+/7695091
5. 7695806: [riscv] Fix SIMD lane load source register | https://chromium-review.googlesource.com/c/v8/v8/+/7695806
6. 重构cpu 文件  
   7683553: [base] Refactor CPU detection code into architecture-specific files | https://chromium-review.googlesource.com/c/v8/v8/+/7683553
8. 7669710: [riscv] Fix vector lmul calculation for RVV | https://chromium-review.googlesource.com/c/v8/v8/+/7669710
9. 7669917: [riscv] Optimize memory access for allocatable double registers in DeoptimizationEntry | https://chromium-review.googlesource.com/c/v8/v8/+/7669917

#### Port:
1. 7707695: [riscv][base] Refactor EmbeddedVector: decouple from Vector | https://chromium-review.googlesource.com/c/v8/v8/+/7707695   
2. 7699360: [riscv][wasm][wasmfx] Implement switch instruction | https://chromium-review.googlesource.com/c/v8/v8/+/7699360
3. 7695807: [riscv][turboshaft] Direct call for known functions | https://chromium-review.googlesource.com/c/v8/v8/+/7695807  
4. 7687330: [riscv][maps] Prepare for splitting MAP_TYPE into multiple values | https://chromium-review.googlesource.com/c/v8/v8/+/7687330
5. 7685620: [riscv][wasmfx] Trap on null for resume_throw_ref | https://chromium-review.googlesource.com/c/v8/v8/+/7685620
6. 7683933: Reland "[riscv][superspread] port to riscv" | https://chromium-review.googlesource.com/c/v8/v8/+/7683933

## Spidermonkey / Firefox

## OpenJDK
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/29464 (8376575: aarch64: incorrect array index load in aastore)
- https://github.com/openjdk/valhalla/pull/2009 (8376883: [lworld] Only enable compiler/valhalla/inlinetypes/TestTrivialMethods.java for aarch64 and x86)
- https://github.com/openjdk/valhalla/pull/2020 (8377065: [lworld] Fix merge removing VM_Version::supports_fast_class_init_checks() check)
- https://github.com/openjdk/valhalla/pull/2071 (8377563: [lworld] Lower ReservedCodeCacheSize for runtime/valhalla/inlinetypes/classloading/ConcurrentClassLoadingTest.java)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/29458 (8376572: RISC-V: Interpreter: Load array index as signed int)
- https://github.com/openjdk/jdk/pull/29310 (8377225: RISC-V: Improve receiver type profiling reliability)
- https://github.com/openjdk/jdk/pull/29383 (8373595: A new ObjectMonitorTable implementation)
- https://github.com/openjdk/jdk/pull/29682 (8376168: RISC-V：Improve performance of copy_memory_v)
- https://github.com/openjdk/jdk/pull/29683 (8376167: RISC-V: Fix redundant zext.w in macroAssembler_riscv.cpp)
- https://github.com/openjdk/jdk/pull/29933 (8378752: Enable some subword vector casts IR matching tests for RISC-V)
- https://github.com/openjdk/jdk/pull/29951 (8378810: Enable missing FFM test via jtreg requires for RISC-V)
- https://github.com/openjdk/jdk/pull/29974 (8378883: Enable more vector reductions IR matching tests for RISC-V)

3. Proposed JDK-25u/26u backport PRs:
- https://github.com/openjdk/jdk26u/pull/48 (8374056: RISC-V: Fix argument passing for the RiscvFlushIcache::flush)
- https://github.com/openjdk/jdk25u-dev/pull/216 (8376572: RISC-V: Interpreter: Load array index as signed int)
- https://github.com/openjdk/jdk25u-dev/pull/245 (8374056: RISC-V: Fix argument passing for the RiscvFlushIcache::flush)
- https://github.com/openjdk/jdk25u-dev/pull/270 (8368677: acvp test should throw SkippedException when no ACVP-Server available)
- https://github.com/openjdk/jdk21u-dev/pull/2608 (8374056: RISC-V: Fix argument passing for the RiscvFlushIcache::flush)
- https://github.com/openjdk/jdk17u-dev/pull/4264 (8374056: RISC-V: Fix argument passing for the RiscvFlushIcache::flush)

## Go

## GNU Toolchain

## LLVM Team

## MLIR / Buddy Compiler

## opensbi

## 罗云翔测试团队

## 参考链接
