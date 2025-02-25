A collection of high-performance applications and tools designed for sending network packets. It serves two main purposes: penetration testing, which involves assessing network security by simulating various attacks like [Denial of Service](https://www.cloudflare.com/learning/ddos/glossary/denial-of-service/) (DoS); and network monitoring, which involves analyzing and inspecting network traffic.

Among these applications, two stand out as they utilize [AF_XDP](https://docs.kernel.org/networking/af_xdp.html) (eXpress Data Path) and the [DPDK](https://dpdk.org) (Data Plane Development Kit) technologies. AF_XDP is a fast and efficient network socket technology, while the DPDK is a kernel-bypass framework that allows for optimized packet processing in the user space.

By leveraging AF_XDP and the DPDK, these special applications can generate a significant amount of network traffic, making the most out of the available hardware resources.

With that said, if these applications are launched from multiple sources to the same network/IP address, it is considered a [**Distributed** Denial of Service](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/) (DDoS) attack.

These applications allow you to customize many of the packet's contents including layer 2/3/4 headers and payload data along with launch different types of attacks at once or in a chain via *sequences*. 

**NOTE** - This project was inspired by my previous Packet Sequence [project](https://github.com/gamemann/Packet-Sequence). Packet Sequence only supports `AF_PACKETv3` Linux sockets, though.

## 2025 Revamp
A revamp is in-progress that'll combine all packet processing technologies listed below into one main program. At this time, the revamp is not completed, but you may notice some repositories are marked as **old** (these are mostly unsupported).

Development of this revamp can be found in [this](https://github.com/Packet-Batch/Program/tree/20250218-rewrite) branch! Each packet processing tech will be stored as separate repositories in Packet Batch's [organization](https://github.com/Packet-Batch) prefixed with `tech-`.

## Applications
As mentioned above, there are three applications for this project; Standard, AF_XDP, and DPDK.

* [Standard](https://github.com/Packet-Batch/PB-Standard) - Utilizes `AF_PACKET` Linux sockets and supports TCP cooked sockets for establishing TCP connections automatically.
* [AF_XDP](https://github.com/Packet-Batch/PB-AF-XDP) - Uses `AF_XDP` Linux sockets which is faster than `AF_PACKETv3`, but doesn't support TCP cooked sockets.
* [DPDK](https://github.com/Packet-Batch/PB-DPDK) - Uses [the DPDK](https://dpdk.org) which is faster than other applications, but since the DPDK is a kernel-bypass library, it is harder to setup and only supports certain hardware. The tool also doesn't support TCP cooked sockets.

## Alternatives
If Packet Batch does not meet your expectations/needs, there are other tools that may accomplish what you're looking for, so I wanted to list them here. I will build this list as time goes on and if you have any suggestions, please feel free to reach out to me!

* [Pcktgen-DPDK](https://github.com/pktgen/Pktgen-DPDK)
* [go-pktgen](https://github.com/atoonk/go-pktgen)
* [netsniff-ng](https://github.com/netsniff-ng/netsniff-ng)

## Credits
* [Christian Deacon](https://github.com/gamemann)
