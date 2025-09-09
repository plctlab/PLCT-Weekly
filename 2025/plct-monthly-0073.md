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
1. Authored/Co-authored JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/25765 (8359270: C2: alignment check should consider base offset when emitting arraycopy runtime call)
- https://github.com/openjdk/jdk/pull/25696 (8358892: RISC-V: jvm crash when running dacapo sunflow after JDK-8352504)

2. Reviewed JDK-mainline PRs:
- https://github.com/openjdk/jdk/pull/25578 (8358310: ZGC: riscv, ppc ZPlatformAddressOffsetBits may return a too large value)
- https://github.com/openjdk/jdk/pull/25438 (8357695: RISC-V: Move vector intrinsic condition checks into match_rule_supported_vector)
- https://github.com/openjdk/jdk/pull/25412 (8357626: RISCV: Tighten up template interpreter method entry code)
- https://github.com/openjdk/jdk/pull/25502 (8357968: RISC-V: Interpreter volatile reference stores with G1 are not sequentially consistent)
- https://github.com/openjdk/jdk/pull/25520 (8358105: RISC-V: Optimize interpreter profile updates)
- https://github.com/openjdk/jdk/pull/25652 (8358634: RISC-V: Fix several broken documentation web-links)
- https://github.com/openjdk/jdk/pull/25743 (8359218: RISC-V: Only enable CRC32 intrinsic when AvoidUnalignedAccess == false)
- https://github.com/openjdk/jdk/pull/25709 (8359105: RISC-V: No need for acquire fence in safepoint poll during JNI calls)
- https://github.com/openjdk/jdk/pull/25848 (8359801: RISC-V: Simplify Interpreter::profile_taken_branch)
- https://github.com/openjdk/jdk/pull/25923 (8360179: RISC-V: Only enable BigInteger intrinsics when AvoidUnalignedAccess == false)
- https://github.com/openjdk/jdk/pull/25924 (8360169: Problem list CodeInvalidationReasonTest.java on linux-riscv64 until JDK-8360168 is fixed)
- https://github.com/openjdk/jdk/pull/25976 (8360520: RISC-V: C1: Fix primitive array clone intrinsic regression after JDK-8333154)
- https://github.com/openjdk/jdk/pull/26004 (8360707: Globally enumerate all blobs, stubs and entries)

3. Reviewed JDK-21u/17u mainline PRs:
- https://github.com/openjdk/jdk21u-dev/pull/1845 (8358310: ZGC: riscv, ppc ZPlatformAddressOffsetBits may return a too large value)
- https://github.com/openjdk/jdk17u-dev/pull/3678 (8357968: RISC-V: Interpreter volatile reference stores with G1 are not sequentially consistent)

4. Proposed JDK-25u mainline PRs:
- https://github.com/openjdk/jdk25u/pull/4 (8359218: RISC-V: Only enable CRC32 intrinsic when AvoidUnalignedAccess == false)
- https://github.com/openjdk/jdk25u/pull/5 (8360179: RISC-V: Only enable BigInteger intrinsics when AvoidUnalignedAccess == false)
- https://github.com/openjdk/jdk25u/pull/6 (8359270: C2: alignment check should consider base offset when emitting arraycopy runtime call)

## Go

1. Authored/Co-authored Go-mainline CLs:
647596: runtime: unify C -> Go ABI transitions on riscv64 | https://go-review.googlesource.com/c/go/+/647596
all: add race support for riscv64 | https://github.com/mengzhuo/go/commit/a1b9b0d4faae07a31c599e00ee73aa6b4f882068 
https://github.com/golang/go/issues/64345
659175: cmd/link: generate proper attributes for riscv profile | https://go-review.googlesource.com/c/go/+/659175
657036: internal/bytealg: vector implementation of count 1 byte for riscv64 | https://go-review.googlesource.com/c/go/+/657036 
663778: cmd/asm, cmd/internal/obj: add zvbb/zvbc/zvkb for riscv64 | https://go-review.googlesource.com/c/go/+/663778
664155: cmd/asm, cmd/internal/obj: add crypto algorithm suites for riscv64 | https://go-review.googlesource.com/c/go/+/664155
664375: cpu: add crypto extensions detection for riscv64 | https://go-review.googlesource.com/c/sys/+/664375
663675: cmd/internal/obj: add crypto extension for riscv64 | https://go-review.googlesource.com/c/go/+/663675
696655: MinimumRequirements: update minimum requirements for riscv64 | https://go-review.googlesource.com/c/wiki/+/696655 
697615: cmd/compile: simplify zerorange on riscv64 | https://go-review.googlesource.com/c/go/+/697615

2. Reviewed Go-mainline CLs:
652717: doc, cmd/internal/obj/riscv: document the riscv64 assembler | https://go-review.googlesource.com/c/go/+/652717 
646736: internal/bytealg: vector implementation of equal for riscv64 | https://go-review.googlesource.com/c/go/+/646736
646737: internal/bytealg: vector implementation of compare for riscv64 | https://go-review.googlesource.com/c/go/+/646737
670876: riscv64: add support for RVV 1.0 instructions | https://go-review.googlesource.com/c/arch/+/670876
670875: riscv64: fix the path to the RISC-V extensions in spec.go | https://go-review.googlesource.com/c/arch/+/670875
cmd/compile: line number debug info regression in go1.25 around literal rewriting | https://github.com/golang/go/issues/74576
348389: cmd/compile: emit classify instructions for infinity tests on riscv64 | https://go-review.googlesource.com/c/go/+/348389
670875: riscv64: fix the path to the RISC-V extensions in spec.go | https://go-review.googlesource.com/c/arch/+/670875


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

- Buddy Compiler 主页地址 - https://buddy-compiler.github.io/
- Buddy Compiler As A Service (Buddy CAAS) - https://buddy.isrc.ac.cn/
- Buddy Compiler 开源之夏 2025 - https://summer-ospp.ac.cn/org/orgdetail/8d995d4c-b188-4690-9a53-c022dc7c19e3?lang=zh

**buddy-mlir**

- [Examples] Add f16 support for DeepSeekR1.
- [RVV] Update RVVEnvironment.md and sync to LLVM 21.0.0git
- [examples] Update E2E models pass pipeline to LLVM 21.0.0git
- [Torch] Add torch dynamo and triton based backend inductor docs and example.
- [Docs] Add introduction to PyTorch runtime.
- [VIR] Add dynamic vector type.
- [VIR] Add memory, basic, and arith operations.
- [VIR] Add lowering pass for set_vl and memory operations.
- [VIR] Add fma, constant, and broadcast operations conversion.
- [midend] Fixed multi-core computing capability of batchmatmul.
- [frontend] Update the matmul operator.
- [examples] Add fixed/scalable/vp SAXPY for evaluation.
- [examples] Add evaluation script for fixed SIMD and RVV.
- [examples] Add macOS support for VIR eval script.

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

Highlights:

解决性能瓶颈问题，采取特定量化方式的 LLM 模型推理速度可在原有向量化实现的基础上提升大约 80%。

Merged PRs:

1. [ggml-cpu : add basic RVV support for vector f32 ops](https://github.com/ggml-org/llama.cpp/pull/15057)
2. [ggml-cpu : optimize RVV kernels](https://github.com/ggml-org/llama.cpp/pull/15720)

## coreboot for riscv

本期没有新的进展。

## openocd

本期没有新的进展。

## opensbi

- 修正sbi_dbtr_read_trig从真实的csr读取。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008723.html)
- 添加1024个核心支持。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008715.html)
- 修正msiaddrcfgh中的lock机制，lock位只存在于mmsiaddrcfg中smsiaddrcfg中没有。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008721.html)
- 添加CVA6平台支持。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008727.html)
- 把openpiton移动到通用平台。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008734.html)
- 添加QiLai SoC支持。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008735.html)
- 简化fdt_parse_isa_extensions， 减少scratch内存占用。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008747.html)
- SmePMP改进。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008736.html)
- 扩展保留PMP条目。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008749.html)
- 添加 SiFive TMC0、SMC0驱动。[1](https://lists.infradead.org/pipermail/opensbi/2025-August/008757.html)

## u-boot

本期没有新的进展。

## eunomia-bpf

- [Zero instrucment LLM and AI agent observability in eBPF](https://github.com/eunomia-bpf/agentsight) ([Arxiv](https://www.arxiv.org/abs/2508.02736), will be presented at PACMI'25)
- [xpu-perf: eBPF wall clock profiler for CPU & GPU](https://github.com/eunomia-bpf/xpu-perf)
- [MCP Server for Linux Scheduler Management](https://github.com/eunomia-bpf/schedcp)
- [MCPtrace](https://github.com/eunomia-bpf/MCPtrace) MCP server: using eBPF to tracing your kernel
- bpftime:
  - [**GPU: support per-thread GPU ringbuffer**](https://github.com/eunomia-bpf/bpftime/pull/425)
    #425 merged 3 days ago
  - [**fix: cleanup when reattach**](https://github.com/eunomia-bpf/bpftime/pull/439)
    #439 merged last week
  - [**fix a race condition and improve performance in userspace ringbuf reservation**](https://github.com/eunomia-bpf/bpftime/pull/430)
    #430 merged last week
  - [**feat: Enhance file descriptor management and environment variable par…**](https://github.com/eunomia-bpf/bpftime/pull/438)
    #438 merged last week
  - [**feat: Add ARM64 Docker support and build test script**](https://github.com/eunomia-bpf/bpftime/pull/437)
    #437 merged last week
  - [**fix: Resolve compilation failure on AArch64**](https://github.com/eunomia-bpf/bpftime/pull/432)
    #432 merged 2 weeks ago
- Minor update to documents and tutorials

## RevyOS (Debian for Xuantie)

### Debian
本月主要维护 Debian riscv64 构建、测试的稳定： Debian 13 发布后，unstable 累计了大量的更新， 同时， debci team 反馈需要注意个别包引起的测试 worker 奔溃问题;
例行的包 upload 及 维护。

* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1110520#19 [jpeg-xl build]
* https://salsa.debian.org/lintian/lintian/-/merge_requests/596 [MR update]
* https://tracker.debian.org/news/1653227/accepted-strace-616ds-1-source-into-experimental/ [6.16 experimental]
* https://tracker.debian.org/news/1653477/accepted-strace-616ds-2-source-into-unstable/ [strace 6.16 unstable]
* https://fast-mirror.isrc.ac.cn/redleafos/dev/redleafos-base/ [redleados-base udate]
* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1111438 [ruyi ITP]
* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1102620 [construct RC done]
* https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1112166 [golang-1.24 FTBFS]
* http://vimer.7766.org:63015/chromium/139/ [chromium 139]
* https://www.eclipse.org/lists/epp-dev/msg07018.html [eclipse +1]
* https://github.com/ptitSeb/gl4es/issues/489 [gl4es issue]
* https://github.com/HardySimpson/zlog/issues/304 [zlog issue]

### Redleafos
Redleafos 本月主要有2个方面的更新：v2 kernel 的更新以及 v3 启动固件的更新。

* http://vimer.7766.org:63015/nanhu/packages/kernel/testing/  [验证后合并到 iscas mirror]


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

（包含 SAIL 和 ACT 测试部分）

1. RuyiSDK 多版本测试与生态完善
- 完成 RuyiSDK v0.39 版本全面测试，覆盖 LicheePi4A、RevyOS、ArchLinux、Debian、Deepin、Fedora、Ubuntu、openEuler 等多个操作系统和架构（x86_64、riscv64、aarch64），提交详细测试报告。
- 开发与测试工具持续增强：
  - 在 `ruyi-packaging` 提交10个PR，支持新包生成、Armbian适配、版本降级等功能。
  - 在 `packages-index` 提交8个PR，修复manifest问题并新增多个板卡镜像支持。
- 网站与文档优化：
  - 网站前端实现多语言Sitemap、主题系统优化、响应式布局改进、数据统计页面增强。
  - 规范代码块格式和术语使用。

2. 操作系统支持矩阵
- 新增多款开发板与系统支持，包括DC-ROMA系列、OrangePi-R2S/RV、PineTab-V等，更新Fedora、Debian、Irradium等系统测试报告。
- 元数据系统重构与前端优化
  - 实现`vendor`字段标准化，清理冗余测试数据。
  - 前端支持多语言Sitemap、响应式布局和测试报告筛选功能。
- 镜像检查工具开发：
  - 开发`image-checker`工具，提升镜像发布可靠性。
- 社区内容建设：
  - 在`ruyisdk.cn`发布多篇RISC-V MCU技术文章，丰富操作系统支持矩阵内容。

3. Sail/ACT
- Sail模型功能增强：
  - 实现Hypervisor扩展（VU/VS特权级）、ELF动态加载、本地中断处理等核心功能。
  - 开发JSON配置验证工具，提升配置可靠性。
- 测试框架优化：
  - 修复Zfinx测试用例，同步RISCOF插件，提升验证覆盖率。
- 推进Pydrofoil与XiangShan的diff测试支持。
  - 在ACT中修复Zdinx等ISA错误，更新多个压缩指令测试用例。

4. RISC-V教育推广
- 制作《LicheePi 4A ROS2实战》《K230 AI应用开发》等多部技术视频。
  - 提交玄铁课程《在LicheePi4A运行Deepseek》。

- 参加北京 World RISC-V Days，展示RuyiSDK在南湖笔记本上的应用
- 参加深圳 Elexcon 2025，展示PLCT Lab和RuyiSDK在RISC-V工具链、操作系统等方面的研发成果。
  
### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK v0.39测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/README.md)
    - [LPi4A openEuler 23.09 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_LicheePi4A_openEuler23.09_riscv64_测试结果.md)
    - [LPi4A openEuler 24.03 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250818/RUYI_%E5%8C%85%E7%AE%A1%E7%90%86_LicheePi4A_openEuler24.03_riscv64_%E6%B5%8B%E8%AF%95%E7%BB%93%E6%9E%9C.md)
    - [LPi4A RevyOS 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_LicheePi4A_RevyOS_riscv64_测试结果.md)
    - [RevyOS riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_RevyOS_riscv64_测试结果.md)
    - [Archlinux riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Archlinux_riscv64_测试结果.md)
    - [Archlinux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Archlinux_x86_64_测试结果.md)
    - [Debian sid riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Debiansid_riscv64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Fedora41 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Fedora41_x86_64_测试结果.md)
    - [Fedora42 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20250818/RUYI_%E5%8C%85%E7%AE%A1%E7%90%86_Fedora42_x86_64_%E6%B5%8B%E8%AF%95%E7%BB%93%E6%9E%9C.md)
    - [Ubuntu22.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Ubuntu22.04_x86_64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [openEuler24.03 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_openEuler24.03_riscv64_测试结果.md)
    - [openEuler24.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_openEuler24.03_x86_64_测试结果.md)
    - [openEuler25.03 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [Debian12 aarch64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Debian12_aarch64_测试结果.md)
    - [Debian12 x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Debian12_x86_64_测试结果.md)
    - [Gentoo Linux x86\_64 测试结果](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20250818/RUYI_包管理_Gentoo_x86_64_测试结果.md)

    - 缺陷：
      0.39.0 版本 packages-index 新增 1 个 issue:
      - [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)
      - RuyiSDK Eclipse Plugins 0.0.5 版本遗留 issue 如下：
        - 未配置 PATH 导致无法轻松访问 ruyi [ruyisdk/ruyisdk-eclipse-plugins#38](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/38)
      - 下载完成不够明显 [ruyisdk/ruyisdk-eclipse-plugins#39](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/39)

    - 资源
      - [本版本 litester 测试程序](https://github.com/weilinfox/ruyi-litester/tree/c918eeb6c1fa9e40eb8c52fb76e443b9815486e9)
      - [本版本自动化调度程序](https://github.com/weilinfox/ruyi-reimu/tree/6094edd22648e2084a2367633401fc569b92cc16)

- ruyi 仓库提交两个 Feature Request
    - [[Feature Request] check mounted partition before ruyi device provision dd block device #345](https://github.com/ruyisdk/ruyi/issues/345)
    - [[Feature Request] a command line interface as an alternative to device provision wizard #346](https://github.com/ruyisdk/ruyi/issues/346)

#### 1.2 RuyiSDK 开发和测试工具开发

- ruyi-packaging 仓库提交 10 个 pr
  - [riko: subcommand manifests to generate new tomls #26](https://github.com/ruyisdk/ruyi-packaging/pull/26)
  - [riko: fix unexpected behaviour when generating buildroot-sdk-sipeed-licheervnano tomls #27](https://github.com/ruyisdk/ruyi-packaging/pull/27)
  - [riko: raise exception when provisionable strategy not supported #28](https://github.com/ruyisdk/ruyi-packaging/pull/28)
  - [riko: add armbian riko.py #29](https://github.com/ruyisdk/ruyi-packaging/pull/29)
  - [riko: skip armbian #30](https://github.com/ruyisdk/ruyi-packaging/pull/30)
  - [riko: add support for nvchecker source regex and new policies config #31](https://github.com/ruyisdk/ruyi-packaging/pull/31)
  - [riko: better regex source support for new package revyos-lpi4a #32](https://github.com/ruyisdk/ruyi-packaging/pull/32)
  - [ruyi_packaging: new packages revyos-{meles,lcon4a} #33](https://github.com/ruyisdk/ruyi-packaging/pull/33)
  - [riko: allow generating downgrade manifests #34](https://github.com/ruyisdk/ruyi-packaging/pull/34)
  - [New package mars-buildroot-sdk and make riko easier to use #35](https://github.com/ruyisdk/ruyi-packaging/pull/35)
- packages-index 仓库提交 2 个 issue
  - [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)
  - [Jupiter and Megrez missing for MilkV product line support #104](https://github.com/ruyisdk/packages-index/issues/104)
- packages-index 仓库提交 8 个 pr
  - [board-image/buildroot-sdk-sipeed-licheervnano: add missing versions #95](https://github.com/ruyisdk/packages-index/pull/95)
  - [board-image/revyos-sipeed-lpi4a: new version 0.20250729.0 #96](https://github.com/ruyisdk/packages-index/pull/96)
  - [board-image/revyos-sipeed-lcon4a: new versions 0.20240720.0 and 0.20250729.0 #97](https://github.com/ruyisdk/packages-index/pull/97)
  - [board-image/revyos-milkv-meles: new version 1.20250729.0 #98](https://github.com/ruyisdk/packages-index/pull/98)
  - [Fix broken bianbu-bpi-f3 manifest and unify bianbu upstream_version format #99](https://github.com/ruyisdk/packages-index/pull/99)
  - [board-image/bianbu-{desktop,minimal}-spacemit-k1-sd: new versions from v2.0.0 to v3.0.0 #100](https://github.com/ruyisdk/packages-index/pull/100)
  - [Update board-image/bianbu-{desktop,minimal}-spacemit-k1-sd manifests #102](https://github.com/ruyisdk/packages-index/pull/102)
  - [board-image/debian-desktop-sdk-milkv-mars-cm-sd: add old version 1.0.5+3.6.1 #103](https://github.com/ruyisdk/packages-index/pull/103)

- 新的 ruyi deb 包下载源 [launchpad.net](https://launchpad.net/~ruyisdk-test/+archive/ubuntu/ruyi)

#### 1.3 RuyiSDK网站

- [docs: update case1 English version #189](https://github.com/ruyisdk/ruyisdk-website/pull/189)
- [Optimize the copy button showing strategy and fix the code highlight cutoff #190](https://github.com/ruyisdk/ruyisdk-website/pull/190)（修复长代码行，灰底只渲染一次导致滚动后没有底色的问题，但测试感觉没有解决问题）
- [Update RuyiInLive for more data and a clear indicator to stats page #192](https://github.com/ruyisdk/ruyisdk-website/pull/192)
- [Feat/newscase auto switch #193](https://github.com/ruyisdk/ruyisdk-website/pull/193)
- [NewsShowcase with better visuals #194](https://github.com/ruyisdk/ruyisdk-website/pull/194) 优化了鼠标移上去时的图片放大圆角
- [Improved image spacing for popups #195](https://github.com/ruyisdk/ruyisdk-website/pull/195)
- [deleted some code #198](https://github.com/ruyisdk/ruyisdk-website/pull/198)
- [Synchronize ruyisdk biweekly #202](https://github.com/ruyisdk/ruyisdk-website/pull/202)
- [docs: Shorten titles to improve typography #206](https://github.com/ruyisdk/ruyisdk-website/pull/206)
- [Feat/bar chart #199](https://github.com/ruyisdk/ruyisdk-website/pull/199)
- [Feat/newscase auto switch #200](https://github.com/ruyisdk/ruyisdk-website/pull/200)
- [Re-patch for codeblock update #201](https://github.com/ruyisdk/ruyisdk-website/pull/201)
- [feat: add UnoCSS integration #208](https://github.com/ruyisdk/ruyisdk-website/pull/208)
- [Feat/add slide #209](https://github.com/ruyisdk/ruyisdk-website/pull/209)
- [Update/newscase #210](https://github.com/ruyisdk/ruyisdk-website/pull/210)
- [Optimize stats page colouring #211](https://github.com/ruyisdk/ruyisdk-website/pull/211)
- [Update stats page's colouring to ensure visibility #212](https://github.com/ruyisdk/ruyisdk-website/pull/212)
- [pages: modify statistical data page text #196](https://github.com/ruyisdk/ruyisdk-website/pull/196)
- 210 [ruyisdk/ruyisdk-website#210](https://github.com/ruyisdk/ruyisdk-website/pull/210)
- Pull 209 [ruyisdk/ruyisdk-website#209](https://github.com/ruyisdk/ruyisdk-website/pull/209)
  On the document page, added a smooth sliding positioning function to the navigation bar
- Pull 204 [ruyisdk/ruyisdk-website#204](https://github.com/ruyisdk/ruyisdk-website/pull/204)
- Pull 203 [ruyisdk/ruyisdk-website#203](https://github.com/ruyisdk/ruyisdk-website/pull/203)
  - added blogs:
    2025-05-13-ruyi-0.33.md
    2025-05-27-ruyi-0.34.md
    2025-06-10-ruyi-0.35.md
    2025-06-24-ruyi-0.36.md
    2025-07-08-ruyi-0.37.md
    2025-07-22-ruyi-0.38.md
    2025-08-12-ruyi-0.39.md

- Pull 200 [ruyisdk/ruyisdk-website#200](https://github.com/ruyisdk/ruyisdk-website/pull/200)
  - Added auto-switching function
  - add the ability of switching since the newscase model in the vision 
- Pull 199 [ruyisdk/ruyisdk-website#199](https://github.com/ruyisdk/ruyisdk-website/pull/199)
  - optimized the position of barchart;
  - changed the height of card;
  - shortened the distance between label and bar
- Pull 198 [ruyisdk/ruyisdk-website#198](https://github.com/ruyisdk/ruyisdk-website/pull/198)
  - deleted some commented model
- Pull 187 [ruyisdk/ruyisdk-website#187](https://github.com/ruyisdk/ruyisdk-website/pull/187)
  - updated the static:
    Optimized language version;
    Corrected FlipCounter flip direction and remove double-line display issue
    optimized both the mobile and pc style of static page
- Pull 185 [ruyisdk/ruyisdk-website#185](https://github.com/ruyisdk/ruyisdk-website/pull/185)
  - Updated News on Jul 30
- Pull 183 [ruyisdk/ruyisdk-website#183](https://github.com/ruyisdk/ruyisdk-website/pull/183)
  - Optimize project architecture
- Pull 180 [ruyisdk/ruyisdk-website#180](https://github.com/ruyisdk/ruyisdk-website/pull/180)
  - custumed footer style
  - Moved QR code to better align with visual layout
  - Applied changes for both "en" and "de" localized footers
- Pull 179 [ruyisdk/ruyisdk-website#179](https://github.com/ruyisdk/ruyisdk-website/pull/179)
  - Adjusted the redirect address of the revyos link, and the Chinese interface will be redirected to zh, and the English and German interfaces will be redirected to en
- Pull 177 [ruyisdk/ruyisdk-website#177](https://github.com/ruyisdk/ruyisdk-website/pull/177)
  - Adjusted WeChat QR code dimensions for better layout consistency
  - Updated QQGroup component styling to match light theme
  - Improved overall visual harmony on the contact page
- Pull 184 https://github.com/ruyisdk/ruyisdk-website/pull/184
  - Allow using prop "showTitleCopyButton" to control the toggle of main copy button.
- Pull 190 https://github.com/ruyisdk/ruyisdk-website/pull/190
- Pull 201 https://github.com/ruyisdk/ruyisdk-website/pull/201
  - Optimize the copy button showing strategy
  - Fix the code highlight cutoff
- Pull 192 https://github.com/ruyisdk/ruyisdk-website/pull/192
  - Now RuyiInLive display the data including active users, download and installation count.
  - Update for a clear indiactor to new Stats page.
  - Add translations to new strings
- Pull 194 https://github.com/ruyisdk/ruyisdk-website/pull/194
  - Update NewsShowcase for avoid cropping in hovering effects.
- Pull 195 https://github.com/ruyisdk/ruyisdk-website/pull/195
  - Improving the placing and cropping strategy to make sure center part of image displayed to user.
- Pull 211 https://github.com/ruyisdk/ruyisdk-website/pull/211
- Pull 212 https://github.com/ruyisdk/ruyisdk-website/pull/212
  - Adapt the Ruyi accent colours to the new stats page.
  - Adapt mobile colouring
- Pull 214 https://github.com/ruyisdk/ruyisdk-website/pull/214
  - Add automatic stripping for CodeBlock, for better documentation formats.

#### 1.4 RuyiSDK文档

- docs 仓库提交 4 个 issue
  - [文档代码块格式不统一 #93](https://github.com/ruyisdk/docs/issues/93)
  - [链接中的 RuyiSDK 大小写问题 #94](https://github.com/ruyisdk/docs/issues/94)
  - [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)
  - [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)

#### 1.5 RuyiSDK会议和技术分享

- 08/08 北京 World RISC-V Days 2025 参会和演示
- 08/26 深圳 Elexcon 参展（ruyisdk展台）
- [VSCode RISC-V 插件技术+AI辅助变成能力边界+理想的 RISC-V 开发环境构想](https://www.bilibili.com/video/BV1GyePzBEpw/?spm_id_from=333.337.search-card.all.click&vd_source=de633d4318be770bdffc3275f1e20c2c)

- [RISCV插件技术技术分享PPT](https://github.com/ddsfda99/vscode-riscv-plugin-dev/blob/main/presentations/RISCV插件技术报告-2025-08-13.pptx)

- [RuyiSDK 工具链学习、安装与使用b站技术分享视频](https://www.bilibili.com/video/BV14heGzJEgQ)

- [RuyiSDK使用方法技术分享PPT](https://github.com/ddsfda99/vscode-riscv-plugin-dev/blob/main/presentations/RuyiSDK使用方法-2025-08-20.pptx)

- [RuyiSDK安装与使用文档](https://github.com/ddsfda99/vscode-riscv-plugin-dev/blob/main/docs/RuyiSDK安装与使用-2025-08-20.md)

- [Milk-V Duo 开发板实践：安装Alpine系统和配置并使用RuyiSDK
b站技术分享视频](https://www.bilibili.com/video/BV1X8hRzuEBh)

- [在 Milk-V Duo 上跑通 Alpine 与 RuyiSDK 的完整实践PPT](https://github.com/ddsfda99/vscode-riscv-plugin-dev/blob/main/presentations/在 Milk-V Duo 上跑通 Alpine 与 RuyiSDK 的完整实践-2025-08-27.pptx)

- [在 Milk-V Duo 上跑通 Alpine 与 RuyiSDK 的完整实践文档](https://github.com/ddsfda99/vscode-riscv-plugin-dev/blob/main/docs/在 Milk-V Duo 上跑通 Alpine 与 RuyiSDK 的完整实践-2025-08-27.md)

#### 1.6 RuyiSDK 实习生面试

- 实习生面试考核题 [J162](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month26/jy.md)

#### 1.7 RuyiSDK测试服务器设备维护

- 安装RuyiSDK测试服务器，2台Pioneerbox+RevyOS

### 2. 操作系统支持矩阵

#### 2.1 开发板操作系统支持测试

- [Add new boards, support status,test reports,documents and CI updates ](https://github.com/ruyisdk/support-matrix/pull/350)
- [docs(treewide): unify case of distro names & fix typo](https://github.com/ruyisdk/support-matrix/pull/351)
- [LiP3A: Add irradium test report (good).](https://github.com/ruyisdk/support-matrix/pull/352)
- [OrangePi RV2: Add BredOS test report (good).](https://github.com/ruyisdk/support-matrix/pull/354)
- [LiP4A: Bump Fedora Version to 42](https://github.com/ruyisdk/support-matrix/pull/356)
- [OrangePi RV2: Add Debian Trixie test report (basic).](https://github.com/ruyisdk/support-matrix/pull/357)
- [docs: Replace device names with placeholders](https://github.com/ruyisdk/support-matrix/pull/359)
- [docs: Correct sys_ver in LicheePi4A RevyOS README](https://github.com/ruyisdk/support-matrix/pull/360)
- [Duo: Bump Buildroot to v2.0.1](https://github.com/ruyisdk/support-matrix/pull/363)
- [EIC7700X Board information supplement](https://github.com/ruyisdk/support-matrix/pull/364)
- [Update for LPi3A & MUSE Pi Pro](https://github.com/ruyisdk/support-matrix/pull/355)
- [VF2: fix link typo](https://github.com/ruyisdk/support-matrix/pull/361)
- [[Image Check] Pine64 Star64 images disappeared on armbian community release 353](https://github.com/ruyisdk/support-matrix/issues/353)
- [EIC7700 信息补全](https://github.com/ruyisdk/support-matrix/pull/364)
- [Arch Linux @ Duo S](https://github.com/ruyisdk/support-matrix/pull/365)
- [litmus-tests-riscv K1 测试报告](https://github.com/QA-Team-lo/litmus-tests/commit/4febdc7be881c011d169697452e5282452d9ab55)
- [Add new boards, support status,test reports,documents and CI updates ](https://github.com/ruyisdk/support-matrix/pull/350)
  - New Boards
    DC-ROMA Laptop2, DC-ROMA_Mainboard, DC-ROMA_Mainboard2, DC-ROMA_PAD2, DP1000-EVB, EBC77, MUSE BOOK, OrangePi-R2S, OrangePi-RV, PineTab-V, Taurus, Titan
  - New Support Status (by Operating System)
    - Android: DC-ROMA_PAD2
    - Bianbu: Jupiter (2), LP3A (2), MUSE Book (3),
    - Bredos: Bit-Brick K1
    - Debian: OrangePi-R2S, OrangePi-RV, PineTab-V
    - Deepin: DP1000-EVB, Jupiter, LP3A, MUSE Book, Titan
    - Fedora: BPI-F3 (3), BeagleV-Ahead (2), DC-ROMA_Mainboard, DC-ROMA_Mainboard2 (3), DP1000-EVB, Jupiter (3), LP3A, LP4A (2), MUSE Book (3), Mars (2), Megrez (3), Meles, P550 (4), Taurus, Titan, VF2 (2)
    - Gentoo: PineTab-V
    - Irradium: BPI-F3, Jupiter, LP3A, NeZha, OrangePi-RV, Megrez
    - OpenCloudOS: DP1000-EVB
    - OpenKylin: Megrez
    - OpenWrt: OrangePi-R2S
    - Pmos: BPI-F3, DC-ROMA_PAD2, VF2
    - RHEL: P550
    - RockOS: P550
    - Ubuntu: DC-ROMA_Laptop2, DC-ROMA_Mainboard (2), DC-ROMA_Mainboard2, DC-ROMA_PAD2,
    - Yocto: PineTab-V
  - New Test Reports
    Good
    - Bit-Brick K1: Bianbu 3.0 Desktop Lite
    - Bit-Brick K1: Bianbu 3.0 Desktop
    - Bit-Brick K1: Bianbu Star 2.1.5
    - Bit-Brick K1: Bredos
    Basic
    - Bit-Brick K1: Bianbu 3.0 Minimal
    - Jupiter: Bianbu 3.0 Minimal (tested by @KevinMX)
    - Megrez: OpenCloudOS (tested by @KevinMX)
    CFT
    - EBC77: ubuntu
  - Metadata Updates
    - `sys`: Changed from `LiteOS` to `liteos` (lowercase).
    - New Frontmatter Field: `provider`. This field will be added to reports where the image originates from a vendor customization, a community, or is not directly from Dirtro.
  - Document Changes
    - `CONTRIBUTING`: Removed documentation for deleted scripts, updated to use the current frontmatter format and file structure, and added more support status information.
    - `report-template`: Updated to use the new, simplified report structure.
  - CI Updates
    - Deleted unused script: `package-index-sync`.
    - Transferred existing CI tasks (`table`, `metadata`) to use `uv`.
  - [Delete metadata no longer use, add nuttx](https://github.com/apr3vau/support-matrix/pull/1)
- 补充 TH1520 开发板信息，更正 LPi4A RevyOS 系统版本，将存储设备名替换成占位符（避免误操作），Orange Pi RV2 Debian，Orange Pi RV2 BredOS，LPi4A Fedora 42，LPi3A Irradium，Duo buildroot v2.0.1
  - https://github.com/ruyisdk/support-matrix/pull/352
  - https://github.com/ruyisdk/support-matrix/pull/354
  - https://github.com/ruyisdk/support-matrix/pull/356
  - https://github.com/ruyisdk/support-matrix/pull/357
  - https://github.com/ruyisdk/support-matrix/pull/359
  - https://github.com/ruyisdk/support-matrix/pull/360
  - https://github.com/ruyisdk/support-matrix/pull/362
  - https://github.com/ruyisdk/support-matrix/pull/363
  
#### 2.2 操作系统支持矩阵Web UI

入口：https://github.com/QA-Team-lo/support-matrix-frontend

- 修改组件文件结构
- 重新设计测试报告数据结构,分离原始支持矩阵测试报告的文件结构,分为原始开发板,原始测试报告,单开发板,单系统,全站数据
- 重构数据获取与处理代码,分离工具函数,增加数据检查与统计函数
- 使用新数据结构更新测试报告页,更新 UI,增加按处理器和时间筛选和多选功能,调整列表展示数据与宽度
- 更新 i18n,更新 astro 等

#### 2.3 ruyisdk.cn操作系统支持矩阵板块

- [RISC-V MCU 漫游 (3)：博流传奇之 BL602](https://ruyisdk.cn/t/topic/1032)
- [RISC-V MCU 漫游 (4)：博流传奇之 BL70x 系列（上）](https://ruyisdk.cn/t/topic/1040)
- [RISC-V MCU 漫游 (5)：博流传奇之 BL70x 系列（下）](https://ruyisdk.cn/t/topic/1264)
- [RISC-V MCU 漫游 (6)：黄紫色的 ESP32 之 ESP32-S3 系列](https://ruyisdk.cn/t/topic/1296)
- https://ruyisdk.cn/t/topic/957
- https://ruyisdk.cn/t/topic/1054
- https://ruyisdk.cn/t/topic/1182
- https://ruyisdk.cn/t/topic/1239
- https://ruyisdk.cn/t/topic/942
- https://ruyisdk.cn/t/topic/1087
- https://ruyisdk.cn/t/topic/1192
  
#### 2.4 会议和技术分享

- 深圳 Elexcon 2025（RuyiSDK 展台）
    - https://mp.weixin.qq.com/s/XvIFFTCuAGyKHVP8irzIXw
    - 展出物：Milk-V Meles + [RuyiSDK 介绍视频](https://www.bilibili.com/video/av664932287/) + PPSSPP / 洞窟物语 Demo
    - [展位布置](https://github.com/user-attachments/assets/af21fc0c-e17e-45cb-9260-4512900f00c2)
    - [Meles 测试报告](https://matrix.ruyisdk.org/reports/Meles-RevyOS-README/)
    - 实习生在甲辰计划展位服务一天，为观众提供了甲辰计划相关信息的介绍。
- [RV Infra Slide](https://github.com/KevinMX/PLCT-Works/tree/main/reports/month28/RVInfra/)
- ruyisdk上周报
  - https://github.com/ruyisdk/wechat-articles/pull/176
  - https://github.com/ruyisdk/wechat-articles/pull/174

### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- SAIL
  - <https://github.com/riscv/sail-riscv/pull/538> Make \{m,s\}status\[VS\] read-only zero when Ext_V not supported
New activity
  - <https://github.com/riscv/sail-riscv/pull/1251> Add basic syscall support
  - <https://github.com/riscv/sail-riscv/pull/538> Add Zicbop extension
  - <https://github.com/riscv/sail-riscv/pull/1099> Move RVFI to C
  - [#1203](https://github.com/riscv/sail-riscv/pull/1203) : 简化Sail-RISCV 代码函数` riscv_insts_vext_mem`签名, 使代码更简洁易读
  - [#1229](https://github.com/riscv/sail-riscv/pull/1229) : 删除不必要函数`vlenwidth_bytesnumber`, 减少运行时函数调用, 提高运行效率
  - [#1243](https://github.com/riscv/sail-riscv/pull/1243) : 修复Sail-RISCV代码逻辑, 保证V扩展指令在提前退出时也能将vstart寄存器设为0
  - [#1431](https://github.com/rems-project/sail/pull/1431) : 删除在当前实现中不被调用的函数`fast_update_subrange`
  - [#792](https://github.com/riscv/sail-riscv/pull/792) : 重新rebase, 并决定在删除相关函数签名后合入
  - [#654](https://github.com/riscv/sail-riscv/pull/654) : 由于当前主线尚无需此功能遂关闭
  - [sail_config.c: Add cJSON error message output.](https://github.com/rems-project/sail/pull/1388)
  - [config: add template rvd.json.in to generate config](https://github.com/riscv/sail-riscv/pull/1151)
  - [Validate JSON config file with schema](https://github.com/riscv/sail-riscv/pull/1161)
  - [Add DYN (Position-Independent Executable file) support](https://github.com/riscv/sail-riscv/pull/1171)
  - [riscv_sim.cpp: add SIGINT processor.](https://github.com/riscv/sail-riscv/pull/1172)
  - [valijson](https://github.com/riscv/sail-riscv/pull/1173)
  - [Bump cJSON version.](https://github.com/rems-project/sail/pull/1389)

- Pydrofoil
  - [Pydrofoil difftest workload](https://github.com/OpenXiangShan/XiangShan/pull/4926)
    Basic functionalities (e.g. difftest_regcpy, difftest_csrcpy, difftest_skip_one) are available yet need further test to ensure correctness.
  - [Documenting Pydrofoil Building with Nix](https://github.com/pydrofoil/pydrofoil/pull/140), and [Out-of-tree Nix support](https://github.com/definfo/pydrofoil/tree/nix-support)

- [AUR sail-model](https://aur.archlinux.org/packages/sail-model)
  
- ACT
  - 提交了一个修复缺失的压缩非法指令缺失覆盖的问题[#695](https://github.com/riscv-non-isa/riscv-arch-test/pull/695)
  - 更新了readme说明文档并成功合入[#676](https://github.com/riscv-non-isa/riscv-arch-test/pull/676)
  - 更新了修复Zdinx ISA错误的bug并成功合入[#651](https://github.com/riscv-non-isa/riscv-arch-test/pull/651)

  | 测试用例名 | 所属拓展 | 更新测试用例数 | 地址                                                         |
  | ---------- | -------- | -------------- | ------------------------------------------------------------ |
  | cadd       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi16sp  | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi4spn  | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cand       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | candi      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cbeqz      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cbnez      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cj         | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cjal       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cjalr      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cjr        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cli        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clui       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clw        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clwsp      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cmv        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cor        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cslli      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csrai      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csrli      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csub       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csw        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cswsp      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cxor       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |

- Issues
  - <https://github.com/riscv/sail-riscv/pull/1250> Add syscall support
  - [#1428](https://github.com/rems-project/sail/issues/1428) : 明确Sail配置无法动态检查配置合法性的问题
  - [#1204](https://github.com/riscv/sail-riscv/issues/1204) : 参与对`fprintf`替代方案讨论
  - [#1239](https://github.com/riscv/sail-riscv/issues/1239) : 明确Sail-RISCV 存在`sc`时不会检查pmp的bug
  - [sail cannot be removed](https://github.com/rems-project/sail/issues/1401)
  - [Is there a good reason why some of our external libs are fetched dynamically and some are just part of the repo? We have softfloat and are about to add CLI11 as well now as part of the repo.](https://github.com/riscv/sail-riscv/issues/1164)
  - [Add AUR package for sail bin](https://github.com/rems-project/sail/issues/1381)
  - [where does this binnary c_emulator/reset_vec.bin came from?](https://github.com/riscv/sail-riscv/issues/1154)
  - [openSBI with sail-riscv](https://github.com/riscv/sail-riscv/issues/886)
  - [Fix Pydrofoil build on rpypkgs](https://github.com/rpypkgs/rpypkgs/issues/1)
    Current Makefile-based build procedure is fragile with unstable deps, such as sail-riscv, isla.
    [rpypkgs](https://github.com/rpypkgs/rpypkgs) maintains RPython/PyPy projects (including pydrofoil-riscv), and is working on Pydrofoil scripting API support.
    Note that Pydrofoil scripting API isn't supported.
  - [Discussion about refactoring Pydrofoil build targets](https://github.com/pydrofoil/pydrofoil/issues/142)
    Pydrofoil highly depends on PyPy2/RPython infrastructure, which is somehow fragile in case of out-of-tree maintenanace.
  
#### 3.2 SAIL技术分享
  
- 8.23 RISC-V 研讨会：SAIL-RISCV 如何攻克 RISC-V 可配置性 [PPT](https://github.com/trdthg/plct/blob/main/doc/sail/json-config/main.pdf)
- Pydrofoil技术分享
- [Document for Pydrofoil difftest workload](https://github.com/definfo/pydrofoil/blob/a5d158f9eb0322d0ca27d0820a7c160a057c966a/README_difftest.md)

#### 3.3 SAIL会议

- tech-golden-model meeting [`08.18`, `08.25`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
  - PLCT建议创建预发布版本或测试版本，并加入 CI 自动发布预发布版本。
  - Json 验证方案
    - PLCT 选择了 valijson + nlohmann/json, 已经提交了两种方案, 分别使用 FetchContent 和直接 push 库源代码, Tim 建议直接推源代码, 认为会更简洁, 尽管可能导致难以审查.
    - 结论, 最终目标是 sail 自动生成 C 代码的验证函数, 但当前的折中方案是用 Boon
  - PLCT 建议 CLI 改进, 需要修复 --trace 选项
  - PLCT 提到 ELF 文件动态加载, 目前难以确定偏移量, 需要检查 ELF 是否位置无关
    - Tim 建议使用 Elfio 库代替 sail 目前的 elf 处理代码.
  - PLCT 提到 cJSON 版本老旧, Alasdair 解释为了实现任意精度整数, sail 的 cJSON 代码被修改过, 将所有的数字都视为字符串解析
  - PLCT 建议用看板或者里程碑等工具跟踪发布进度. Prashanth 后续研究
- 8.21 东亚双周会 [PPT](https://docs.google.com/presentation/d/1wFh9WXinsaQhMQgQBXODzm8KRUB_JeGJuWgfOXwNeiA/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 8.8 北京 World RISC-V Days 2025 参会和演示 [文章](https://mp.weixin.qq.com/s/OW8OAXUPN-kWurjVjk2VsQ)
- 8.26-8.28 深圳 Elexcon 2025，PLCT Lab 展位 [文章](https://mp.weixin.qq.com/s/HqU26th_RpWFhKcK4IQLmQ)

### 4. 独立项目/应用软件生态观测

#### 4.1 北京 World RISC-V Days 2025

- 展示物准备
- 展示RuyiSDK 在 南湖笔记上的应用

#### 4.2 深圳 Elexcon 2025 

- 主导 PLCT Lab和RuyiSDK站台
  - 展示物准备
  - 海报准备
  - 现场布展
  - 展出服务
- 参与 RevyOS和甲辰计划站台
  - 展出服务

#### 4.3 RuyiSDK GNU Tests

- [curl 的新版本修复了导致测试失败的 bug](https://github.com/QA-Team-lo/ruyisdk-gnu-tests/commit/ddfa3f91e3441e8ec0d3be45bd87881c36511c8b)

#### 4.4 玄铁课程

-  提交玄铁课程《在Licheepi4A运行Deepseek》

#### 4.5 英麒 RISC-V Lab

-  [实习生成长手册](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/yq_Get_started.md)

#### 4.6 eweOS

- [完成软件包移植 `radeontop`](https://os.ewe.moe/pkginfo/main/radeontop/riscv64)

#### 4.7 Litmus-Tests

- [litmus-tests-riscv on sg2042测试报告](https://github.com/QA-Team-lo/litmus-tests/tree/main/SG2042)

#### 4.8 FluidX3D on riscv

- 编译 PoCL(rv64gc)和安装到 opencl-icd 
- 在 `-march=rv64gc -mabi=lp64d` 运行异常,benchmark 结果异常的高,在在修改代码调试后为 LBM 构造函数静默失败
- 通过对代码仓库多步调试最终发现为 opencl kernel LBM 函数部分存在异常,加入对 kernel.cpp 相关探针 进行二分调试,将可能和平台相关的函数换为和平台无关的函数
- 发现将代码部分注释后,opencl kernel 可成功运行,得分在 490-550 左右,符合预期
- 初步判断是 llvm 编译器后端问题,尝试修改代码逻辑,降低编译器优化难度后问题依然没有解决

### 5. RISC-V教育和短视频

#### 5.1 短视频课程设计

- 项目迭代计划
https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Plan_Document
- 项目迭代回溯
https://github.com/DuoQilai/PLCT-Works/tree/main/RISC-V_short_video/Review_Document
- 新人手册
https://github.com/DuoQilai/PLCT-Works/blob/main/RISC-V_short_video/baby_book.md
  
#### 5.2 短视频设计和实现

- [RuyiSDK案例-学习使用qemu、llvm和cmake](https://www.bilibili.com/video/BV1mjefzLEL6/)

#### 5.3 短视频剧本和文档、素材
- [口播稿（RuyiSDK使用 qemu llvm cmake）](https://github.com/jason-hue/plct/blob/main/%E5%8F%A3%E6%92%AD%E7%A8%BF/%E5%8F%A3%E6%92%AD%E7%A8%BF%EF%BC%88RuyiSDK%E4%BD%BF%E7%94%A8%20qemu%20llvm%20cmake%EF%BC%89.md)

- [RuyiSDK文档-Taisei 交叉编译测试结果](https://github.com/jason-hue/plct/blob/main/%E6%B5%8B%E8%AF%95%E6%96%87%E6%A1%A3/RuyiSDK%E6%96%87%E6%A1%A3-Taisei%20%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91%E6%B5%8B%E8%AF%95%E7%BB%93%E6%9E%9C.md)

#### 5.4 短视频技术分享

- [RISC-V教育和南京合作伙伴RISC-V Lab协同建设ppt](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISC-V%E6%95%99%E8%82%B2%E5%92%8C%E5%8D%97%E4%BA%AC%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4RISC-V%20Lab%E5%8D%8F%E5%90%8C%E5%BB%BA%E8%AE%BE.pptx)

### 6. 职工

#### 6.1 蔡玮霖

1. 指导 Web 实习生重新设计了官网的数据统计页面，更新博客和双周报，同时有一些其他零散的更新
2. 在 ruyi-packaging 仓库完善打包工具，并使用打包工具生成配置，向 packages-index 提交 pr
3. 将文档、 packages-index 之前已知问题同步到 issue
4. 提交对 Ruyi 的新功能请求
5. 整理已有的 Ruyi 的 deb 包打包到新的仓库

- Ruyi v0.39.0 测试完成 [pr](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/78)
- ruyi 仓库提交两个 Feature Request
  - [[Feature Request] check mounted partition before ruyi device provision dd block device #345](https://github.com/ruyisdk/ruyi/issues/345)
  - [[Feature Request] a command line interface as an alternative to device provision wizard #346](https://github.com/ruyisdk/ruyi/issues/346)
- ruyisdk-website 仓库审核 18 个 pr
  - [docs: update case1 English version #189](https://github.com/ruyisdk/ruyisdk-website/pull/189)
  - [Optimize the copy button showing strategy and fix the code highlight cutoff #190](https://github.com/ruyisdk/ruyisdk-website/pull/190)（修复长代码行，灰底只渲染一次导致滚动后没有底色的问题，但测试感觉没有解决问题）
  - [Update RuyiInLive for more data and a clear indicator to stats page #192](https://github.com/ruyisdk/ruyisdk-website/pull/192)
  - [Feat/newscase auto switch #193](https://github.com/ruyisdk/ruyisdk-website/pull/193)
  - [NewsShowcase with better visuals #194](https://github.com/ruyisdk/ruyisdk-website/pull/194) 优化了鼠标移上去时的图片放大圆角
  - [Improved image spacing for popups #195](https://github.com/ruyisdk/ruyisdk-website/pull/195)
  - [deleted some code #198](https://github.com/ruyisdk/ruyisdk-website/pull/198)
  - [Synchronize ruyisdk biweekly #202](https://github.com/ruyisdk/ruyisdk-website/pull/202)
  - [Update/blogs #203](https://github.com/ruyisdk/ruyisdk-website/pull/203)
  - [docs: Shorten titles to improve typography #206](https://github.com/ruyisdk/ruyisdk-website/pull/206)
  - [Feat/bar chart #199](https://github.com/ruyisdk/ruyisdk-website/pull/199)
  - [Feat/newscase auto switch #200](https://github.com/ruyisdk/ruyisdk-website/pull/200)
  - [Re-patch for codeblock update #201](https://github.com/ruyisdk/ruyisdk-website/pull/201)
  - [feat: add UnoCSS integration #208](https://github.com/ruyisdk/ruyisdk-website/pull/208)
  - [Feat/add slide #209](https://github.com/ruyisdk/ruyisdk-website/pull/209)
  - [Update/newscase #210](https://github.com/ruyisdk/ruyisdk-website/pull/210)
  - [Optimize stats page colouring #211](https://github.com/ruyisdk/ruyisdk-website/pull/211)
  - [Update stats page's colouring to ensure visibility #212](https://github.com/ruyisdk/ruyisdk-website/pull/212)
- ruyisdk-website 仓库提交 1 个 pr
  - [pages: modify statistical data page text #196](https://github.com/ruyisdk/ruyisdk-website/pull/196)
- ruyi-packaging 仓库提交 10 个 pr
  - [riko: subcommand manifests to generate new tomls #26](https://github.com/ruyisdk/ruyi-packaging/pull/26)
  - [riko: fix unexpected behaviour when generating buildroot-sdk-sipeed-licheervnano tomls #27](https://github.com/ruyisdk/ruyi-packaging/pull/27)
  - [riko: raise exception when provisionable strategy not supported #28](https://github.com/ruyisdk/ruyi-packaging/pull/28)
  - [riko: add armbian riko.py #29](https://github.com/ruyisdk/ruyi-packaging/pull/29)
  - [riko: skip armbian #30](https://github.com/ruyisdk/ruyi-packaging/pull/30)
  - [riko: add support for nvchecker source regex and new policies config #31](https://github.com/ruyisdk/ruyi-packaging/pull/31)
  - [riko: better regex source support for new package revyos-lpi4a #32](https://github.com/ruyisdk/ruyi-packaging/pull/32)
  - [ruyi_packaging: new packages revyos-{meles,lcon4a} #33](https://github.com/ruyisdk/ruyi-packaging/pull/33)
  - [riko: allow generating downgrade manifests #34](https://github.com/ruyisdk/ruyi-packaging/pull/34)
  - [New package mars-buildroot-sdk and make riko easier to use #35](https://github.com/ruyisdk/ruyi-packaging/pull/35)
- packages-index 仓库提交 2 个 issue
  - [BananaPi BPI-F3 eMMC storage variant did not refer to any combo #101](https://github.com/ruyisdk/packages-index/issues/101)
  - [Jupiter and Megrez missing for MilkV product line support #104](https://github.com/ruyisdk/packages-index/issues/104)
- packages-index 仓库提交 8 个 pr
  - [board-image/buildroot-sdk-sipeed-licheervnano: add missing versions #95](https://github.com/ruyisdk/packages-index/pull/95)
  - [board-image/revyos-sipeed-lpi4a: new version 0.20250729.0 #96](https://github.com/ruyisdk/packages-index/pull/96)
  - [board-image/revyos-sipeed-lcon4a: new versions 0.20240720.0 and 0.20250729.0 #97](https://github.com/ruyisdk/packages-index/pull/97)
  - [board-image/revyos-milkv-meles: new version 1.20250729.0 #98](https://github.com/ruyisdk/packages-index/pull/98)
  - [Fix broken bianbu-bpi-f3 manifest and unify bianbu upstream_version format #99](https://github.com/ruyisdk/packages-index/pull/99)
  - [board-image/bianbu-{desktop,minimal}-spacemit-k1-sd: new versions from v2.0.0 to v3.0.0 #100](https://github.com/ruyisdk/packages-index/pull/100)
  - [Update board-image/bianbu-{desktop,minimal}-spacemit-k1-sd manifests #102](https://github.com/ruyisdk/packages-index/pull/102)
  - [board-image/debian-desktop-sdk-milkv-mars-cm-sd: add old version 1.0.5+3.6.1 #103](https://github.com/ruyisdk/packages-index/pull/103)
- support-matrix 仓库提交 1 个 issue
  - [[Image Check] Pine64 Star64 images disappeared on armbian community release #353](https://github.com/ruyisdk/support-matrix/issues/353)
- docs 仓库提交 4 个 issue
  - [文档代码块格式不统一 #93](https://github.com/ruyisdk/docs/issues/93)
  - [链接中的 RuyiSDK 大小写问题 #94](https://github.com/ruyisdk/docs/issues/94)
  - [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)
  - [关于使用 pip 安装 ruyi 的文档提示 #96](https://github.com/ruyisdk/docs/issues/96)
- 08/08 北京 World RISC-V Days 2025 参会和演示
- 08/26 深圳 Elexcon 参展
- 新的 ruyi deb 包下载源 [launchpad.net](https://launchpad.net/~ruyisdk-test/+archive/ubuntu/ruyi)
- 实习生面试考核题 [J162](https://gitlab.inuyasha.love/weilinfox/plct-working/-/blob/master/Done/Month26/jy.md)

#### 6.2 郑景坤

##### 6.2.1 操作系统支持矩阵

- PR Review (对测试团队操作系统支持矩阵产出的review审核，以下内容同测试团队产出，此处为review)
  - [Add new boards, support status,test reports,documents and CI updates ](https://github.com/ruyisdk/support-matrix/pull/350)
  - [docs(treewide): unify case of distro names & fix typo](https://github.com/ruyisdk/support-matrix/pull/351)
  - [LiP3A: Add irradium test report (good).](https://github.com/ruyisdk/support-matrix/pull/352)
  - [OrangePi RV2: Add BredOS test report (good).](https://github.com/ruyisdk/support-matrix/pull/354)
  - [LiP4A: Bump Fedora Version to 42](https://github.com/ruyisdk/support-matrix/pull/356)
  - [OrangePi RV2: Add Debian Trixie test report (basic).](https://github.com/ruyisdk/support-matrix/pull/357)
  - [docs: Replace device names with placeholders](https://github.com/ruyisdk/support-matrix/pull/359)
  - [docs: Correct sys_ver in LicheePi4A RevyOS README](https://github.com/ruyisdk/support-matrix/pull/360)
  - [Duo: Bump Buildroot to v2.0.1](https://github.com/ruyisdk/support-matrix/pull/363)
  - [EIC7700X Board information supplement](https://github.com/ruyisdk/support-matrix/pull/364)
  - 网页前端 Review：https://github.com/QA-Team-lo/support-matrix-frontend
- New PR（独立完成）
  - [Update for LPi3A & MUSE Pi Pro](https://github.com/ruyisdk/support-matrix/pull/355)
  - [VF2: fix link typo](https://github.com/ruyisdk/support-matrix/pull/361)

##### 6.2.2 双周报

- https://github.com/ruyisdk/wechat-articles/pull/176
- https://github.com/ruyisdk/wechat-articles/pull/174

##### 6.2.3 深圳 Elexcon 2025（主要是 RuyiSDK 展台）
- https://mp.weixin.qq.com/s/XvIFFTCuAGyKHVP8irzIXw
- 展出物：Milk-V Meles + [RuyiSDK 介绍视频](https://www.bilibili.com/video/av664932287/) + PPSSPP / 洞窟物语 Demo
- [展品部署](https://github.com/user-attachments/assets/af21fc0c-e17e-45cb-9260-4512900f00c2)
- Meles 测试报告见 https://matrix.ruyisdk.org/reports/Meles-RevyOS-README/
- [RV Infra Slide](https://github.com/KevinMX/PLCT-Works/tree/main/reports/month28/RVInfra/)

#### 6.3 阎明铸

##### 6.3.1 sail/act
- 提交 PR
  - <https://github.com/riscv/sail-riscv/pull/538> Make \{m,s\}status\[VS\] read-only zero when Ext_V not supported
  New activity
  - <https://github.com/riscv/sail-riscv/pull/1251> Add basic syscall support
- 推进 PR
  - <https://github.com/riscv/sail-riscv/pull/538> Add Zicbop extension
  - <https://github.com/riscv/sail-riscv/pull/1099> Move RVFI to C
- Issue
  - <https://github.com/riscv/sail-riscv/pull/1250> Add syscall support

##### 6.3.2 会议和技术分享

- 8.23 RISC-V 研讨会：SAIL-RISCV 如何攻克 RISC-V 可配置性 [PPT](https://github.com/trdthg/plct/blob/main/doc/sail/json-config/main.pdf)
- tech-golden-model meeting [`08.18`, `08.25`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 8.21 东亚双周会 [PPT](https://docs.google.com/presentation/d/1wFh9WXinsaQhMQgQBXODzm8KRUB_JeGJuWgfOXwNeiA/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 8.8 北京 World RISC-V Days 2025 参会和演示 [文章](https://mp.weixin.qq.com/s/OW8OAXUPN-kWurjVjk2VsQ)
- 8.26-8.28 深圳 Elexcon 2025，PLCT Lab 展位 [文章](https://mp.weixin.qq.com/s/HqU26th_RpWFhKcK4IQLmQ)

#### 6.4 张馥媛

##### 6.4.1 视频

- [RuyiSDK案例-学习使用qemu、llvm和cmake](https://www.bilibili.com/video/BV1mjefzLEL6/)

##### 6.4.2 RISC-V short video项目文档

-  [新人手册](https://github.com/DuoQilai/PLCT-Works/blob/main/RISC-V_short_video/baby_book.md)

##### 6.4.3 玄铁课程

-  提交玄铁课程《在Licheepi4A运行Deepseek》

##### 6.4.4 英麒RISC-V Lab

-  [实习生成长手册](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISCVLab/yq_Get_started.md)

##### 6.4.5 第17次RISC-V研讨会演讲

-  [RISC-V教育和南京合作伙伴RISC-V Lab协同建设ppt](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/RISC-V%E6%95%99%E8%82%B2%E5%92%8C%E5%8D%97%E4%BA%AC%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4RISC-V%20Lab%E5%8D%8F%E5%90%8C%E5%BB%BA%E8%AE%BE.pptx)

##### 6.4.6 深圳电子展

- 展品准备（k230 ai识别）
- 展区服务

#### 6.5 朱旭昌

- ACT PR
  - 提交了一个修复缺失的压缩非法指令缺失覆盖的问题[#695](https://github.com/riscv-non-isa/riscv-arch-test/pull/695)
  - 更新了readme说明文档并成功合入[#676](https://github.com/riscv-non-isa/riscv-arch-test/pull/676)
  - 更新了修复Zdinx ISA错误的bug并成功合入[#651](https://github.com/riscv-non-isa/riscv-arch-test/pull/651)

  | 测试用例名 | 所属拓展 | 更新测试用例数 | 地址                                                         |
  | ---------- | -------- | -------------- | ------------------------------------------------------------ |
  | cadd       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi16sp  | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | caddi4spn  | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cand       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | candi      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cbeqz      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cbnez      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cj         | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cjal       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cjalr      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cjr        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cli        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clui       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clw        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | clwsp      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cmv        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cor        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cslli      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csrai      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csrli      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csub       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | csw        | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cswsp      | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |
  | cxor       | C        | 2              | [github](https://github.com/riscv-non-isa/riscv-arch-test/tree/dev/riscv-test-suite/rv32i_m/Zfinx/src) |

- 深圳展会deepseek展品准备，PLCT Lab展位服务

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

## Songsong Zhang

- [博客双周报合并为新闻](https://github.com/ruyisdk/ruyisdk-website/issues/145)
  - [chore: add Prettier configuration and plugins to project](https://github.com/ruyisdk/ruyisdk-website/pull/169)
  - [feat: add UnoCSS integration](https://github.com/ruyisdk/ruyisdk-website/pull/208)
  - [merge blog and biweekly into news](https://github.com/ruyisdk/ruyisdk-website/pull/213)

## 参考链接

- [PLCT 实验室的开放职位（实习生）](https://github.com/plctlab/weloveinterns/blob/master/open-internships.md)
- [PLCT 开源进展 (PLCT Weekly)](https://github.com/plctlab/PLCT-Weekly)
- [PLCT 公开报告幻灯片（选集）](https://github.com/plctlab/PLCT-Open-Reports)
