# STM32 嵌入式开发项目集合

## 项目概述

本仓库包含多个基于STM32F103系列微控制器的嵌入式开发项目，涵盖了从基础GPIO控制到RTOS应用的各种实例。

## 项目结构

```
Clion_Stm32/
├── 01_RTOS/          # FreeRTOS实时操作系统项目
├── Blik/             # 闪烁控制项目
├── LED/              # LED控制基础项目
├── .gitignore        # Git忽略文件配置
└── README.md         # 项目说明文档
```

## 项目详情

### 1. LED项目
- **功能**: 基础LED控制
- **芯片**: STM32F103
- **开发环境**: CLion + CMake
- **特性**: GPIO基础操作、LED闪烁控制

### 2. Blik项目
- **功能**: 高级闪烁控制
- **芯片**: STM32F103
- **开发环境**: CLion + CMake
- **特性**: 可配置闪烁模式、定时器应用

### 3. 01_RTOS项目
- **功能**: FreeRTOS实时操作系统应用
- **芯片**: STM32F103
- **开发环境**: Keil MDK-ARM
- **特性**: 多任务调度、信号量、队列通信

## 开发环境要求

### 硬件要求
- STM32F103系列开发板
- ST-Link调试器
- USB数据线

### 软件要求
- **CLion**: 用于CMake项目开发
- **Keil MDK-ARM**: 用于传统ARM项目开发
- **STM32CubeMX**: 用于硬件配置和代码生成
- **ARM GCC工具链**: 用于编译
- **OpenOCD**: 用于调试和烧录

## 快速开始

### 1. 克隆仓库
```bash
git clone <仓库地址>
cd Clion_Stm32
```

### 2. 选择项目
根据需要进入相应的项目目录：
```bash
cd LED          # 进入LED项目
# 或
cd Blik         # 进入Blik项目
# 或
cd 01_RTOS      # 进入RTOS项目
```

### 3. 编译项目

#### 对于CMake项目（LED、Blik）：
```bash
mkdir build
cd build
cmake ..
make
```

#### 对于Keil项目（01_RTOS）：
1. 打开Keil MDK-ARM
2. 打开项目文件 `01_RTOS.uvprojx`
3. 编译项目（F7）

### 4. 烧录和调试
- 连接ST-Link调试器
- 使用相应IDE的调试功能进行烧录和调试

## 代码规范

本项目遵循以下代码规范：
- 使用中文注释
- 函数命名采用模块名_功能名格式
- 变量命名采用驼峰命名法
- 所有公共函数必须有详细的Doxygen注释

## 文件说明

### 通用文件
- `*.ioc`: STM32CubeMX配置文件
- `CMakeLists.txt`: CMake构建配置
- `*.ld`: 链接脚本文件
- `startup_*.s`: 启动汇编文件

### 目录结构
- `Core/Inc/`: 头文件目录
- `Core/Src/`: 源文件目录
- `Drivers/`: STM32 HAL库驱动
- `Middlewares/`: 中间件（如FreeRTOS）

## 贡献指南

1. Fork本仓库
2. 创建特性分支 (`git checkout -b feature/新功能`)
3. 提交更改 (`git commit -am '添加新功能'`)
4. 推送到分支 (`git push origin feature/新功能`)
5. 创建Pull Request

## 许可证

本项目采用MIT许可证 - 详见 [LICENSE](LICENSE) 文件

## 联系方式

如有问题或建议，请通过以下方式联系：
- 创建Issue
- 发送邮件至：[您的邮箱]

## 更新日志

### v1.0.0 (2025-01-15)
- 初始版本发布
- 包含LED、Blik、RTOS三个基础项目
- 完善项目文档和构建配置

---

**注意**: 请确保在使用前已正确配置开发环境，并根据具体硬件调整GPIO配置。