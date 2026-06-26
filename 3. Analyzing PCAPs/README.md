# 3. Analyzing PCAP Files

This section demonstrates how to analyze previously captured packet capture (PCAP) files using Wireshark. It covers display filters, following protocol streams, customizing packet views, and using Wireshark's built-in statistics to better understand network traffic.

---

## Applying a Display Filter

Display filters control which packets are shown in the Packet List, making it easier to isolate and analyze specific network traffic without modifying the original capture.

To filter by protocol, simply enter the protocol name.

Examples:

```text
udp

http.request

dns

icmp
```

> **Screenshot: <img width="855" height="207" alt="3(1)" src="https://github.com/user-attachments/assets/2ad61938-fdbc-4e99-a968-e097585de9a4" />**

To filter packets based on specific field values, specify the field name, comparison operator, and desired value.

Examples:

```text
tcp.port == 80

tcp.window_size_value >= 8000

ip.dst == 192.168.1.7
```

> **Screenshot: <img width="855" height="202" alt="3(2)" src="https://github.com/user-attachments/assets/f1242533-7185-4822-9eff-ebdca8220456" />
**

Multiple filter expressions can be combined using logical operators.

Examples:

```text
ip.dst == 192.168.1.7 && tcp

ntp || udp.port == 20000

!ftp
```

Logical operators supported include:

* `&&` (AND)
* `||` (OR)
* `!` (NOT)

Parentheses can also be used to group filter expressions for more advanced filtering.

---

## Following Streams & Custom Columns

Instead of inspecting packets individually, Wireshark can reconstruct an entire protocol conversation using the **Follow Stream** feature.

To follow a stream:

* Right-click a packet.
* Select **Follow**.
* Choose the appropriate protocol (TCP, UDP, HTTP, TLS, etc.).

> **Screenshot: <img width="858" height="243" alt="3(3)" src="https://github.com/user-attachments/assets/b38b99eb-1d0c-4c61-b51d-d14ec4fb56ae" />**

Wireshark automatically applies the appropriate display filter and opens a new window showing the complete conversation between the communicating hosts.

> **Screenshot: <img width="393" height="522" alt="3(4)" src="https://github.com/user-attachments/assets/539d692d-46b4-47ea-8bf4-4ca12da27104" />**

HTTP requests are typically displayed in **red**, while server responses appear in **blue**, making it easier to follow the complete exchange.

### Custom Columns

Packet List columns can also be customized to display additional protocol fields.

To add a custom column:

* Right-click any protocol field.
* Select **Apply as Column**.

> **Screenshot: <img width="861" height="282" alt="3(5)" src="https://github.com/user-attachments/assets/e7301652-887b-49b4-b66e-5ed8095aff4d" />

**

Adding frequently used protocol fields as columns allows important information to be identified much more quickly during packet analysis.

---

## Viewing Capture Statistics

Wireshark includes several statistics windows that provide an overview of captured network traffic.

The statistics discussed in this lab include:

* Protocol Hierarchy
* Conversations
* Endpoints

---

## Protocol Hierarchy

The **Protocol Hierarchy** window displays the percentage of packets and bytes used by each protocol within the capture.

Protocols are organized according to the OSI layers, allowing you to quickly identify the protocols generating the most traffic.

> **Screenshot: <img width="857" height="225" alt="3(6) " src="https://github.com/user-attachments/assets/a97ffba6-595d-42fd-a597-99279647389b" />**

This view can also help identify unusual protocols that may indicate suspicious or unexpected network activity.

Individual protocols can be right-clicked and applied as display filters for further investigation.

---

## Conversations

The **Conversations** window displays communication between hosts, including:

* Source and Destination IP Addresses
* Ports
* Number of Packets
* Total Bytes Transferred

> **Screenshot: <img width="855" height="536" alt="3(7)" src="https://github.com/user-attachments/assets/e4a577d4-1132-4fce-9043-cfc80297a522" />
**

This information helps identify which systems communicated, how much data was exchanged, and whether any hosts exhibit unusual communication patterns.

Each conversation can also be applied directly as a display filter for deeper analysis.

---

## Endpoints

The **Endpoints** window lists every host that appears within the capture.

For each endpoint, Wireshark displays:

* Packets Sent
* Packets Received
* Bytes Sent
* Bytes Received

> **Screenshot: <img width="857" height="406" alt="3(8)" src="https://github.com/user-attachments/assets/02d53332-0707-4b84-91ca-e08aedce8cd3" />**

This information helps identify the most active devices within the capture. Hosts transmitting significantly more data than they receive may be uploading information, while hosts receiving much more data may be downloading files or updates.

Endpoints can also be filtered directly from this window for additional investigation.

---

### Summary

In this section, I learned how to analyze PCAP files using display filters, reconstruct protocol conversations with Follow Stream, customize packet list columns, and use Wireshark's statistics windows to identify communication patterns, protocol usage, and active hosts within a network capture.















