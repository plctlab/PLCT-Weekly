# 第二年的许愿池计划

Hi all，

软件所PLCT实验室正在规划2021年在 RISC-V 开源开发工具上的布局。

欢迎各位通过 Pull Requests 或 Issues 提供建议和帮助，将自己想要的 features / tools 发给我们。

我们会根据关注和提到的用户数进行功能点的排序，在2021年1月1日确定好2021年路线图。

所有功能点默认开源，代码托管在软件所PLCT实验室[在GitHub上的官方账号](https://github.com/isrc-cas)（ `isrc-cas` ）上。

我们对所有花费时间提交功能点许愿内容的朋友表示感激。

## 2020 回顾

2020 收到的信息比较少：
* 我们主动联系了芯来科技，提供了QEMU支持；跟RT-Thread建立了良好的社区合作，在树莓派等多个领域有了合作。

同时，
* V8 for RISC-V 作为主体项目推出，并在今年与 FutureWei 团队联合起来进行 upstreaming。
* RVV-LLVM 项目继续稳步发展，目前已经跟踪实现到了 v1.0-draft 版本，并开始跟 LLVM RISCV 上游合作。
* OpenCV for RISC-V 优化项目顺利的完成了里程碑，后续会继续改进。
* OpenJDK 由 BishengJDK 团队开源了 RV64G 后端，PLCT实验室目前跟BishengJDK进行了联合。

## 2021 许愿池计划

### 图书翻译

如果有想要看到中文版的RISC-V相关或者编译器、虚拟机、模拟器相关的技术类书籍，也可以许愿翻译。PLCT会去找出版社商量，购买版权，翻译出版。

### Toolchain, llvm

Pull Requests are welcome!

### Toolchain, GNU GCC, Binutils

Pull Requests are welcome!

### Profilers, Performance Analysis Tools

Pull Requests are welcome!

### Perf Tracking Infrastructure

Pull Requests are welcome!

### GDB and other debuggers

Pull Requests are welcome!

### glibc, other system libs

Pull Requests are welcome!

# 英文版 Open Wishlist for RISC-V 2021

Hi all,

The PLCT Lab is inviting everyone inside the RISC-V community to write to us
the dev-tools or other softwares you wish to have in the RISC-V ecosystem.
Feel free to open an issue on plctlab.org[0] and describe the tools you want.

A few simple rules should be met:
- Only open source projects are considered.
- Softwares that have not been ported to RV64G are prefered.
- Language VMs, Compilers, and Performance Analyzing tools are prefered.

There are some items already on the wishlist:
1. Enable Firefox/Spidermonkey running on RV64GCV platform[8].
2. Speed up more than 100x compared with OpenJDK/zero for Java applications[7].
3. Ensure the speed of JS/WASM on RV64GCV is on par with AArch64.
4. Enable DynamoRIO running on RV64GC.

Feel free to contact us and add more items on the wishlist.

This is the second time that the PLCT lab invites all friends in the RISC-V
community to write in what softwares or tools you wish to have for the RISC-V
ecosystem. The first year was mainly targeting the RISC-V China community.
We collected a few wishes at the end of 2019[1], and put (some of) them
into the PLCT Lab's Roadmap 2020[2]. Most of them have been achieved, includes:

- V8 for RISC-V project: Ready to upstream. Collaborating with FutureWei [3].
- Vector Extension Support in LLVM (RVV-LLVM): Implemented v0.7.1, v0.8, v0.9
  and v1.0-draft versions. Used as a codebase by a few AI Chip startups [4].
- OpenCV for RISC-V: Basic Vector Extension support is done. Upstreaming.
  More features are co-developing with the RVV-LLVM project [5].
- QEMU Supports: Implemented SoC emulation for one RISC-V startup. Open Sourced [6].


[0] https://github.com/plctlab/plctlab.github.io/issues

[1] (Zh_CN) https://github.com/isrc-cas/PLCT-Weekly/blob/master/RISCV-DevTools-Wishlist-2020.md

[2] (Zh_CN) https://github.com/isrc-cas/PLCT-Weekly/blob/master/RISCV-Roadmap-2020.md

[3] https://github.com/v8-riscv/v8/

[4] https://github.com/isrc-cas/rvv-llvm

[5] https://plctlab.github.io/opencv/Optimize_OpenCV_for_RISC-V.html

[6] https://github.com/isrc-cas/plct-qemu

[7] BishengJDK has already speed up 20x: https://plctlab.github.io/openjdk/Building_instruction_and_test_of_BishengJDK11_on_HiFive_Unleashed.html

[8] Chromium is being ported by some groups, e.g. the RIOS Lab. So we do not to take care of it.
