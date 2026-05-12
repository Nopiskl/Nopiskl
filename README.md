由于本人的项目正在完善+改正BUG，为了使开源项目能更规范、更可观，我也正在学习工程化SDK打包、更进阶的git管理等，
因此我需要一段时间沉淀修改并且交叉验证后后才能逐步把这些项目放出来，望谅解

CSDN blog：https://blog.csdn.net/Nopiskl

Github仓库介绍：
## 学习笔记

[Learning_Notes](https://github.com/Nopiskl/Learning_Notes)


### 1. 底层架构 / Bootloader / Linux 内核 / 驱动体系 / 操作系统学习资料汇总

主要记录 Linux 内核、Bootloader、驱动子系统、Android HAL 框架等底层方向的学习与研究内容。

内容包括：

1. 系统研究 Linux 内核进程调度、内存分配、网络、驱动框架等具体底层实现，主要依赖 Mainline Kernel 进行分析。

2. 研究底层 Bootloader、U-Boot 启动流程、AI Fastboot 快起加速、rootfs 裁剪等内容，主要以 Allwinner、Rockchip和Mainline Kernel为例进行分析。

3. 研究 Linux 各类子系统具体实现，包括 V4L2、DRM、Pinctrl 等，主要以 Allwinner、Rockchip 平台为例进行分析。

4. 研究 Android HAL 驱动框架，包括 SurfaceFlinger、Camera HAL、Codec2 等框架实现，主要以 Allwinner、Rockchip 平台为例进行分析。

### 2. AI 学习资料汇总

主要记录基础神经网络、CNN、目标检测以及 Transformer / LLM 相关学习内容。

内容包括：

1. 基础神经网络学习笔记汇总。

2. 基于卷积神经网络的学习笔记，以及个人实现的 SSD Demo 与 YOLO 源码简析。

3. 基于 Transformer 架构的 LLM 神经网络学习笔记。

---

## 项目目录

### 1. 底层系统 / CPU / SoC / FPGA / Linux驱动开发

主要方向包括 RISC-V MCU、RISC-V64 SoC、FPGA 数据通道、Bootloader 与 Linux 启动流程。

- [RISC-V_MCU](https://github.com/Nopiskl/RISC-V_MCU)  
  自研三级流水 RISC-V MCU，支持中断与外设，并完成 RTOS 移植，实现 FPGA 部署。

- [RISCV64_SOC](https://github.com/Nopiskl/RISCV64_SOC)  
  参考开源项目移植适配的可运行 Linux 的 RISC-V64 SoC，完成主线 Linux 移植，并支持基础外设 pinctrl、I2C、SPI、SDCard、网口等驱动。  
  在 XC7A100T FPGA 部署后，可正常运行 Debian 11 rootfs。

---

### 2. IIoT 设计 / BSP / Linux 驱动 ROOTFS 移植适配

主要涉及 PCB 设计、ARM64 Linux 移植、Ubuntu 系统适配、BSP 设计以及工业 / 嵌入式硬件平台开发。

- [Linux_BSP](https://github.com/Nopiskl/Linux_BSP)  
  轻量化的Linux开发SDK，用于开发Mainline U-Boot / Kernel / Rootfs。  
  支持全自动编译 BSP、自定义配置，简单易上手。  
  自研轻量级、多SoC支持的BSP设计，面向主线Linux，关注可维护性、可移植性与多平台复用。

- [T527_MicroPC](https://github.com/Nopiskl/T527_MicroPC)  
  基于T527的MicroPC IIOT ，8 层高速 PCB 设计。  
  已完成官方 SDK 适配以及自定义 BSP 适配，支持 Mainline Linux / Ubuntu CLI / Armbian / Openwrt系统适配。
  可用于Openwrt作为网关、适配ROS系统、作为AI控制上位等  
  已完成与 [Linux_BSP](https://github.com/Nopiskl/Linux_BSP) 项目联动。

---

### 3. 嵌入式音视频 / 驱动 / AI 摄像头 / 边缘 AI / AIoT 全栈类型项目

围绕嵌入式 Linux 音视频链路及驱动 、硬件编解码、C++ 网络通信、AI 推理应用进行开发，多个项目实现硬件编解码加速+AI npu部署的全栈项目。

- [AI_SportCamera](https://github.com/Nopiskl/AI_SportCamera)  
  V851S YOLO 相机 / 行车记录仪项目，包含 OpenCV 通用版与全志 MPP 双版本实现+原型PCB设计。  
  适用于 Sport AI Camera 扩展开发与研究。

- [AI_SecurityRecorder](https://github.com/Nopiskl/AI_SecurityRecorder)  
  V853 AI 物联网安防记录仪，可作为 AI 监控摄像头使用，支持RTSP 推流、标记录像、只能抓拍、人形智能警报等功能。

  - [V821_AIGlassess](https://github.com/Nopiskl/V821_AIGlassess)  
  基于 V821 为主控的光波导 AI 眼镜项目，支持本地部署小智 AI、触摸拍照、录音录像等功能+原型PCB设计。

- [Smart_IPC](https://github.com/Nopiskl/Smart_IPC)  
  RV1106 YOLO IPC，支持手机小程序与 Web 端控制的IPC，可进行AI识别RTSP推流，采用RK硬件VPU NPU加速。
  
- [HiSilicon_IPC](https://github.com/Nopiskl/HiSilicon_IPC)  
  基于 HiSilicon 平台的 IPC 摄像头 MPP APP 开发，纯应用层。

- [AIOT](https://github.com/Nopiskl/AIOT)  
  基于Allwinner平台T527/A733以及Rockchip平台RK3568/RK3576/RK3588等设计的的AI agent环境，便于后续 AIoT 相关开发。

---

### 4. Android 系统移植 / HAL / 驱动适配

关注 Android 系统移植、Linux 驱动适配、HAL 层开发以及上层基础应用开发。

- [A133-Android-Phone](https://github.com/Nopiskl/A133-Android-Phone)  
  A133 Android10 MobilePhone，包含硬件设计、Android 10 系统移植、HIDL / Legacy HAL 驱动适配与上层简易APP开发(用于演示APP驱动交互)。

- [A733_AndroidPad](https://github.com/Nopiskl/A733_AndroidPad)  
  A733 Android15 Pad，原型Teclast P50AI。包含 Android15 系统移植、HIDL / AIDL 驱动适配与 NPU 相关 Android 视觉 APP 开发
  注：该仓库主要侧重于软件方面的移植适配，对于硬件则采用成品主板+Teclast P50AI为硬件基础，
  在其基础上进行官方SDK迁移+APP研发以覆盖完整的AllwinnerPAD系列开发。

---

### 5. 具体 AI 应用类项目

主要记录基于 AI 模型的完整应用工程，包括桌面端检测、后端服务、数据库存储以及 Web 可视化等内容。

- [Qt_YOLOv5_DetectSystem](https://github.com/Nopiskl/Qt_YOLOv5_DetectSystem)  
  qt-yolo 是一个“桌面端实时检测 + 本地数据库 + 后端查询 + Web 仪表板”的完整示例工程。  
  桌面端使用 Qt6 / C++ 调用摄像头并运行 YOLOv5 ONNX 模型，检测结果写入 SQLite。  
  FastAPI 后端读取同一份数据目录，Vue / Vite 前端用于展示运行状态、统计数据和快照。

---

### 6. Linux 网络 / 工业网关

主要记录 Linux 网络服务、工业网关、数据采集、代理服务以及 Web 管理界面等相关项目。

- [Embedded_TinyGateway](https://github.com/Nopiskl/Embedded_TinyGateway)  
  TinyServer 是一个完整的工业网关系统解决方案，提供数据采集、文件服务、代理服务和 Web 管理界面等功能。
  采用最基础的Linux系统调用+函数封装，从最底层打造最简单、资源占用最少的小型嵌入式网关。
  
---

### 7. Misc Projects

记录一些独立项目、早期应用实践以及个人 Blog 中提到的相关资源。

- [PVZ_CPP_Remake](https://github.com/Nopiskl/PVZ_CPP_Remake)  
  PVZ 的 C++ 自制版，用于学习 C++、设计模式以及底层游戏引擎。

- [Allwinner_Drivers](https://github.com/Nopiskl/Allwinner_Drivers)  
  一些个人 Blog 中提到的 Allwinner 相关资源。
