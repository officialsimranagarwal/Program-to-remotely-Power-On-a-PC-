# Remote PC Power On (Wake-on-LAN) 🔌

A lightweight **C program** that enables you to remotely power on a computer over a Local Area Network (LAN) using the **Wake-on-LAN (WOL)** protocol. It constructs and broadcasts a "Magic Packet" to wake the target machine.

![C](https://img.shields.io/badge/Language-C-A8B9CC?style=for-the-badge&logo=c&logoColor=white)

## ✨ Features

- **Wake-on-LAN**: Uses industry-standard Magic Packets.
- **Socket Programming**: Demonstrates raw UDP socket usage in C.
- **Network Broadcast**: Broadcasts packets to the local subnet.

## 🚀 Getting Started

### Prerequisites

- A C Compiler (GCC).
- Target PC must have Wake-on-LAN enabled in BIOS/UEFI.

### Installation & Usage

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/officialsimranagarwal/Program-to-remotely-Power-On-a-PC-.git
    cd Program-to-remotely-Power-On-a-PC-
    ```

2.  **Configure**:
    - Open `ptr.c` and update the MAC Address and Broadcast IP to match your network.

3.  **Compile the code**:
    ```bash
    gcc ptr.c -o wol
    ```

4.  **Run the application**:
    ```bash
    ./wol
    ```

## 🛠️ Tech Stack

- **Language**: C
- **Networking**: BSD Sockets (UDP)

## 🤝 Contributing

Contributions are welcome! Please check the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
