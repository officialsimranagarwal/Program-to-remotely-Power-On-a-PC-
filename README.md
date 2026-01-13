# Remote PC Power-On (Wake-on-LAN) ⚡

![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
![Network](https://img.shields.io/badge/Network-UDP_Socket-blue?style=for-the-badge)
![Protocol](https://img.shields.io/badge/Protocol-WoL-success?style=for-the-badge)

## 📖 Overview

A raw C implementation of the **Wake-on-LAN (WoL)** protocol. This tool allows a user to turn on a remote computer within the same Local Area Network (LAN) by broadcasting a specially compliant UDP packet known as the "Magic Packet".

## 💻 Technical Implementation

### Socket Programming
The program operates at the Transport Layer using **UDP (User Datagram Protocol)** because WoL is a connectionless broadcast protocol.
-   **Socket Creation**: `socket(AF_INET, SOCK_DGRAM, 0)` creates a datagram socket.
-   **Broadcast Option**: `setsockopt(..., SO_BROADCAST, ...)` is crucial; it explicitly permits the socket to send packets to the broadcast address (`255.255.255.255` or subnet-specific).

### The "Magic Packet" Structure
The standard Magic Packet frame is 102 bytes long:
1.  **Synchronization Stream** (6 Bytes): `0xFF 0xFF 0xFF 0xFF 0xFF 0xFF`.
2.  **Target MAC Sequence** (96 Bytes): The target NIC's 48-bit (6-byte) MAC address repeated 16 times.

### Logic Flow
1.  **Buffer Initialization**: An unsigned char array `toSend[102]` is allocated.
2.  **Payload Construction**: Loops populate the sync stream and the 16 MAC repetitions using `memcpy` or direct assignment.
3.  **Transmission**: `sendto()` blasts the buffer to port `9` (standard WoL port) at the broadcast IP.

## 🛠️ Usage & Compilation

**Prerequisite**: Edit `ptr.c` to set the `mac` array to your target machine's hardware address.

```bash
# Compile
gcc ptr.c -o wake_pc

# Execute
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
