# Week 5 - Supplementary Materials 
[Markdown](https://github.com/lawfareblog/hacking-cybersecurity/blob/main/week05/Week_05_Homework.md) | [PDF](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week05/Week_05_Homework.pdf) | [MS Word DOCX](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week05/Week_05_Homework.docx) | [Libre ODT](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week05/Week_05_Homework.odt) | [HTML](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week05/Week_05_Homework.html)

## Basic Networking Commands

This week we give an overview of basic networking concepts and associated commands in the CLI.

**NOTE:** You will need to use Kali Linux for these and future practical exercises. If you have not set it up yet, please see our instructions in the [class README](https://github.com/lawfareblog/hacking-cybersecurity/).

#### `ip address`

Use `ip address` to display IP addresses, bind a new IP address to a network interface (e.g, `eth0`), or delete address entries.

`ip address show dev`

The following command displays the IP address assigned to network interface `eth0`:

`ip address show dev eth0`

_NOTE:_ The `man` manual page  for `ip address` is named `ip-address`.

---

#### `ifconfig`

The `ifconfig` command is a utility for managing network interfaces. On newer Kali Linux systems, you will have to install the `net-tools` package to use `ifconfig`:

`sudo apt-get install net-tools`

Each interface with access to the Internet will have an IPv4 address listed as `inet` in the `ifconfig` output. The IPv6 address (we will not use these in class) is listed as `inet6`.

The interface called `lo` is the "localhost" (or "loopback") interface, referring to your machine and listed with an IP address of 127.0.0.1

Your Ethernet or WiFi network card's physical hardware address (Media Access Control or MAC Address) is listed as `inet address` in the output of `ifconfig`.

If you are using a virtual machine, such as the Kali Linux VM we use for class, that address will be a virtual interface that is "bridged" to the network of the device hosting the VM.

---

#### `nslookup`

`nslookup` allows network nodes to query domain name servers (DNS) and the associated IP addresses.

`nslookup lawfareblog.com`

DNS ties Internet addresses (such as IPv4) to domain names such as lawfareblog.com

---

#### `dig`

"Domain Information Groper" is commonly used to "dig" for information from DNS servers.

`dig lawfareblog.com`

---

#### `netstat`

`netstat` is used to find information about network connections, routing tables, and network statistics. Use `-i` option to list network interfaces.

`netstat -i`

The `-r` option will display the routing table, which is a configuration that routers and other network devices use to send packets to the machines.

`netstat -r`

Any packet intended for a network not listed in the table is handled by the default destination.

With no options, `netstat` displays a list of open "sockets", which is a concept we will explore in later networking classes. You can use the `-l` option to show listening sockets.

`netstat -l`

Use the `-a` option to show all sockets.

`netstat -a`

#### `ss`

`ss` is very similar to `netstat` and is used on modern operating systems. To view all TCP sockets, use: 

`ss -ta`

These sockets are important information for an attacker who may have compromised the machine or is intending to do so.


