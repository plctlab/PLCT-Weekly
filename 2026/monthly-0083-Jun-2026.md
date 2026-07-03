# RISC-V 软件生态进展 · 第 83 期·2026 年 6 月汇总

## 本期亮点

## RuyiSDK IDE / Eclipse Plugin

## RuyiSDK IDE / VSCode Plugin

## RuyiSDK 包管理器

## RuyiSDK 网站更新

## V8 / Chromium
#### Update:
实现 fp16 的 vfadd/vfsub/vfmul/vfdiv；新增 ZVFH 扩展 CPU feature；Simulator 中实现 ZFH  
- 7897892: [riscv]Implement ZFH in Simulator | https://chromium-review.googlesource.com/c/v8/v8/+/7897892
- 7980710: [riscv] Enable ZVFH support for Liftoff WebAssembly SIMD | https://chromium-review.googlesource.com/c/v8/v8/+/7980710  
- 7953190: [riscv] Implement vfadd/vfsub/vfmul/vfdiv for fp16 | https://chromium-review.googlesource.com/c/v8/v8/+/7953190  
- 7953184: [riscv] Implement CompareSmiAndAssert | https://chromium-review.googlesource.com/c/v8/v8/+/7953184  
#### 错误修复
- 7917370: [riscv] Fix Debug check failed: !L->is_bound() | https://chromium-review.googlesource.com/c/v8/v8/+/7917370
- 7908311: [riscv] Fix error that use of undeclared identifier | https://chromium-review.googlesource.com/c/v8/v8/+/7908311
- 7889597: [riscv] Disable float16 due to RVV don't support Zvfh now. | https://chromium-review.googlesource.com/c/v8/v8/+/7889597
- 7882462: [riscv] Support i16 in liftoff | https://chromium-review.googlesource.com/c/v8/v8/+/7882462
- 7884915: [riscv] Use unsigned comparison in JSToWasmWrapperHelper | https://chromium-review.googlesource.com/c/v8/v8/+/7884915


####  Uptream  Port:
- 7992037: Reland [riscv][maglev] Sign extend index register in DataView bounds check | https://chromium-review.googlesource.com/c/v8/v8/+/7992037  
- 7983344: [riscv]sandbox: Replace CPT with TPT | https://chromium-review.googlesource.com/c/v8/v8/+/7983344  
- 7953185: [riscv][debug] Move DebugInfo to trusted space | https://chromium-review.googlesource.com/c/v8/v8/+/7953185  
- 7901154: [riscv][wasmfx] Avoid code cache lookup on suspend | https://chromium-review.googlesource.com/c/v8/v8/+/7901154
- 7888915: [riscv]Add SmiUntagUnsigned helpers and adjust maglev debug condition | https://chromium-review.googlesource.com/c/v8/v8/+/7888915
- 7888915: [riscv]Add SmiUntagUnsigned helpers and adjust maglev debug condition | https://chromium-review.googlesource.com/c/v8/v8/+/7888915


## Spidermonkey / Firefox

## OpenJDK

## Go

## GNU Toolchain

## LLVM Team

## MLIR / Buddy Compiler

## opensbi

## 罗云翔测试团队
（包含 SAIL 和 ACT 测试部分）

本月在RuyiSDK方面，完成了0.50.0-beta.20260623版本在13种Linux发行版和多架构上的测试，无新增缺陷，包管理器符合出口标准准予发版；新增了K510、Duo S、Duo 256M等开发板示例文档，推进了board-docs-frontend示例网站建设；撰写了sysroot系列实用文档和开发板烧录指南；对官网进行了下载页面重构、移动端适配、文档UX优化等约28项更新。RuyiAI方面为buddy-mlir贡献7个PR，涵盖LLVM升级、CI增强与RISC-V依赖修复，同时推进llvm-project后端拆分和triton-riscv版本升级。SAIL方面完成AME指令编解码实现并向上游提交PR。开发板工具链测试覆盖8款以上RISC-V开发板，嵌入式课程完成第一章讲义与实验。团队4张海报在2026 RISC-V欧洲峰会展示。

### 1. RuyiSDK

#### 1.1 RuyiSDK测试

- [RuyiSDK 测试策略和测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/README.md)
  - [RuyiSDK RuyiSDK 0.50.0-beta.20260623 版本测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/README.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260623/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian13 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Debian13_x86_64_测试结果.md)
    - [Debian13 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Debian13_riscv64_测试结果.md)
    - [Debian13 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Debian13_aarch64_测试结果.md)
    - [Debian sid x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Debiansid_x86_64_测试结果.md)
    - [Debian sid aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Debiansid_aarch64_测试结果.md)
    - [Ubuntu24.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Ubuntu24.04_x86_64_测试结果.md)
    - [Ubuntu24.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Ubuntu24.04_riscv64_测试结果.md)
    - [Ubuntu26.04 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/blob/master/20260623/RUYI_包管理_Ubuntu26.04_x86_64_测试结果.md)
    - [Ubuntu26.04 riscv64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Ubuntu26.04_riscv64_测试结果.md)
    - [Ubuntu26.04 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Ubuntu26.04_aarch64_测试结果.md)
    - [openEuler24.03 sp1 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_openEuler24.03sp1_x86_64_测试结果.md)
    - [openEuler24.03 sp1 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_openEuler24.03sp1_aarch64_测试结果.md)
    - [openEuler24.03 sp2 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_openEuler24.03sp2_x86_64_测试结果.md)
    - [openEuler24.03 sp2 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_openEuler24.03sp2_aarch64_测试结果.md)
    - [openEuler25.03 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_openEuler25.03_x86_64_测试结果.md)
    - [openEuler25.03 aarch64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_openEuler25.03_aarch64_测试结果.md)
    - [Fedora42 x86\_64 测试报告](https://gitee.com/yunxiangluo/ruyisdk-test/tree/master/20260623/RUYI_包管理_Fedora42_x86_64_测试结果.md)

    - 缺陷：  
      RuyiSDK 遗留缺陷：
      | 缺陷 | 问题等级 | 备注 |
      | — | — | — |
      | i18中文翻译问题 #156 | 修复 | |
      | ruyinews界面卡片特效缩放异常 #157 | 修复 | |
      | 新闻中英文按钮大小不一致 #160 | 修复 | |
      | i18n中文支持情况 #161 | 修复 | |
      | ruyi-venv创建过程时default默认情况下sysroot配置消失 #162 | 修复 | |
      | 在无网络状态下，插件新闻无法离线渲染以及加载出中英文按钮 #171 | 建议 | |
      无新增缺陷。

      RuyiSDK Eclipse IDE 测试
      本版本无同步发版的 Eclipse 插件测试。
      遗留缺陷：
      | 缺陷 | 问题等级 | 备注 |
      | — | — | — |
      | 命令执行提示框可以任意关闭且无法重新打开 #82 | 建议 | |
      | 虚拟环境建立的项目绑定问题 #84 | 建议 | |
      | 安装插件时 Eclipse 提示未签名 #85 | 建议 | |
      | 有一些可以自动获取的东西，不需要手动填写 #90 | 建议 | |
      | UI：新闻界面切换仅未读"勾号"不明显 #98 | 建议 | |
      | ruyi-venv中的vnev path需要手动点击右侧列表，显示项目路径 #152 | 建议 | |
      | ruyi-venv名称可以默认设置为ruyi-venv-profile属性 #153 | 建议 | |
      无新增缺陷。

      文档测试
      遗留缺陷：
      | 缺陷 | 问题等级 | 备注 |
      | — | — | — |
      | 关于 fastboot 的文档提示 #95 | 严重 | 建立新的 issue 进行更新，修复已经延后 |

      Ruyi 包管理器测试
      遗留缺陷：
      | 缺陷 | 问题等级 | 判定依据 |
      | — | — | — |
      | Occasional pygit2 failures during testing #415 | 一般 | 已有 issue 回复 |
      无新增缺陷。
      新增特性手动测试验证功能正常。

- 更新 Ruyi 0.49.0 测试报告的 IDE 和 VSCode 部分
  - [!95 Update 0.49.0 IDE test status](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/95)
  - [!96 Update 0.49.0 IDE test status](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/96)

- [Ruyi 0.50.0-beta.20260616: No module named '\_bz2' #473](https://github.com/ruyisdk/ruyi/issues/473)

- ruyisdk-eclipse-plugins 测试
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/177 New Virtual environment添加虚拟环境时响应时间过长
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/178 venv创建Ruyi-venv名称默认情况下finishbutton报错
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/179 在使用不包含 sysroot 的工具链 （例如 xscc） 时，可通过指定其他工具链，此时仍包含xscc
  - https://github.com/ruyisdk/ruyisdk-eclipse-plugins/issues/180 eclipse 插件暂不支持0.49版本ruyi的复制，软连接，rootfs投影方式
 
- ruyisdk-vscode-extension 测试
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/180 抑制如意侦测消息后重启方式
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/181 管理仓库中对系统仓库（ruyisdk）的操作失败
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/182 删除ruyi cli的新闻阅读状态后，扩展的新闻状态仍是已读
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/183 Ruyi News界面左上角为英文 
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/186 如意board docs 扩展页为英文
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/187 Ruyi venv 列表模拟器和toolchain列表版本标签英文
  - https://github.com/ruyisdk/ruyisdk-vscode-extension/issues/188 如意新闻搜索提示英文

- [#480 repo add ruyisdk 报错信息在非 Rich 终端下缺失关键词 repo](https://github.com/ruyisdk/ruyi/issues/480)

#### 1.2 RuyiSDK测试开发

- packages-index
  - Bianbu for k1 更新的最新 v2.3.3 [board-image/bianbu-{desktop,desktop-lite,minimal}-spacemit-k1{,-sd}: new version v2.3.3 #196](https://github.com/ruyisdk/packages-index/pull/196)
  - 增加 Spacemit Muse Pi Pro 支持和 Bianbu UEFI 镜像支持 [New device spacemit muse pi pro and uefi support for spacemit-k1-v1 strategy #198](https://github.com/ruyisdk/packages-index/pull/198)
  - Bianbu for K3 的支持 draft， 由实习生在 Spacemit K3 Pico-ITX 测试中 [New device Spacemit K3 Pico-ITX #199](https://github.com/ruyisdk/packages-index/pull/199)
  - 关联 #198 [Spacemit K1 UEFI image support #197](https://github.com/ruyisdk/packages-index/issues/197)
  - 关联 #199 [New device Spacemit K3 Pico-ITX #199](https://github.com/ruyisdk/packages-index/issues/200)
  - [#190 board-image/armbian-spacemit-musepipro: add new packages](https://github.com/ruyisdk/packages-index/pull/190)
  - [#184 board-image/armbian-orangepi-rv2-xfce:add new packages](https://github.com/ruyisdk/packages-index/pull/184)
  - [#185 board-image/armbian-orangepi-rv2-minimal:add new packages](https://github.com/ruyisdk/packages-index/pull/185)
  - [#188 board-image/armbian-starfive-visionfive2-xfce:add new packages](https://github.com/ruyisdk/packages-index/pull/188)
  - [#189 board-image/armbian-starfive-visionfive2-minimal:add new packages](https://github.com/ruyisdk/packages-index/pull/189)

-ruyi-backend
  - [添加 IDE 最新版本查询 endpoint #98](https://github.com/ruyisdk/ruyi-backend/issues/98)

- [制作claude code桌面机器人](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-June/claude%20code%20桌面机器人.md)

- ruyisdk-test
  - [#10 tests: add repo test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/10)
  - [#11 tests: add update test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/11)
  - [#5 tests: add config test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/5)
  - [#7 tests: add device test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/7)
  - [#8 tests: add uninstall test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/8)
  - [#9 tests: add pytest-html for visual test reports](https://github.com/ruyisdk-test/ruyi-pytest/pull/9)
  - [#12 tests: add telemetry test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/12)
  - [#6 tests: add self test cases](https://github.com/ruyisdk-test/ruyi-pytest/pull/6)

- riko-bot
  - [b517ab5 ruyi_packages: update the metadata desc for armbian-musepipro](https://github.com/ruyisdk-test/riko-bot/commit/b517ab51a569f2525ac79ad04bf2ab9ec27f59fa)
  - [a8ebb79 ruyi_packages: split armbian-musepipro image-combo into minimal and xfce variants](https://github.com/ruyisdk-test/riko-bot/commit/a8ebb792ce78777a5da8bf8d0b53506d863dd16e)
  - [5e19925 ruyi_packages: split armbian-orangepirv2 image-combo into minimal and xfce variants](https://github.com/ruyisdk-test/riko-bot/commit/5e19925eac7d250dc15d747d31973f27224b30f7)
  - [b9b4c4e ruyi_packages: split armbian-visionfive2 image-combo into minimal and xfce variants](https://github.com/ruyisdk-test/riko-bot/commit/b9b4c4e3a0f942e2002e7ed80db1eea9ac02a7c2)

#### 1.3 RuyiSDK开发示例库和示例库网站开发

- Canaan K510-CRB-V1.2 KIT
 - [概述](https://github.com/ruyisdk/board-docs/blob/main/K510/README.md);[中文概述](https://github.com/ruyisdk/board-docs/blob/main/K510/README_zh.md)
 - [HelloWorld](https://github.com/ruyisdk/board-docs/blob/main/K510/HelloWorld/README.md)
 - [Coremark](https://github.com/ruyisdk/board-docs/blob/main/K510/Coremark/README.md)
 - [RuyiSDK GPIO 示例：GPIO KEYS Demo](https://github.com/ruyisdk/board-docs/blob/main/K510/GPIO_KEYS/README.md)
 - [RuyiSDK 系统示例：RTC Demo](https://github.com/ruyisdk/board-docs/blob/main/K510/RTC/README.md)
- Milk-V Duo S
 - [SPI 测试](https://github.com/ZihanCheng63/board-docs/blob/main/Duo_S/SPI/README_zh.md)
 - [DF9GMS 测试](https://github.com/ZihanCheng63/board-docs/blob/main/Duo_S/DF9GMS/README_zh.md)
- Duo 256M
 - [YOLOv8-person-pets](https://github.com/ruyisdk/board-docs/blob/main/Duo_256m/%20yolov8-person-pets/README_zh.md)
 - [face-detection](https://github.com/ruyisdk/board-docs/blob/main/Duo_256m/face-detection/README_zh.md)
 - [pedestrian-detection](https://github.com/ruyisdk/board-docs/blob/main/Duo_256m/pedestrian-detection/README_zh.md)
- Sipeed Tang Mega 138K
 - [Sipeed Tang Mega 138K 测试报告](https://github.com/ZihanCheng63/ruyisdk-dev-archive/blob/main/reports/ZihanCheng/Test%20reports.md)
- [Add Canaan K510-CRB-V1.2 KIT cases and docs](https://github.com/ruyisdk/board-docs/pull/17)
- [Add RTC demo for Canaan K510 CRB-V1.2 KIT](https://github.com/ruyisdk/board-docs/pull/20)

- RuyiSDK开发板示例库网站（board-docs-frontend）
 - 项目仓库：[board-docs-frontend](https://github.com/DuoQilai/board-docs-frontend)
 - 在线站点：[https://board-docs-frontend.pages.dev](https://board-docs-frontend.pages.dev/)

#### 1.4 RuyiSDK 文档编写

- [testing: update 0.49.0 test status #266](https://github.com/ruyisdk/wechat-articles/pull/266)
- [20260526-ruyisdk-biweekly-69.md: update test status #277](https://github.com/ruyisdk/wechat-articles/pull/277)
- [如何制作sysroot](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-May/%E5%A6%82%E4%BD%95%E5%88%B6%E4%BD%9Csysroot.md)
- [sysroot介绍](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-May/sysroot%E4%BB%8B%E7%BB%8D.md)
- [在ruyisdk中使用sysroot](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-May/%E5%9C%A8ruyisdk%E4%B8%AD%E4%BD%BF%E7%94%A8sysroot.md)
- [K3开发板烧录 openruyi](https://github.com/ruyisdk-test/test-working/blob/main/cjh/26-May/K3%E5%BC%80%E5%8F%91%E6%9D%BF%E7%83%A7%E5%BD%95openruyi.md)
- [B站视频去水印及二次剪辑操作手册](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/research/bili_test.md)

#### 1.5 RuyiSDK网站

- 修复文档页面代码块渲染问题：[docs: fix code block rendering in VS Code case1 #495](https://github.com/ruyisdk/ruyisdk-website/pull/495)
- 修复移动端边栏出现时顶栏和边栏动画透明度不一致的问题：[Navbar and sidebar transparency fix #512](https://github.com/ruyisdk/ruyisdk-website/pull/512)
- 调整开发板板块的移动端显示：[pages(index): better DevBoards components Mobile layout #497](https://github.com/ruyisdk/ruyisdk-website/pull/497)
- 将新的开发板板块发布到首页：[pages(index): add DevBoards component to index #498](https://github.com/ruyisdk/ruyisdk-website/pull/498)
- 更新 VF2 Lite 图片：[pages(index): swap vf2 img with vf2lite #500](https://github.com/ruyisdk/ruyisdk-website/pull/500)
- 优化开发板板块的链接跳转：[pages(index): better mobile title and link jump #501](https://github.com/ruyisdk/ruyisdk-website/pull/501)
- 优化 CI 调用 GitHub API 的逻辑，选取合适的等待时间并减少调用次数：[ci: wait longer on github api data update #502](https://github.com/ruyisdk/ruyisdk-website/pull/502)
- 让官网在 api.ruyisdk.cn 失效时保持正常工作：[misc: fix loading failure when api.ruyisdk.cn failed #503](https://github.com/ruyisdk/ruyisdk-website/pull/503)
- 固定顶栏，增加快速回到顶部按钮：[pages: add back to top button](https://github.com/ruyisdk/ruyisdk-website/commit/3af287b04ec0987b0fae8e0401557a1b5299d74b)
- 完善新下载页面在 /downloads：[pages(downloads): merge some download inform text #513](https://github.com/ruyisdk/ruyisdk-website/pull/513)
- 重构下载页面为组件化：[pages(downloads): refactor into components #515](https://github.com/ruyisdk/ruyisdk-website/pull/515)
- 调整下载页面布局：[pages(downloads): modify page layout #516](https://github.com/ruyisdk/ruyisdk-website/pull/516)
- 整理项目结构，去掉多余的中文翻译：[i18n: remove i18n/zh-Hans #517](https://github.com/ruyisdk/ruyisdk-website/pull/517)
- 修复首页字体因 #507 导致的问题：[pages(index): fix index font broken caused by #507 #518](https://github.com/ruyisdk/ruyisdk-website/pull/518)
- 整理项目结构，修复部分页面视觉宽度的微小差异：[pages(about,news,News/{Blogs,Events}): modify page layout #519](https://github.com/ruyisdk/ruyisdk-website/pull/519)
- 修复文档页面列表显示问题：[pages(docs): fix li, ol and ul #520](https://github.com/ruyisdk/ruyisdk-website/pull/520)
- 新下载页面 IDE 下载链接切换到 api.ruyisdk.cn 的新 endpoint：[api.ruyisdk.cn endpoint form eclipse and vscode plugin release info #521](https://github.com/ruyisdk/ruyisdk-website/pull/521)
- 优化下载页面设计和布局：[pages(downloads): better design and layout #523](https://github.com/ruyisdk/ruyisdk-website/pull/523)
- 完善新下载感谢页面和引导用户阅读文档：[pages(thanks): better download thanks page #525](https://github.com/ruyisdk/ruyisdk-website/pull/525)
- 去除文档页面代码块的黄色底色，统一所有代码块的视觉风格：[pages(docs): remove yellow background from CodeBlock #526](https://github.com/ruyisdk/ruyisdk-website/pull/526)
- 修复下载感谢页面命令行复制功能：[pages(thanks): fix command line copy #527](https://github.com/ruyisdk/ruyisdk-website/pull/527)
- 修复新下载页面部分代码块的行复制按钮：[docs(CodeBlock): fix code copy on downloads page #528](https://github.com/ruyisdk/ruyisdk-website/pull/528)
- 修复新下载页面部分 Markdown 维护的内容的代码块语法兼容问题：[pages(downloads): fix markdown codeblock support #529](https://github.com/ruyisdk/ruyisdk-website/pull/529)
- 修复文档页面架构切换时代码块出现横向滚动条的问题：[pages(docs): fix arch selecte scroll bar #530](https://github.com/ruyisdk/ruyisdk-website/pull/530)
- 调整下载感谢页面渲染时序，在获取到 URI 参数后再渲染 card：[pages(thanks): do not show card before we can get params #531](https://github.com/ruyisdk/ruyisdk-website/pull/531)
- 将 RuyiSDK 站点设计规范应用到 /docs 页面，改进移动端可访问性：[Pull #532 Optimize UX on /docs pages](https://github.com/ruyisdk/ruyisdk-website/pull/532)
- 新的"报告问题"页面：[pages: new page /issue #534](https://github.com/ruyisdk/ruyisdk-website/pull/534)
- News 页面翻页增加 URL 翻页参数：[pages(news): add page url param #535](https://github.com/ruyisdk/ruyisdk-website/pull/535)
- Issue 页面添加 meta 英文翻译：[pages(issue): add meta translation for English page #536](https://github.com/ruyisdk/ruyisdk-website/pull/536)
- 下载页面设计 Issue：[下载页面设计 #522](https://github.com/ruyisdk/ruyisdk-website/issues/522)
- New WebUI and its backend for RuyiSDK Packages-index [a1gorhythm7/packages-index-web](https://github.com/a1gorhythm7/packages-index-web)

#### 1.6 RuyiSDK.cn 社区

- [简单介绍一下制作sysroot的几种常用方式](https://ruyisdk.cn/t/topic/2681)
- [关于sysroot的一些简单说明~](https://ruyisdk.cn/t/topic/2679)

#### 1.7 RuyiSDK技术分享

- 每周三技术分享，实习生实习总结

### 2. RuyiAI

- buddy-compiler/buddy-mlir
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/811 [build] Fixed various dependency installation issues for riscv
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/810 [test] Fix buddy-llc not found
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/809 [LLVM] Bump llvm
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/802 [mlir] Use OpTy::create instead of OpBuilder::create
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/799 [ci] Run check-buddy on multi pytorch version
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/797 [LLVM] Bump llvm
  - 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/766 [LLVM] Remove LLVM source deps

- RuyiAI-Stack/llvm-project
  - 提交 PR https://github.com/RuyiAI-Stack/llvm-project/pull/13 Split Buddy extended backends to separate files

- RuyiAI-Stack/triton-riscv
  - 提交 PR https://github.com/RuyiAI-Stack/triton-riscv/pull/34 Bump triton and llvm to latest

### 3. RISC-V 开发板编译工具链测试

- [RISC-V 开发板调研](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/research/8%E9%A1%B9Linux%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)
- RuyiSDK开发资源梳理和资源申请
 - [[Resource Request]: riscv32-esp-elf Toolchain for ESP32 Series (Bare-metal)](https://github.com/ruyisdk/ruyisdk/issues/87)
- RISC-V 编译工具链开发板可用性测试（烧录镜像、安装 ruyi、测试 ruyi gcc 工具链）
  - [CH32V208](https://github.com/DuoQilai/ruyisdk-dev-archive/pull/15)
  - [EBC7700](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/EBC7700.md)
  - [EBC7702](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/EBC7702.md)
  - [P550](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/P550.md)
  - [A210](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/A210.md)
  - [K3](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/K3_Pico-ITX.md)
  - [SG2044](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/SG2044.md)
  - [CH32V208WBU6-EVT-R0-1v4](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/reports/ZhiyaoBian/Test%20repoorts/CH32V208.md)
  - [Sipeed Tang Mega 138K](https://github.com/ZihanCheng63/my-repo/blob/main/10%E7%A7%8D%E5%BC%80%E5%8F%91%E6%9D%BF%2B%E7%BC%96%E8%AF%91%E5%99%A8%E6%B5%8B%E8%AF%95%E7%94%A8%E4%BE%8B-v2(1).docx)

### 4. SAIL和ACT

#### 4.1 SAIL和ACT开发

- [实现 SAIL AME 编解码](https://github.com/trdthg/sail-riscv/commit/3cc341b44fc2f7f0cd5acc72bfb7bbf7b930c4bc) 
- [sail-riscv#1786](https://github.com/riscv/sail-riscv/pull/1786)
- [ame-helper#commit](https://github.com/KotorinMinami/sail-riscv/commit/d5a1d1ac8437d8c7eefb3f2b816dabfff1bb5934)

#### 4.2 技术分享

- 每周三技术分享2次，为实习生实习总结

#### 4.3 SAIL会议

- 参加 tech-golden-model meeting [`06.01`, `06.15`, `06.22`, `06.29`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 参加东亚双周会 0611，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1zlKeiVVGMVIzTayEVoIDLlk2A7yy8-KX9mymSohx-9I/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0625，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1k2A1T-pR-M0w0qfafuMykMRiZtMWWp2bHvHh4gnxDvk/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

### 5. RISC-V Linux 嵌入式课程开发

- riscv-embedded-course · 自研课程大纲（课程研发）
 - 项目仓库：[riscv-embedded-course](https://github.com/EnzoDing-rgb/riscv-embedded-course)
 - 在线大纲：[https://enzoding-rgb.github.io/riscv-embedded-course/](https://enzoding-rgb.github.io/riscv-embedded-course/)
 - 课程大纲：[CourseOutline.html](https://enzoding-rgb.github.io/riscv-embedded-course/CourseOutline.html)（在线浏览完整大纲）

- ruyi-riscv-linux-book · 教材仓库协作（重构 + 教案）
 - 项目仓库：[ruyi-riscv-linux-book](https://github.com/DuoQilai/ruyi-riscv-linux-book)
 - 课程总大纲：[course-outline.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/main/docs/course-outline.md)
 - 课程计划：[course-plan.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/main/docs/course-plan.md)
 - 课件开发规范：[course-production-spec-v1.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/main/docs/course-production-spec-v1.md)

 - 文档模板：
   - [asset-guidelines.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/main/docs/templates/asset-guidelines.md)（素材规范）
   - [course-document-template.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/main/docs/templates/course-document-template.md)（课程文档模板）
   - [lab-template.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/main/docs/templates/lab-template.md)（实验模板）
   - [ppt-template.md](https://github.com/DuoQilai/ruyi-riscv-linux-book/blob/main/docs/templates/ppt-template.md)（PPT 模板）

### 6. 2026年RISC-V 欧洲峰会

- 6.10 6.11 6.12 4张海报在2026年欧洲峰会展示
参考：https://riscv-europe.org/summit/2026/posters

- 编写欧洲峰会团队海报宣传稿

### 6. 职工

#### 6.1 蔡玮霖

- 更新 Ruyi 0.49.0 测试报告的 IDE 和 VSCode 部分
    - [!95 Update 0.49.0 IDE test status](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/95)
    - [!96 Update 0.49.0 IDE test status](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/96)
- 测试 Ruyi 0.50.0-beta.20260623 提交测试报告
    - [!97 Add 0.50.0-beta test reports](https://gitee.com/yunxiangluo/ruyisdk-test/pulls/97)
- ruyi 仓库提交 1 个 issue
    - [Ruyi 0.50.0-beta.20260616: No module named '\_bz2' #473](https://github.com/ruyisdk/ruyi/issues/473)
- ruyisdk-website 仓库审核 2 个 pr
    - [docs: fix code block rendering in VS Code case1 #495](https://github.com/ruyisdk/ruyisdk-website/pull/495)
    - 修复移动端边栏出现时顶栏和边栏动画透明度不一致的问题 [Navbar and sidebar transparency fix #512](https://github.com/ruyisdk/ruyisdk-website/pull/512)
- ruyisdk-website 仓库提交 26 个 pr
    - 调整开发板板块的移动端现实 [pages(index): better DevBoards components Mobile layout #497](https://github.com/ruyisdk/ruyisdk-website/pull/497)
    - 将新的开发板板块发布到首页 [pages(index): add DevBoards component to index #498](https://github.com/ruyisdk/ruyisdk-website/pull/498)
    - 更新 vf2 lite 图片 [pages(index): swap vf2 img with vf2lite #500](https://github.com/ruyisdk/ruyisdk-website/pull/500)
    - 优化开发板板块的链接跳转 [pages(index): better mobile title and link jump #501](https://github.com/ruyisdk/ruyisdk-website/pull/501)
    - 优化 ci 调用 github api 的逻辑，选取合适的等待时间并减少调用次数 [ci: wait longer on github api data update #502](https://github.com/ruyisdk/ruyisdk-website/pull/502)
    - 让官网在 api.ruyisdk.cn 失效时保持正常工作 [misc: fix loading failure when api.ruyisdk.cn failed #503](https://github.com/ruyisdk/ruyisdk-website/pull/503)
    - 固定顶栏，增加快速回到顶部按钮 [pages: add back to top button](https://github.com/ruyisdk/ruyisdk-website/commit/3af287b04ec0987b0fae8e0401557a1b5299d74b)
    - 完善新下载页面在 /downloads [pages(downloads): merge some download inform text #513](https://github.com/ruyisdk/ruyisdk-website/pull/513)
    - [pages(downloads): refactor into components #515](https://github.com/ruyisdk/ruyisdk-website/pull/515)
    - [pages(downloads): modify page layout #516](https://github.com/ruyisdk/ruyisdk-website/pull/516)
    - 整理项目结构，去掉多余的中文翻译 [i18n: remove i18n/zh-Hans #517](https://github.com/ruyisdk/ruyisdk-website/pull/517)
    - [pages(index): fix index font broken caused by #507 #518](https://github.com/ruyisdk/ruyisdk-website/pull/518)
    - 整理项目结构，修复部分页面视觉宽度的微小差异 [pages(about,news,News/{Blogs,Events}): modify page layout #519](https://github.com/ruyisdk/ruyisdk-website/pull/519)
    - 修复文档页面列表显示问题 [pages(docs): fix li, ol and ul #520](https://github.com/ruyisdk/ruyisdk-website/pull/520)
    - 新下载页面 IDE 下载链接切换到 api.ruyisdk.cn 的新 endpoint [api.ruyisdk.cn endpoint form eclipse and vscode plugin release info #521](https://github.com/ruyisdk/ruyisdk-website/pull/521)
    - [pages(downloads): better design and layout #523](https://github.com/ruyisdk/ruyisdk-website/pull/523)
    - 完善新下载感谢页面和引导用户阅读文档 [pages(thanks): better download thanks page #525](https://github.com/ruyisdk/ruyisdk-website/pull/525)
    - 去除文档页面代码块的黄色底色，统一所有代码块的视觉风格 [pages(docs): remove yellow background from CodeBlock #526](https://github.com/ruyisdk/ruyisdk-website/pull/526)
    - [pages(thands): fix command line copy #527](https://github.com/ruyisdk/ruyisdk-website/pull/527)
    - 修复新下载页面部分代码块的行复制按钮 [docs(CodeBlock): fix code copy on downloads page #528](https://github.com/ruyisdk/ruyisdk-website/pull/528)
    - 修复新下载页面部分 markdown 维护的内容的代码块语法兼容问题 [pages(downloads): fix markdown codeblock support #529](https://github.com/ruyisdk/ruyisdk-website/pull/529)
    - 修复文档页面架构切换时代码块出现横向滚动条的问题 [pages(docs): fix arch selecte scroll bar #530](https://github.com/ruyisdk/ruyisdk-website/pull/530)
    - 调整下载感谢页面渲染时序，在获取到 uri 参数后再渲染 card [pages(thanks): do not show card before we can get params #531](https://github.com/ruyisdk/ruyisdk-website/pull/531)
    - 新的 报告问题 页面 [pages: new page /issue #534](https://github.com/ruyisdk/ruyisdk-website/pull/534)
    - news 页面翻页增加 url 翻页 [pages(news): add page url param #535](https://github.com/ruyisdk/ruyisdk-website/pull/535)
    - issue 页面添加 meta 英文翻译 [pages(issue): add meta translation for English page #536](https://github.com/ruyisdk/ruyisdk-website/pull/536)
- ruyisdk-website 仓库提交 1 个 issue
    - [下载页面设计 #522](https://github.com/ruyisdk/ruyisdk-website/issues/522)
- packages-index 仓库提交 3 个 pr
    - Bianbu for k1 更新的最新 v2.3.3 [board-image/bianbu-{desktop,desktop-lite,minimal}-spacemit-k1{,-sd}: new version v2.3.3 #196](https://github.com/ruyisdk/packages-index/pull/196)
    - 增加 Spacemit Muse Pi Pro 支持和 Bianbu UEFI 镜像支持 [New device spacemit muse pi pro and uefi support for spacemit-k1-v1 strategy #198](https://github.com/ruyisdk/packages-index/pull/198)
    - Bianbu for K3 的支持 draft， 由实习生在 Spacemit K3 Pico-ITX 测试中 [New device Spacemit K3 Pico-ITX #199](https://github.com/ruyisdk/packages-index/pull/199)
- packages-index 仓库提交 2 个 issue
    - 关联 #198 [Spacemit K1 UEFI image support #197](https://github.com/ruyisdk/packages-index/issues/197)
    - 关联 #199 [New device Spacemit K3 Pico-ITX #199](https://github.com/ruyisdk/packages-index/issues/200)
- ruyi-backend 仓库提交 1 个 issue
    - [添加 IDE 最新版本查询 endpoint #98](https://github.com/ruyisdk/ruyi-backend/issues/98)

#### 6.2 阎明铸

##### 6.2.1 Sail

- 实现 SAIL AME 编解码 https://github.com/trdthg/sail-riscv/commit/3cc341b44fc2f7f0cd5acc72bfb7bbf7b930c4bc

##### 6.2.2 Ruyi AI

buddy-compiler/buddy-mlir
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/811 [build] Fixed various dependency installation issues for riscv
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/810 [test] Fix buddy-llc not found
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/809 [LLVM] Bump llvm
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/802 [mlir] Use OpTy::create instead of OpBuilder::create
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/799 [ci] Run check-buddy on multi pytorch version
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/797 [LLVM] Bump llvm
- 提交 PR https://github.com/buddy-compiler/buddy-mlir/pull/766 [LLVM] Remove LLVM source deps

RuyiAI-Stack/llvm-project
- 提交 PR https://github.com/RuyiAI-Stack/llvm-project/pull/13 Split Buddy extended backends to separate files

RuyiAI-Stack/triton-riscv
- 提交 PR https://github.com/RuyiAI-Stack/triton-riscv/pull/34 Bump triton and llvm to latest

##### 6.2.3 会议和展示

- 参加 tech-golden-model meeting [`06.01`, `06.15`, `06.22`, `06.29`](https://docs.google.com/document/d/1f9ihMT8vcmgijmvebMiHttwSbw9eY_MKkR9ea3CNFCg)
- 参加东亚双周会 0611，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1zlKeiVVGMVIzTayEVoIDLlk2A7yy8-KX9mymSohx-9I/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)
- 参加东亚双周会 0625，更新 sail/act 进展 [PPT](https://docs.google.com/presentation/d/1k2A1T-pR-M0w0qfafuMykMRiZtMWWp2bHvHh4gnxDvk/edit?slide=id.g327cde8f41c_0_68#slide=id.g327cde8f41c_0_68)

#### 6.3 张馥媛

##### 6.3.1 RuyiSDK 示例代码库建设

- 开发板示例文档扩充
	 - Canaan K510-CRB-V1.2 KIT：测试用例及说明文档
		- 概述:[README.md](http://github.com/ruyisdk/board-docs/blob/main/K510/README.md);[README_zh.md](https://github.com/ruyisdk/board-docs/blob/main/K510/README_zh.md)
		- [HelloWorld](https://github.com/ruyisdk/board-docs/blob/main/K510/HelloWorld/README.md)
		- [Coremark](https://github.com/ruyisdk/board-docs/blob/main/K510/Coremark/README.md)
		- [RuyiSDK GPIO 示例：GPIO KEYS Demo](https://github.com/ruyisdk/board-docs/blob/main/K510/GPIO_KEYS/README.md)
		- [RuyiSDK 系统示例：RTC Demo](https://github.com/ruyisdk/board-docs/blob/main/K510/RTC/README.md)
	- Milk-V Duo S
		- [SPI 测试](https://github.com/ZihanCheng63/board-docs/blob/main/Duo_S/SPI/README_zh.md)
		- [DF9GMS 测试](https://github.com/ZihanCheng63/board-docs/blob/main/Duo_S/DF9GMS/README_zh.md)
- 前端示例网站
	- 项目仓库：[board-docs-frontend](https://github.com/DuoQilai/board-docs-frontend)
	- 在线站点：[https://board-docs-frontend.pages.dev/](https://board-docs-frontend.pages.dev/)
	- **CI 自动化**：新增每日 `board-docs` 子模块自动同步工作流——有更新则验证 `pnpm build` 通过后推送 `main`，触发线上重新部署。
	- **修复同步流程**：修正 pnpm 安装（仅用 `packageManager` 字段）、submodule sync 在提交前不再 reset、CI pnpm 版本等问题。
	- **示例分类扩展**：扩充示例 `status` 分类 slug（基础 / 外设 / 通信 / 网络 / 系统 / 多媒体 / 视觉 / AI / 加密 / 压缩 / GUI / 性能测试），旧值自动映射。
	- **访问统计**：接入 Cloudflare Web Analytics beacon，并简化为 Cloudflare-only 部署的统计文档。
	- **文档整理**：文档统一收进 `docs/` 目录；README 补充线上地址与部署事实；部署 / 统计文档按场景拆分；补充验证步骤的 Mac 快捷键说明。
- Duo 256M 示例文档：
  - [yolov8-person-pets](https://github.com/ruyisdk/board-docs/blob/main/Duo_256m/%20yolov8-person-pets/README_zh.md)
  - [face-detection](https://github.com/ruyisdk/board-docs/blob/main/Duo_256m/face-detection/README_zh.md)
  - [pedestrian-detection](https://github.com/ruyisdk/board-docs/blob/main/Duo_256m/pedestrian-detection/README_zh.md)

##### 6.3.2 编译工具链测试

测试开发板的可用性

- 已经烧录镜像、安装ruyi、测试 ruyi gcc 工具链
	- [EBC7700](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/EBC7700.md)
	- [P550](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/EBC7702.md)
	- [EBC7702](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/P550.md)
- 调研开发板操作系统和基本测试用例
	- [A210 Debian](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/A210.md)
	- [K3 Ubuntu](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/K3_Pico-ITX.md)
	- [SG2044 Ubuntu](https://github.com/DuoQilai/PLCT-Works/blob/main/Notes/July_Ledger/SG2044.md)
- 测试或调研失败
	- V100 
		- 公开资料能证明 V100 平台 Linux 和服务器固件栈已在 FPGA 原型平台上运行和演示；但完整产品规格书、整机手册、系统镜像、BSP 仓库、默认账号密码仍需供应商提供。
	- [CH32V208WBU6-EVT-R0-1v4 测试报告](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/reports/ZhiyaoBian/Test%20repoorts/CH32V208.md)
	- [Sipeed Tang Mega 138K 测试报告](https://github.com/ZihanCheng63/my-repo/blob/main/10%E7%A7%8D%E5%BC%80%E5%8F%91%E6%9D%BF%2B%E7%BC%96%E8%AF%91%E5%99%A8%E6%B5%8B%E8%AF%95%E7%94%A8%E4%BE%8B-v2\(1\).docx)
- 调研报告
	- [8项开发板调研报告](https://github.com/zhiyao310/ruyisdk-dev-archive/blob/main/research/8%E9%A1%B9Linux%E5%BC%80%E5%8F%91%E6%9D%BF%E8%B0%83%E7%A0%94%E6%8A%A5%E5%91%8A.md)

##### 6.3.3 RISC-V Linux系统与开发板实践课程

- 项目仓库：[riscv-embedded-course](https://github.com/EnzoDing-rgb/riscv-embedded-course)
- 在线大纲：[https://enzoding-rgb.github.io/riscv-embedded-course/](https://enzoding-rgb.github.io/riscv-embedded-course/)
- 定位：实习生课程研发，独立产出的一版《RISC-V Linux 嵌入式实践》课程草稿——在 RISC-V Linux 开发板上用 RuyiSDK + C 做嵌入式应用，含术语表、章节表、物料 BOM 与递进式项目。
- 项目仓库：[ruyi-riscv-linux-book](https://github.com/DuoQilai/ruyi-riscv-linux-book)
