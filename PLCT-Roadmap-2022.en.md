# PLCT Roadmap 2022

（This article was translated by Google Translate. Syntax & Semantic issue reporting are welcome.)

Hello everyone, this is the roadmap of PLCT Lab for 2022.
In 2022, we will continue to increase support for RISC-V on toolchains, virtual machines, and simulators.
The investment in GCC, LLVM, V8, QEMU and other communities will continue to increase.
At the same time, we are pleased to announce that Tarsier Team has completed its incubation and will begin to operate as an independent operating system team of ISRC.

## key goals

In 2022 the PLCT Lab hopes to achieve the following key goals:

1. Prepare the software system required by RISC-V laptops, so that popular Linux distributions and commonly used OA software and development tools can run smoothly on RISC-V laptops.
2. Complete the porting and adaptation of more than half of the "last 5%" common open source software on RISC-V.
3. Set up a RISC-V software testing team through the Tarsier Project to ensure the stability and software quality of open source software in the RISC-V ecosystem.

## Main project: Tarsier Project

The Intelligent Software Research Center (ISRC) of the Institute of Software, Chinese Academy of Sciences (ISCAS) incubated the Tarsier Project in 2021. The goal of the Tarsier Project is to promote support for the RISC-V platform in mainstream Linux distributions (including Debian/Ubuntu, Fedora, Arch Linux, Gentoo, openEuler, etc.) to match or exceed the level of support for the AArch64 platform. Specifically divided into the following different aspects:

### Tarsier Team

The Tarsier Team was established at the end of 2021 and undertakes various specific tasks required by the software institute Tarsier Project. The Tarsier team in 2022 will start from the integration and testing of open source operating systems, and form a testing team of more than 300 full-time, part-time, interns and volunteers to provide more comprehensive quality assurance for the RISC-V software ecosystem and the status quo.

All those interested in RISC-V and open source work are welcome to join us. Feel free to send an email to "Wei Wu <wuwei2016@iscas.ac.cn>" to inquire. At the same time, it also recruits repair kits and developers, and there is no limit to the number of people.

### Operating systems and common software optimized for RISC-V laptops

We expect to see RISC-V laptops coming out by the end of 2022. The Institute of Software, Chinese Academy of Sciences will prepare for the RISC-V software ecosystem. In 2021, two open source browsers, Chromium and Firefox, have completed initial support. In 2022, PLCT Lab will work with the Tarsier team to complete the porting and optimization of common software and system libraries including LibreOffice.

### RISC-V CI Infrastructure for Open Source Communities

In 2021, PLCT Lab, in cooperation with RVI, begins to build an infrastructure expected to exceed 2,000 RISC-V development boards, open to all open source communities in all RISC-V software ecosystems. In 2022, we will continue to improve the infrastructure of RISC-V Lab and complete the free opening to RVI corporate and individual members. RVI members will be able to log in directly to the Nezha D1 development board to use RISC-V software.

At the same time, in 2022, the Performance Tracking System (PTS) will rely on the infrastructure established by the Tarsier Project to begin performance tracking of basic software such as GCC, LLVM, V8, and OpenJDK.

## From scratch: RISC-V adaptation of compilers and virtual machines

### LibreOffice

LibreOffice is a very important office software, and it has not been successfully transplanted on RISC-V. In 2022, we hope to be able to use LibreOffice on RISC-V notebooks for daily OA office work.

- Make LibreOffice's Writer, Calc, and Impress run stably on the RISC-V platform, and experimentally support Draw and Math.
- Provides precompiled binary packages for users of various Linux distributions through the Tarsier Project.

### Python Wheels for RISC-V

Following [Python Wheels for the Raspberry Pi](https://piwheels.org/), we will try to maintain a python package repository for RISC-V in 2022. Thanks to [alexfanqi](https://github.com/alexfanqi) for the suggestion

### DartVM

The Dart language is becoming more and more important in some areas, and DartVM is one of the few language execution environments that has not been ported to the RISC-V platform. We hope to complete the porting of DartVM in 2022, bringing a new software ecosystem to the RISC-V community.

### Valgrind

We underestimated the importance of Valgrind in 2021, which is relied upon by a large number of applications. We hope to complete the porting of Valgrind in 2022, ending the blocking of dependent packages.

### Spidermonkey

Spidermonkey can already be executed in interpreter mode on RISC-V. In 2021 we are opening a Spidermonkey JIT development internship in partnership with RVI. There are two students who have developed it. Unfortunately, the development work has not been completed yet, and helloworld.js has not been run yet. In 2022, we expect to complete the adaptation of Baseline JIT and IonMonkey JIT, and be able to achieve more than 10 times performance improvement.

### DynamoRIO

We hope to complete the DynamoRIO port in 2021. It's a pity it wasn't done in 2021. It is hoped that DynamoRIO's RISC-V porting will be complete and upstream by the end of 2022.


### LuaJIT

We hope to complete the porting of LuaJIT in 2021. It's a pity it wasn't done in 2021. Hope to complete the RISC-V port of LuaJIT by the end of 2022.

## Improvements for 2022

### V8

In 2021, under the leadership of Brice Dobry, the V8 RISC-V project was successfully accepted by Google V8 upstream and entered upstream. Since RISC-V is still a tier-3 support platform, new submissions by developers may break the RISC-V backend at any time. PLCT Labs established an independent CI to detect the availability of the latest V8 code on the RISC-V platform. , and have done so in an average of 1-2 business days to submit a fix.

In 2022, we hope to:
- Continue to look for speed optimization opportunities for V8, combined with the new ratify ISA Specs at the end of 2021, to improve the code execution speed of JS by about 25%. The goal set last year was to increase N times, which was a bit hasty.
- Incorporates the speed of the V8 into the PTS for tracking.

### Node.js

With V8 upstream, the use of Node.js on RISC-V became possible.

In 2022, we hope to:
- Starting from Node.js 16 LTS, provide technical support for RISC-V to ensure the normal operation of node.js LTS version on RV64GC.
- Through the Tariser project, help major Linux distributions complete the fix of node.js dependencies.

### Chromium Browser

The RISC-V adaptation of Chromium Browser was first completed in 2021 by SUSE engineer Andreas Schwab, with technical support for V8 from PLCT Labs. In addition to openSUSE, Arch Linux, Gentoo Linux, Fedora, etc. have successfully run Chromium.

In 2022, we hope to:
- Assist all RISC-V supported patchsets into Chromium upstream.
- Incorporates Chromium performance into PTS for real-time tracking.
- The Tarsier Project will ensure stable Chromium binaries are available on all popular Linux distributions.

### Firefox

The RISC-V adaptation of Firefox was first completed by Firefox developer Makoto Kato in 2021. The intern students in the PLCT lab successfully rebase the patchset to the latest version and package it on Arch Linux, Gentoo Linux, Fedora and other distributions. Can run some common web pages smoothly. Since Spidermonkey is currently executed by an interpreter, there is still an order of magnitude gap in speed compared with V8.

In 2022, we hope to:
- Completed Spidermonkey's JIT support and integrated into Firefox.
- Assist all RISC-V supported patchsets into Mozilla Firefox upstream.
- Incorporates Firefox performance into PTS for real-time tracking.
- The Tarsier Project will ensure stable Firefox binaries are available on all popular Linux distributions.

### GCC

- Continue to assist RVI in providing GCC implementations of various draft standards as a Development Partner.
- Establish dynamic CI based on mailing list, find patchsets that break the RISC-V platform in a timely manner and repair them.
- Incorporate performance metrics such as GCC speed and code size into PTS for tracking.
- Attempt to implement and optimize auto-vectorization support for Vector and P extensions.
- Continuously integrate the whole family bucket branch to ensure that the function is available.
- Enable Gold Linker to support RISC-V.
- Improve RISC-V features not yet supported in GDB and fix all bugs currently known in GDB.

### Clang/LLVM

- Continue to assist RVI in providing LLVM implementations of various draft standards as a Development Partner.
- Provide more CI infrastructure, find and repair patchsets that break the RISC-V platform in a timely manner.
- Incorporate performance metrics such as Clang/LLVM speed and code size into PTS for tracking.
- Attempt to implement and optimize auto-vectorization support for Vector and P extensions.
- Improve RISC-V support in JITLink in LLVM.
- Improve Flang's RISC-V support.

### OpenJDK

In 2021, the Huawei BishengJDK team and the Alibaba Cloud JVM team began to submit the patchset of RV64GC to the OpenJDK upstream community. PLCT laboratory is responsible for the adaptation development task of RV32GC. The project that was originally planned for half a year has been developed for more than a year, and finally the operation of helloworld.class under RV32GC will be completed in the first week of 2022. In 2022, we hope to:

- Complete the JIT (C1) implementation of the OpenJDK RV32GC backend and make an upstream commit.
- Run common Java benchmarks and look for optimization opportunities to improve performance.
- Incorporates OpenJDK for RV64GC and RV32GC into PTS for real-time performance tracking.

### Chisel

- Improve the execution speed of Chisel/FIRRTL and Verilator to reduce memory overhead. It enables notebooks with 16GB of memory to build Xiangshan open source processors. Thanks []() for the suggestion.

### OpenCV

In 2022 we will continue to support OpenCV performance on RISC-V, using extensions including Vector, P extensions for optimization.

### openEuler RISC-V

As part of the Tarsier Project, we are incorporating openEuler RISC-V support into the Tarsier Project 2022 schedule. It is hoped that by the end of 2022, openEuler will be able to achieve the same level of support for fedora and debian on RISC-V.

### More suggestions from the community

Many thanks to all the reviewers for their suggestions!

- oreboot & rustSBI: In 2022 we will start watching and providing support for oreboot & rustSBI.
- herbceptions: In 2022 we try to get familiar with [herbceptions:](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0709r1.pdf) and in RISC-V toolchain support. Thanks to [tearosccebe](https://github.com/tearosccebe) for the suggestion.
- wasm GCC backend: Interesting idea, we will try some in 2022. Thanks to [tearosccebe](https://github.com/tearosccebe) for the suggestion.
- FPGA optimized RV64GC (preferably V) soft core. Thanks to [Icenowy](https://github.com/Icenowy) for the suggestion. We don't know how to do it yet, but we will try.
- I hope PLCT can write a book on explaining the principles of compiler GCC and QEMU, and analyze it through actual combat. Thanks to [bigmagic123](https://github.com/bigmagic123) for the suggestion. We must not delay this year!
- Hope PLCT can put more effort into RISC-V GCC to better support RVV, and at the same time can support auto-vectorization of p-extended and v-extended. Thanks to [bigmagic123](https://github.com/bigmagic123) for the suggestion. Already included in GCC's annual plan.
- Hope to use the RISC-V family bucket version of GCC/LLVM as soon as possible, and support the automatic vectorization of V/P extension. Thanks to [fanghuaqi](https://github.com/fanghuaqi) for the suggestion. Already included in GCC's annual plan.

## Education, training, publications

- Train 100 interns and reach LV2 or higher by the end of the internship.
- Curated a series of RISC-V Linux hacks to provide a more interesting learning experience for enthusiasts to get started with RISC-V.
- Complete a V8 related book writing.
- Completed the writing of an OpenJDK related book.
- Complete the writing of a QuickJS related book.
- Complete a book on simulator principles and development.

### Interns, school recruitment, and social recruitment are carried out at the same time, welcome to consult and submit resumes!

If you are interested, you can email me: "Wu Wei <wuwei2016@iscas.ac.cn>"
