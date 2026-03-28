# packet-sniffer-cli-tool
A command-line tool implemented in C using libpcap to capture, analyze, and process network packets. It serves as a foundational project for building a simple packet sniffer and a single-threaded framework for an Intrusion Detection System (IDS)


# idsniff: A Basic Packet Sniffer and Intrusion Detection System

## 🌟 Overview

`idsniff` is a foundational command-line application designed to capture and process network packets from a specified interface. It is built in C and leverages the `libpcap` library for packet sniffing.

This project skeleton provides the core components for:
1.  **Packet Sniffing**: Using `pcap_open_live` and `pcap_next` to capture packets from a live network interface.
2.  **Packet Dispatching**: A simple mechanism (`dispatch.c`) to pass captured packets to an analysis function. (Future development could use this for thread-based dispatching).
3.  **Basic Analysis Framework**: The `analyse.c` file serves as the entry point for implementing protocol decoding and custom intrusion detection logic.
4.  **Debugging Tools**: Includes a verbose mode with a `dump` utility to print raw packet and Ethernet header details.

## 🛠️ Build and Dependencies

### Dependencies
The project requires the `libpcap` development library.

**On Debian/Ubuntu:**
```bash
sudo apt-get install libpcap-dev


Option,Long Option,Description,Default
-i [interface],--interface,Specify the network interface to sniff from.,eth0
-v,--verbose,"Enable verbose mode, which dumps raw packet data (Ethernet header and payload) to the terminal.",Disabled (0)

## 🌟 Project Structure

File,Description
main.c,Handles command-line argument parsing and initializes the sniffing loop.
sniff.c / sniff.h,Contains the core libpcap sniffing logic (sniff) and a utility function to print packet contents (dump).
dispatch.c / dispatch.h,"The dispatch layer. Currently, it simply calls analyse, but is intended for future thread/queue management."
analysis.c / analysis.h,The core analysis component where protocol decoding and IDS logic is implemented. (Your current task/TODO is in this file).
Makefile,Build configuration for the project.
