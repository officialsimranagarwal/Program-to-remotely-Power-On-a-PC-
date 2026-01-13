# Remote PC Power-On (Wake-on-LAN) ⚡

![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
![Network](https://img.shields.io/badge/Network-Socket_Programming-blue?style=for-the-badge)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

## 📖 Overview

This is a C program that implements the **Wake-on-LAN (WoL)** protocol to remotely power on a computer over a network. It constructs and broadcasts a "Magic Packet" containing the target machine's MAC address.

## ⚙️ How It Works

The program creates a UDP socket and broadcasts a packet structued as:
1.  **Synchronization Stream**: 6 bytes of `0xFF`.
2.  **Target Details**: The target device's MAC address repeated 16 times.

## 🛠️ Configuration

Before compiling, you **must** update the source code with your target machine's MAC address:

Open `ptr.c` and modify lines 40-45:
```c
mac[0] = 0xab; // 1st octet
mac[1] = 0xcd; // ...
// ...
```

## 🚀 Usage

1.  **Compile** the program:
    ```bash
    gcc ptr.c -o wake_pc
    ```
2.  **Run** the executable:
    ```bash
    ./wake_pc
    ```

## 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## 👤 Author

**Simran Agarwal**
-   [Profile](https://github.com/officialsimranagarwal)
-   [LinkedIn](https://linkedin.com/in/simran-agarwal-54751b191)

---
*Generated with ❤️ by Simran Agarwal*
