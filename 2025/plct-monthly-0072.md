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

## Go

## OpenCV

## GNU Toolchain

## LLVM Team

## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

- ksco
  - [\[LA64_DYNAREC\] Removed some TABLE64 usage](https://github.com/ptitSeb/box64/pull/2782)
  - [\[LA64_DYNAREC\] Optimized GETIP macro](https://github.com/ptitSeb/box64/pull/2781)
  - [\[DYNACACHE\]\[LA64\] More work on internal reloc](https://github.com/ptitSeb/box64/pull/2779)
  - [\[LA64_DYNAREC\] Removed some redundant macro definitions](https://github.com/ptitSeb/box64/pull/2778)
  - [\[DYNACACHE\]\[LA64\] Added const table for later use in internal relocation](https://github.com/ptitSeb/box64/pull/2770)
  - [\[CI\] Upgraded QEMU and loongarch64 toolchains](https://github.com/ptitSeb/box64/pull/2768)
  - [\[DYNAREC\] Removed some unused code](https://github.com/ptitSeb/box64/pull/2767)
  - [\[DYNACACHE\]\[RV64\] Enabled dynacache for RV64](https://github.com/ptitSeb/box64/pull/2762)
  - [\[DYNACACHE\] Make sure dynacache folder ends with pathsep](https://github.com/ptitSeb/box64/pull/2761)
  - [\[DOCS\] Performance as the top section in USAGE.md](https://github.com/ptitSeb/box64/pull/2760)
  - [\[DYNACACHE\]\[RV64\] More work on internal reloc](https://github.com/ptitSeb/box64/pull/2759)
  - [\[DYNACACHE\]\[RV64\] Added const table for later use in internal relocation](https://github.com/ptitSeb/box64/pull/2758)
  - [Fixed compilation errors](https://github.com/ptitSeb/box64/pull/2757)
  - [\[BIONIC\] Fixed some compilation warnings](https://github.com/ptitSeb/box64/pull/2756)
  - [\[WOW64\] Finished host extension detection](https://github.com/ptitSeb/box64/pull/2755)
  - [\[WOW64\] Refactored host extention detection and added preliminary support for WowBox64](https://github.com/ptitSeb/box64/pull/2752)
  - [\[RCFILE\] Updated MiSide profile](https://github.com/ptitSeb/box64/pull/2751)
  - [\[CMAKE\] Limit the optim level to O1 on bionic build](https://github.com/ptitSeb/box64/pull/2749)
  - [\[TERMUX\] Better handling of non-exists pthread functions](https://github.com/ptitSeb/box64/pull/2748)
  - [\[WOW64\] Inherit the build type from main project](https://github.com/ptitSeb/box64/pull/2746)
  - [\[DOCS\] Reworked Wine usage guide](https://github.com/ptitSeb/box64/pull/2743)
  - [\[ANDROID\] Unimportant updates](https://github.com/ptitSeb/box64/pull/2741)
  - [\[WRAPPER\] Wrapped a few more functions in gio2 and libresolv](https://github.com/ptitSeb/box64/pull/2737)
  - [\[ARM64_DYNAREC\] Fixed some typos related ymm unneeded tracing (helps #2724)](https://github.com/ptitSeb/box64/pull/2735)
  - [\[WRAPPER\] Added 2 more functions to libc (for #2731)](https://github.com/ptitSeb/box64/pull/2733)
  - [\[CPUID\] Do not warn on the Hypervisor interface query](https://github.com/ptitSeb/box64/pull/2732)
  - [\[ARM64_DYNAREC\] Added 64/65 67 89/8B 64bits opcodes](https://github.com/ptitSeb/box64/pull/2730)
  - [\[INTERP\] Fixed 64/65 67 64bit rex decoding](https://github.com/ptitSeb/box64/pull/2729)
  - [\[WOW64\] Small improvement to grab_segdata](https://github.com/ptitSeb/box64/pull/2728)
  - [\[TRACE\] Bring back in-house zydis header for v3.x](https://github.com/ptitSeb/box64/pull/2727)
  - [\[WOW64\] Small refinement to tls slots usage](https://github.com/ptitSeb/box64/pull/2726)
  - [\[ARM64_DYNAREC\] Removed redundant flags save/restore around call_c](https://github.com/ptitSeb/box64/pull/2725)
  - [\[WOW64\] Added a minimal Windows runtime](https://github.com/ptitSeb/box64/pull/2723)
  - [\[DYNAREC\] Sync indirect lookup handling and some cleanup](https://github.com/ptitSeb/box64/pull/2722)
  - [\[TRACE\] Fixed explicit BOX64_TRACE=0](https://github.com/ptitSeb/box64/pull/2721)
  - [\[TRACE\] Added support for libzydis v4.x and removed the in-house zydis header](https://github.com/ptitSeb/box64/pull/2720)
  - [\[WOW64\] Moved things around for the future](https://github.com/ptitSeb/box64/pull/2712)
  - [\[WOW64\] The official file name is wowbox64.dll](https://github.com/ptitSeb/box64/pull/2709)
  - [\[WOW64\] Added rcfile support](https://github.com/ptitSeb/box64/pull/2708)
  - [\[WOW64\] More cleanups and implemented a few more BTCpu functions](https://github.com/ptitSeb/box64/pull/2702)
  - [\[DOCS\] Updated COMPILE.md about WowBox64](https://github.com/ptitSeb/box64/pull/2701)
  - [\[ENV\]\[WOW64\] Not every env var applies to WowBox64](https://github.com/ptitSeb/box64/pull/2700)
  - [\[WOW64\] The name is WowBox64](https://github.com/ptitSeb/box64/pull/2699)
  - [\[WOW64\] Override DOS stub to Wine builtin DLL](https://github.com/ptitSeb/box64/pull/2698)
  - [\[WRAPPER\] Fixed some xcb-image wrappings](https://github.com/ptitSeb/box64/pull/2697)
  - [\[CI\] Upload libwowbox64.dll to CI artifacts](https://github.com/ptitSeb/box64/pull/2696)

## DynamoRIO

## llama.cpp

主要进展：完成了 ggml CPU 后端对七个主要架构的优化代码的重构，使得后续 RISC-V 支持的进一步开发和维护工作更加便利

- xctan
  - [ggml-cpu : split arch-specific implementations](https://github.com/ggml-org/llama.cpp/pull/13892)
  - [ggml-cpu : rework weak alias on apple targets](https://github.com/ggml-org/llama.cpp/pull/14146)
  - [ggml-cpu : remove the weak alias trick](https://github.com/ggml-org/llama.cpp/pull/14221)

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
