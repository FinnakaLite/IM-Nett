
| NR  | VLAN Name       | Subnett        | Purpose                                                          |
| --- | --------------- | -------------- | ---------------------------------------------------------------- |
| 1   | Management      | 172.16.1.1/24  | Connection between network devices. Backbone infrastructure.     |
| 10  | IM-Static       | 172.20.0.0/20  | Static IM Testnet that students will use for their router setup. |
| 11  | IM-Dynamic      | 172.20.16.0/23 | IM Testnet with DHCP. Also used for wireless network.            |
| 12  | IM-TravelRouter | 172.20.24.0/23 |                                                                  |

**Reserved Subnets:**
172.18.0.0/16 - Address space is used for virtual networks on Proxmox