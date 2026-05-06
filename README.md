# Networks
# 🌐 Multi-Site Network with Inter-VLAN Routing — Cisco Packet Tracer

A simulated enterprise network built in **Cisco Packet Tracer**, featuring two switched sites interconnected via a router, with VLAN segmentation, dual-stack (IPv4 + IPv6) addressing, and full inter-VLAN communication.

---

## 📐 Network Topology Overview

```
[Sales VLAN 100]  [Management VLAN 200]
  PC0, PC1, PC2,     PC3, PC4,
  PC5, Printer0      Printer1
        |                |
        +---[ Switch A1 (2960-24TT) ]---+
                         |
                    [ Router0 (2911) ]
                         |
               [ Switch A2 (2960-24TT) ]
                         |
              [IT VLAN 300]
          PC6, PC7, PC8, PC9, Printer2
```

### 📸 Topology Screenshot

![Network Topology](./assets/topology.png)

---

## 🏗️ Devices & Roles

| Device       | Model        | Role                              |
|--------------|--------------|-----------------------------------|
| Switch A1    | Cisco 2960-24TT | Distribution switch — Site 1   |
| Switch A2    | Cisco 2960-24TT | Distribution switch — Site 2   |
| Router0      | Cisco 2911   | Inter-site & inter-VLAN routing   |
| PC0–PC5      | PC-PT        | End hosts — Site 1               |
| PC6–PC9      | PC-PT        | End hosts — Site 2               |
| Printer0–2   | Printer-PT   | Network printers                  |

---

## 🗂️ VLAN Configuration

### Switch A1

| VLAN | Name       | Ports | Devices                        |
|------|------------|-------|--------------------------------|
| 100  | Sales      | 1–5   | PC0, PC1, PC2, PC5, Printer0  |
| 200  | Management | 6–8   | PC3, PC4, Printer1             |

### Switch A2

| VLAN | Name | Ports | Devices                          |
|------|------|-------|----------------------------------|
| 300  | IT   | 1–5   | PC6, PC7, PC8, PC9, Printer2    |

---

## ⚙️ CLI Configurations Applied

### Switch A1 (`hostname A1`)
- Renamed from `Switch0` → `A1`
- Console, enable, and VTY **password configuration with encryption**
- Created **2 VLANs**: Sales (100) and Management (200)
- **IPv4 and IPv6** subnetting and static address attribution
- Default gateway configured for both IPv4 and IPv6
- **Trunk port** configured toward Router0
- **Inter-VLAN communication** enabled via Router-on-a-Stick

### Switch A2 (`hostname A2`)
- Renamed from `Switch0` → `A2`
- Console, enable, and VTY **password configuration with encryption**
- Created **1 VLAN**: IT (300)
- **IPv4 and IPv6** subnetting and static address attribution
- Default gateway configured for both IPv4 and IPv6
- **Trunk port** configured toward Router0
- **Inter-VLAN communication** enabled via Router-on-a-Stick

---

## 🛣️ Routing

- **Router0 (Cisco 2911)** acts as the central hub between both sites and handles inter-VLAN routing using **subinterfaces** (Router-on-a-Stick).
- Both **IPv4** and **IPv6** static routes are configured.
- All VLANs (100, 200, 300) can communicate through the router.

---

## 🔒 Security

- Enable secret and console passwords set on all devices
- `service password-encryption` applied to protect credentials in running config
- VTY lines secured with login and password

---

## 🧰 Tools Used

- **Cisco Packet Tracer** — Network simulation
- **Cisco IOS CLI** — Device configuration

---

## 🚀 How to Open

1. Install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (free with a NetAcad account).
2. Clone or download this repository.
3. Open the `.pkt` file in Packet Tracer.
4. Explore device configurations via the CLI tab on each device.

---

## 📚 Concepts Demonstrated

- VLAN creation and port assignment
- Trunk port configuration (802.1Q)
- Router-on-a-Stick inter-VLAN routing
- Dual-stack IPv4 / IPv6 static addressing
- Default gateway configuration
- Password security and encryption on Cisco IOS

---

## 👤 Author

> Project built as part of a network fundamentals / CCNA study lab.
