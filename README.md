[README.md](https://github.com/user-attachments/files/29216356/README.md)
# Nopiskl

[中文版本](./README_CN.md) | [CSDN Blog](https://blog.csdn.net/Nopiskl)

Welcome to my GitHub project index.

This repository is used as the main entry point for my study notes, embedded Linux projects, AIoT prototypes, BSP work, Android porting experiments, and full-stack AI application demos.

> Many projects are still being refined, debugged, reorganized, and cross-validated.  
> I am also improving the engineering structure of SDK packaging, Git workflow management, and project documentation.  
> Some repositories may therefore be released, updated, or reorganized gradually.

---

## Focus Areas

- Embedded Linux, Bootloader, Linux kernel, drivers, and operating systems
- RISC-V MCU / SoC design, FPGA deployment, and Linux-capable soft SoC experiments
- BSP development, rootfs customization, ARM64 Linux porting, and industrial embedded platforms
- Edge AI, AIoT, embedded audio/video pipelines, hardware codec acceleration, NPU deployment, and IPC systems
- Android system porting, HAL adaptation, driver development, and application-level integration
- AI application engineering, including desktop detection systems, backend services, databases, and web dashboards
- Linux networking, industrial gateways, and lightweight embedded service frameworks

---

## Study Notes

### 1. Low-Level Architecture / Bootloader / Linux Kernel / Driver Framework / Operating System Notes

[Learning_Notes](https://github.com/Nopiskl/Learning_Notes)

This section records study and research notes related to the Linux kernel, Bootloader, driver subsystems, Android HAL frameworks, and other low-level system topics.

Topics include:

1. Linux kernel internals such as process scheduling, memory allocation, networking, and driver frameworks, mainly based on Mainline Linux.
2. Bootloader and U-Boot boot flow analysis, AI Fastboot acceleration, rootfs trimming, and related startup optimization topics, mainly based on Allwinner, Rockchip, and Mainline Linux platforms.
3. Linux subsystem implementation studies, including V4L2, DRM, Pinctrl, and related driver frameworks.
4. Android HAL and system framework studies, including SurfaceFlinger, Camera HAL, Codec2, and related platform adaptation topics.

### 2. AI Learning Notes

[Learning_Notes](https://github.com/Nopiskl/Learning_Notes)

This section records learning materials related to basic neural networks, CNNs, object detection, Transformer architectures, and LLMs.

Topics include:

1. Basic neural network study notes.
2. CNN-based study notes, a personal SSD demo implementation, and YOLO source-code analysis.
3. Transformer-based LLM neural network notes.

---

## Project Directory

### 1. Low-Level Systems / CPU / SoC / FPGA / Linux Driver Development

This category focuses on RISC-V MCUs, RISC-V64 SoCs, FPGA data paths, Bootloader design, and Linux boot flows.

#### [RISC-V_MCU](https://github.com/Nopiskl/RISC-V_MCU)

A self-developed three-stage pipeline RISC-V MCU in Verilog with interrupt and peripheral support.  
The project also includes FreeRTOS porting and FPGA deployment.

#### [RISCV64_SOC](https://github.com/Nopiskl/RISCV64_SOC)

A complete Linux-capable SoC based on the open-source RocketChip RISC-V64 core.  
The project integrates peripheral, SDMMC, DDR, display, video and Ethernet controllers, self-developed MJPEG and ISP IP, and the corresponding Linux drivers.

After FPGA deployment, the SoC can boot and run a Debian 13 rootfs.

#### [TinyISP](https://github.com/Nopiskl/TinyISP)

A self-developed Verilog MJPEG codec with a Linux driver, integrated into RISCV64_SOC.

#### [TinyMjpeg](https://github.com/Nopiskl/TinyMjpeg)

A self-developed Verilog ISP image processor with a Linux driver, integrated into RISCV64_SOC.

#### [PCIe-yolov5-accelerator](https://github.com/Nopiskl/PCIe-yolov5-accelerator)

A YOLOv5 CNN hardware accelerator with a Linux driver, available as an XDMA PCIe version and a packaged ZYNQ IP version.

#### [Neko_zephyr](https://github.com/Nopiskl/zephyr)

An Allwinner F101 Zephyr port forked from YuzukiHD for modification and learning, targeting the YuzukiNeko board.  
It covers board support, display, audio, USB and storage drivers, with functional components and examples in zephyr-components.

#### [Neko_APP](https://github.com/Nopiskl/zephyr-components)

An application modification and learning project based on forks from the YuzukiHD / YuzukiNeko ecosystem for Allwinner F101 and Zephyr.  
It covers NekoBox, LVGL interfaces, media playback, game emulators, MicroPython and ncnn examples.

---

### 2. IIoT Design / BSP / Linux Driver / Rootfs Porting

This category covers PCB design, ARM64 Linux porting, Ubuntu system adaptation, BSP design, and industrial embedded hardware platforms.

#### [Linux_BSP](https://github.com/Nopiskl/Linux_BSP)

A lightweight Linux development SDK for Mainline U-Boot, Linux kernel, and rootfs development.

Features include:

- Automated BSP build flow
- Custom configuration support
- Lightweight and easy-to-use structure
- Multi-SoC BSP design
- Focus on maintainability, portability, and reuse across platforms

#### [T527_MicroPC](https://github.com/Nopiskl/T527_MicroPC)

A T527-based MicroPC / IIoT hardware platform with an 8-layer high-speed PCB design.

The project includes a custom mainline BSP with Bootloader development, Linux kernel adaptation and automated rootfs builds.  
It also supports Android 13 and provides schematic, EDA, Gerber and STEP hardware files.

Potential use cases include:

- OpenWrt gateway
- ROS platform adaptation
- AI control host
- Industrial embedded development platform

This project is also integrated with [Linux_BSP](https://github.com/Nopiskl/Linux_BSP).

#### [AI_VisionModule_Hardware](https://github.com/Nopiskl/AI_VisionModule/tree/main/Hardware)

V851S AI vision module hardware with DVP and MIPI variants, including schematics, EDA projects and STEP files.

#### [A133_Android_MobilePhone_Hardware](https://github.com/Nopiskl/A133_Android_MobilePhone/tree/main/A133_Hardware)

A133 portable terminal hardware designs, including v1.0 / v2.0 projects, design references and board-test images.

#### [YuzukiNeko_Hardware](https://github.com/Nopiskl/YuzukiNeko)

An Allwinner F101 Pico-style board project forked from YuzukiHD / YuzukiNeko for modification and learning.  
It includes hardware designs, carrier-board resources and 3D enclosure files.

---

### 3. Embedded Audio/Video / Drivers / Edge AI / AIoT Full-Stack Projects

This category focuses on embedded Linux audio/video pipelines, drivers, hardware codecs, C++ network communication, AI inference applications, and NPU-accelerated full-stack AIoT projects.

#### [AI_VisionModule](https://github.com/Nopiskl/AI_VisionModule)

A V851S-based miniature YOLO vision module / edge AI coprocessor.

The project includes:

- OpenCV general version
- Allwinner MPP version
- Prototype PCB design

It can also serve as a UVC AI module, smart action camera, visual robot controller and AI gimbal controller.

#### [EdgeVision-AMP](https://github.com/Nopiskl/EdgeVision-AMP)

An industrial CDR / IPC demo for Allwinner AMP platforms, covering V853 AI cameras and V821 low-power AOV / fast-start camera environments.

Features include:

- V853 AI camera / recorder development
- V821 low-power AOV / fast-start CDR support
- AMP media-pipeline acceleration
- Low-power WiFi standby control

#### [V821_AIGlassess](https://github.com/Nopiskl/V821_AIGlassess)

A V821-based optical waveguide AI glasses project using AMP heterogeneous processing to reduce latency.

Features include:

- Local XiaoZhi AI deployment
- Touch-triggered photo capture
- Audio recording
- Stabilized video recording
- Prototype PCB design

#### [Smart_IPC](https://github.com/Nopiskl/Smart_IPC)

An RV1106-based YOLO IPC project.

Features include:

- Mobile mini-program control
- Web control
- AI recognition
- RTSP streaming
- Rockchip VPU and NPU hardware acceleration

#### [HiSilicon_IPC](https://github.com/Nopiskl/HiSilicon_IPC)

A HiSilicon platform IPC camera MPP application project, implemented entirely at the application layer.

#### [AIOT](https://github.com/Nopiskl/AIOT)

An AI agent environment designed for AIoT development on Allwinner and Rockchip platforms, including:

- Allwinner T527 / A733
- Rockchip RK3568 / RK3576 / RK3588

---

### 4. Android System Porting / HAL / Driver Development and Adaptation

This category focuses on Android system porting, Linux driver adaptation, HAL development, and basic upper-layer application development.

#### [A133-Android-Phone](https://github.com/Nopiskl/A133-Android-Phone)

An A133 Android 10 mobile phone project with a complete four-layer schematic and PCB design.

The project includes:

- Hardware design
- Android 10 system porting
- HIDL / Legacy HAL driver adaptation
- Board-level Android system validation

#### [A733_AndroidPad](https://github.com/Nopiskl/A733_AndroidPad)

An A733 Android 15 Pad port based on reverse engineering of mass-produced Teclast hardware.

The project focuses on software migration and adaptation, including:

- Android 15 system porting
- HIDL / AIDL driver adaptation
- Camera, Display and Codec AIDL pipeline validation
- Teclast hardware reverse engineering and system validation

---

### 5. AI Application Projects

This category records complete AI application engineering projects, including desktop detection, backend services, database storage, and web visualization.

#### [Qt_YOLOv5_DetectSystem](https://github.com/Nopiskl/Qt_YOLOv5_DetectSystem)

`qt-yolo` is a complete example project that combines:

- Desktop real-time detection
- Local database storage
- Backend query service
- Web dashboard

The desktop application uses Qt6 / C++ to access the camera and run a YOLOv5 ONNX model.  
Detection results are written into SQLite.  
The FastAPI backend reads the same data directory, while the Vue / Vite frontend displays runtime status, statistics, and snapshots.

---

### 6. Linux Networking / Industrial Gateway

This category focuses on Linux network services, industrial gateways, data collection, proxy services, and web management interfaces.

#### [Embedded_TinyGateway](https://github.com/Nopiskl/Embedded_TinyGateway)

`TinyServer` is a complete industrial gateway system solution.

It provides:

- Data collection
- File service
- Proxy service
- Web management interface

The system is built using basic Linux system calls and lightweight function wrappers, aiming to create a simple, low-resource embedded gateway from the ground up.

---

### 7. Misc Projects

This category records independent projects, early application experiments, and resources mentioned in my personal blog.

#### [PVZ_CPP_Remake](https://github.com/Nopiskl/PVZ_CPP_Remake)

A C++ remake of Plants vs. Zombies, used for learning C++, design patterns, and low-level game engine concepts.

#### [Allwinner_Drivers](https://github.com/Nopiskl/Allwinner_Drivers)

A collection of Allwinner SoC drivers, patches and multimedia libraries, including A133 CedarX resources and V851S OpenCV / VIN ISP adaptation.

---

## Notes

This repository is continuously updated.  
Project content, structure, documentation, and release status may change as the related repositories are improved.

