# The PLCT Lab 2021 plan in the direction of RISC-V development tool

Change history:
- 2021-1-3 v0.3 Add 2021 publication plan
- 2021-1-1 v0.2 Add Xiong Da's wish for wasm-micro-runtime
- 2021-1-1 v0.1 Set goals for 2021

Thanks to all of your contributions to the Trevi Fountain project. This year, we have received much more wishes and suggestions compared to last year. Based on the current summary and sequencing, we disclose the PLCT Lab goals for 2021 as follows:

### V8 for RISC-V

In 2020, we have started to combine with FutureWei and RIOS Lab into one team, and carry out Upstreaming to Google Chromium/V8. It is believed that it can enter to the upstream at the beginning of 2021. Based on what has been collected so far, the V8 for RISC-V project's 2021 annual goals are as follows:

- Continue to look for speed optimization opportunities for JS, and improve the performances of JS on RV64GC by N times compared to the current speed. Here, N has not been determined yet. It will be determined by supervisor Qui Ji through the V8 performance data, which is on the same performance of AArch64.
- Begin to maintain the NodeJS ecosystem as important as the V8 project, and make it possible to run NodeJS program on the RV64GC without any hassle.
- Pay more attention to the functional integrity and performance improvement of wasm on RV64GC to provide support for the subsequent AIot and other specific application scenarios of wasm.
- Try to support extensions like C, V, B, P, etc.
- Track V8 performance improvements with infrastructure provided by the PLCT Lab and RISC-V International Foundation. Simultaneously,  improve CI infrastructure.
- Train at least 1 new full-time employee and at least 10 new LV3+ interns.

### OpenJDK for RISC-V

In the fourth quater of 2020, we launched an ambitious plan to make Java programs execute more than 100 times faster on RISC-V than OpenJDK/Zero. Shortly after we publicly launched the project, we partnered with Huwei's BishengJDK team. BishengJDK has implemented the basic OpenJDK/Hotspot RV64G backend and has been open sourced. After the practical comparison test on HiFive Unleashed by the PLCT Lab, it has achieved ~20x speed improvement on various benchmarks. In 2021, the PLCT Lab's annual goals are as follows:

- Cooperate with more domestic and international teams, including Huawei, to enable Java programs to execute more than 100 times faster on RV64GC compared to OpenJDK/Zero.
- Assist the BishengJDK team in Upstreaming.
- Try to support extensions like C, V, B, P, etc.
- Track OpenJDK/HotSpot performance improvements with infrastructure provided by the PLCT Lab and RISC-V International Foundation. Simultaneously, while improving CI infrastructure.
- Train at least 1 new full-time employee and at least 10 new LV3+ interns.

### C/C++ Toolchain for RISC-V

In 2020, the complier branch of the PLCT Lab mainly focused on the implementation of RISC-V Vector Extension of LLVM. Through implementation of RVV-LLVM open source, about 10 new employees and interns have been trained. Additionally, we have started to establish more extensive and frequent contacts with the LLVM upstream community and active peers such as SiFive. In addition to the rvv-llvm project, the compiler branch has experimented with extensions such as Zfinx.

In the second half of 2020, the PLCT Lab began to become more actively involved in the work of RISC-V International Foundation. As the new staff JiaWei Chen take over the reference implementation of Zfinx on GCC/Binutils/GDB, the PLCT Lab officially started to participate in the development of GNU Toolchain. At the same time, the PLCT Lab pushed the Institute of Software, Chinese ACademy pf Sciences to complete the signing of FSF Copyright Assignments, which has completed preparation for the subsequent direct participation in the upstream development of GNU Toolchain and code submission.

In 2021, the PLCT Lab plans to achieve the following objectives on the GCC and LLVM projects:

- Continue to promote the rvv-llvm project to support OpenCV for RISC-V and other V-extended large application projects. Simultaneously, cultivate no less than 10 new LV3+ interns.
- Participate more actively in the development of RISC-V GNU Toolchain and have at least 1 new full-time employee and at least 5 new LV3+ interns.
- Let the LLVM code performance and code volume continue to catch up with the progress of GNU Toolchain in RISC-V domain.
- Enhance code size and speed of LLVM and GCC on RV64GCV platform (No specific optimization target for now)
- Enable Gold Linker to support RISC-V
- Attract at least 3 new full-time employees to join amd train more than 15 new LV3+ interns.

### AOSP for RISC-V

Andriod Open Source Project (AOSP) is one of the most important Open Source systems in the mobile phone, tablet and other fields, which has self-evident importance in the software ecosystem. So far, no company or team other than the PLCT Lab has publicly announced that they are working on RISC-V porting, including Google. Maybe it's because everyone is still waiting. However, for the PLCT Lab, we should start to try as early as possible to push the whole community towards a broader application scenario.

In 2020, Mr. Wang Chen from the PLCT Lab completed the operation of AOSP's minimum system on RISC-V. In 2021, we plan to:

- Continue to advance the AOSP for RISC-V project and attract more vendors and community developers to join our porting team.
- Start the RISC-V porting of the critical component of Davlik/ART. Director Ningning Shi will participate in this project.
- By the end of 2021, run AOSP on the RV64GC development board and be able to start Hello World Activity. If the progress goes fast enough, the V8 engine will be able to be started.

### Firefox on RV64GCV

Mozilla Firefox plays an important role in the free software world. More than just a desktop browser, Firefox is also the basis for many free distributions. Although graphics stack and rendering engine parts are not the strong point of the PLCT Lab, we still feel that we have the capability and therefore should be the driving/encouraging force to promote Firefox on RISC-V. In 2021, the PLCT Lab plans to achieve the following goals:

- Make sure that Rust language and tools can run smoothly on the RV64GCV platform.
- Port SpiderMonkey to RV64GC for functional integrity. If time and manpower permit, the poring of JITs such as IonMonkey will begin.
- Create a new co-development team to enable Firefox to run on RV64GC Linux.
- Attract as least 1 new full-time employee to join and cultivate at least 5 new LV3+ interns.

### Enable DynamoRIO running on RV64GC

DynamoRIO is an important performance tracking and analysis tool for developers. In 2021, the PLCT Lab plans to achieve the following goals:

- Enable DynamoRIO and its dependent profiling tools to run on the RV64GC platform. Make it can be used for performance tracking and profiling of RISC-V systems or programs.
### wasm micro runtime for RISC-V

Thanks for the Xiong Da's supplement. In 2021, the PLCT Lab plans to achieve the following goals:
- Porting more WASM runtime to RISC-V platform, including RV32G and RV64G, in addition to V8/SM large engines.

https://github.com/bytecodealliance/wasm-micro-runtime


### OpenCV for RV64GCV

OpenCV is one the key application libraries selected by the PLCT Lab in RISC-V domain. In 2020, at the opportunity of GSoC project, Yin Zhang completed the basic support of OpenCV for RVV 1.0-draft, which has been merged into Upstream. There is still a lot of work to be done. In 2021, the PLCT Lab plans to achieve the following goals:

- Continue to maintain the OpenCV for RISC-V project and track changes in the V extension until the final ratification.
- Support OpenCV optimization for at least one domestic RISC-V platform after supporting RVV on domestic RISC-V platform.
- Attract as least one new full-time employee to join and cultivate at least 2 new Lv3+ inters.

### LuaJIT RV64G porting

- Try to introduce the RV64G porting of LuaJIT and cultivate two new LV3+ interns.

### RISC-V software ecological completion tracking

- Complete a more detailed tracking platform of various software support for the RISC-V platform.

### Toolchain/Emulator Support for RISC-V International

- Continue with the reference implementation of Zfinx. Currently, reference implementations of GNU GCC/Binutils/GDB, LLVM, QEMU and Spike have been completed. Subsequent updates will continue as the draft of ABI and etc being promoted.
- Participate in promoting reference implementation of GNU GCC/Binuitls/GDB, LLVM, GEMU, Spike for V, B, P and other extensions.

### Book writing and translation plans

- Write a new Dalvik/ART, which will be written by NingNing Shi.
- Write a new book about V8 source code analysis, which will be written by Qiu Ji and supervised by Wu Wei.
- Write a new book about emulator(including QEMU/Spike). Junqiang Li and Weiwei Li will be responsible for the writing and Wei Wu will be responsible for the supervision.
- Plan to translate one or two foreign books in the complier, virtual machine, simulator domain, RISC-V domain. Welcome to recommend to us.
  

### Interns, on-campus recruitment and social recruitment are all open for recruitment. Welcome to send us your resume or consult us!

If interested, welcome to send emails to me: "Wu Wei <wuwei2016@iscas.ac.cn>"
