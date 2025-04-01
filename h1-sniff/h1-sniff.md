# Homework 1

Homework report for [h1 Sniff](https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/#h1-sniff) [1]

## Table of Contents

- [Introduction](#1-introduction)
- [x. Read and summarize](#x-read-and-summarize)
- [Bibliography](#bibliography)

## Introduction



## x. Read and Summarize

### Wireshark

Wireshark is a network sniffer and analyzer. It can be used to capture traffic on network interfaces, which can then be analyzed in more detail. Packet captures can be saved as pcap-files, saving them for later analysis. Packets can be filtered in various ways to make finding them in the list easier. [[2]]

### Network Interface Names on Linux

These days, network interfaces on Linux use a naming scheme by systemd. Instead of 'eth', wired ethernet interfaces use the prefix 'en' (eg. enp1s0). WLAN, instead of 'wlan', use 'wl' now (eg. wlp4s0). The abbreviation 'lo' refers to the loopback address. You can check your interfaces with the command ``ip a``. [[3]]

## a. Linux

I downloaded a pre-built VirtualBox machine image with Kali Linux from [kali.org](https://www.kali.org/get-kali/#kali-virtual-machines), ran it, and changed the default password.

## b. Can't fish



## Bibliography

[1]
T. Karvinen, “h1 Sniff - Verkkoon Tunkeutuminen Ja Tiedustelu - Network Attacks and Reconnaissance,” Terokarvinen.com, 2025. https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/#h1-sniff (accessed Apr. 01, 2025).

[2]
T. Karvinen, “Wireshark - Getting Started,” Terokarvinen.com, 2025. https://terokarvinen.com/wireshark-getting-started/ (accessed Apr. 01, 2025).

[3]
T. Karvinen, “Network Interface Names on Linux - wlp4s0 lo enp1s0,” Terokarvinen.com, 2025. https://terokarvinen.com/network-interface-linux/ (accessed Apr. 01, 2025).