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

The Kali Linux I will be using still uses the old naming scheme.

## a. Linux

I downloaded a pre-built VirtualBox machine image with Kali Linux from [kali.org](https://www.kali.org/get-kali/#kali-virtual-machines), ran it, and changed the default password.

I will use this virtual machine for the remainder of this homework, unless otherwise stated.

## b. Can't fish

I can disconnect the eth0 interface inside Kali Linux. Pinging will now result in the following error:

![02](imgs/h1-02.png)

I can also cut the connection by going in to VirtualBox settings, and selecting 'None' in the dropdown menu of Network Adapter 1. This will result in the following error when pinging inside Kali Linux:

![03](imgs/h1-03.png)

Restoring the connection will result in the following:

![01](imgs/h1-01.png)

## c. Wireshark

Conveniently, Kali Linux has Wireshark already installed. I launched Wireshark, then made a ping google.com to confirm that it's capturing traffic.

![04](imgs/h1-04.png)

## d. Really TCP/IP

![05](imgs/h1-05.png)

In the above image is a packet I captured in Wireshark when browsing to 'google.com' in Firefox. There are five entries. The first two are the link layer in the TCP/IP-model. The second specifically, shows the MAC addresses in the frame. The third is the internet layer, and shows the IP-address of my Linux virtual machine (10.0.2.15), as well as the IP-address of the Google server. The fourth is the transport layer and shows information on the TCP segment. The last entry shows the application layer, which in this case shows information on the HTTP PDU.

## e. What did I surf?

I downloaded the surfing-secure.pcap file provided in the assignment and opened it with Wireshark. The traffic consists mostly of encrypted communications using TLSv1.3. The start also contains some packets using QUIC. Other protocols that can be observed in the traffic are DNS, TCP, and ARP.

Using Wireshark's IPv4 analysis, I can see there are seven different hosts. The host capturing the traffic and initiating the connections is 192.168.122.7, as it's found in 100% of the captured packets. Over half of the traffic happened with the host 139.162.131.217. The DNS queries reveal that IP-address belongs to the domain terokarvinen.com. Typing that address into Firefox takes me to app.terokarvinen.com.

The following seems to indicate that the host communicated with a server in terokarvinen.com, and that it was secured. Any more specifically I cannot tell with my current limited skills in sniffing.

## g. What model is the network card?

There are two MAC addresses, but both are locally administered, meaning they are not the original hardware addresses. Therefore, I cannot determine the make of the network card based on the MAC address.

Currently, I don't know of another way to find out who made the network card.

## h. What web-server has the user surfed at?

As mentioned previously, the host 139.162.131.217 seems to belong to a server in terokarvinen.com.

## i. Analysis

WIP

## Bibliography

[1]
T. Karvinen, “h1 Sniff - Verkkoon Tunkeutuminen Ja Tiedustelu - Network Attacks and Reconnaissance,” Terokarvinen.com, 2025. https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/#h1-sniff (accessed Apr. 01, 2025).

[2]
T. Karvinen, “Wireshark - Getting Started,” Terokarvinen.com, 2025. https://terokarvinen.com/wireshark-getting-started/ (accessed Apr. 01, 2025).

[3]
T. Karvinen, “Network Interface Names on Linux - wlp4s0 lo enp1s0,” Terokarvinen.com, 2025. https://terokarvinen.com/network-interface-linux/ (accessed Apr. 01, 2025).