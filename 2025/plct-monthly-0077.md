# RISC-V 软件生态进展 · 第 77 期·2025 年 12 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium

## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK

## Go

Fixing https://github.com/golang/go/issues/76816 for RVA22U64 builder

1. Authored/Co-authored Go-mainline CLs:
- 647596: runtime: unify C -> Go ABI transitions on riscv64 | https://go-review.googlesource.com/c/go/+/647596
- 659175: cmd/link: generate proper attributes for riscv profile | https://go-review.googlesource.com/c/go/+/659175
- 657036: internal/bytealg: vector implementation of count 1 byte for riscv64 | https://go-review.googlesource.com/c/go/+/657036 
- 663778: cmd/asm, cmd/internal/obj: add zvbb/zvbc/zvkb for riscv64 | https://go-review.googlesource.com/c/go/+/663778
- 664155: cmd/asm, cmd/internal/obj: add crypto algorithm suites for riscv64 | https://go-review.googlesource.com/c/go/+/664155
- 663675: cmd/internal/obj: add crypto extension for riscv64 | https://go-review.googlesource.com/c/go/+/663675
- 702695: cmd/internal/obj: add zfh extensions for riscv64 | https://go-review.googlesource.com/c/go/+/702695
- 711075: chacha20: improve performance for riscv64 | https://go-review.googlesource.com/c/crypto/+/711075
- 719880: math/big: use vector for addVV on riscv64 | https://go-review.googlesource.com/c/go/+/719880
- 728940: runtime/secret: enable secret on riscv64 | https://go-review.googlesource.com/c/go/+/728940
- 728901: cmd/compile: update ABI document for riscv64 | https://go-review.googlesource.com/c/go/+/728901 [merged]
- 732540: runtime: reduce stack size of gcWriteBarrier on riscv64 | https://go-review.googlesource.com/c/go/+/732540 [Abondon]

2. Reviewed Go-mainline CLs:
- 652717: doc, cmd/internal/obj/riscv: document the riscv64 assembler | https://go-review.googlesource.com/c/go/+/652717 
- 646736: internal/bytealg: vector implementation of equal for riscv64 | https://go-review.googlesource.com/c/go/+/646736
- 646737: internal/bytealg: vector implementation of compare for riscv64 | https://go-review.googlesource.com/c/go/+/646737
- 670875: riscv64: fix the path to the RISC-V extensions in spec.go | https://go-review.googlesource.com/c/arch/+/670875
- 670875: riscv64: fix the path to the RISC-V extensions in spec.go | https://go-review.googlesource.com/c/arch/+/670875
- 690495: runtime: identify virtual memory layout for riscv64 | https://go-review.googlesource.com/c/go/+/690495
- 703715: cmd/compile/internal/ssa: add codegen for Zicond extension on riscv64 | https://go-review.googlesource.com/c/go/+/703715
- 717560: cmd/compile: use FCLASSD for subnormal checks on riscv64 | https://go-review.googlesource.com/c/go/+/717560
- 705996: cmd/compile/internal/ssa: add codegen for Zicond extension on riscv64 | https://go-review.googlesource.com/c/go/+/705996
- 732180: test/codegen: codify bit related code generation for riscv64 | https://go-review.googlesource.com/c/go/+/732180 [merged]
- 731921: cmd/asm/internal/asm: run riscv64 end-to-end tests for each profile | https://go-review.googlesource.com/c/go/+/731921 [merged]

## GNU Toolchain

## LLVM Team

## MLIR / Buddy Compiler

## opensbi

## RT-Thread

## 罗云翔测试团队

## LuaJIT

## Jeandle

### 实习生

#### 邓冲之

- \[PR\] <https://github.com/jeandle/jeandle-jdk/pull/265> enhancement: Add LLVM fatal error handler
- \[PR\] <https://github.com/jeandle/jeandle-jdk/pull/268> Fix compiler debugging assertion macro spelling case error and correct some typos

## 参考链接
