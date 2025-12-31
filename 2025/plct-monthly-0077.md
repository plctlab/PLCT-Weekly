# RISC-V 软件生态进展 · 第 77 期·2025 年 12 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium

Update by PLCT（Lu Yahan): 
- 7206634: [frames] Track stack frame iteration depth in StackFrameIterator | https://chromium-review.googlesource.com/c/v8/v8/+/7206634
Fix meaglev  overflow check failed about SMI
- 7202584: [riscv][maglev] Fix  an issue where SMI values do not overflow correctly | https://chromium-review.googlesource.com/c/v8/v8/+/7202584
- 7149198: [riscv] Enable v8_enable_external_code_space | https://chromium-review.googlesource.com/c/v8/v8/+/7149198 
修复 位转换FP32->UINT64时没有正确NanBox,此外减少arm64多余的指令
IR中ChangeUint32ToUint64(BitcastFloat32ToUint32)会将fp32零扩展到uint64不符合RISC-V spec
- 7271804: [Turbofan] optimize ChangeUint32ToUint64(BitcastFloat32ToUint32) | https://chromium-review.googlesource.com/c/v8/v8/+/7271804
支持Zicfiss
- 7039660: [riscv64] Protect return addresses stored on stack. | https://chromium-review.googlesource.com/c/v8/v8/+/7039660
- 7274581: [riscv] [builtins] Refactor CallApiGetter builtin | https://chromium-review.googlesource.com/c/v8/v8/+/7274581
- 7271945: [riscv][heap] Make read-only MemoryChunk field conditionally optional | https://chromium-review.googlesource.com/c/v8/v8/+/7271945
- 7259655: [riscv][api] Flatten v8::FunctionCallbackInfo<T> | https://chromium-review.googlesource.com/c/v8/v8/+/7259655
- 7255074: [riscv][wasmfx] Support return values in stack wrapper | https://chromium-review.googlesource.com/c/v8/v8/+/7255074
- 7252469: [riscv][maglev] Materialize undefined for undefined nan on exception | https://chromium-review.googlesource.com/c/v8/v8/+/7252469

Review:
优化开启Zba时多余的指令
- 7255075: [riscv] Change 'zextw + add' to 'add.uw'  | https://chromium-review.googlesource.com/c/v8/v8/+/7255075


Clean Code
- 7220250: [riscv] rename x0 to tmp1 in ByteSwap | https://chromium-review.googlesource.com/c/v8/v8/+/7220250
- 7221190: [riscv] Enable wasm-deopt flag | https://chromium-review.googlesource.com/c/v8/v8/+/7221190
- 7214846: [riscv][codegen] Remove IsolateAddressId in favour of IsolateFieldId | https://chromium-review.googlesource.com/c/v8/v8/+/7214846
- 7202304: [riscv][wasmfx] Implement tag parameters and returns | https://chromium-review.googlesource.com/c/v8/v8/+/7202304 

Update by RIVOS:
- 7171091: [riscv] Save and restore simd128 registers when deopting | https://chromium-review.googlesource.com/c/v8/v8/+/7171091
- 7157374: [riscv] Add compilation flags to control code-related alignment | https://chromium-review.googlesource.com/c/chromium/src/+/7157374 


## Spidermonkey / Firefox

一般都是风平浪静。欢迎对 Firefox 开发感兴趣的同学来实习。

## OpenJDK

## Go

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
