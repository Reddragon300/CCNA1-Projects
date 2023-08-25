
# Packet Tracer - Connect the Physical Layer

# Objectives

## Part 1: Identify Physical Characteristics of Internetworking Devices

## Part 2: Select Correct Modules for Connectivity

## Part 3: Connect Devices

## Part 4: Check Connectivity

Background
In this activity, you will explore the different options available on internetworking devices. You will also be required to determine which options provide the necessary connectivity when connecting multiple devices. Finally, you will add the correct modules and connect the devices.

# Instructions

## Part 1: Identify Physical Characteristics of Internetworking Devices

### Step 1: Identify the management ports of a Cisco router.

A.     Click the East router. The Physical tab should be active.

B.     Zoom in and expand the window to see the entire router.

## Question: Which management ports are available?

```text
AUX and Console Ports
```
![East](auxcon.png)

### Step 2: Identify the LAN and WAN interfaces of a Cisco router.

## Question:  Which LAN and WAN interfaces are available on the East router and how many are there?

![East](int.png)

```text
There are 2 WAN interfaces and 2 Gigabit Ethernet interfaces.
```

B.     Click the CLI tab, press the Enter key to access the user mode prompt, and enter the following commands:

Open a configuration window

```terminal
East> show ip interface brief
```

![East IP Interface Brief](eastipbrief.png)

The output verifies the correct number of interfaces and their designation. The vlan1 interface is a virtual interface that only exists in software.

### Question: How many physical interfaces are listed?

```text
There are 4 Physical interfaces.
```

C.     Enter the following commands:

```terminal
East> show interface gigabitethernet 0/0
```

![East GigabitEthernet 0/0](gig00.png)

## Question: What is the default bandwidth of this interface?

```text
1000000 Kbit
```

```terminal
East> show interface serial 0/0/0
```

![East Serial 0/0/0](serial000.png)

## Question: What is the default bandwidth of this interface?

```text
1544 Kbit
```
Note: Bandwidth on serial interfaces is used by routing processes to determine the best path to a destination. It does not indicate the actual bandwidth of the interface. Actual bandwidth is negotiated with a service provider.

### Step 3: Identify module expansion slots.

## Questions: How many expansion slots are available to add additional modules to the East router?

```text
There is 1 expansion slot.
```

Click `Switch2`. How many expansion slots are available?

```text
There are 5 available expansion slots.
```

## Part 2: Select Correct Modules for Connectivity

### Step 1: Determine which modules provide the required connectivity.

A.     Click East and then click the Physical tab. On the left, beneath the Modules label, you see the available options to expand the capabilities of the router. Click each module. A picture and a description display at the bottom. Familiarize yourself with these options.

## Question 1)    You need to connect PCs 1, 2, and 3 to the East router, but you do not have the necessary funds to purchase a new switch. Which module can you use to connect the three PCs to the East router?

```text
HWIC-4ESW module
```

## Question 2)    How many hosts can you connect to the router using this module?

```text
4 hosts
```

B.     Click `Switch2`.

![Switch2](switch2.png)

## Question: Which module can you insert to provide a Gigabit optical connection to Switch3?

```text
PT-SWITCH-NM-1FGE
```

### Step 2: Add the correct modules and power up devices.

A.     Click East and attempt to insert the appropriate module from Step 1a. Modules are added by clicking the module and dragging it to the empty slot on the device.

![East Module](eastmod.png)

The Cannot add a module when the power is on message should display. Interfaces for this router model are not hot-swappable. The device must be turned off before adding or removing modules. Click the power switch located to the right of the Cisco logo to turn off East. Insert the appropriate module from Step 1a. When done, click the power switch to power up East.

Note: If you insert the wrong module and need to remove it, drag the module down to its picture in the bottom right corner, and release the mouse button.

B.     Using the same procedure, insert the module that you identified in Step 1b into the empty slot farthest to the right in `Switch2`.

![Switch2 Module](switch2.png)

C.     Use the show ip interface brief command on Switch2 to identify the slot in which the module was placed.

![Switch2 IP Interface Brief](switch2brief.png)

## Question: Into which slot was it inserted?

```text
GigabitEthernet5/1
```

## Part 3: Connect Devices

This may be the first activity you have done where you are required to connect devices. Although you may not know the purpose of the different cable types, use the table below and follow these guidelines to successfully connect all the devices:

A.     Select the appropriate `cable type`.

B.     Click the `First Device` and select the specified `interface`.

C.     Click the `Second Device` and select the specified `interface`.

D.     If you have correctly connected two devices, you will see your score increase.

# Example: To connect East to `Switch1`, select the `Copper Straight-Through` cable type. Click `East` and choose `GigabitEthernet0/0`. Then, click `Switch1` and choose `GigabitEthernet0/1`. Your score should now be 4/55.

![Chart](chart.png)

## Part 4: Check Connectivity

### Step 1: Check the interface status on East.

A.     Click the `CLI Tab` and enter the following commands:

```console
East> `show ip interface brief`
```

Compare the output to the following:

```table
Interface              IP-Address  OK? Method Status Protocol

GigabitEthernet0/0     172.30.1.1  YES manual up     up

GigabitEthernet0/1     172.31.1.1  YES manual up     up

Serial0/0/0            10.10.10.1  YES manual up     up

Serial0/0/1            unassigned  YES unset  down   down

FastEthernet0/1/0      unassigned  YES unset  up     up

FastEthernet0/1/1      unassigned  YES unset  up     up

FastEthernet0/1/2      unassigned  YES unset  up     up

FastEthernet0/1/3      unassigned  YES unset  up     down

Vlan1                  172.29.1.1  YES manual up     up
```

![East IP Interface Brief](eastipbrief.png)

If all of the cabling is correct the outputs should match.

Close the configuration window

### Step 2: Connect wireless devices, Laptop and TabletPC.

A.     Click the Laptop and select the Config Tab. Select the Wireless0 interface. Put a check in the box labeled On next to Port Status. Within a few seconds the wireless connection should appear.

B.     Click the Desktop tab of the Laptop. Click on the Web Browser icon to launch the web browser. Enter www.cisco.srv in the URL box and click Go. The page should display Cisco Packet Tracer.

C.     Click the TabletPC and select the Config Tab. Select the Wireless0 interface. Put a check in the box labeled On next to Port Status. Within a few seconds the wireless connection should appear.

D.     Repeat the steps in Step 2b to verify the page displays.

### Step 3: Change the access method of the TabletPC.

A.     Click the TabletPC and select the Config Tab. Select the Wireless0 interface. Uncheck the box labeled On next to Port Status. It should now be clear and the wireless connection will drop.

B.     Click the 3G/4G Cell1 interface. Put a check in the box labeled On next to Port Status. Within a few seconds the cellular connection should appear.

C.     Repeat the process of verifying web access.

Note: You should not have both the wireless0 interface and 3G/4G Cell1 interfaces active at the same time. This may cause confusion to the device when attempting to connect to some resources.

### Step 4: Check connectivity of the other PCs.

All of the PCs should have connectivity to the web site and each other. You will learn to use connectivity testing in many upcoming labs.


**Packet Tracer File:**

You can download and open the Packet Tracer simulation file for this module using the link below:

[Download Module1 Packet Tracer File](files\4.7.1-packet-tracer---connect-the-physical-layer.pka)

** PDF Answer Key File:**

You can download and view my PDF Answer Key file for this module using the link below:
[Download PDF](files\4.7.2 Packet Tracer Answers.pdf)