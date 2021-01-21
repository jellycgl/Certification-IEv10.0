## L2 Neighbor Checking

### 1.Certification Input
#### 1.1 Input for ARP Table
```yaml
cli_cmds:
    - show cdp neighbor
system_table: NDP Table
variable_mapping:
    Local Interface: Interface
    Interface Address: Neighbor Interface IP
    Interface Name: Neighbor Interface
    Device Name: Neighbor Device
- index_variables:
    - Interface
    - Neighbor Interface
```

#### 1.2 Input for MAC Table
```yaml
cli_cmds:
  - show mac table
system_table: MAC Table
variable_mapping:
  Port Name: Interface
  Mac Address: Neighbor Interface MAC
- index_variables:
  - Neighbor Interface MAC
  - Interface
```

### 2. Certification Logic

#### 2.1 Build Common Table and Digital Twin Table

![BuildDigitalTwin](https://github.com/PlatformCertification/Certification-IEv10.0/blob/main/Platform%20Certification%20Guidance/images/L3%20Neighbor%20-%20Build%20Degitial%20Twin.png)

#### 2.2 Diagnosis Checking Logic

![CheckingLogic](https://github.com/PlatformCertification/Certification-IEv10.0/blob/main/Platform%20Certification%20Guidance/images/Certification-Diagnosis%20Logic%20Checking.png)

### 3. Important
1. OSPF neighbors across devices are not considered
2. If the neighbor device and neighbor interface cannot be found in the digital twin table, then it is not considered