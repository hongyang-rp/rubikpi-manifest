# RubikPi Manifest Repository

[English](#english) | [中文](#中文)

## 中文

### 项目简介

这是 RubikPi AI 开发板的清单仓库，包含了用于构建 RubikPi 固件的 Yocto 项目清单文件。RubikPi 是基于高通芯片平台的人工智能开发板，支持机器人操作系统（ROS）和 Qt5 图形界面。

### 特性

- 基于 Yocto Project Kirkstone 版本
- 支持高通平台的硬件加速
- 集成 ROS (Robot Operating System) 支持
- 包含 Qt5 图形界面框架
- 支持安全功能和虚拟化
- 包含摄像头和显示驱动

### 系统要求

- Ubuntu 18.04 LTS 或更高版本
- 至少 100GB 可用磁盘空间
- 至少 8GB RAM（推荐 16GB 或更多）
- 安装了 repo 工具

### 快速开始

1. **安装依赖**
   ```bash
   sudo apt-get update
   sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib \
        build-essential chrpath socat cpio python3 python3-pip python3-pexpect \
        xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa \
        libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev
   ```

2. **安装 repo 工具**
   ```bash
   mkdir ~/bin
   PATH=~/bin:$PATH
   curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
   chmod a+x ~/bin/repo
   ```

3. **初始化 repo**
   ```bash
   mkdir rubikpi-build
   cd rubikpi-build
   repo init -u https://github.com/hongyang-rp/rubikpi-manifest.git
   ```

4. **同步代码**
   ```bash
   repo sync
   ```

5. **设置构建环境**
   ```bash
   source setup-environment_RUBIKPi
   ```

6. **开始构建**
   ```bash
   ./rubikpi_build.sh
   ```

### 清单文件说明

本仓库包含两个主要的清单文件：

- `rubikpi-6.6.52-QLI.1.3-Ver.1.1.1_qim-product-sdk-1.1.2.xml` - 版本 1.1.1
- `rubikpi-6.6.52-QLI.1.3-Ver.1.1_qim-product-sdk-1.1.2.xml` - 版本 1.1

### 项目结构

构建完成后，源码将按以下结构组织：

```
rubikpi-build/
├── layers/                    # Yocto 层
│   ├── meta-openembedded/    # OpenEmbedded 核心层
│   ├── meta-qcom/            # 高通硬件支持层
│   ├── meta-rubikpi/         # RubikPi 特定层
│   ├── meta-ros/             # ROS 支持层
│   └── poky/                 # Yocto 核心
├── src/                      # 源码
│   └── vendor/
│       ├── qcom/             # 高通相关源码
│       └── thundercomm/      # 预编译二进制文件
└── rubikpi/                  # RubikPi 构建脚本
```

---

## English

### Project Overview

This is the manifest repository for RubikPi AI development board, containing Yocto Project manifest files for building RubikPi firmware. RubikPi is an artificial intelligence development board based on Qualcomm chipset platforms, supporting Robot Operating System (ROS) and Qt5 graphical interface.

### Features

- Based on Yocto Project Kirkstone release
- Qualcomm platform hardware acceleration support
- Integrated ROS (Robot Operating System) support
- Qt5 graphical interface framework
- Security features and virtualization support
- Camera and display drivers included

### System Requirements

- Ubuntu 18.04 LTS or later
- At least 100GB available disk space
- At least 8GB RAM (16GB or more recommended)
- repo tool installed

### Quick Start

1. **Install Dependencies**
   ```bash
   sudo apt-get update
   sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib \
        build-essential chrpath socat cpio python3 python3-pip python3-pexpect \
        xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa \
        libsdl1.2-dev pylint3 xterm python3-subunit mesa-common-dev
   ```

2. **Install repo tool**
   ```bash
   mkdir ~/bin
   PATH=~/bin:$PATH
   curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
   chmod a+x ~/bin/repo
   ```

3. **Initialize repo**
   ```bash
   mkdir rubikpi-build
   cd rubikpi-build
   repo init -u https://github.com/hongyang-rp/rubikpi-manifest.git
   ```

4. **Sync source code**
   ```bash
   repo sync
   ```

5. **Setup build environment**
   ```bash
   source setup-environment_RUBIKPi
   ```

6. **Start building**
   ```bash
   ./rubikpi_build.sh
   ```

### Manifest Files

This repository contains two main manifest files:

- `rubikpi-6.6.52-QLI.1.3-Ver.1.1.1_qim-product-sdk-1.1.2.xml` - Version 1.1.1
- `rubikpi-6.6.52-QLI.1.3-Ver.1.1_qim-product-sdk-1.1.2.xml` - Version 1.1

### Project Structure

After building, the source code will be organized in the following structure:

```
rubikpi-build/
├── layers/                    # Yocto layers
│   ├── meta-openembedded/    # OpenEmbedded core layers
│   ├── meta-qcom/            # Qualcomm hardware support layer
│   ├── meta-rubikpi/         # RubikPi specific layer
│   ├── meta-ros/             # ROS support layer
│   └── poky/                 # Yocto core
├── src/                      # Source code
│   └── vendor/
│       ├── qcom/             # Qualcomm related source
│       └── thundercomm/      # Prebuilt binaries
└── rubikpi/                  # RubikPi build scripts
```

### Included Components

- **Linux Kernel 6.6** - Custom kernel for Qualcomm platforms
- **Yocto Kirkstone** - Stable Yocto release
- **ROS Support** - Robot Operating System integration
- **Qt5 Framework** - Graphical user interface support
- **Security Features** - SELinux and security hardening
- **Virtualization** - Container and VM support
- **Camera/Display Drivers** - Hardware acceleration support

### Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### License

This project is licensed under the GNU General Public License v2.0 - see the [LICENSE](LICENSE) file for details.

### Support

For technical support and questions, please:
- Open an issue in this repository
- Visit the RubikPi AI community forums
- Check the documentation wiki

### Related Projects

- [rubikpi-ai](https://github.com/rubikpi-ai) - RubikPi AI organization
- [meta-rubikpi](https://github.com/rubikpi-ai/meta-rubikpi) - RubikPi Yocto layer
- [rubikpi-script](https://github.com/rubikpi-ai/rubikpi-script) - Build scripts and tools