---
uid: Connector_help_Oi_Brazil_DSLAM_Collector
---

# Oi Brazil DSLAM Collector

The **Oi Brazil DSLAM Collector** allows the collection of KPIs and dynamic pinging statistics from DSLAM devices deployed as part of the Oi Brazil infrastructure.

## About

The **Oi Brazil DSLAM Collector** driver performs two main operations:

1.  Regular dynamic PING requests to the deployed DSLAM devices in order to check for reachability.
2.  Collecting specific information from the DSLAM devices using SNMP requests. Information to be collected will come from the interfaces table of the devices. The interfaces to be targeted are: Eth1 GigE and Eth2 GigE.

### Ranges of the driver

| **Driver Range** | **Description** | **DCF Integration** | **Cassandra Compliant** |
|------------------|-----------------|---------------------|-------------------------|
| 1.0.0.x          | Initial version | No                  | Yes                     |

### Supported firmware versions

| **Driver Range** | **Device Firmware Version** |
|------------------|-----------------------------|
| 1.0.0.x          | N/A                         |

## Installation and configuration

### Creation

#### SNMP Main Connection

This driver uses a Simple Network Management Protocol (SNMP) connection and requires the following input during element creation:

SNMP CONNECTION:

- **IP address/host**: DataMiner requires that this field is filled in. However, it does not matter which IP address you specify. The IP addresses that will be polled are the addresses imported via the .csv files, not the one specified in this field.

SNMP Settings:

- **IP port**: The port of the connected device, by default *161*.
- **Get community string**: The community string used when reading values from the device, by default *public*.
- **Set community string**: The community string used when setting values on the device, by default *private*.

### Configuration

This protocol requires the pre-provisioning of configuration data in order to function correctly. A .csv file containing the necessary data should be placed in a specific location. The following settings apply to the provisioning logic:

- **File Name**: *DMAID_EID_OBDC.csv*, where DMAID is the DataMiner ID of the Agent that will be handling the file, EID is the element ID of the DataMiner element that will be ingesting the file, and OBDC is a literal string used as file type identifier. Elements running the protocol will look for this structure within the given directory.
- **File Path**: The Windows directory path where the file will be located. Default: *C:\Skyline DataMiner\Documents\Oi Brazil DSLAM Collector\OBDC*.

## Usage

### General

Thispage displays a summary of the collector data, including the total number of **DSLAMs, Models, Stations, Cities, States, Sub-Regions** and **Super-Regions**.

### DSLAM

Thispage displays the collected data for each DSLAM, including **PING** statistics and **Gigabit Ethernet Interfaces** metrics.

The **Thread Statistics** subpage displays the threaded timer performance metrics, including **Thread Pool Usage, Thread Duration, Thread Pool Count** and **Threads Waiting** to be executed.

### Configuration

This page is divided in three sections: PING Settings, Polling Settings and Import Settings.

- The **PING Settings** section allows you to configure the PING parameters, including **PING Status, Packets per Cycle, Buffer Size, Timeout Time, TTL** and **Average Windows Size**.
- The **Polling Settings** section allows you to configure the polling parameters, for example the **Polling Status**.
- The **Import Settings** Section allows you to configure the .csv import parameters, such as **File Import Path**, **Auto-Import Timer** and **Import Status**.

## Revision History

DATE VERSION AUTHOR COMMENTS20/08/2018 1.0.0.1 AIG, Skyline Initial version05/10/2018 1.0.0.2 AIG, Skyline Manual polling of row using a push button09/11/2018 1.0.0.3 RDP, Skyline Decreased multi-threaded timer & other enhancements to make polling faster