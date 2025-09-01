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
- 添加了GCC的`--with-profiles`支持, 用来指定Profiles配置默认构建参数
  - https://patchwork.sourceware.org/project/gcc/patch/20250826092554.1903027-1-jiawei@iscas.ac.cn/

- 使用`--with-profiles`代替`--with-isa-spec`选项作为工具链构建配置参数，目前正在讨论中
  - https://github.com/riscv-collab/riscv-gnu-toolchain/pull/1760

- 支持了`Zvabd`扩展的Binutils部分
  - https://patchwork.sourceware.org/project/binutils/patch/20250818112925.393341-1-jiawei@iscas.ac.cn/
 
- 修复了`Zilsd/Zclsd`无错误信息提示的问题
  - https://patchwork.sourceware.org/project/binutils/patch/20250812133249.1656395-1-chendongyan@isrc.iscas.ac.cn/

- 提交了`Smmtt`扩展关于`mttp`和`msdcfg`地址分配的提案，正在审核中
  - https://github.com/riscv/riscv-smmtt/pull/189

- 更新了compiler-explorer中的Binutils版本到2.45
  - https://github.com/compiler-explorer/compiler-explorer/pull/8003
 
- 更新了RVP intrinsics文档中关于数据类型的定义，目前采用SIMD数据类型(与ARM一致)，其最终实现标准仍在讨论中，欢迎大家参与
  - https://github.com/pz9115/rvp-intrinsic-doc
  - https://lists.riscv.org/g/tech-p-ext/topic/114558149
 
- 添加了RVP intrinsics的GCC支持框架，修复了Binutils实现中的部分编码问题，对实现细节进行了技术分享,正在补全GCC支持中
  - https://github.com/ruyisdk/riscv-gcc/tree/p-dev
  - https://github.com/ruyisdk/riscv-binutils/tree/p-dev
  - https://docs.google.com/presentation/d/1_3Xii6NoFqyc3tLddEus7xT0JSyc-C-xNFhltcCNCuw/edit?usp=sharing
 
- 更新了Ruyisdk工具链的Release版本，修复了GCC版本号不正确的问题
  - https://github.com/plctlab/riscv-gnu-toolchain/releases/tag/2025.08.02
  - https://github.com/ruyisdk/riscv-gcc/commit/f1eda2ebd2c0a72474950df34ce5433612cc779f

## LLVM Team
- 1. Upstream llvm-project 合并的patch:
  - [X86] SimplifyDemandedBitsForTargetNode - add handling for VPMADD52L/VPMADD52H https://github.com/llvm/llvm-project/pull/155494
  - [DAG] Constant fold ISD::FSHL/FSHR nodes https://github.com/llvm/llvm-project/pull/154480
  - [FuncSpec] Skip SCCP on blocks of dead functions and poison their callsites https://github.com/llvm/llvm-project/pull/154668
  - [SCCP][FuncSpec] Poison unreachable constant global variable user https://github.com/llvm/llvm-project/pull/155753
  - [RISCV][NFC] Fix typo v32 -> v31 in document https://github.com/llvm/llvm-project/pull/155389
  - [RISCV] Support Remaining P Extension Instructions for RV32/64 https://github.com/llvm/llvm-project/pull/150379
  - [#151682](https://github.com/llvm/llvm-project/pull/151682) [static analyzer] Fix crash on parenthesized expression in assume attribute
  - [#151790](https://github.com/llvm/llvm-project/pull/151790) [clang][diagnostics] Fix fix-it hint parenthesis placement for fold expressions
  - [#151981](https://github.com/llvm/llvm-project/pull/151981) [RISCV] Create disjoint or in RISCVGatherScatterLowering
  - [#153362](https://github.com/llvm/llvm-project/pull/153362) [CIR] Add InlineAsmOp
  - [#153387](https://github.com/llvm/llvm-project/pull/153387) [CIR] Add InlineAsmOp lowering to LLVM
  - [#153546](https://github.com/llvm/llvm-project/pull/153546) [CIR] Implement codegen for inline assembly without input and output operands 
  - [#152294](https://github.com/llvm/llvm-project/pull/152294) [clang] constexpr integer __builtin_elementwise_{max,min}

- 2. plctlab llvm-project合并的patch:
  - https://github.com/plctlab/llvm-project/pull/71 Add some p-ext intrinsic support 
  - https://github.com/plctlab/llvm-project/pull/72 [RISCV] Add P-ext intrinsic
  - https://github.com/plctlab/llvm-project/pull/73 add llvm intrinsic support for cmix,rdov 

## MLIR

### Buddy Compiler

**buddy-mlir**

**buddy-benchmark**

## Box64

Highlights:

Linux Steam 启动！AVX/AVX2 标量实现绝赞支持中，进度 50%！

Merged PRs:

1. [\[WRAPPER\] Wrapped 2 more symbols for libfreetype](https://github.com/ptitSeb/box64/pull/2984)
1. [\[WRAPPER\] Wrapped mallinfo2 for libc](https://github.com/ptitSeb/box64/pull/2983)
1. [Fixed a misguarded box32 endif](https://github.com/ptitSeb/box64/pull/2982)
1. [\[WRAPPER\] Wrapped more symbols for libresolv](https://github.com/ptitSeb/box64/pull/2981)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2980)
1. [\[LA64_DYNAREC\] Fixed AVX VCVT[T]PS2DQ fastround path](https://github.com/ptitSeb/box64/pull/2979)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2978)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2975)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2974)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2973)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2971)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2970)
1. [\[RV64_DYNAREC\] Added YMM0 placeholder for later optim](https://github.com/ptitSeb/box64/pull/2968)
1. [\[RV64_DYNAREC\] Fixed scalar avx VCMPPD non-ymm case](https://github.com/ptitSeb/box64/pull/2966)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2965)
1. [\[ARM64_DYNAREC\] Fixed an inst name typo](https://github.com/ptitSeb/box64/pull/2964)
1. [\[RV64_DYNAREC\] Added scalar SSE 66 0F 3A 60/61/62 opcodes](https://github.com/ptitSeb/box64/pull/2963)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2961)
1. [\[RV64_DYNAREC\] Added more scalar avx 66 0F opcodes](https://github.com/ptitSeb/box64/pull/2960)
1. [\[RV64_DYNAREC\] Fixed more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2959)
1. [\[CORE\] Better trace_file logging](https://github.com/ptitSeb/box64/pull/2958)
1. [\[COSIM\] Better memory diff printing](https://github.com/ptitSeb/box64/pull/2957)
1. [\[RV64_DYNAREC\] Fixed some scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2956)
1. [\[RV64_DYNAREC\] Added more scalar avx 66 0F3A opcodes](https://github.com/ptitSeb/box64/pull/2955)
1. [\[RV64_DYNAREC\] Added more scalar avx 66 0F38 opcodes](https://github.com/ptitSeb/box64/pull/2954)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2952)
1. [\[RV64_DYNAREC\] Added more scalar avx opcodes](https://github.com/ptitSeb/box64/pull/2951)
1. [\[RV64_DYNAREC\] Added more avx scalar 66 0F38 opcodes](https://github.com/ptitSeb/box64/pull/2950)
1. [\[RV64_DYNAREC\] Added a few more scalar AVX 66 0F38 opcodes](https://github.com/ptitSeb/box64/pull/2949)
1. [\[RV64_DYNAREC\] Added scalar AVX VMOVDQA opcodes](https://github.com/ptitSeb/box64/pull/2948)
1. [\[DYNAREC\] Bump ARCH_VERSION](https://github.com/ptitSeb/box64/pull/2947)
1. [\[LA64_DYNAREC\] Enable AVX/AVX2 by default](https://github.com/ptitSeb/box64/pull/2946)
1. [\[RV64_DYNAREC\] Added more scalar AVX opcodes](https://github.com/ptitSeb/box64/pull/2945)
1. [\[RV64_DYNAREC\] Added more scalar AVX opcodes](https://github.com/ptitSeb/box64/pull/2943)
1. [\[RV64_DYNAREC\] Added more scalar AVX VMOV opcodes](https://github.com/ptitSeb/box64/pull/2942)
1. [\[RV64_DYNAREC\] Added scalar AVX VMOVSS opcodes](https://github.com/ptitSeb/box64/pull/2941)
1. [\[BOX32\] Fixed sign-extend issue when calling RunFunctionFmt with a pointer](https://github.com/ptitSeb/box64/pull/2938)
1. [\[RV64_DYNAREC\] Fixed OF2 handling](https://github.com/ptitSeb/box64/pull/2937)
1. [\[DYNAREC\] Fixed reading emu->df](https://github.com/ptitSeb/box64/pull/2936)
1. [\[RV64_DYNAREC\] Removed a dispensable line from dump](https://github.com/ptitSeb/box64/pull/2932)
1. [\[LA64_DYNAREC\] Fixed a typo in CMPXCHG8B opcode](https://github.com/ptitSeb/box64/pull/2931)
1. [\[DYNAREC\] Rearranged arch-specific AVX infra code](https://github.com/ptitSeb/box64/pull/2930)
1. [\[RV64_DYNAREC\] Added F0 08 LOCK OR opcode](https://github.com/ptitSeb/box64/pull/2928)
1. [\[RV64_DYNAREC\] Fixed F0 10 LOCK ADC opcode](https://github.com/ptitSeb/box64/pull/2927)
1. [\[RV64_DYNAREC\][\LA64_DYNAREC] Fixed missing zeroup in geted_32()](https://github.com/ptitSeb/box64/pull/2921)
1. [\[LA64_DYNAREC\] Fixed AVX VPMOVMSKB opcode](https://github.com/ptitSeb/box64/pull/2920)
1. [\[LA64_DYNAREC\] Fixed AVX VPERM2F128/VPERM2I128 opcodes](https://github.com/ptitSeb/box64/pull/2919)
1. [\[LA64_DYNAREC\] Fixed AVX VMASKMOVDQU opcode](https://github.com/ptitSeb/box64/pull/2918)
1. [\[LA64_DYNAREC\] Fixed AVX VPBLENDW opcodes](https://github.com/ptitSeb/box64/pull/2917)
1. [\[LA64_DYNAREC\] Fixed AVX VMOVMSKPS/VMOVMSKPD opcodes](https://github.com/ptitSeb/box64/pull/2916)
1. [\[LA64_DYNAREC\] Fixed AVX VMOVSS opcode](https://github.com/ptitSeb/box64/pull/2915)
1. [\[LA64_DYNAREC\] Fixed AVX VCMPSS/VCMPSD opcodes](https://github.com/ptitSeb/box64/pull/2914)
1. [\[LA64_DYNAREC\] Fixed some AVX scalar MIN/MAX opcodes](https://github.com/ptitSeb/box64/pull/2913)
1. [\[LA64_DYNAREC\] Refined F3 0F 5D/5F MINSS/MAXSS opcodes](https://github.com/ptitSeb/box64/pull/2912)
1. [\[BOX32\] Enlarge xcb connects size for Linux Steam](https://github.com/ptitSeb/box64/pull/2910)
1. [\[ARM64_DYNAREC\] Fixed AVX VMOVMSKPD opcode](https://github.com/ptitSeb/box64/pull/2909)
1. [\[ARM64_DYNAREC\] Fixed AVX VMOVSS opcode](https://github.com/ptitSeb/box64/pull/2908)
1. [\[ARM64_DYNAREC\][INTERP] Fixed AVX VPERM2F128/VPERM2I128 opcodes ](https://github.com/ptitSeb/box64/pull/2907)
1. [\[LA64_DYNAREC\] Fixed 66 0F 3A 16 PEXTRD opcode](https://github.com/ptitSeb/box64/pull/2906)
1. [\[LA64_DYNAREC\] Fixed 66 F3 0F B8 POPCNT opcode](https://github.com/ptitSeb/box64/pull/2905)
1. [\[RV64_DYNAREC\] Added 1 more opcode](https://github.com/ptitSeb/box64/pull/2903)
1. [\[LA64_DYNAREC\] Added more opcodes](https://github.com/ptitSeb/box64/pull/2902)
1. [\[LA64_DYNAREC\] Fixed 66 0F 3A 0F PALIGNR for case where dst==src](https://github.com/ptitSeb/box64/pull/2894)
1. [\[LA64_DYNAREC\] Fixed 66 0F 38 06 PHSUBD opcode](https://github.com/ptitSeb/box64/pull/2893)
1. [\[LA64_DYNAREC\] Fixed F3 0F 53 RCPSS opcode](https://github.com/ptitSeb/box64/pull/2892)
1. [\[LA64_DYNAREC\] Fixed 66 0F 3A 21 INSERTPS opcode](https://github.com/ptitSeb/box64/pull/2891)
1. [\[LA64_DYNAREC\] Added and optimized more fastround=0 cases](https://github.com/ptitSeb/box64/pull/2890)
1. [\[LA64_DYNAREC\] Fixed 66 0F 38 14 BLENDVPS opcode](https://github.com/ptitSeb/box64/pull/2888)
1. [\[LA64_DYNAREC\] Fixed 66 0F 3A 0C/0D BLENDPS/D opcodes](https://github.com/ptitSeb/box64/pull/2887)
1. [\[LA64_DYNAREC\] Fixed a few GETEX usage](https://github.com/ptitSeb/box64/pull/2886)
1. [\[LA64_DYNAREC\] Fixed 0F E2 PSRAD opcode](https://github.com/ptitSeb/box64/pull/2885)
1. [\[LA64_DYNAREC\] Fixed 0F E3 PAVGW opcode](https://github.com/ptitSeb/box64/pull/2884)
1. [\[RV64_DYNAREC\] Fixed scalar version of 66 0F 3A 21 INSERTPS opcode](https://github.com/ptitSeb/box64/pull/2881)
1. [\[RV64_DYNAREC\] Fixed scalar and vector versions of mmx PSRAW/PSRAD](https://github.com/ptitSeb/box64/pull/2880)
1. [\[RV64_DYNAREC\] Fixed some mmx opcodes](https://github.com/ptitSeb/box64/pull/2879)
1. [\[INTERP\] Fixed 16bit version POPCNT](https://github.com/ptitSeb/box64/pull/2877)
1. [\[ARM64_DYNAREC\] Fixed PCMPESTRI fastpath SF flag computation](https://github.com/ptitSeb/box64/pull/2876)
1. [\[ARM64_DYNAREC\] Fixed a typo](https://github.com/ptitSeb/box64/pull/2875)
1. [\[ARM64_DYNAREC\] Fixed some edge cases for mmx PSRLQ](https://github.com/ptitSeb/box64/pull/2874)
1. [\[INTERP\] Added 66 F0 0F BA BTS opcode](https://github.com/ptitSeb/box64/pull/2872)
1. [\[TRACE\] Minor improvements to trace logging](https://github.com/ptitSeb/box64/pull/2871)
1. [\[WRAPPED\] Wrapped more functions for libc](https://github.com/ptitSeb/box64/pull/2870)

## DynamoRIO

## llama.cpp

## coreboot for riscv

## openocd

## opensbi

## u-boot

## RevyOS (Debian for Xuantie)

### Debian

## RT-Thread

- [utest: re-org utest framework (initial version)][rtt-10534]
- [doxygen: fix build error][rtt-10599]
- [bsp:k230:add support for temperature sensor driver][rtt-10609]
- [bsp: k230: increase object name max length to 16][rtt-10612]
- [bsp: k230: Provide a unified interrupt header file][rtt-10615]
- [doxygen: add howto for utest][rtt-10638]
- [bsp:k230:add pdma support for uart driver][rtt-10639]

Articles:
- [[文章] 基于k230 01studio开发板上的rtthread操作系统上的温度传感器驱动移植](https://bbs.elecfans.com/jishu_2499183_1_1.html)

[rtt-10534]:https://github.com/RT-Thread/rt-thread/pull/10534
[rtt-10599]:https://github.com/RT-Thread/rt-thread/pull/10599
[rtt-10609]:https://github.com/RT-Thread/rt-thread/pull/10609
[rtt-10612]:https://github.com/RT-Thread/rt-thread/pull/10612
[rtt-10615]:https://github.com/RT-Thread/rt-thread/pull/10615
[rtt-10638]:https://github.com/RT-Thread/rt-thread/pull/10638
[rtt-10639]:https://github.com/RT-Thread/rt-thread/pull/10639

## PLCT罗云翔测试团队

## SG2042/SG2044 Upstream

- [[PATCH 0/4] Add SPI NOR DTS node for SG2042 SoC and boards using it][lk-sg204x-1]
- [[PATCH 0/4] irqchip/sg2042-msi: Set irq type according to DT configuration][lk-sg204x-2]
- [[PATCH v2 0/3] irqchip/sg2042-msi: Set irq type according to DT configuration][lk-sg204x-3]
- [[PATCH 0/5] Add PCIe support to Sophgo SG2042 SoC][lk-sg204x-4]

[lk-sg204x-1]:https://lore.kernel.org/linux-riscv/20250813-sfg-spidts-v1-0-99b7e2be89d9@gmail.com/
[lk-sg204x-2]:https://lore.kernel.org/linux-riscv/cover.1756103516.git.unicorn_wang@outlook.com/
[lk-sg204x-3]:https://lore.kernel.org/linux-riscv/cover.1756169460.git.unicorn_wang@outlook.com/
[lk-sg204x-4]:https://lore.kernel.org/linux-riscv/cover.1756344464.git.unicorn_wang@outlook.com/

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
