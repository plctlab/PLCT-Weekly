# 第二年的许愿池计划

Hi all，

软件所PLCT实验室正在规划2022年开源软件方面的路线图。侧重但不限于于RISC-V生态。

欢迎各位通过 [Pull Requests 或 Issues](https://github.com/plctlab/PLCT-Weekly/issues) 提供建议和帮助，将自己想要的 features / tools 发给我们。

我们会根据关注和提到的用户数进行功能点的排序，在2022年1月1日确定好2022年路线图。

所有功能点默认开源，代码托管在软件所PLCT实验室[在GitHub上的官方账号](https://github.com/plctlab)（ `plctlab` ）上。

我们对所有花费时间提交功能点许愿内容的朋友表示感激。

## 2021 回顾

TODO

## 2022 许愿池计划


# 英文版 Open Wishlist for RISC-V 2022

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

[1] (Zh_CN) https://github.com/plctlab/PLCT-Weekly/blob/master/RISCV-DevTools-Wishlist-2020.md

[2] (Zh_CN) https://github.com/plctlab/PLCT-Weekly/blob/master/RISCV-Roadmap-2020.md

[3] https://github.com/v8-riscv/v8/

[4] https://github.com/plctlab/rvv-llvm

[5] https://plctlab.github.io/opencv/Optimize_OpenCV_for_RISC-V.html

[6] https://github.com/plctlab/plct-qemu

[7] BishengJDK has already speed up 20x: https://plctlab.github.io/openjdk/Building_instruction_and_test_of_BishengJDK11_on_HiFive_Unleashed.html

[8] Chromium is being ported by some groups, e.g. the RIOS Lab. So we do not to take care of it.
