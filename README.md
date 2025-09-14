# 5G System Standardization  

## 1. Introduction  
- Global rules so telecom systems work the same everywhere.  
- Ensures *compatibility, safety, and innovation*.  

## 2. Why Standardization?  
- Devices work globally.  
- Avoid fragmentation.  
- Allows faster technology adoption.  

## 3. Global Landscape  
- 5G is an international effort to connect people and industries.  
- Involves governments, operators, and manufacturers.  

## 4. 3GPP – Main Standards Body  
- *3GPP (3rd Generation Partnership Project)* develops standards for 3G, 4G, 5G.  
- Members: ETSI, ATIS, ARIB etc.  
- Website: [3gpp.org](https://www.3gpp.org)  

### Releases Timeline  
- *Release 15 (2018)*: Initial 5G specs.  
- *Release 16 (2020)*: Industrial IoT, URLLC.  
- *Release 17 (2022)*: Satellite support, more IoT.  
- *Release 18+*: 5G Advanced.  

## 5. 5G Requirements  
- High Data Rate (up to 20 Gbps).  
- Ultra Low Latency (~1 ms).  
- Massive Device Connectivity (IoT).  
- High Reliability and Energy Efficiency.  

## 6. Network Architecture (Basic)  
- *NR RAN (New Radio)* connects devices to network.  
- *Core Network* handles data processing and security.  
- *Call Flows* define how voice/data travel.  

## 7. Summary  
- 3GPP sets specifications.  
- Architecture includes NR RAN + Core Network.

# 5G System Use Cases  

5G targets *three major use cases*:

## 1. Enhanced Mobile Broadband (eMBB)  
- Peak data: 20 Gbps DL / 10 Gbps UL.  
- User experience: 100 Mbps DL / 50 Mbps UL.  
- Mobility up to 500 km/h.  
- Low cost per bit and energy efficiency.  
- Applications: 4K/8K streaming, AR/VR, cloud gaming.  

## 2. Massive Machine Type Communications (mMTC)  
- 1 million devices per km².  
- Battery life 10–15 years.  
- Low data rate (1–100 kbps).  
- Enhanced coverage.  
- Applications: Smart cities, IoT sensors, agriculture.  

## 3. Ultra Reliable Low Latency Communications (URLLC)  
- User plane latency ~1 ms.  
- Control plane latency ~10 ms.  
- Reliability 99.999%.  
- Zero mobility interruption.  
- Applications: Self-driving cars, remote surgery, industrial control.  

## Summary Table  

| Use Case | Focus | Data Rate | Latency | Devices Density |
|----------|-------|-----------|---------|----------------|
| eMBB | High Speed Internet | 20 Gbps peak | ~10 ms | Normal Users |
| mMTC | IoT Devices | 1–100 kbps | Not critical | 1 million/km² |
| URLLC | Mission-Critical Apps | Moderate | 1 ms | Moderate |

## Key Idea  
- *eMBB = Speed, **mMTC = Scale, **URLLC = Reliability*.  
- Network slicing allows different slices for each use case.

# The 5G System  

## 1. Overview  
- Two main parts: *5G RAN* (Radio Access Network) and *5G Core Network*.  
- Flow: UE → gNodeB → 5G Core → Internet/Data Network.  

## 2. Key Components  

| Component | Full Form | Function |
|-----------|-----------|-----------|
| UE | User Equipment | Phone or IoT device |
| gNodeB | Next-Gen Base Station | Connects UE to network |
| AMF | Access & Mobility Mgmt Function | Registration & mobility |
| SMF | Session Mgmt Function | Creates/manages sessions |
| UPF | User Plane Function | Forwards user data |
| AUSF | Authentication Server Function | Security & authentication |
| UDM | Unified Data Management | Stores subscription data |
| PCF | Policy Control Function | QoS, charging & policies |
| Data Network | Internet/Cloud | Final destination of data |

## 3. Control Plane vs User Plane  
- *Control Plane*: Signalling (registration, handover, policy).  
- *User Plane*: Actual data (internet, video).  
- Separation = independent scaling and flexibility.  

## 4. Interfaces  
- *N1*: UE ↔ AMF (control).  
- *N2*: gNodeB ↔ AMF (control).  
- *N3*: gNodeB ↔ UPF (user data).  
- *N4*: SMF ↔ UPF (session info).  

## 5. Service-Based Architecture  
- Network functions as microservices.  
- Functions communicate via APIs.  
- Enables cloud-native deployment and flexible scaling.  

## 6. Features  
- Flexible deployment (on-premise or cloud).  
- Network slicing for different use cases.  
- Independent scaling for control & user plane.  

## 7. Analogy  
- Airport analogy:  
  - gNodeB = Entry Gate,  
  - AMF = Immigration,  
  - AUSF = Security Check,  
  - SMF = Flight Desk,  
  - UPF = Runway,  
  - UDM = Passenger Database,  
  - PCF = Rules/Policies.

# 5G System Deployment Options  

## 1. Introduction  
- 5G can be deployed in multiple ways depending on legacy networks and coverage.  
- Options define how 4G and 5G networks work together during transition.  

## 2. Key Terms  
- *eNodeB (Evolved Node B)* = 4G tower.  
- *gNodeB (Next-gen Node B)* = 5G tower.  
- *EPC (Evolved Packet Core)* = 4G core network.  
- *5G Core* = New core network for 5G.  

## 3. Deployment Options Overview  

| Option | Description | Core Used | Notes |
|--------|-------------|-----------|-------|
| *Option 1* | Legacy 4G only | EPC | No interworking |
| *Option 2* | Standalone 5G | 5G Core | Pure 5G |
| *Option 3/3a/3x* | EN-DC (E-UTRAN New Radio Dual Connectivity) | EPC | 4G core with 5G NR for coverage |
| *Option 4/4a* | NE-DC (Next-Gen Dual Connectivity) | 5G Core | 5G coverage primary |
| *Option 5* | eLTE with 5G Core | 5G Core | Enhanced LTE |
| *Option 6* | eLTE with 4G Core | EPC | Not widely supported |
| *Option 7* | NG-EN DC | 5G Core | eNodeB + gNodeB dual connectivity |

## 4. NSA vs SA  
- *Non-Standalone (NSA)*: Uses existing 4G core (EPC) but adds 5G radio for speed.  
- *Standalone (SA)*: Uses full 5G Core and 5G Radio — full 5G benefits.  

## 5. Summary  
- Options allow a gradual migration from 4G to 5G.  
- NSA (Option 3) common initially, SA (Option 2) is future-proof.
---

# RAN Protocol Stack

The *Radio Access Network (RAN) Protocol Stack* is the "ladder of communication" between your phone (UE - User Equipment) and the 5G tower (gNodeB).

It has two main parts:
- *User Plane (for actual data like video, calls, internet)*
- *Control Plane (for instructions, authentication, management)*

---

### 1. Layers in the User Plane

1. *Physical Layer (PHY)*  
   - Think of this as the *real radio signals* flying in the air.  
   - It handles modulation, coding, antennas.  
   - Without PHY, nothing gets transmitted.

2. *MAC (Medium Access Control)*  
   - Works like a *traffic police*.  
   - Decides who can talk when, does *scheduling, multiplexing/demultiplexing, and **retransmission*.

3. *RLC (Radio Link Control)*  
   - Splits big data into smaller chunks (segmentation).  
   - Ensures no data is lost by using *ARQ (Automatic Repeat reQuest)*.  
   - Like cutting a big pizza into slices and reordering them properly.

4. *PDCP (Packet Data Convergence Protocol)*  
   - Does *header compression* (makes packets smaller).  
   - Provides *security (ciphering & integrity protection)*.  
   - Removes duplicates.  
   - Think of it as a *data sanitizer and protector*.

5. *SDAP (Service Data Adaptation Protocol)*  
   - Handles *Quality of Service (QoS)*.  
   - Makes sure voice calls, video, browsing — all get proper priority.  
   - Like giving *VIP lane for ambulance (video call)* vs *normal lane for cars (browsing)*.

---

### 2. Layers in the Control Plane

1. *RRC (Radio Resource Control)*  
   - Manages *radio bearers, system info, and measurements*.  
   - Like the *manager* who sets rules and resources.

2. *NAS (Non-Access Stratum)*  
   - Deals with *authentication, security, idle mode procedures*.  
   - Works with *AMF (Access & Mobility Management Function)* in the core network.  
   - Example: When your SIM card verifies identity with the network.

---

*Summary of RAN Stack:*  
- *PHY → MAC → RLC → PDCP → SDAP* (User plane for actual data)  
- *PHY → MAC → RLC → PDCP → RRC → NAS* (Control plane for management)  

---

# SDAP (Service Data Adaptation Protocol)

SDAP is a *new protocol in 5G* (not in 4G).  
It is responsible for *QoS (Quality of Service)* — making sure every app/service gets what it needs.

---

### 1. Why SDAP?

Different applications need different performance:
- *Voice Call* → low data rate but steady.
- *Broadband/YouTube* → high data rate but can tolerate delay.
- *Massive IoT (MTC)* → small data, many devices.
- *URLLC (Ultra Reliable Low Latency Communication)* → super fast and reliable (like self-driving cars).

SDAP ensures all these work together smoothly.

---

### 2. QoS Flows

- *QoS Flow = A dedicated lane for data traffic.*  
- Each flow has a *QoS Identifier (QFI)*.  
- Example: WhatsApp video call vs YouTube streaming → both get their own flows.

*Types of QoS Flows:*
1. *GBR (Guaranteed Bit Rate):* Reserved bandwidth (e.g., video call).  
2. *Non-GBR:* Best effort traffic (e.g., browsing).  
3. *Delay Critical GBR:* For *real-time* sensitive apps (e.g., VR, gaming).  

---

### 3. Parameters of QoS Flow
- *5QI (QoS Identifier)*
- *GBR parameters:* GFBR (guaranteed), MFBR (max), packet loss rate, delay type.  
- *Non-GBR:* AMBR (Aggregate Maximum Bit Rate).  

---

### 4. Multiplexing

- SDAP can put *multiple QoS flows* inside a *single PDU session*.  
- Like multiple apps sharing one internet tunnel, but each app still gets priority.

Example:
- Browsing (best effort)  
- WhatsApp video (high priority)  
- Zoom video (medium priority)  
- YouTube (non-GBR)  

All flow together but *SDAP ensures correct priority*.

---

### 5. Uplink QoS Mapping
- *Reflective Mapping:* UE learns from downlink QoS.  
- *Explicit Mapping:* Direct mapping by network.  

---

*Summary of SDAP:*  
- SDAP = *Traffic manager* of 5G.  
- Ensures every service gets proper speed, reliability, and priority.  

---

# PDCP (Packet Data Convergence Protocol)

PDCP works above RLC and below RRC/SDAP.  
It is responsible for *security, compression, and ordering*.

---

### 1. Functions of PDCP
1. *Header Compression*  
   - IP headers are big (IPv4 = 40 bytes, IPv6 = 60 bytes).  
   - PDCP compresses them using *ROHC (Robust Header Compression)*.  
   - Saves bandwidth.

2. *Ciphering & Integrity Protection*  
   - Encrypts data so no one can *eavesdrop*.  
   - Adds integrity check so no one can *modify packets*.  
   - Uses keys: Krrc,enc and Krrc,int.

3. *Routing & Duplication of Split Bearers*  
   - In dual connectivity (using 2 cells), PDCP can *duplicate packets* for reliability.  
   - Like sending the same parcel by 2 routes — at least one reaches.

4. *In-sequence Delivery*  
   - Ensures packets arrive in the right order.  
   - Example: Video frames 1-2-3-4 → not 1-3-4-2.  
   - PDCP reorders and removes duplicates.

---

### 2. PDCP Data Flow
- *Sender:* Adds header → compress → cipher → integrity → route/duplicate.  
- *Receiver:* Remove header → decompress → decipher → reorder → deliver.

---

*Summary of PDCP:*  
- PDCP = *Security guard + Data optimizer + Order keeper*.  
- Without PDCP, 5G would be insecure, heavy, and unreliable.

---
# 5G Protocol Layers (RLC + PHY + PHY2)

## 1. RLC (Radio Link Control)

The *RLC layer* sits between *MAC* and *PDCP*.  
It ensures *data segmentation, retransmissions, and reliability*.

---

### 2. Functions of RLC
1. *Segmentation*  
   - Breaks large SDUs (Service Data Units) into smaller PDUs (Protocol Data Units).  
   - Example: Cutting a movie file into smaller packets so they can travel easily.

2. *ARQ (Automatic Repeat reQuest)*  
   - If a packet is lost, RLC retransmits it.  
   - Ensures reliability.

---

### 3. RLC Modes
1. *Transparent Mode (TM)*  
   - No retransmission, no segmentation.  
   - Like sending raw data directly (used for system broadcast info).

2. *Unacknowledged Mode (UM)*  
   - Does segmentation but *no retransmission*.  
   - Example: Video streaming — if one frame is lost, no need to resend.

3. *Acknowledged Mode (AM)*  
   - Retransmissions, segmentation, duplicate removal.  
   - Example: File transfer — accuracy is critical.

---

### 4. Retransmission Process
- Works with *Tx (transmitter) window* and *Rx (receiver) window*.  
- Missing packets are identified via *status reports*.  
- Retransmits until receiver confirms successful delivery.  

*Summary of RLC:*  
- *Segmentation = Slicing data*  
- *ARQ = Reliability via retransmission*  
- *Modes = Flexible handling (TM, UM, AM)*  

---

# Medium Access Control (MAC) Layer

### 1. *Core Functions of MAC*
- *Logical-channel multiplexing:* Efficiently combines multiple logical channels for transmission.
- *Hybrid-ARQ retransmissions:* Implements error correction via retransmissions to ensure data integrity.
- *Scheduling:* Allocates resources to users based on network demands.
- *Multiplexing/Demultiplexing for Carrier Aggregation (CA):* Supports simultaneous transmission across multiple frequency bands.

### 2. *Multiplexing Logical Channels*
- *Types of Logical Channels:*
  - *Broadcast Control Channel (BCCH):* Broadcast system information.
  - *Paging Control Channel (PCCH):* Handle paging messages.
  - *Common Control Channel (CCCH):* For connection establishment.
  - *Dedicated Control Channel (DCCH):* Used for control signaling.
  - *Dedicated Traffic Channel (DTCH):* Transfers user data.

- *Transport Channels:*
  - *Broadcast Channel (BCH):* Transmits system information.
  - *Paging Channel (PCH):* Used for paging.
  - *Downlink Shared Channel (DL-SCH):* For downlink data.
  - *Uplink Shared Channel (UL-SCH):* For uplink data.
  - *Random Access Channel (RACH):* For initial access.

### 3. *Control Elements (MAC CE)*
- Handle critical tasks such as:
  - *Scheduling*
  - *Random Access Procedures*
  - *Timing Advance Adjustments*

### 4. *Carrier Aggregation (CA)*
- Enhances throughput by combining multiple frequency carriers for data transmission.

### 5. *Hybrid Automatic Repeat Request (HARQ)*
- *Stop-and-Wait Protocol:* Retransmission mechanism where only one packet is outstanding.
- *Asynchronous HARQ:* NR uses an asynchronous protocol offering greater flexibility.
- *HARQ with Code Block Groups (CBG):* Data is divided into smaller blocks allowing efficient retransmission.

---

# Scheduler in 5G NR

### 1. *What is a Scheduler?*
A scheduler manages how resources are distributed among users. It dynamically allocates bandwidth, power, and time slots based on:
- Channel conditions
- Buffer status
- Priority of data flows

### 2. *Inputs for Scheduling*
- *Devices:* The number and type of users.
- *Resource Blocks:* Available frequency resources.
- *Transport Formats:* Includes Transport Block Size (TBS), modulation schemes, and antenna configurations.

### 3. *Downlink Scheduling*
- *Measurements:* Based on CSI-RS and SSB signals.
- *Channel Conditions:* Includes metrics like RSRP, CQI, PMI, and RI.
- *Types of Scheduling:* Periodic, semi-persistent, and aperiodic.

- *Techniques:*
  - *Channel-dependent scheduling:* Prioritizes users with better channel conditions.
  - *Bandwidth Parts:* Allows receivers to adapt their bandwidth.
  - *Preemption:* Enables reallocating resources in case of higher priority data.

- *Scheduling Types:*
  - *Dynamic Scheduling:* Resources allocated based on real-time demands.
  - *Configured Scheduling:* Predefined allocations.
  - *Semi-Persistent Scheduling (SPS):* Optimizes periodic transmissions.

### 4. *Uplink Scheduling*
- *Measurements:* Based on Sounding Reference Signals (SRS).
- *Resource Allocation:* Considers both power and bandwidth limitations.
- *Scheduling Types:*
  - *Type 1 Configured Scheduling*
  - *Type 2 Configured Scheduling*

- *Priority Handling:* Ensures important data is transmitted with minimal delay.

---

##  Summary

The *MAC Layer* and *Scheduler* form the backbone of data transmission in 5G networks. Through logical channel multiplexing, HARQ retransmissions, and efficient scheduling, they ensure optimal use of available resources while adapting to real-time network conditions. This results in higher throughput, reliability, and better user experiences.

---

# PHY (Physical Layer – Part 1)

The *PHY layer* is the *foundation of 5G communication*.  
It deals with real *radio signals, modulation, antennas, and frequency resources*.

---

### 1. Physical Channels
- *PBCH:* Broadcasts basic cell info.  
- *PDSCH:* Main data downlink.  
- *PDCCH:* Control messages downlink.  
- *PUSCH:* Main data uplink.  
- *PUCCH:* Control uplink.  
- *PRACH:* Random access channel (when UE wants to connect).

---

### 2. Processing Steps in PHY
1. *CRC (Cyclic Redundancy Check)*  
   - Error detection at transport block level.  

2. *LDPC Coding (Low-Density Parity Check)*  
   - Adds redundant bits for reliability.  
   - Two base graphs:  
     - BG1 (big, reliable, high data)  
     - BG2 (smaller, for low data).  

3. *Code Block Segmentation*  
   - Large data → smaller blocks.  

4. *Rate Matching*  
   - Extracts exact bits needed for transmission.  

5. *Scrambling*  
   - Randomizes data so interference reduces.  

6. *Modulation*  
   - Converts bits into waveforms: *QPSK, 16QAM, 64QAM, 256QAM*.  

7. *Layer & Antenna Mapping*  
   - Maps data streams to antennas (MIMO).  

8. *Resource Mapping*  
   - Assigns time-frequency resources.  

9. *OFDM (Orthogonal Frequency Division Multiplexing)*  
   - Converts digital data → analog signals for transmission.  

*Summary of PHY (Part 1):*  
- PHY = *Ground floor of 5G*.  
- Handles *error detection, coding, modulation, antenna mapping, OFDM*.  

---

# PHY2 (Physical Layer – Part 2: Advanced Structure)

### 1. Modulation & OFDM
- OFDM splits one *wideband signal into many narrowband signals*.  
- Downlink = OFDM.  
- Uplink = OFDM + *DFT-precoded OFDM (SC-FDM)* (better for power saving).  
- Problem: *High PAPR (Peak to Average Power Ratio)* in OFDM.

---

### 2. Multiple Access
- *OFDMA (Orthogonal Frequency Division Multiple Access)* → used in downlink/uplink.  
- *DFT-Precoded OFDMA* → used for uplink (better power efficiency).  
- Allows *multiple users* to share spectrum effectively.

---

### 3. Flexible Numerology
- Different *subcarrier spacings (SCS)* allow different use cases.  

| Subcarrier Spacing (kHz) | Useful Symbol Time (µs) | CP (µs) |
|--------------------------|--------------------------|---------|
| 15  | 66.7  | 4.7 |
| 30  | 33.3  | 2.3 |
| 60  | 16.7  | 1.2 |
| 120 | 8.33  | 0.59 |
| 240 | 4.17  | 0.29 |

- *Small SCS → Efficient CP, but sensitive to frequency errors.*  
- *Large SCS → Less sensitive to errors, but inefficient CP.*  

---

### 4. Time Domain Structure
- *NR Frame = 10ms*  
- Frames → Subframes → Slots → Symbols.  
- Flexible design supports *wide range of frequencies and bandwidths*.

---

### 5. Resource Blocks
- *Resource Element (RE):* Smallest unit (1 subcarrier × 1 symbol).  
- *Resource Block (RB):* Group of REs.  
- *SLIV (Start and Length Indicator Value):* Identifies scheduling.

---

### 6. Mini Slots
- Special slots (2, 4, or 7 symbols).  
- Can start anytime (not just at slot boundaries).  
- Useful for *low-latency transmission*.

---

*Summary of PHY2:*  
- PHY2 adds *OFDM, numerology, time frames, resource blocks, and mini slots*.  
- Makes 5G *flexible, scalable, and efficient* for all use cases (IoT → broadband).

---
