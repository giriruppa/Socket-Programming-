
---

## 🧾 README.md — Networking & Socket Programming Projects

### 📘 Overview

This repository contains a collection of Python programs demonstrating **network programming, port scanning, HTTP method enumeration, and socket-based client-server communication**.
Some of these examples also show how attackers may misuse sockets for reverse shells — useful for **cybersecurity learning and ethical analysis** only.

> ⚠️ **Disclaimer:**
> These programs are for **educational and ethical cybersecurity learning only**.
> Do **not** deploy or use these scripts on systems you do not own or have explicit authorization to test.

---

## 📂 Folder Structure

```
Networking-Projects/
│
├── README.md
│
├── 1_reverseshell_server.py      # Server-side (attacker) shell handler
├── 2_socket_server.py            # Basic socket communication example
├── 3_http_options_scanner.py     # Detects allowed HTTP methods (OPTIONS)
├── 4_portscanner_basic.py        # Simple port scanner
├── 5_portscanner_duplicate.py    # Duplicate (for practice)
└── 6_reverseshell_client.py      # Client-side (victim) reverse shell
```

---

## 📜 Program Descriptions

### 🧩 1) Reverse Shell Server — `1_reverseshell_server.py`

A Python-based server that waits for incoming connections from a reverse shell client.
Once connected, it allows command execution, file upload/download, and remote shell interaction.

#### ⚙️ Features

* Accepts a connection from a remote target
* Sends shell commands and receives output
* Uploads/downloads files to/from the target
* Gracefully handles JSON-based reliable communication

#### 🧠 Ethical Use

Used in **red team simulations**, **ethical hacking labs**, or **malware analysis** to understand reverse shell communication flow.

---

### 🔌 2) Socket Server Example — `2_socket_server.py`

A simple TCP server that listens on a given port and sends a thank-you message when a client connects.

#### 🧠 Learning Outcome

* Understand basic TCP socket creation, binding, and listening.
* Practice exception handling with `try-except` for socket operations.

---

### 🌐 3) HTTP OPTIONS Scanner — `3_http_options_scanner.py`

Scans a web server to check which HTTP methods are enabled (GET, POST, PUT, DELETE, etc.) using the `OPTIONS` request.

#### 🧠 Use Case

* Helps identify **misconfigurations** or **unnecessary HTTP methods** that may allow unintended access or modification.

---

### 🚪 4) Port Scanner — `4_portscanner_basic.py`

A classic TCP port scanner that checks if ports in a given range are open or closed.

#### ⚙️ Example:

```
Enter the IP address of the host: 192.168.1.10
Enter the port range to scan (e.g., 22-80): 20-100
```

#### 🧠 Learning Outcome

* Understand how TCP handshake works.
* Learn how `socket.connect_ex()` reports open/closed ports.

---

### 🔁 5) Duplicate Port Scanner — `5_portscanner_duplicate.py`

Same as Program 4 — kept for comparison, editing practice, or future feature extension (e.g., threading or banner grabbing).

---

### 🪝 6) Reverse Shell Client — `6_reverseshell_client.py`

A **reverse shell client** that tries to connect back to a listening server (Program 1). Once connected, it executes received commands.

#### ⚙️ Features

* Persistent connection retry mechanism
* File upload/download
* Remote command execution
* JSON-based reliable communication

#### ⚠️ Warning

Run this **only in an isolated lab environment (e.g., VirtualBox or local test network)**.
This mimics real-world malware behavior for research and blue-team defense learning.

---

## 🧰 Requirements

### 📦 Install Dependencies

No external libraries are required beyond Python’s built-in modules:

```bash
python3 -m pip install --upgrade pip
```

### 🧑‍💻 Tested On

* Python 3.8+
* Windows 10 / Kali Linux / Ubuntu
* Isolated VM environments

---

## 🚀 How to Run

### 🧩 Reverse Shell Demo

1. Run the **server** first:

   ```bash
   python3 1_reverseshell_server.py
   ```

2. On another machine (or VM), run the **client**:

   ```bash
   python3 6_reverseshell_client.py
   ```

3. Once connected, you’ll see:

   ```
   [+] Listening For The Incoming Connections
   [+] Target Connected From: ('10.0.2.15', 5555)
   * Shell~('10.0.2.15', 5555):
   ```

4. Try commands like:

   ```
   whoami
   ls
   upload test.txt
   download sample.log
   quit
   ```

---

## 🧠 Concepts Covered

| Concept             | Description                                       |
| ------------------- | ------------------------------------------------- |
| Sockets             | Foundation for network communication              |
| Client-Server Model | Basic setup for networked apps                    |
| Reverse Shell       | Remote command execution for ethical hacking labs |
| Port Scanning       | Discover open ports on a host                     |
| HTTP Methods        | Web reconnaissance using OPTIONS requests         |
| Exception Handling  | Graceful handling of socket/network errors        |

---

## 🔒 Ethical Note

These programs are intended **solely for authorized educational and cybersecurity training purposes**.
Unauthorized deployment, intrusion, or remote access is **illegal** under laws such as the **Information Technology Act (India)** and **Computer Fraud and Abuse Act (US)**.

---


**README section showing safe testing setup in VirtualBox/Kali + Windows sandbox**
