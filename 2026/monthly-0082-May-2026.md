# RISC-V 软件生态进展 · 第 82 期·2026 年 5 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium

## Spidermonkey / Firefox

## OpenJDK

## Go

## GNU Toolchain

## LLVM Team

## MLIR / Buddy Compiler

## opensbi

## 罗云翔测试团队
（包含 SAIL 和 ACT 测试部分）

本月在RuyiSDK方面，完成了0.49.0版本在多种Linux发行版和多架构上的测试，发现了遗留和新增的严重缺陷，需修复后重新发版；新增了多款开发板的示例文档，启动了嵌入式及ROS2机器人课程设计；撰写了sysroot等实用文档，并对官网进行了仪表板、新闻页等约30项更新。RuyiAI方面为buddy-mlir贡献了多个PR，增强CI与RISC-V支持。SAIL方面提交多个PR，开展AME指令调研，受邀RISC-V工委会进行技术讲座并参与书籍SAIL部分编写。团队提交了2026 RISC-V欧洲峰会的四张海报，并在中科院公众科学日展示了16项RuyiSDK与RuyiAI的互动成果。

## 工作总结

1. RuyiSDK

1.1 RuyiSDK测试 
   - 完成了 RuyiSDK 0.49.0-beta.20260519 版本测试，覆盖 Debian、Ubuntu、openEuler、Fedora、Deepin、OpenCloudOS、ArchLinux 等发行版，涉及 x86_64、aarch64、riscv64 架构。  
   - 跟踪并管理缺陷：文档遗留 2 项（含严重 1 项），Eclipse 插件遗留 9 项（建议级），新增严重缺陷 1 项；VSCode 插件新增严重缺陷 1 项及多项建议缺陷；包管理器遗留一般缺陷 1 项。  
   - 测试结论：本版本存在遗留和新增的严重缺陷，需按计划修复并重新发版测试。
1.2 RuyiSDK开发示例库建设和课程设计 
   - 新增 VisionFive2Lite、DuoS、ESP32-P4-Function-EV-Board、Nuclei RV-STAR、LicheePi4A、Duo 256M 等开发板的示例文档，涵盖 GPIO、PWM、I2C、Coremark、YOLO 系列、LVGL 等应用。  
   - 启动了 RuyiSDK RISC-V 嵌入式开发课程设计项目，完成教学大纲和调研文档。  
   - 完成RuyiSDK RISC-V ROS2机器人操作系统编程技术课程仿真环境开发。
1.2 RuyiSDK文档   
   - 撰写了 sysroot 制作、使用介绍，以及 K3 开发板烧录、B站视频剪辑等实用文档。
1.4 网站建设 
   - 对 ruyisdk-website 进行多项更新：新增仪表板页面、新闻/活动页面、优化代码块和国际化、迁移旧博客、删除冗余路由、优化图片格式等，累计提交 PR 约 30 个。

2. RuyiAI
- 为 buddy-mlir 提交多个 PR，包括自动发布、RISC-V 版本支持、CI 测试增强、示例修复、版本打包优化等。  
- 为 triton-riscv 提交 PR，增加 triton-shared-opt 命令行入口。  
- 参与 buddy-mlir PR 评审。

3. SAIL 和 ACT
- 提交多个 SAIL PR（sail-riscv#1727、#1725、#1732、#1706、#1581 等），更新 smwid。
- 调研AME指令编码，评估开发工作量和制定开发计划。
- 参与SAIL和AME会议。  
- 受 RISC-V 工委会邀请进行 SAIL 技术讲座，编写SAIL相关技术文档（RISC-V工委会出书使用），团队内部持续开展 SAIL 技术分享。

4. 2026 RISC-V 欧洲峰会
- 入选2026 RISC-V 欧洲峰会的4个项目完成海报制作
提交和打印，题目涉及：RuyiSDK 包管理器、Sail 模型应用于芯片验证、浏览器原生 RISC-V 工具链、RISC-V 课程设计。 

5. 2026 年中国科学院公众科学日
- 团队参与2026 年中国科学院公众科学日，展示 RuyiSDK 和 RuyiAI 成果，共展出 16 项互动/实物项目。  
- 内容涵盖：RISC-V 发展史、大模型问答、开发板展示、ROS2 机器人、无人机、多模态盲人应用、人脸/手势/手写识别、高性能计算、LLM 互动等。  

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK 0.49.0-beta.20260519  版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/README.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260520/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu26.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260520/RUYI_包管理_Ubuntu26.04_x86_64_测试结果.md)
    - [Ubuntu26.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Ubuntu26.04_riscv64_测试结果.md)
    - [Ubuntu26.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Ubuntu26.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Fedora42_x86_64_测试结果.md)
    - [Fedora42 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Fedora42_aarch64_测试结果.md)
    - [Fedora43 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Fedora43_x86_64_测试结果.md)  
    - [Fedora43 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Fedora43_aarch64_测试结果.md)
    - [Deepin23 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Deepin23_x86_64_测试结果.md)
    - [Deepin23 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Deepin23_riscv64_测试结果.md)
    - [Deepin25 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Deepin25_x86_64_测试结果.md)
    - [Deepin25 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Deepin25_riscv64_测试结果.md)
    - [Deepin25 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Deepin25_aarch64_测试结果.md)
    - [OpenCloudOS 9.4 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_OpenCloudOS_x86_64_测试结果.md)
    - [OpenCloudOS 9.4 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_OpenCloudOS_aarch64_测试结果.md)
    - [Archlinux x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260520/RUYI_包管理_Archlinux_x86_64_测试结果.md)

    - 缺陷：  
      - 文档测试
        上一版本遗留 2 个缺陷：
        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [关于 fastboot 的文档提示 #95](https://github.com/ruyisdk/docs/issues/95)   | 严重 | 建立新的 [issue](https://github.com/ruyisdk/ruyisdk/issues/52) 进行更新，修复已经延后  |

      - packages-index 测试
        无新增缺陷
      - RuyiSDK IDE 测试
        RuyiSDK Eclipse IDE 测试
        本版本同步发版的 Eclipse 插件测试[报告](https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/tree/v0.1.4)。

        遗留缺陷：
        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [命令执行提示框可以任意关闭且无法重新打开 #82](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/82)   | 建议 |   |
        | [开发板选择框中开发板型号未排序 #83](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/83) | 建议 |  |
        | [虚拟环境建立的项目绑定问题 #84](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/84) | 建议 |  |
        | [安装插件时 Eclipse 提示未签名 #85](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/85) | 建议 |  |
        | [有一些可以自动获取的东西，不需要手动填写 #90](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/90) | 建议 |  |
        | [UI：新闻界面切换仅未读“勾号”不明显 #98](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/98) | 建议 |  |
        | [ruyi-venv中的vnev path需要手动点击右侧列表，显示项目路径 #152](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/152) | 建议 |  |
        | [ruyi-venv名称可以默认设置为ruyi-venv-profile属性 #153](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/153) | 建议 |  |
        | [eclipse中版本检测中升级ruyi包管理器，显示由于不支持utf8报错 #154](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/154) | 建议 |  |

        新增缺陷
        | 缺陷      | 问题等级 | 备注 |
        | ----------- | ----------- | --- |
        | [ruyi installation更新异常 #164](https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/164) | 严重 |  |

      - RuyiSDK VSCode IDE 测试
        本版本同步发布的 VSCode 插件测试[报告](https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/tree/v0.1.4)。
        无遗留缺陷。
        新增缺陷：
        | 缺陷 | 问题等级 | 备注 |
        | --- | --- | --- |
        | [i18中文翻译问题 #156](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/156) | 建议 | 已有修复 commit |
        | [ruyinews界面卡片特效缩放异常 #157](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/157) | 建议 |  |
        | [新闻中英文按钮大小不一致 #160](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/160) | 建议 |  |
        | [i18n中文支持情况 #161](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/161) | 建议 | 已有修复 commit |
        | [ruyi-venv创建过程时default默认情况下sysroot配置消失 #162](https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/162) | 严重 | 已有修复 commit |

      - Ruyi 包管理器测试
        遗留缺陷：
        | 缺陷      | 问题等级 |判定依据 |
        | ----------- | ----------- | --- |
        | [Occasional pygit2 failures during testing #415](https://github.com/ruyisdk/ruyi/issues/415) | 一般 | 已有 issue 回复 |
        无新增缺陷。

    - 测试结论
      - 本版本包含遗留的严重缺陷，均按照修复时间表修复中；
      - 本版本 VSCode 和 Eclipse 插件包含新增的严重缺陷，需要需要重新发测试版测试。

- https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/11
- https://github.com/ruyisdk-test/ruyisdk-eclipse-plugins-test/pull/8
- https://github.com/ruyisdk-test/ruyisdk-vscode-extension-test/pull/10

- ruyisdk-eclipse-plugins Issues
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/164 Ruyi installation更新异常 

- ruyisdk-vscode-extension Issues
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/156 i18中文翻译问题
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/157 Ruyinews界面卡片特效缩放异常
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/160 新闻中英文按钮大小不一致
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/161 i18n中文支持情况 
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/162 ruyi-venv创建过程时default默认情况下sysroot配置消失
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/168 新闻内容乱行排列
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/169 多版本管理中路径检测弹窗i18n
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/171 在无网络状态下，插件新闻无法离线渲染以及加载出中英文按钮

#### 1.3 RuyiSDK开发示例库和示例库网站开发

- VisionFive2Lite
	- [RuyiSDK GPIO功能示例：VisionFive 2 Lite GPIO PUD 验证](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/GPIO_PUD/README_zh.md)
	- [RuyiSDK GPIO功能示例：VisionFive 2 Lite LED 闪烁基准测试](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/GPIO_LED/README_zh.md)
- DuoS 
	- [PWM 脉宽调制测试](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Duo_S/example_pwm_Duo_S.md)
	- [I2C OLED 显示屏测试](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Duo_S/example_I2C_Duo_S.md)
- ESP32-P4-Function-EV-Board
	- [概述](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/README.md);[中文概述](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/README_zh.md)
	- [HelloWorld](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/HelloWorld/README_zh.md)
	- [Coremark](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/Coremark/README_zh.md)
	- [RuyiSDK LVGL 示例：LVGL Demo v8](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/LVGL%20Demo%20v8/README_zh.md)
	- [RuyiSDK LVGL 示例：LVGL Demo v9](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/LVGL_Demo_v9/README_zh.md)
- Nuclei RV-STAR
	- [Coremark](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Nuclei%20RV-STAR/example_Coremark_rv-star.md)
	- [HelloWorld](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Nuclei%20RV-STAR/example_HelloWorld_rv-star.md)
- Licheepi4A  
  - [YOLOV5s](https://github.com/TOT2232/board-docs/blob/main/LicheePi4A/YOLOV5s/README_zh.md)
- Duo 256M 示例文档：  
  - [YOLOv5](https://github.com/TOT2232/board-docs/blob/main/Duo_256m/YOLOv5/READEME_zh.md)
  - [YOLOv8](https://github.com/TOT2232/board-docs/blob/main/Duo_256m/YOLOv8/README_zh.md)
  - [YOLOv11](https://github.com/TOT2232/board-docs/blob/main/Duo_256m/YOLOv11/README_zh.md)
  - [YOLOv12](https://github.com/TOT2232/board-docs/blob/main/Duo_256m/YOLOv12/README_zh.md)
- [RuyiSDK GPIO功能示例：VisionFive 2 Lite GPIO PUD 验证](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/GPIO_PUD/README_zh.md)
- [RuyiSDK GPIO功能示例：VisionFive 2 Lite LED 闪烁基准测试](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/GPIO_LED/README_zh.md)
- [RuyiSDK LVGL 示例：LVGL Demo v8](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/LVGL%20Demo%20v8/README_zh.md)
- [RuyiSDK LVGL 示例：LVGL Demo v9](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/LVGL_Demo_v9/README_zh.md)
- [Add GPIO LED blinker and PUD test for VisionFive2 Lite](https://github.com/ruyisdk/board-docs/pull/12)
- ESP32-p4工具链资源issue[Resource Request riscv32-esp-elf Toolchain for ESP32 Series (Bare-metal)](https://github.com/ruyisdk/ruyisdk/issues/87)
- [PWM 脉宽调制测试](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Duo_S/example_pwm_Duo_S.md)
- [I2C OLED 显示屏测试](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Duo_S/example_I2C_Duo_S.md)

- Nuclei RV-STAR
  - [Coremark](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Nuclei%20RV-STAR/example_Coremark_rv-star.md)
  - [HelloWorld](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Nuclei%20RV-STAR/example_HelloWorld_rv-star.md)

- RuyiSDK RISC-V 嵌入式开发课程设计
  - 项目仓库：[riscv-embedded-course](https://github.com/EnzoDing-rgb/riscv-embedded-course)
  - [初步教学大纲](https://github.com/EnzoDing-rgb/riscv-embedded-course/blob/master/docs/outline.md)
  - [调研文档](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/%E8%AF%BE%E7%A8%8B%E4%BD%93%E7%B3%BB%E5%88%86%E6%9E%90%E8%A1%A8.xlsx)
  
- RuyiSDK开发资源梳理和资源申请
	- [[Resource Request]: riscv32-esp-elf Toolchain for ESP32 Series (Bare-metal)](https://github.com/ruyisdk/ruyisdk/issues/87)

#### 1.4 RuyiSDK 文档编写

- [testing: update 0.49.0 test status #266](https://github.com/ruyisdk/wechat-articles/pull/266)
- [20260526-ruyisdk-biweekly-69.md: update test status #277](https://github.com/ruyisdk/wechat-articles/pull/277)
- [如何制作sysroot](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-May/%E5%A6%82%E4%BD%95%E5%88%B6%E4%BD%9Csysroot.md)
- [sysroot介绍](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-May/sysroot%E4%BB%8B%E7%BB%8D.md)
- [在ruyisdk中使用sysroot](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-May/%E5%9C%A8ruyisdk%E4%B8%AD%E4%BD%BF%E7%94%A8sysroot.md)
- [K3开发板烧录 openruyi](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-May/K3%E5%BC%80%E5%8F%91%E6%9D%BF%E7%83%A7%E5%BD%95openruyi.md)
- [B站视频去水印及二次剪辑操作手册](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/research/bili_test.md)

#### 1.5 RuyiSDK网站

- [misc: remove /blog /biweekly route from sitemap #445](https://github.com/ruyisdk/ruyisdk-website/pull/445)
- [Auto-update: API data to latest #448](https://github.com/ruyisdk/ruyisdk-website/pull/448)
- [ci: wait longer on 202 to reduse api using rate #450](https://github.com/ruyisdk/ruyisdk-website/pull/450)
- [Auto-update: API data to latest #452](https://github.com/ruyisdk/ruyisdk-website/pull/452)
- [pages(dashboard): new testing dashboard page /dashboard_thin #453](https://github.com/ruyisdk/ruyisdk-website/pull/453)
- [pages(dashboard): add data update time to dashboard_thin #454](https://github.com/ruyisdk/ruyisdk-website/pull/454)
- [pages(dashboard): better api data update animation for dashboard_thin #455](https://github.com/ruyisdk/ruyisdk-website/pull/455)
- [pages(about): use docusaurus mdx render #456](https://github.com/ruyisdk/ruyisdk-website/pull/456)
- [pages(dashboard): add stats detail doc to dashboard_thin #457](https://github.com/ruyisdk/ruyisdk-website/pull/457)
- [docs(CodeBlock): better codeblock #458](https://github.com/ruyisdk/ruyisdk-website/pull/458)
- [docs(CodeBlock): move docs_utils to Docs and fix docs import #459](https://github.com/ruyisdk/ruyisdk-website/pull/459)
- [pages(DashBoard): dashboard_thin data animation 5 times max #463](https://github.com/ruyisdk/ruyisdk-website/pull/463)
- [pages(DashBoard): dashboard_thin data animation 30 times max #464](https://github.com/ruyisdk/ruyisdk-website/pull/464)
- [pages(dashboard): add translation for dashboard_thin #465](https://github.com/ruyisdk/ruyisdk-website/pull/465)
- [Release new dashboard page #466](https://github.com/ruyisdk/ruyisdk-website/pull/466)
- [pages(news/events): new event 202605-cas-public-science-day-2026 #467](https://github.com/ruyisdk/ruyisdk-website/pull/467)
- [pages(news/events/202605-cas-public-science-day-2026): fallback on pdf preview failed #468](https://github.com/ruyisdk/ruyisdk-website/pull/468)
- [pages(index): add 202605-cas-public-science-day-2026 card #469](https://github.com/ruyisdk/ruyisdk-website/pull/469)
- [pages(news/events/202605-cas-public-science-day-2026): modify more registration option link #470](https://github.com/ruyisdk/ruyisdk-website/pull/470)
- [pages(news/events): fix wechat triger download pdf before hydration #471](https://github.com/ruyisdk/ruyisdk-website/pull/471)
- [pages(footer): add /riscv-specs #477](https://github.com/ruyisdk/ruyisdk-website/pull/477)
- [pages(index): remove 202605-cas-public-science-day-2026 index card #478](https://github.com/ruyisdk/ruyisdk-website/pull/478)
- [pages(news): use loadContent/loadContent instead of news.json #481](https://github.com/ruyisdk/ruyisdk-website/pull/481)
- [Merge old blogs to /news page and remove duplicate blogs #482](https://github.com/ruyisdk/ruyisdk-website/pull/482)
- [pages(news): restore old meetup news and NewsShowcase news to /news #483](https://github.com/ruyisdk/ruyisdk-website/pull/483)
- [pages(index): add cas-public-science-day-2026 to news #484](https://github.com/ruyisdk/ruyisdk-website/pull/484)
- [static(img): convert all imgs to webp #485](https://github.com/ruyisdk/ruyisdk-website/pull/485)
- [pages(news): add news page title #486](https://github.com/ruyisdk/ruyisdk-website/pull/486)
- [pages(news): restore missing old NewsShowcase news #487](https://github.com/ruyisdk/ruyisdk-website/pull/487)
- [pages(biweekly): remove all biweekly pages #488](https://github.com/ruyisdk/ruyisdk-website/pull/488)
- [pages(index): restore index VideoIntro #492](https://github.com/ruyisdk/ruyisdk-website/pull/492)
- [pages(index): new component DevBoards #494](https://github.com/ruyisdk/ruyisdk-website/pull/494)
- [Enhance installation process and update related documentation #443](https://github.com/ruyisdk/ruyisdk-website/pull/443)

#### 1.6 RuyiSDK.cn 社区

- [简单介绍一下制作sysroot的几种常用方式](https://ruyisdk.cn/t/topic/2681)
- [关于sysroot的一些简单说明~](https://ruyisdk.cn/t/topic/2679)

#### 1.7 RuyiSDK技术分享

- 每周三技术分享，RuyiSDK.org网站开发技术分享

### 2. RuyiAI

- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/795 [ci] Weekly auto-release
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/782 [ci] Enable riscv release for py310/py311
- 提交 PR https://github.com/RuyiAI-Stack/triton-riscv/pull/22 [cli] Add triton-shared-opt to console_scripts
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/797 Bump llvm
- Review PR https://github.com/buddy-compiler/buddy-mlir/pull/796 [exmple] Update BuddyYOLO26

### 3. SAIL和ACT

#### 3.1 SAIL和ACT开发

- [sail-riscv#1727](https://github.com/riscv/sail-riscv/pull/1727)
- [sail-riscv#1725](https://github.com/riscv/sail-riscv/pull/1725)
- [sail-riscv#1732](https://github.com/riscv/sail-riscv/pull/1732)  
- [更新smwid](https://github.com/challenger1024/sail-riscv/pull/1)  
- [sail-riscv#1706](https://github.com/riscv/sail-riscv/pull/1706)
- [ame-reg#commit](https://github.com/riscv/sail-riscv/compare/master...KotorinMinami:sail-riscv:ame-regs)
- [sail-riscv#1581](https://github.com/riscv/sail-riscv/pull/1581)
- [lean: add match equation binders for termination measures](https://github.com/rems-project/sail/pull/1673)
- [Review PR1581](https://github.com/riscv/sail-riscv/pull/1581)
- 调研 AME 指令指令编码，opcodes/sail/asm 生成

#### 3.2 技术分享

- 受RISC-V工委会邀请，分享SAIL技术讲座
- 每周三技术分享，SAIL技术讲座

#### 3.3 SAIL会议

- 参加东亚双周会 0514，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1N3kEAB6Lvu_aFeGpgrEf9HqRUcvQmIFLK7_xjjqJfBs/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0528，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1_v9aq2fp0H2MsySiYubt92K6BWXVpkcfi8rJ0CSB6jE/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

### 4. 2026年RISC-V 欧洲峰会

2026年欧洲峰会入选海报提交
参考：https://riscv-europe.org/summit/2026/posters

- [RuyiSDK Package Manager - A Unified Package Management and Development Environment for RISC-V](https://cfp.riscv-europe.org/eu-summit-2026/talk/review/GXE9CB8EZPTVJTKQKNZDHH3VUMKLTBM9)

- [An Efficient Approach to Apply the RISC-V Sail Model to Chip Verification](https://cfp.riscv-europe.org/eu-summit-2026/talk/review/ZNJWLQ3JXRVJRQNKY79JPRWU79CZHLDF)

- [Sail-RISCV-WASM A Browser-Native RISC-V Toolchain and Debugging Workbench](https://cfp.riscv-europe.org/eu-summit-2026/talk/review/EGGGKS9RSPFGRA3NSN9HZVREZVLYMZFC)

- [From Fragmentation to Systematization: A Standardized Quality Selection and Reconstruction Approach for RISC-V Courses](https://cfp.riscv-europe.org/eu-summit-2026/talk/review/EK7LLMAHYGNZAWAMJSZNWKBYCPTYRYVL)

4张海报完成打印

### 5. 2026年中国科学院公众科学日

团队参加2026年5月16日中国科学院公众科学日软件研究所活动，展示RuyiSDK和RuyiAI成果，展出互动和展示实物16项，[软件所科学日链接](https://mp.weixin.qq.com/s/b4TYZOtbSkqCLPRhZ4Balw)，[RuyiSDK社区链接](https://ruyisdk.cn/t/topic/2690)。开展RuyiSDK推广活动，促进RuyiSDK的文档下载。

- RISC-V发展史
- RISC-V大模型知识问答互动
- RuyiSDK介绍
- RuyiAI介绍
- RISC-V 开发板实物展示
- RuyiSDK RISC-V ROS2机器人开发课堂
- RISC-V ROS移植和机器人开发介绍
- RISC-V移动机器人
- RISC-V无人机
- RuyiSDK RISC-V 嵌入式开发课堂
- RuyiSDK开发应用实例——RISC-V多模态大模型盲人应用互动
- RuyiSDK开发应用实例——Duo人脸识别
- RuyiSDK开发应用实例——手势识别
- RuyiSDK开发应用实例——手写识别
- RuyiSDK开发应用实例——openMPI高性能计算
- RuyiAI开发应用实例——LLM互动问答（飞书 -OpenClaw -RuyiAI Serving -buddy-cli -Tenstorrent）

- RuyiSDK RISC-V 嵌入式开发课堂 ——DHT22+OLED 温湿度检测编程实验
  - [RuyiSDK RISC-V 嵌入式开发课堂主体文档](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/ScienceDay/%E7%A7%91%E5%AD%A6%E6%97%A5/RuyiSDK%20RISC-V%20%E5%B5%8C%E5%85%A5%E5%BC%8F%E5%BC%80%E5%8F%91%E8%AF%BE%E5%A0%82%20%E2%80%94%E2%80%94DHT22%2BOLED%20%E6%B8%A9%E6%B9%BF%E5%BA%A6%E6%A3%80%E6%B5%8B%E7%BC%96%E7%A8%8B%E5%AE%9E%E9%AA%8C.md#752-%E5%AE%8C%E6%95%B4%E4%BB%A3%E7%A0%81) 
  - [Dht22 部署文档](https://github.com/ZihanCheng63/my-repo/blob/main/Duo_S/Dht22%20%E9%83%A8%E7%BD%B2%E6%96%87%E6%A1%A3.md)
  - [OLED 例题](https://github.com/ZihanCheng63/my-repo/blob/main/ruyi/%E7%A7%91%E5%AD%A6%E6%97%A5/%E4%BE%8B%E9%A2%98)
  - [OLED 示例填空](https://github.com/ZihanCheng63/my-repo/blob/main/ruyi/%E7%A7%91%E5%AD%A6%E6%97%A5/%E5%A1%AB%E7%A9%BA)
- [RISC-V大模型知识问答互动](https://github.com/EnzoDing-rgb/OpenSiliconBet) 
- [RuyiSDK开发应用实例——RISC-V多模态大模型盲人应用互动]https://github.com/challenger1024/SeeTheWorld

- [ROS2-Academy-for-Beginners](https://github.com/YunxiangLuo/ROS2-Academy-for-Beginners)

### 6. 职工

#### 6.1 蔡玮霖

-测试 Ruyi 0.49.0-beta.20260519 提交测试报告
   -[!94 Add v0.49.0 test report](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/94)
-ruyisdk-website 仓库提交 32 个 pr
   -[misc: remove /blog /biweekly route from sitemap #445](https://github.com/ruyisdk/ruyisdk-website/pull/445)
   -[Auto-update: API data to latest #448](https://github.com/ruyisdk/ruyisdk-website/pull/448)
   -[ci: wait longer on 202 to reduse api using rate #450](https://github.com/ruyisdk/ruyisdk-website/pull/450)
   -[Auto-update: API data to latest #452](https://github.com/ruyisdk/ruyisdk-website/pull/452)
   -[pages(dashboard): new testing dashboard page /dashboard_thin #453](https://github.com/ruyisdk/ruyisdk-website/pull/453)
   -[pages(dashboard): add data update time to dashboard_thin #454](https://github.com/ruyisdk/ruyisdk-website/pull/454)
   -[pages(dashboard): better api data update animation for dashboard_thin #455](https://github.com/ruyisdk/ruyisdk-website/pull/455)
   -[pages(about): use docusaurus mdx render #456](https://github.com/ruyisdk/ruyisdk-website/pull/456)
   -[pages(dashboard): add stats detail doc to dashboard_thin #457](https://github.com/ruyisdk/ruyisdk-website/pull/457)
   -[docs(CodeBlock): better codeblock #458](https://github.com/ruyisdk/ruyisdk-website/pull/458)
   -[docs(CodeBlock): move docs_utils to Docs and fix docs import #459](https://github.com/ruyisdk/ruyisdk-website/pull/459)
   -[pages(DashBoard): dashboard_thin data animation 5 times max #463](https://github.com/ruyisdk/ruyisdk-website/pull/463)
   -[pages(DashBoard): dashboard_thin data animation 30 times max #464](https://github.com/ruyisdk/ruyisdk-website/pull/464)
   -[pages(dashboard): add translation for dashboard_thin #465](https://github.com/ruyisdk/ruyisdk-website/pull/465)
   -[Release new dashboard page #466](https://github.com/ruyisdk/ruyisdk-website/pull/466)
   -[pages(news/events): new event 202605-cas-public-science-day-2026 #467](https://github.com/ruyisdk/ruyisdk-website/pull/467)
   -[pages(news/events/202605-cas-public-science-day-2026): fallback on pdf preview failed #468](https://github.com/ruyisdk/ruyisdk-website/pull/468)
   -[pages(index): add 202605-cas-public-science-day-2026 card #469](https://github.com/ruyisdk/ruyisdk-website/pull/469)
   -[pages(news/events/202605-cas-public-science-day-2026): modify more registration option link #470](https://github.com/ruyisdk/ruyisdk-website/pull/470)
   -[pages(news/events): fix wechat triger download pdf before hydration #471](https://github.com/ruyisdk/ruyisdk-website/pull/471)
   -[pages(footer): add /riscv-specs #477](https://github.com/ruyisdk/ruyisdk-website/pull/477)
   -[pages(index): remove 202605-cas-public-science-day-2026 index card #478](https://github.com/ruyisdk/ruyisdk-website/pull/478)
   -[pages(news): use loadContent/loadContent instead of news.json #481](https://github.com/ruyisdk/ruyisdk-website/pull/481)
   -[Merge old blogs to /news page and remove duplicate blogs #482](https://github.com/ruyisdk/ruyisdk-website/pull/482)
   -[pages(news): restore old meetup news and NewsShowcase news to /news #483](https://github.com/ruyisdk/ruyisdk-website/pull/483)
   -[pages(index): add cas-public-science-day-2026 to news #484](https://github.com/ruyisdk/ruyisdk-website/pull/484)
   -[static(img): convert all imgs to webp #485](https://github.com/ruyisdk/ruyisdk-website/pull/485)
   -[pages(news): add news page title #486](https://github.com/ruyisdk/ruyisdk-website/pull/486)
   -[pages(news): restore missing old NewsShowcase news #487](https://github.com/ruyisdk/ruyisdk-website/pull/487)
   -[pages(biweekly): remove all biweekly pages #488](https://github.com/ruyisdk/ruyisdk-website/pull/488)
   -[pages(index): restore index VideoIntro #492](https://github.com/ruyisdk/ruyisdk-website/pull/492)
   -[pages(index): new component DevBoards #494](https://github.com/ruyisdk/ruyisdk-website/pull/494)
-ruyisdk-website 仓库审核 1 个 pr
   -[Enhance installation process and update related documentation #443](https://github.com/ruyisdk/ruyisdk-website/pull/443)
-wechat-articles 仓库提交 2 个 pr
   -[testing: update 0.49.0 test status #266](https://github.com/ruyisdk/wechat-articles/pull/266)
   -[20260526-ruyisdk-biweekly-69.md: update test status #277](https://github.com/ruyisdk/wechat-articles/pull/277)
-迁移 ruyi 的 lit 测试到 pytest [534d2e4...78b3990](https://github.com/ruyisdk-test/ruyi-pytest/compare/534d2e47412e44a7d2a1a4ef82bdbe7638407b17...78b39902a2ad63b03c109e8e297849554a37997a)
   -共计 15 个 commit，212 行增加，51 行删除
   -pytest-ci [b51b59b...98b7ef6](https://github.com/ruyisdk-test/ruyi-pytest-ci/compare/b51b59b253addeeae2d1bdc19436ff9f01fc5290...98b7ef6b87f3d2ec3f147203359fd793562263f8) 共计 45 个 commit，1058 行增加
   -pytest-report [0a1d1b0...f139253](https://github.com/ruyisdk-test/ruyi-pytest-reports/compare/0a1d1b0b7aa9cb02ec1f9ec80cf59fd0c8a8c875...f1392537848bd25cbc030d9661d6294d4e9c856d) 共计 7 个 commit，112 行增加，332 行删除

#### 6.2 阎明铸

##### 6.2.1 Sail

- 初步调研 AME 指令指令编码，opcodes/sail/asm 生成
- Review PR https://github.com/riscv/sail-riscv/pull/1581

##### 6.2.2 Ruyi AI

- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/795 [ci] Weekly auto-release
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/782 [ci] Enable riscv release for py310/py311
- 提交 PR https://github.com/RuyiAI-Stack/triton-riscv/pull/22 [cli] Add triton-shared-opt to console_scripts
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/797 Bump llvm
- Review PR https://github.com/buddy-compiler/buddy-mlir/pull/796 [exmple] Update BuddyYOLO26

##### 6.2.3 会议和展示

- [RISC-V欧洲峰会 Poster 1](https://github.com/trdthg/plct/blob/main/outcome_byear/2026/archive/An%20Efficient%20Approach%20to%20Apply%20the%20RISC-V%20Sail%20Model%20to%20Chip%20Verification.pptx)
- [RISC-V欧洲峰会 Poster 2](https://github.com/trdthg/plct/blob/main/outcome_byear/2026/archive/Sail-RISCV-WASM%20A%20Browser-Native%20RISC-V%20Toolchain%20and%20Debugging%20Workbench.pptx)
- RuyiSDK 机器人开发课程仿真开发（用于中国科学院公众科学日） https://github.com/trdthg/ROS-Academy-for-Beginners
- 参加东亚双周会 0514，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1N3kEAB6Lvu_aFeGpgrEf9HqRUcvQmIFLK7_xjjqJfBs/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0528，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1_v9aq2fp0H2MsySiYubt92K6BWXVpkcfi8rJ0CSB6jE/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

#### 6.3 张馥媛

##### 6.3.1 RuyiSDK 示例代码库建设

设计、参与开发或审核

- 开发板示例文档扩充
	- VisionFive2Lite
		- [RuyiSDK GPIO功能示例：VisionFive 2 Lite GPIO PUD 验证](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/GPIO_PUD/README_zh.md)
		- [RuyiSDK GPIO功能示例：VisionFive 2 Lite LED 闪烁基准测试](https://github.com/zhiyao310/board-docs/blob/main/VisionFive2Lite/GPIO_LED/README_zh.md)
	- DuoS 
		- [PWM 脉宽调制测试](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Duo_S/example_pwm_Duo_S.md)
		- [I2C OLED 显示屏测试](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Duo_S/example_I2C_Duo_S.md)
	- ESP32-P4-Function-EV-Board
		- 概述:[README.md](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/README.md);[README_zh.md](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/README_zh.md)
		- [HelloWorld](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/HelloWorld/README_zh.md)
		- [Coremark](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/Coremark/README_zh.md)
		- [RuyiSDK LVGL 示例：LVGL Demo v8](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/LVGL%20Demo%20v8/README_zh.md)
		- [RuyiSDK LVGL 示例：LVGL Demo v9](https://github.com/zhiyao310/board-docs/blob/main/ESP32-P4/LVGL_Demo_v9/README_zh.md)
	- Nuclei RV-STAR
		- [Coremark](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Nuclei%20RV-STAR/example_Coremark_rv-star.md)
		- [HelloWorld](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Nuclei%20RV-STAR/example_HelloWorld_rv-star.md)
- RuyiSDK开发资源梳理和资源申请
	- [[Resource Request]: riscv32-esp-elf Toolchain for ESP32 Series (Bare-metal)](https://github.com/ruyisdk/ruyisdk/issues/87)

- Licheepi4A 示例文档：  
  - [YOLOV5s](https://github.com/TOT2232/board-docs/blob/main/LicheePi4A/YOLOV5s/README_zh.md)

Duo 256M 示例文档：  
  - [YOLOv5](https://github.com/TOT2232/board-docs/blob/main/Duo_256m/YOLOv5/READEME_zh.md)
  - [YOLOv8](https://github.com/TOT2232/board-docs/blob/main/Duo_256m/YOLOv8/README_zh.md)
  - [YOLOv11](https://github.com/TOT2232/board-docs/blob/main/Duo_256m/YOLOv11/README_zh.md)
  - [YOLOv12](https://github.com/TOT2232/board-docs/blob/main/Duo_256m/YOLOv12/README_zh.md)

- [B站视频去水印及二次剪辑操作手册](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/research/bili_test.md)

##### 6.3.2 中国科学院公众科学日

参与展示物设计、开发或审核
1.RuyiSDK RISC-V 嵌入式开发课堂 ——DHT22+OLED 温湿度检测编程实验

  - [RuyiSDK RISC-V 嵌入式开发课堂主体文档](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/ScienceDay/%E7%A7%91%E5%AD%A6%E6%97%A5/RuyiSDK%20RISC-V%20%E5%B5%8C%E5%85%A5%E5%BC%8F%E5%BC%80%E5%8F%91%E8%AF%BE%E5%A0%82%20%E2%80%94%E2%80%94DHT22%2BOLED%20%E6%B8%A9%E6%B9%BF%E5%BA%A6%E6%A3%80%E6%B5%8B%E7%BC%96%E7%A8%8B%E5%AE%9E%E9%AA%8C.md#752-%E5%AE%8C%E6%95%B4%E4%BB%A3%E7%A0%81) 
  - [Dht22 部署文档](https://github.com/ZihanCheng63/my-repo/blob/main/Duo_S/Dht22%20%E9%83%A8%E7%BD%B2%E6%96%87%E6%A1%A3.md)
  - [OLED 例题](https://github.com/ZihanCheng63/my-repo/blob/main/ruyi/%E7%A7%91%E5%AD%A6%E6%97%A5/%E4%BE%8B%E9%A2%98)
  - [OLED 示例填空](https://github.com/ZihanCheng63/my-repo/blob/main/ruyi/%E7%A7%91%E5%AD%A6%E6%97%A5/%E5%A1%AB%E7%A9%BA)

- RISC-V 三国杀互动 Demo
  - 参与中科院公众科学日展示活动，现场布展并演示全栈互动应用，活动当天工作量较大。
  - 项目仓库：[OpenSiliconBet](https://github.com/EnzoDing-rgb/OpenSiliconBet) — RISC-V 三国杀 · 指令集 × AI/Agent 时代互动 Demo。
  - 项目概述
    - 全栈小应用（FastAPI + React/Vite）：论坛交锋形式，设 RISC-V / x86 / ARM 三阵营 + Lex 主持 + 黄仁勋环节 + 观众问答。
    - 面向中关村·公众科学日类科普分会场，不做胜负式辩论，强调科普互动体验。
    - 文档
      - `docs/design/architecture.md` — 架构宪章
      - `docs/design/implementation.md` — 实现计划与测试策略
      - `docs/design/realtime-tts-architecture.md` — 实时 TTS 架构
      - `docs/background/deep-research.md` — 共享事实背景
      - `docs/characters/` — 五嘉宾视角 SKILL
      - `dev.sh` — 一键本地运行 / Cloudflare Tunnel 生产部署脚本
      - `README.md` — 完整项目文档与使用说明

##### 6.3.3 RISC-V Linux系统与开发板实践课程

参与展示物设计、开发或审核
- [初步教学大纲](https://github.com/EnzoDing-rgb/riscv-embedded-course/blob/master/docs/outline.md)
- [调研文档](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/%E8%AF%BE%E7%A8%8B%E4%BD%93%E7%B3%BB%E5%88%86%E6%9E%90%E8%A1%A8.xlsx)
