# Packet Tracer - Examine the ARP Table

** Addressing Table**
![Addressing Table](table.png)

## Objectives

### Part 1: Examine an ARP Request

### Part 2: Examine a Switch MAC Address Table

### Part 3: Examine the ARP Process in Remote Communications

Background
This activity is optimized for viewing PDUs. The devices are already configured. You will gather PDU information in simulation mode and answer a series of questions about the data you collect.

# Instructions

## Part 1: Examine an ARP Request

### Step 1: Generate ARP requests by pinging 172.16.31.3 from 172.16.31.2.

Open A `Command Prompt`

A.     Click `172.16.31.2` and open the `Command Prompt`.

B.     Enter the `arp -d` command to clear the `ARP Table`.

![ARP -D Command](1b.png)

Close a `Command Prompt`

C.     Enter Simulation mode and enter the command `ping 172.16.31.3`. Two PDUs will be generated. The ping command cannot complete the ICMP packet without knowing the MAC address of the destination. So the computer sends an ARP broadcast frame to find the MAC address of the destination.

![Ping Command](1c.png)

D.     Click Capture/Forward once. The ARP PDU moves Switch1 while the ICMP PDU disappears, waiting for the ARP reply. Open the PDU and record the destination MAC address.

![ARP PDU](1d.png)

## Question: Is this address listed in the table above?

```text
No, the MAC address is not listed in the table above.
```

## Question: How many copies of the PDU did Switch1 make?

```text
Switch1 made 3 copies of the PDU.
```



## Question: What is the IP address of the device that accepted the PDU?

```text
The IP address of the device that accepted the `PDU` is `172.16.31.3`
```

E.     Open the `PDU` and examine `Layer 2`.

![ARP PDU](1e.png)

## Question: What happened to the source and destination MAC addresses?

```text
-	Source MAC Address became Destination MAC Address.
-	FFFF:FFFF:FFFF Converted to MAC address of 172.16.31.3
```

F.      Click `Capture/Forward` until the `PDU` returns to `172.16.31.2`.

## Question: How many copies of the PDU did the switch make during the ARP reply?

```text
The Switch Made One Copy Of The PDU During The ARP Reply.
```

### Step 2: Examine the ARP table.

A.     Note that the ICMP packet reappears. Open the PDU and examine the MAC addresses.

## Question: Do the MAC addresses of the source and destination align with their IP addresses?

```text
Yes, the MAC addresses of the source and destination align with their IP addresses.
```

B.     Switch back to `Realtime` and the `ping` completes.

C.     Click `172.16.31.2`and enter the `arp –a` command.



## Question: To what IP address does the MAC address entry correspond?

```text
IP Address: 172.16.31.3
```

![ARP -A Command](2c.png)

## Question: In general, when does an end device issue an ARP request?

```text
When The Receiver's MAC Address Is Not Known.
```

## Part 2: Examine a Switch MAC Address Table

### Step 1: Generate additional traffic to populate the switch MAC address table.

`Open a command prompt`

A.     From `172.16.31.2`, enter the `ping 172.16.31.4` command.

B.     Click 10.10.10.2 and open the `Command Prompt`.

C.     Enter the `ping 10.10.10.3` command.

![Ping Command](21c.png)

## Question: How many replies were sent and received?

```text
There were 4 replies sent and received.
```

`Close a command prompt`

### Step 2: Examine the MAC address table on the switches.

A.     Click `Switch1` and then the `CLI` tab. Enter the `show mac-address-table` command.

![Show Mac-Address-Table Command](SW1.png)

## Question: Do the entries correspond to those in the table above?

```text
Yes, the entries correspond to those in the table above.
```

B.     Click `Switch0`, then the `CLI` tab. Enter the `show mac-address-table` command.

![Show Mac-Address-Table Command](SW0.png)

## Questions: Do the entries correspond to those in the table above?

```text
Yes, the entries correspond to those in the table above.
```

## Questions: Why are two MAC addresses associated with one port?

```text
They both are connected to the one port which is through the Access Point.
```

## Part 3: Examine the ARP Process in Remote Communications

### Step 1: Generate traffic to produce ARP traffic.

`Open a command prompt`

A.     Click `172.16.31.2` and open the `Command Prompt`.

B.     Enter the `ping 10.10.10.1` command.


C.     Type `arp –a`.

![Ping Command](31b.png)


## Question: What is the IP address of the new ARP table entry?

```text
The IP address of the new ARP table entry is - 172.16.31.1
```

D.     Enter `arp -d` to clear the `ARP Table` and switch to `Simulation Mode`.

E.     Repeat the `ping 10.10.10.1`.

![Ping Command](31c.png)

## Question: How many PDUs appear?

```text
There are 2 PDUs that appear.
```

`Close a command prompt`

F.      Click `Capture/Forward` Click the `PDU` that is now at `Switch1`



## Question: What is the target destination IP destination address of the ARP request?

![Ping Command](31f.png)

```text
The target destination IP destination address of the ARP request is - 172.16.31.1
```

G.     The `Destination IP Address` is not `10.10.10.1`.

## Question: Why?

```text
This is because the gateway address of the router interface is stored in the IPv4 configuration of the hosts. If the receiving host is not on the same network, the source uses the ARP process to determine a MAC address for the router interface serving as the gateway.
```

### Step 2: Examine the ARP table on Router1.

A.     Switch to `Realtime mode`. Click `Router1` and then the `CLI Tab`.

B.     Enter `Privileged EXEC Mode` and then the `Show Mac-Address-Table` command.

## Question: How many MAC addresses are in the table? Why?

![Show Mac-Address-Table Command](2bb.png)

```text
There aren’t any MAC Addresses shown because this command doesn’t have the same meaning on the router as it does for the switch.
```

C.     Enter the `Show arp` command.

## Questions: Is there an entry for `172.16.31.2`?

```text
Yes there is an entry for `172.16.31.2
```

![Show arp Command](2cc.png)

## Question: What happens to the first ping in a situation where the router responds to the ARP request?

```text
The first ping Will Be Dropped Or Time Out In This Situation.
```

**Packet Tracer File:**

You can download and open the Packet Tracer simulation file for this module using the link below:

[Download Module1 Packet Tracer File](files\9.2.9-ARP-Table.pkz)