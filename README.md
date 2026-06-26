
# 1. Wireshark GUI Walkthrough

Wireshark is a free and open-source network protocol analyzer used to capture and inspect network traffic in real time. It is widely used by network administrators, security professionals, and IT technicians for troubleshooting and traffic analysis.

The Wireshark interface consists of two primary screens:

* **Startup Window** – Displayed when Wireshark is first launched.
* **Main Window** – Displayed after starting or opening a packet capture.

---

# Wireshark Startup Window

The **Startup Window** appears when Wireshark launches. It allows you to start a new packet capture, open previously saved capture files, and configure capture settings.

> **Screenshot: Wireshark Startup Window**

### 1. Start Capture

The **Start Capture** button begins capturing inbound and outbound network traffic on the selected network interface. Any configured capture filters are applied before packets are collected.

### 2. Open Saved Files

Wireshark can open previously captured packet files for analysis. Supported formats include:

* `.pcap`
* `.pcapng`
* `.cap`

### 3. Capture Filter

Capture filters limit which packets are collected during a live capture.

For example:

```text
not arp
```

This filter excludes ARP packets from the capture.

Capture filters can also be saved for future use.

### 4. Capture Interface Selection

Wireshark displays all available network interfaces along with a live activity graph.

Select the interface that corresponds to the traffic you want to capture, such as:

* Wi-Fi
* Ethernet
* VirtualBox Network Adapter

It is recommended to enable **Promiscuous Mode**, which allows Wireshark to capture packets that are not directly addressed to the local machine, providing a broader view of network traffic.

> **Screenshot: Capture Options (Promiscuous Mode)**

Promiscuous Mode can be enabled or disabled from the **Capture Options** (gear icon) for individual interfaces or globally.

---

# Wireshark Main Window

After starting a capture or opening an existing PCAP file, Wireshark displays the **Main Window**, where packet inspection and analysis take place.

> **Screenshot: Wireshark Main Window**

### 1. Menu Bar

The Menu Bar contains controls to:

* Start, stop, and restart captures
* Open and save capture files
* Configure capture settings
* Search for packets
* Access Wireshark analysis tools

### 2. Display Filter

Display filters control which packets are shown in the packet list without modifying the original capture.

Example:

```text
ip.src == 192.168.1.7 && tcp.port == 443
```

This filter displays packets originating from **192.168.1.7** using **TCP port 443**.

Display filters support logical operators such as:

* `&&` (AND)
* `||` (OR)
* `!` (NOT)

> **Screenshot: Display Filter Example**

### 3. Packet Panes

The Main Window is divided into three primary panes:

* Packet List
* Packet Details
* Packet Bytes

These panes provide different levels of detail for each captured packet.

### 4. Packet List

The Packet List displays a summary of every captured packet, including:

* Packet Number
* Time
* Source
* Destination
* Protocol
* Length
* Packet Information

This provides an overview of network activity and protocol conversations.

### 5. Packet Details

The Packet Details pane displays protocol information in a layered structure, allowing individual fields to be expanded for detailed inspection.

Information includes:

* Ethernet
* IP
* TCP / UDP
* DNS
* HTTP
* TLS

> **Screenshot: Packet Details (DNS Packet)**

The Packet Details pane allows you to inspect information such as MAC addresses, IP addresses, ports, protocol flags, and application-layer data.

### 6. Packet Bytes (Hex Dump & ASCII)

The Packet Bytes pane displays the raw contents of the selected packet in both hexadecimal and ASCII format.

> **Screenshot: Hex Dump & ASCII Pane**

Selecting a field in the Packet Details pane automatically highlights the corresponding bytes in the hex dump. This feature is useful when identifying protocol fields and constructing display filters, as Wireshark also displays the associated field name (for example, `tcp.seq`).

---

### Summary

In this section, I explored the Wireshark Startup Window and Main Window, learning how to start packet captures, configure capture settings, navigate the interface, and inspect captured network traffic before moving on to live packet capture and PCAP analysis.
