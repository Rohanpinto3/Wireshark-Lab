# 2. Capturing Live Traffic

This section demonstrates how to capture live network traffic using Wireshark. It covers starting a packet capture, applying capture filters to collect specific traffic, and saving or exporting packet captures for future analysis.

---

## Starting a Packet Capture

A live packet capture can be started by clicking the **Start Capture** (blue shark fin) button in the top-left corner of Wireshark.

You can also select the desired network interface (such as Wi-Fi or Ethernet) before starting the capture. If needed, **Promiscuous Mode** can be enabled or disabled by selecting the **Capture Options** (gear icon).

> **Screenshot: <img width="992" height="638" alt="2(1)" src="https://github.com/user-attachments/assets/6a99003b-f5d7-41da-b4d5-4e6a85b6ede6" />**

---

## Applying a Capture Filter

Capture filters determine which packets Wireshark records during a live capture. Unlike display filters, capture filters are more limited and support filtering only up to Layer 4 of the OSI model.

Common capture filters can be viewed by selecting the **bookmark icon** and choosing **Manage Capture Filters**.

> **Screenshot: <img width="327" height="422" alt="2(2)" src="https://github.com/user-attachments/assets/4ceb4b11-db86-4c43-8532-c0517b0b113a" />**

Capture filters support filtering by:

* IP addresses
* MAC addresses
* TCP/UDP ports
* Network protocols (TCP, UDP, IPv4, IPv6, etc.)

Unlike display filters, capture filters do not use dots (`.`) or comparison operators (`==`).

For example:

```text
tcp port 80

udp port 53

host 192.168.1.100

not arp
```

Capture filters are designed to reduce the amount of traffic collected during a capture. If more detailed filtering is required, a display filter can be applied after the capture has been completed.

---

## Saving a Packet Capture

After collecting sufficient traffic, stop the capture by clicking the **Stop Capture** (red square) button.

The capture can then be saved by selecting the **Save** icon or navigating to:

**File → Save**

Wireshark supports several capture formats, including:

* `.pcap`
* `.pcapng`
* `.cap`

> **Screenshot: <img width="862" height="408" alt="2(3)" src="https://github.com/user-attachments/assets/d34f0078-4fc9-421f-9eee-d4e7af815f71" />**

---

## Exporting Specific Packets

Instead of saving the entire packet capture, Wireshark also allows exporting only selected packets.

This is useful when you want to save traffic that matches a specific display filter or isolate a particular network conversation.

> **Screenshot: Export Specified Packets**

To export selected packets:

1. Apply a display filter.
2. Navigate to **File → Export Specified Packets**.
3. Select **Displayed** to export only the filtered packets.
4. Choose the destination and save the new capture file.

You can also export a specific range of packet numbers instead of the entire filtered capture.

---

### Summary

In this section, I learned how to capture live network traffic, apply capture filters before recording packets, save packet captures for future analysis, and export specific packets using display filters.




















