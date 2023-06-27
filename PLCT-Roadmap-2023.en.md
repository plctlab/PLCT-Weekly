# PLCT Roadmap 2023

Welcome to the PLCT Lab's Roadmap for 2023. In 2023, we will continue our effort to enhance RISC-V support in various system components, particularly toolchains, virtual machines, and emulators. This also means increased developer investment in open source projects such as GCC, LLVM, QEMU, Mozilla, AOSP, and openEuler.

We are also pleased to announce the RUYISDK project, which aims to simplify deployment, development, testing, debugging, and distribution of RISC-V software solutions. With this powerful toolkit, developers can refocus their effort on research and development.

## Key Objectives

For 2023, the PLCT Lab (and the TARSIER team) identified the following key objectives:

1. Design and develop RUYISDK and establish a user-developer community, building the foundation for long-term maintenance.
2. Begin staging software stack for RISC-V powered supercomputer clusters and plan for a 1024-core demo cluster in preparation for TOP500.
3. Continue to expand software support for RISC-V, including .NET/Mono, LuaJIT, and Box64.

## RUYISDK

The Institute of Software, Chinese Academy of Sciences (ISCAS) commenced work on RUBYSDK in late 2022. At present, we have assembled a development team, with the aim to provide RISC-V developers with a full-featured and turn-key development environment in the next three years.

We envision that RUYISDK will help developers in the following ways:

1. Developers who have purchased virtually any RISC-V development boards or modules will be able to obtain hardware datasheets, firmware/software updates, debugging support for virtually any RISC-V development boards or modules.
2. Developers will be able to build and release operating systems, toolchains, development environments (runtimes or virtual machines), compute libraries, and application frameworks for most RISC-V instruction set architectures. RUYISDK will fully support Vector 0.7.1, RVP 0.5.2, and other mainstream standards, drafts, or manufacturer-specific extensions already implemented in silicon.
3. Developers will benefit from an active developer community.

We welcome all RISC-V and open source enthusiasts to join this quest to build a comprehensive SDK for RISC-V developers. If you are interested, please email Wu Wei at <wuwei2016@iscas.ac.cn>. We are also seeking developers and package maintainers.

## Detailed Objectives

Most of the objectives listed below are continuations from [2022](https://github.com/plctlab/PLCT-Weekly/blob/master/PLCT-Roadmap-2022.md) and [2021](https://github.com/plctlab/PLCT-Weekly/blob/master/PLCT-Roadmap-2021.md), please refer to the linked roadmaps for details.

- .NET/Mono: Complete a usable JIT port.
- Box64: Complete JIT implementation and integrate into RUYISDK.
- LuaJIT: Complete JIT implementation and integrate into RUYISDK.
- OpenJDK/RV32G: Complete C2 debugging.
- OpenJDK8/RV64GC: Complete backporting.
- PTS: Deployment by Q3 2023.
- DynamoRIO: Complete porting and integrate into RUYISDK.
- Valgrind: Complete porting and integrate into RUYISDK.
- GHC: Expedite RISC-V port and bug fixes.
- Keystone Engine: Update vendored LLVM to a version that supports RISC-V, complete porting and integrate into RUYISDK.
- LLVM: Implement RISC-V PE/COFF writer support.
- [SBCL (Steel Bank Common Lisp)](https://sourceforge.net/p/sbcl/sbcl/ci/master/tree/), a dependency for ROS1: Implement RISC-V support.
- [Mimick](https://github.com/Snaipe/Mimick), a dependency for ROS2: Implement RISC-V support.

## Recap: 2022

**Key Objectives**

In 2022, the PLCT Lab has set the following key objectives:

- Prepare the software systems required by RISC-V laptops so that popular Linux distributions and commonly used OA software and development tools can run smoothly on RISC-V laptops.
  - **Result:** Objective achieved, as we added or optimized RISC-V support for LibreOffice, Chromium, Firefox, OpenJDK, Node.js, and other commonly used software packages.
- Complete the porting and adaptation of more than half of the "last 5%" common open source software on RISC-V.
  - **Result:** Still a work-in-progress. We must admit that the "last 5%" had been a much heftier task than expected, with more issues and requirements surfacing as work progressed. We have incorporated newly found requirements into this year's roadmap, and will likely see appearance in future ones.
- Set up a RISC-V software testing team through the TARSIER Project to ensure the stability and quality of open source software in the RISC-V ecosystem.
  - **Result:** Objective achieved, thanks to the excellent work from our colleagues at TARSIER.

**Detailed Objectives**

- **Completed:** Optimize operating systems and software solutions for RISC-V laptops.
- **Work-in-Progress:** RISC-V CI Infrastructure for Open Source Communities.
  - CI Farm deployed according to plans, PTS deployment delayed to Q3 2023.
- **Completed:** Upstreamed LibreOffice support.
- **Pending:** Python Wheels for RISC-V.
  - We are recruiting interns for this objective.
- **Completed:** DartVM.
  - Google's Dart team has implemented preliminary support for RISC-V.
- **Work-in-Progress:** Valgrind.
  - Under construction, support for RISC-V not yet complete.
- **Completed:** SpiderMonkey.
  - Implemented RV64GC JIT support and accepted by Mozilla upstream.
- **Work-in-Progress:** DynamoRIO.
  - Under construction, currently collaborating with RIVOS. Prioritized in 2023.
- **Work-in-Progress:**: LuaJIT.
  - Interpreter support complete, JIT support under construction.

**Incremental Objectives**

- V8: The V8 team at PLCT implemented on-demand CI, which produces regression discovery in 2-hour time frames.
- Node.js: In stable maintenance.
- Chromium Browser: Producing rpm/deb packages for openEuler RISC-V and other Linux distributions. PTS tracking and upstreaming pending.
- Firefox: JIT for the JavaScript engine has been merged upstream. Producing rpm/deb packages for openEuler RISC-V and other Linux distributions. PTS tracking pending.
- GCC: All 6 projects, except for gold linker support, has been completed.
- Clang/LLVM: Flang support under construction.
- OpenJDK: Upstreamed a series of RISC-V feature support patches. C2 JIT support for RV32GC under construction.
- Chisel: Platform support improvements underway.
- OpenCV: Platform support improvements underway.
- openEuler RISC-V: To quote the recap from openEuler Summit 2022, "on the RISC-V architecture, openEuler is now amongst the top global players."
- From community feedback...
  - Our comprehensive SDK has now transformed into RUYISDK.
  - We redoubled our effort for RVV support in GCC.
  - Objectives that are not yet complete have now rolled over into our 2023 Roadmap.
- Education, training, and publication: over 100 interns trained, with more than 5 new LV4+ qualifiers and 15 new senior interns. Book publication delayed.

## Internship Recruitment Underway, We Look Forward to Your Applications!

If you are interested in joining us, please don't hesitate to e-mail our director Wu Wei at <wuwei2016@iscas.ac.cn>.
