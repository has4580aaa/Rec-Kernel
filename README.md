---

# ![RecCore Logo](REC.png)

RecCore is a lightweight operating system kernel designed specifically for ARM64 architecture, written entirely in C. It focuses on efficient task scheduling, memory management, and device driver support. This kernel system supports only ARM64 architecture; 32-bit systems are not supported. System drives and network mounts are located under the `drives` directory. Future plans include a Flex version with a modern user interface (UI).

---

## **Warnings**
**⚠️ Warning: Non-Debug (Non-Open Source) Versions Are Strictly Prohibited from Being Unpacked!**  
Any unauthorized unpacking, including but not limited to extracting unreleased components and incorporating them into distribution versions, will face legal action. We reserve the right to pursue legal responsibility.  
**Special Warning**: If anyone is found replacing or tampering with `lab` files, we will take immediate legal action without tolerance!  
**Legal Notice**: Any unauthorized actions will result in legal notices, and violators will bear the consequences!

**⚠️ Note: UI and Command Features Are Not Yet Complete!**  
The current version of the RecCore kernel has not yet completed the development of the user interface (UI) and command-line tools (Command). Please do not use these incomplete features in production environments. We are actively developing them, so stay tuned for updates.

---

## **Table of Contents**
1. [Features](#features)
2. [Quick Start](#quick-start)
   - [Compiling the Kernel](#compiling-the-kernel)
   - [Running the Kernel](#running-the-kernel)
3. [Code Structure](#code-structure)
4. [Drive and Network Mounting](#drive-and-network-mounting)
5. [Download](#download)
6. [Community](#community)
7. [Future Plans](#future-plans)
8. [Contribution Guidelines](#contribution-guidelines)
9. [License](#license)

---

## **Features**
- **ARM64 Exclusive Support**: Optimized for ARM64 architecture only.
- **Efficient Task Scheduling**: Priority-based round-robin scheduling algorithm.
- **Memory Management**: Provides virtual memory management and physical memory allocation.
- **Drive Mounting Support**: System drives and network mounts are located under the `drives` directory.
- **Modular Design**: Kernel features are modular, supporting dynamic loading and unloading.
- **Pure C Implementation**: Written entirely in C, **with no dependency on Linux kernel code**.
- **Future Flex UI**: Plans to release a Flex version with a modern user interface.

---

## **Quick Start**

### **Compiling the Kernel**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/RecCore.git
   cd RecCore
   ```
2. Install dependencies:
   ```bash
   sudo apt install gcc-aarch64-linux-gnu qemu-system-arm
   ```
3. Compile the kernel:
   ```bash
   make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- all
   ```

### **Running the Kernel**
1. Run using QEMU:
   ```bash
   qemu-system-aarch64 -M virt -cpu cortex-a53 -kernel bin/RecCore-arm64.bin
   ```
2. Debug mode:
   ```bash
   qemu-system-aarch64 -M virt -cpu cortex-a53 -kernel bin/RecCore-arm64.bin -s -S
   ```
   In another terminal, start GDB:
   ```bash
   gdb-multiarch -ex "target remote localhost:1234" -ex "symbol-file bin/RecCore-arm64.bin"
   ```

---

## **Code Structure**
```
RecCore/
├── arch/               # Architecture-specific code
│   └── arm64/          # ARM64 implementation
├── drives/             # Drive and network mounts
│   ├── system/         # System drive
│   └── network/        # Network mount
├── drivers/            # Device drivers
│   ├── storage/        # Storage device drivers
│   └── network/        # Network device drivers
├── include/            # Header files
├── kernel/             # Core functionality
│   ├── scheduler/      # Task scheduling
│   └── memory/         # Memory management
├── lib/                # Utility libraries
└── Makefile            # Build script
```

---

## **Drive and Network Mounting**

### **System Drive (drives/system)**
- **Functionality**: System drive is mounted under `drives/system`.
- **Usage**:
  ```bash
  mount /dev/sdX /drives/system
  ```

### **Network Mount (drives/network)**
- **Functionality**: Network mount is located under `drives/network`.
- **Usage**:
  ```bash
  mount -t nfs 192.168.1.100:/remote/path /drives/network
  ```

---

## **Download**
You can download the latest version of the RecCore kernel from SourceForge:

[![Download RecCore](https://camo.githubusercontent.com/16389ff70a277784214098c9d1c2dce20f404183457e3bda6a4e69e9dbce8adb/68747470733a2f2f612e6673646e2e636f6d2f636f6e2f6170702f73662d646f776e6c6f61642d627574746f6e)](https://sourceforge.net/projects/reccore/)

---

## **Community**
Join our community to interact with other developers:

- **QQ Channel**: [Join QQ Channel](#)
- **Discord**: [Join Discord](#)
- **Gitter**: [![Join the chat at https://gitter.im/RecCore/community](https://camo.githubusercontent.com/ef3705254e766b5edea93f49291c6d9239f29b942cfdb84f3296d0e37898b067/68747470733a2f2f6261646765732e6769747465722e696d2f4a6f696e253230436861742e737667)](https://gitter.im/RecCore/community)

---

## **Future Plans**
- **Flex UI Version**: Plans to release a Flex version with a modern user interface.
- **More Device Drivers**: Expand support for additional hardware devices.
- **Performance Optimization**: Further optimize task scheduling and memory management algorithms.

---

## **Contribution Guidelines**
We welcome contributions of any kind! Here’s how to get involved:
1. **Fork the Repository**: Click the `Fork` button at the top right to create your copy.
2. **Create a Branch**:
   ```bash
   git checkout -b feature/your-feature
   ```
3. **Submit Code**: After development, submit a Pull Request.
4. **Code Standards**:
   - Follow consistent coding styles.
   - Ensure commit messages are clear and concise, describing the changes.

---

## **License**
The RecCore kernel is licensed under **GPL-3.0**. For details, see the [LICENSE](LICENSE) file.

---

## **Contact**
- **Email**: your.email@example.com
- **GitHub**: [yourusername](https://github.com/yourusername)

---

## **Acknowledgments**
Thanks to all contributors and users for their support! Special thanks to the following projects:
- [OSDev Wiki](https://wiki.osdev.org/): Provided valuable development resources.

---

**Happy Hacking!** 🚀

---

### **Notes**
- Replace `YOUR_BASE64_IMAGE_HERE` with your RecCore Logo's Base64 encoding.
- Replace `yourusername` with your GitHub username.
- If the project is hosted on another platform (e.g., GitLab), update the links.
- Adjust the code structure and descriptions based on actual functionality.
