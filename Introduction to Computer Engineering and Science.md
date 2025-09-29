Cpu - controls flow to help it has registers or cache to make it 
Everything communicates through buses - Data bus, 

Data bus - CPU, memory and input output 

Address bus - which identiffies where the dtaa shpuld go or come from 

control bus 0- basically tell how the data ashould be read handled , write or wait

IN ORDER TO RUN TO RUN A C FILE its gcc -o helloworld.c

and then ./helloworld.c

but for python ts python3 main.py 

ths illustrates the diff between complied and interpreted language 

C code must be compiled into machine instructions before it can be run 
![[Pasted image 20250826184529.png]]


Of course. This is a fundamental concept in computer architecture. Here’s a clear breakdown of the differences between the address bus, data bus, and control bus.

### The Core Analogy: Think of a Postal System

Imagine the CPU is the central post office and the RAM (memory) is a massive street with millions of mailboxes.

*   **Address Bus:** This is the **address** on the envelope. It tells the postal worker (the memory controller) *which specific mailbox* to go to. It's a one-way street from the CPU to memory.
*   **Data Bus:** This is the **contents** of the envelope (the letter or package itself). Once the correct mailbox is found, data (instructions or information) is either placed *into* the mailbox (write) or taken *out of* the mailbox (read). This is a two-way street.
*   **Control Bus:** This is the **instructions** for the postal worker. It carries signals like "I want to *read* from this mailbox" or "I want to *write* to this mailbox." It coordinates the entire operation.

---

### Detailed Comparison Table

| Feature | Address Bus | Data Bus | Control Bus |
| :--- | :--- | :--- | :--- |
| **Primary Function** | To carry **memory addresses** from the CPU to other components. | To carry the **actual data** between the CPU, memory, and I/O devices. | To carry **control and timing signals** that manage the system's operation. |
| **Direction** | **Unidirectional** (One-Way). Only the CPU can place addresses on this bus. | **Bidirectional** (Two-Way). Data can flow to or from the CPU. | **Bidirectional**, but most lines are **unidirectional**. It carries both incoming (e.g., interrupt requests) and outgoing (e.g., read/write) signals. |
| **What it Carries** | A binary number specifying a unique memory location or I/O port. | The binary instructions or information being processed. | Signals like: **Memory Read, Memory Write, I/O Read, I/O Write, Interrupt Request, Bus Grant, Clock**. |
| **Who Controls It** | Exclusively by the CPU (or the Memory Controller). | Can be controlled by the CPU, memory, or I/O devices, depending on the operation. | Various components control different lines (CPU, memory, I/O controllers). |
| **Width & Performance** | **Width determines the amount of addressable memory.** <br> A 32-bit bus can address 2³² (4 GB) locations. <br> A 64-bit bus can address 2⁴⁴ locations (a massive amount). | **Width determines how much data is transferred at once (word size).** <br> A 32-bit bus moves 4 bytes per cycle. <br> A 64-bit bus moves 8 bytes per cycle. This is a key factor in speed. | Width varies and is not tied to system capacity in the same way. It has as many lines as needed for the control signals. |

---

### How They Work Together: A "Read from Memory" Operation

Let's see how the three buses cooperate to perform a simple task: the CPU needs to read a piece of data from memory.

1.  **CPU places the address on the Address Bus.**
    *   The CPU calculates the specific location in memory where the desired data is stored and outputs this address onto the address bus lines.

2.  **CPU places a command on the Control Bus.**
    *   The CPU activates the **Memory Read** (MEMR) line on the control bus. This signal tells every other component in the system: "The CPU wants to read from the memory location specified on the address bus."

3.  **Memory responds.**
    *   The memory chip sees the address and the "read" command. It fetches the data from the requested location.

4.  **Memory places the data on the Data Bus.**
    *   The memory chip outputs the requested data onto the data bus lines.

5.  **CPU reads the data.**
    *   The CPU grabs the data from the data bus and stores it in one of its internal registers for processing. The operation is complete.

### Summary in One Sentence

*   The **Address Bus** says **"WHERE."**
*   The **Data Bus** carries **"WHAT."**
*   The **Control Bus** says **"HOW."** (e.g., read it or write it)

Together, these three buses form the **system bus**, which is the primary communication highway of the computer, connecting the CPU to the main memory and other components on the motherboard.

Of course. Here is the information formatted as a clear and structured report for your notes.

---

### **Report: The `ifconfig` Command & MAC Address Spoofing**

**Date:** October 26, 2023
**Subject:** Network Interface Management on Unix/Linux Systems

---

#### **1. Executive Summary**
The `ifconfig` (Interface Configurator) command is a legacy tool for viewing, configuring, and troubleshooting network interfaces on Unix-like operating systems (Linux, macOS). While modern systems have moved to the `ip` command, `ifconfig` remains widely used and understood. A key function is MAC address spoofing, which temporarily changes a network interface's software-presented address without altering its physical hardware.

---

#### **2. What is `ifconfig`?**
`ifconfig` is a command-line utility used to manage network interfaces, which are the points of connection between a computer and a network (e.g., Ethernet ports, Wi-Fi adapters, virtual interfaces).

---

#### **3. Primary Functions of `ifconfig`**

##### **3.1. View Interface Status**
*   **Command:** `ifconfig`
*   **Purpose:** Displays information for all active network interfaces.
*   **Key Output Fields:**
    *   **`inet`:** The IPv4 address (e.g., `192.168.1.15`).
    *   **`netmask`:** The subnet mask (e.g., `255.255.255.0`).
    *   **`ether`:** The MAC (hardware) address.
    *   **`RX` / `TX`:** Statistics on received/transmitted packets (useful for troubleshooting).
    *   **`UP`:** Flag indicating the interface is active.
*   To view all interfaces (including inactive ones): `ifconfig -a`

##### **3.2. Configure Interfaces**
*   **Assign an IP Address:**
    ```bash
    sudo ifconfig eth0 192.168.1.100
    ```
*   **Enable/Disable an Interface:**
    ```bash
    sudo ifconfig eth0 down  # Deactivates the interface
    sudo ifconfig eth0 up    # Reactivates the interface
    ```
*   **Set IP, Netmask, and Broadcast:**
    ```bash
    sudo ifconfig eth0 192.168.1.100 netmask 255.255.255.0 broadcast 192.168.1.255
    ```

##### **3.3. MAC Address Spoofing**
*   **Command:**
    ```bash
    sudo ifconfig eth0 hw ether 08:00:27:4e:66:a2
    ```
*   **Purpose:** Temporarily changes the MAC address seen by the operating system and network.

---

#### **4. `ifconfig` vs. The Modern `ip` Command**
`ifconfig` is from the deprecated `net-tools` package. The modern replacement is the `ip` command from `iproute2`.

| Task | `ifconfig` (Legacy) | `ip` command (Modern) |
| :--- | :--- | :--- |
| **Show IP Addresses** | `ifconfig` | `ip address show` or `ip a` |
| **Bring Interface Up** | `sudo ifconfig eth0 up` | `sudo ip link set eth0 up` |
| **Bring Interface Down** | `sudo ifconfig eth0 down` | `sudo ip link set eth0 down` |
| **Add IP Address** | `sudo ifconfig eth0 192.168.1.100` | `sudo ip address add 192.168.1.100/24 dev eth0` |
| **Show Routing Table** | `route -n` | `ip route show` or `ip r` |

**Note:** Learn the `ip` command for new scripts and systems, but knowledge of `ifconfig` is essential for working on older systems.

---

#### **5. Understanding MAC Address Spoofing**

##### **5.1. The Analogy**
*   **Real MAC Address:** Your **legal name** on a birth certificate. It is permanent and burned into the network card's hardware (ROM).
*   **Spoofed MAC Address:** A **nametag** at an event. It is a temporary, software-level override that is used only until the system reboots or the interface is reset.

##### **5.2. Key Technical Points**
*   **Hardware vs. Software:** The spoofed address is changed only in the interface's **software-driven RAM**, not its physical **ROM**.
*   **Temporary:** The change is **not persistent**. It lasts only until:
    *   The next reboot.
    *   The interface is manually restarted (e.g., `sudo ifconfig eth0 down && sudo ifconfig eth0 up`).
*   **Purpose:**
    *   **Privacy:** Avoiding tracking on public networks.
    *   **Bypassing Filters:** Circumventing network policies that allow or block specific MAC addresses.
    *   **Testing:** Validating network security and access controls.

##### **5.3. Conclusion on Spoofing**
Spoofing is a surface-level change. The operating system and network see the new "mask," but the **underlying hardware address remains physically unchanged and reverts** once the temporary software override is cleared.

---
**End of Report**



Os always provies built in I/O functions 

INFO COMMAND PROVIDES MORE INFO THAN MAN 




