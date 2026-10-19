[README_CN.md](https://github.com/user-attachments/files/29216310/README_CN.md)
# Nopiskl

[English](./README.md) | [CSDN Blog](https://blog.csdn.net/Nopiskl)

欢迎来到我的 GitHub 项目索引。

该仓库主要作为我的学习笔记、嵌入式 Linux 项目、AIoT 原型项目、BSP 工程、Android 移植实验以及 AI 全栈应用 Demo 的统一入口。

> 由于部分项目仍在完善、修复 BUG、重构工程结构并进行交叉验证中，  
> 同时我也在继续学习和完善工程化 SDK 打包、更规范的 Git 管理流程以及项目文档，  
> 因此部分仓库会逐步发布、更新或重构，感谢理解。

---

## 主要方向

- 嵌入式 Linux、Bootloader、Linux 内核、驱动与操作系统
- RISC-V MCU / SoC 设计、FPGA 部署以及可运行 Linux 的软核 SoC 实验
- BSP 开发、rootfs 裁剪、ARM64 Linux 移植以及工业嵌入式平台
- 边缘 AI、AIoT、嵌入式音视频链路、硬件编解码加速、NPU 部署与 IPC 系统
- Android 系统移植、HAL 适配、驱动开发与上层应用联动
- AI 应用工程，包括桌面端检测、后端服务、数据库以及 Web 可视化
- Linux 网络、工业网关与轻量级嵌入式服务框架

---

## 学习笔记

### 1. 底层架构 / Bootloader / Linux 内核 / 驱动体系 / 操作系统学习资料汇总

[Learning_Notes](https://github.com/Nopiskl/Learning_Notes)

主要记录 Linux 内核、Bootloader、驱动子系统、Android HAL 框架等底层方向的学习与研究内容。

内容包括：

1. Linux 内核进程调度、内存分配、网络、驱动框架等底层实现，主要基于 Mainline Linux 进行分析。
2. Bootloader、U-Boot 启动流程、AI Fastboot 快起加速、rootfs 裁剪等内容，主要以 Allwinner、Rockchip 和 Mainline Linux 为例进行研究。
3. Linux 各类子系统实现，包括 V4L2、DRM、Pinctrl 等。
4. Android HAL 与系统框架，包括 SurfaceFlinger、Camera HAL、Codec2 等。

### 2. AI 学习资料汇总

[Learning_Notes](https://github.com/Nopiskl/Learning_Notes)

主要记录基础神经网络、CNN、目标检测以及 Transformer / LLM 相关学习内容。

内容包括：

1. 基础神经网络学习笔记。
2. CNN 学习笔记、个人 SSD Demo 实现以及 YOLO 源码简析。
3. Transformer 架构与 LLM 神经网络学习笔记。

---

## 项目目录

### 1. 底层系统 / CPU / SoC / FPGA / Linux 驱动开发

主要方向包括 RISC-V MCU、RISC-V64 SoC、FPGA 数据通道、Bootloader 与 Linux 启动流程。

#### [RISC-V_MCU](https://github.com/Nopiskl/RISC-V_MCU)

使用 Verilog 自研三级流水 RISC-V MCU，支持中断与外设，并完成 FreeRTOS 移植和 FPGA 部署。

#### [RISCV64_SOC](https://github.com/Nopiskl/RISCV64_SOC)

基于开源 RocketChip RISC-V64 内核的完整 SoC 设计，可运行 Linux。  
集成基础外设、SDMMC、DDR、显示、视频与以太网控制器、自研 MJPEG 编解码器和 ISP 图像处理器，并完善配套 Linux 驱动。

在 FPGA 上部署后，可正常运行 Debian 13 rootfs。

#### [TinyISP](https://github.com/Nopiskl/TinyISP)

自研基于 Verilog 的 MJPEG 编解码器，配套 Linux 驱动，并成功接入 RISCV64_SOC。

#### [TinyMjpeg](https://github.com/Nopiskl/TinyMjpeg)

自研基于 Verilog 的 ISP 图像处理器，配套 Linux 驱动，并成功接入 RISCV64_SOC。

#### [PCIe-yolov5-accelerator](https://github.com/Nopiskl/PCIe-yolov5-accelerator)

YOLOv5 CNN 硬件加速器，配套 Linux 驱动，提供 XDMA PCIe 版本与 ZYNQ IP 封装版本。

#### [Neko_zephyr](https://github.com/Nopiskl/zephyr)

基于 YuzukiHD Zephyr 分支 fork 的 Allwinner F101 移植适配与学习版本，面向 YuzukiNeko 开发板。  
覆盖板级适配、显示、音频、USB 与存储驱动，并配套提供 zephyr-components 功能组件与示例。

#### [Neko_APP](https://yuzukihd.github.io/YuzukiNeko/zh/)

基于 YuzukiHD / YuzukiNeko 生态 fork 的 Allwinner F101 / Zephyr 应用修改与学习项目。  
覆盖 NekoBox、LVGL 界面、媒体播放、游戏模拟器、MicroPython 与 ncnn 应用示例。

---

### 2. IIoT 设计 / BSP / Linux 驱动 / Rootfs 移植适配

主要涉及 PCB 设计、ARM64 Linux 移植、Ubuntu 系统适配、BSP 设计以及工业 / 嵌入式硬件平台开发。

#### [Linux_BSP](https://github.com/Nopiskl/Linux_BSP)

轻量化 Linux 开发 SDK，用于开发 Mainline U-Boot、Linux Kernel 与 Rootfs。

特性包括：

- 自动化 BSP 编译流程
- 自定义配置支持
- 轻量、易用的工程结构
- 多 SoC BSP 设计
- 关注可维护性、可移植性与多平台复用

#### [T527_MicroPC](https://github.com/Nopiskl/T527_MicroPC)

基于 T527 的 MicroPC / IIoT 硬件平台，采用 8 层高速 PCB 设计。

项目包含自定义主线 BSP，覆盖 Bootloader 编写、Linux 内核适配与 Rootfs 自动化构建，同时兼容 Android 13，并提供原理图、EDA 工程、Gerber 与 STEP 硬件文件。

可用于：

- OpenWrt 网关
- ROS 系统适配
- AI 控制上位机
- 工业嵌入式开发平台

该项目已与 [Linux_BSP](https://github.com/Nopiskl/Linux_BSP) 联动。

#### [AI_VisionModule_Hardware](https://github.com/Nopiskl/AI_VisionModule/tree/main/Hardware)

基于 V851S 的 AI 视觉模组硬件设计，提供 DVP / MIPI 两套方案，包含原理图、EDA 工程与 STEP 结构文件。

#### [A133_Android_MobilePhone_Hardware](https://github.com/Nopiskl/A133_Android_MobilePhone/tree/main/A133_Hardware)

A133 便携终端硬件设计资料，包含 v1.0 / v2.0 硬件工程、设计参考与实机测试图。

#### [YuzukiNeko_Hardware](https://github.com/Nopiskl/YuzukiNeko)

基于 YuzukiHD / YuzukiNeko 上游 fork 的全志 F101 Pico 风格开发板硬件修改与学习项目。  
包含硬件设计、扩展底板与 3D 外壳资料。

---

### 3. 嵌入式音视频 / 驱动 / 边缘 AI / AIoT 全栈项目

围绕嵌入式 Linux 音视频链路、驱动、硬件编解码、C++ 网络通信、AI 推理应用进行开发，多个项目实现了硬件编解码加速与 AI NPU 部署。

#### [AI_VisionModule](https://github.com/Nopiskl/AI_VisionModule)

基于 V851S 的微型 YOLO 图传视觉模组 / AI 边缘协处理器。

项目包括：

- OpenCV 通用版
- 全志 MPP 版本
- 原型 PCB 设计

可用于 UVC AI 模组、智能运动相机、视觉机器人控制处理与 AI 智能云台控制。

#### [EdgeVision-AMP](https://github.com/Nopiskl/EdgeVision-AMP)

面向全志 AMP 异构平台的工业级 CDR / IPC Demo，覆盖 V853 AI 摄像头与 V821 低功耗 AOV / 快起摄像头开发环境。

功能包括：

- V853 AI 摄像头 / 记录仪开发
- V821 低功耗 AOV / 快起 CDR 支持
- AMP 异构加速 Media 链路
- 超低功耗 WiFi 待机控制

#### [V821_AIGlassess](https://github.com/Nopiskl/V821_AIGlassess)

基于 V821 主控的光波导 AI 眼镜项目，使用 AMP 异构并行计算降低延迟。

功能包括：

- 本地部署小智 AI
- 触摸拍照
- 录音与防抖录像
- 原型 PCB 设计

#### [Smart_IPC](https://github.com/Nopiskl/Smart_IPC)

RV1106 YOLO IPC 项目。

功能包括：

- 手机小程序控制
- Web 端控制
- AI 识别
- RTSP 推流
- Rockchip VPU / NPU 硬件加速

#### [HiSilicon_IPC](https://github.com/Nopiskl/HiSilicon_IPC)

基于 HiSilicon 平台的 IPC 摄像头 MPP 应用层开发项目。

#### [AIOT](https://github.com/Nopiskl/AIOT)

面向 AIoT 开发的 AI agent 环境，适配平台包括：

- Allwinner T527 / A733
- Rockchip RK3568 / RK3576 / RK3588

---

### 4. Android 系统移植 / HAL / 驱动编写与适配

关注 Android 系统移植、Linux 驱动适配、HAL 层开发以及上层基础应用开发。

#### [A133-Android-Phone](https://github.com/Nopiskl/A133-Android-Phone)

A133 Android 10 MobilePhone 项目，包含完整的 4 层原理图与 PCB 设计。

项目包括：

- 硬件设计
- Android 10 系统移植
- HIDL / Legacy HAL 驱动适配
- 板级 Android 系统适配与验证

#### [A733_AndroidPad](https://github.com/Nopiskl/A733_AndroidPad)

基于已量产 Teclast 平板硬件逆向的 A733 Android 15 系统移植项目。

项目主要侧重软件迁移与适配，包括：

- Android 15 系统移植
- HIDL / AIDL 驱动适配
- Camera、Display 与 Codec AIDL 链路验证
- Teclast 硬件逆向与系统适配验证

---

### 5. AI 应用类项目

主要记录完整 AI 应用工程，包括桌面端检测、后端服务、数据库存储以及 Web 可视化。

#### [Qt_YOLOv5_DetectSystem](https://github.com/Nopiskl/Qt_YOLOv5_DetectSystem)

`qt-yolo` 是一个完整示例工程，包括：

- 桌面端实时检测
- 本地数据库
- 后端查询服务
- Web 仪表板

桌面端使用 Qt6 / C++ 调用摄像头并运行 YOLOv5 ONNX 模型。  
检测结果写入 SQLite。  
FastAPI 后端读取同一份数据目录，Vue / Vite 前端用于展示运行状态、统计数据和快照。

---

### 6. Linux 网络 / 工业网关

主要记录 Linux 网络服务、工业网关、数据采集、代理服务以及 Web 管理界面等相关项目。

#### [Embedded_TinyGateway](https://github.com/Nopiskl/Embedded_TinyGateway)

`TinyServer` 是一个完整的工业网关系统解决方案。

功能包括：

- 数据采集
- 文件服务
- 代理服务
- Web 管理界面

该系统采用基础 Linux 系统调用与轻量函数封装，从底层构建简单、低资源占用的小型嵌入式网关。

---

### 7. Misc Projects

记录一些独立项目、早期应用实践以及个人 Blog 中提到的相关资源。

#### [PVZ_CPP_Remake](https://github.com/Nopiskl/PVZ_CPP_Remake)

PVZ 的 C++ 自制版，用于学习 C++、设计模式以及底层游戏引擎。

#### [Allwinner_Drivers](https://github.com/Nopiskl/Allwinner_Drivers)

Allwinner SoC 驱动、补丁与多媒体库合集，包含 A133 CedarX 资源及 V851S OpenCV / VIN ISP 适配。

---

## 说明

该仓库会持续更新。  
项目内容、结构、文档与发布状态可能会随着各仓库的完善而调整。

