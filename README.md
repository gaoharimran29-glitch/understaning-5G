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

## 1. Overview of RRC and NAS

### RRC (Radio Resource Control)
The RRC protocol operates between the **UE (User Equipment)** and **gNodeB** (5G base station). It is responsible for:
- **System Information Broadcast:** Sharing network parameters needed by UE.
- **Paging:** Alerting devices when data arrives.
- **Connection Management:** Establishing and releasing RRC connections.
- **Mobility Functions:** Handling handovers and transitions between cells.
- **Measurement Configuration and Reporting:** Monitoring signal strength and quality.
- **Device Capability Handling:** Managing UE’s features and configurations.

### NAS (Non-Access Stratum)
The NAS protocol functions between **UE** and the **AMF (Access and Mobility Management Function)** in the core network. Key responsibilities include:
- **Authentication and Security:** Verifying identity and securing communication.
- **Idle-Mode Procedures:** Managing UE in idle state.
- **IP Address Assignment:** Allocating network resources.
- **Registration Management:** Updating UE's presence in the network.

---

## 2. RRC and NAS States

### IDLE State
- UE is powered on but not registered.
- No RRC context is established.
- Requires attach procedure and RRC connection to move to connected mode.

### CONNECTED State
- UE is registered and has an RRC connection.
- Capable of sending/receiving data.

### INACTIVE State
- Stores configuration and security context.
- Allows faster reconnection without full reconfiguration.
- Supports suspend and resume procedures.

### State Transitions
- **Attach / RRC Connect:** Moves from idle to connected.
- **Detach / RRC Release:** Moves from connected to idle.
- **RRC Suspend / Resume:** Enables temporary disconnection with stored context for fast reestablishment.

---

## 3. Mobility Functions

### Idle and Inactive Mode Mobility
- Controlled by UE.
- Based on **RAN Areas (RAI)** and **Tracking Areas (TAI)**.
- UE performs area updates as it moves.

### Connected Mode Mobility
- Controlled by the network.
- Handover is managed by neighboring cells.
- Based on measurements like **SS Blocks** for signal strength.

---

## 4. Initial Access Procedure

### Purpose
Initial access is the procedure through which a UE synchronizes with the network, detects its identity, and retrieves critical system information.

### Steps

#### 1. Cell Search
- UE scans for synchronization signals to acquire timing and frequency information.
- Detects **Physical Cell ID (PCI)** using:
  - **Primary Synchronization Signal (PSS):** Identifies group ID.
  - **Secondary Synchronization Signal (SSS):** Identifies full cell ID.
  - **PBCH:** Carries system information.

#### 2. Scan for PSS and SSS
- UE searches for PSS across the frequency raster.
- Identifies SSS and derives full cell ID (1008 possible PCI combinations).

#### 3. Decode PBCH for MIB (Master Information Block)
- Contains key parameters like:
  - System bandwidth.
  - Subframe number.
  - Cell barred status.
  - Subcarrier spacing.
  - Parameters to acquire SIB1.

#### 4. Decode SIB1 (System Information Block 1)
- Provides:
  - Cell selection and access info.
  - Other SIB scheduling.

#### 5. Other SIBs
- Includes various information for cell reselection, frequency data, disaster alerts, and timing information:
  - **SIB2:** Reselection across frequencies.
  - **SIB3:** Intra-frequency reselection.
  - **SIB4:** Inter-frequency reselection.
  - **SIB5:** Reselection toward LTE.
  - **SIB6-8:** Emergency notifications.
  - **SIB9:** Timing data (UTC, GPS).

---

## 5. Random Access Procedure

### Purpose
Random access allows a UE to establish communication with the network when triggered by specific events such as:
- Moving from idle to connected.
- Uplink data arrival.
- Synchronization loss.
- Handover procedures.

### Types of Random Access
1. **Contention-Based Random Access (CBRA)**
   - Used when UE randomly selects a preamble from a pool.
   - Possible contention if multiple UEs choose the same preamble.
2. **Contention-Free Random Access (CFRA)**
   - Used during handovers or when the network pre-assigns a unique preamble to the UE.

### CBRA Steps

#### Step 1: Random Access Preamble (PRACH)
- UE sends a random preamble to request network access.
- Uses timing and power adjustments based on SS block measurements.

#### Step 2: Random Access Response (RAR)
- gNodeB acknowledges UE’s preamble.
- Allocates temporary identifiers, timing corrections, and uplink resources.

#### Step 3: Scheduled Transmission / Contention Resolution
- UE sends its unique identity.
- Handles contention scenarios where multiple UEs collide.

#### Step 4: Connection Setup
- Network resolves contention and establishes connection.
- Assigns permanent identifiers (TC-RNTI to C-RNTI).

### CFRA Steps
- Triggered by handover or dedicated network instructions.
- Uses pre-assigned preamble and grants.
- Avoids contention altogether.

### Summary of Random Access
- Supports both contention-based and contention-free modes.
- Ensures efficient access while managing interference and collisions.

---

## 6. Key Concepts Recap

- **RRC** and **NAS** manage control and registration processes.
- **Initial Access** allows a UE to join the network by scanning, decoding signals, and obtaining system info.
- **Random Access** is essential for establishing communication, either through random selection or assigned resources.
- Mobility is handled differently depending on UE state, with faster reconnects in inactive mode.

---
# 5G Core Network – Comprehensive Guide

## 1. Core Network Identifiers

In 5G Core Networks, identifiers are crucial for uniquely recognizing devices, subscriptions, and sessions. They ensure secure communication, seamless mobility, and proper routing of user data.

### *Device Identifier (PEI)*
- *PEI (Permanent Equipment Identifier):* Uniquely identifies each User Equipment (UE).
- Stored in the device and transmitted securely.
- Mainly used for:
  - Device tracking
  - Emergency calls
  - Fraud prevention
- *IMEI / IMEISV:* 
  - *IMEI:* International Mobile Equipment Identity  
  - *IMEISV:* IMEI with Software Version Number
  - Components:
    - TAC (Type Allocation Code)
    - SNR (Serial Number)
    - CD/SD (Check or Spare Digit)
    - SVN (Software Version Number)

### *Subscription Identifier (SUPI & SUCI)*
- *SUPI (Subscription Permanent Identifier):*
  - Based on IMSI (International Mobile Subscriber Identity).
  - Structure:
    - MCC (Mobile Country Code)
    - MNC (Mobile Network Code)
    - MSIN (Mobile Subscriber Identification Number)
  - Represented as username@realm (e.g. 0<IMSI>@wlan.mnc<MNC>.mcc<MCC>.3gppnetwork.org).
- *SUCI (Subscription Concealed Identifier):*
  - Protects the SUPI against IMSI catching attacks.
  - Ensures subscriber privacy through encryption.

### *Temporary Identifier (GUTI)*
- *GUTI (Globally Unique Temporary Identifier):*
  - Combination of GUAMI + 5G-TMSI.
  - *GUAMI (Globally Unique AMF ID):* Includes MCC, MNC, AMF Region ID, AMF Set ID, AMF Pointer.
  - Enables secure re-identification of users without exposing permanent IDs.

---

## 2. Core Service-Based Architecture (SBA)

The 5G Core is built on a *cloud-native service-based architecture (SBA)* for flexibility, scalability, and efficiency.

### *Monolithic vs Service-Based Architecture*
- *Monolithic:*
  - Large, single codebase.
  - Tight coupling between components.
  - Limited scalability and flexibility.
- *SBA (Microservices-based):*
  - Modular, independent *Network Functions (NFs)*.
  - Each NF exposes services to others using standard web APIs.
  - Enables cloud-native deployment and network slicing.

### *Key SBA Characteristics*
- *Network Functions (NF):* Each NF provides one or more services (NF Service 1, 2, … n).
- *Web-Based Interfaces:* Use HTTP/REST with:
  - GET → Fetch data  
  - POST → Create/Send data  
  - PUT → Update/Replace data  
  - DELETE → Remove data  

### *Service Discovery & Registration*
- *NRF (Network Repository Function):*
  - Central registry of available NFs.
  - Supports service registration, discovery, and status tracking.
- *Process Overview:*
  1. *Service Registration:* NF registers with NRF (HTTP PUT).
  2. *Service Discovery:* Other NFs query NRF (HTTP GET).
  3. *Service Request:* NFs request data/services (HTTP POST).
  4. *Responses:* NRF returns acknowledgements or requested data.

This architecture allows dynamic scaling, faster upgrades, and simpler integration with new services.

---

## 3. NF – AMF (Access and Mobility Management Function)

The *AMF* is a critical network function in 5G Core responsible for managing access, mobility, and control plane signaling.

### *Core Responsibilities*
1. *Registration Management*
   - Handles UE registration and deregistration.
   - Establishes UE context in the network.
   - Periodically updates registration state for mobility and capabilities.

2. *Connection Management*
   - Establishes and releases signaling connections (NAS and AS).
   - Two states:
     - *CM-IDLE:* No signaling, UE reachable through paging.
     - *CM-CONNECTED:* Active signaling and data transfer.
   - Uses:
     - RRC signaling (UE ↔ gNB)
     - N2 signaling (gNB ↔ AMF)

3. *Mobility Management*
   - Tracks UE location within the network.
   - Supports seamless handovers between cells.
   - Maintains updated UE context to ensure continuous service.

### *RAN & Core Interaction*
- UE and RAN store security and radio configurations.
- Supports RRC Inactive state for fast resume after suspend.
- Enables efficient signaling and optimized mobility procedures.

---
# 5G Core Network – Complete Reference Guide

## 1. Core Network Identifiers

Identifiers are essential for recognizing devices, subscriptions, and sessions within the 5G Core.

### *Device Identity (PEI)*
- *Permanent Equipment Identifier (PEI)* uniquely identifies the User Equipment (UE).
- Used for:
  - Device tracking
  - Emergency call handling
  - Fraud detection
- *IMEI & IMEISV:*  
  - IMEI = TAC (Type Allocation Code) + SNR (Serial Number) + CD/SD  
  - IMEISV includes Software Version Number (SVN).

### *Subscription Identity (SUPI & SUCI)*
- *SUPI (Subscription Permanent Identifier):*  
  - Usually the IMSI (MCC + MNC + MSIN).  
  - Can also be represented as username@realm (Network Access Identifier).
- *SUCI (Subscription Concealed Identifier):*  
  - Protects SUPI from IMSI-catching attacks using encryption.

### *Temporary Identity (GUTI)*
- *GUTI = GUAMI + 5G-TMSI*  
- *GUAMI* = MCC + MNC + AMF Region ID + AMF Set ID + AMF Pointer  
- Provides privacy by avoiding frequent transmission of SUPI.

---

## 2. Core Service-Based Architecture (SBA)

5G Core is designed on a *cloud-native microservices model* for flexibility and scalability.

### *Monolithic vs SBA*
- *Monolithic Architecture:* tightly coupled network nodes, less flexible.
- *SBA:* loosely coupled *Network Functions (NFs)* communicating over REST APIs, allowing independent scaling and upgrades.

### *Key Components*
- *Network Functions (NFs):* Each NF offers services (NF Service 1, 2, n).
- *Interfaces:*  
  - Use HTTP REST with GET, POST, PUT, DELETE.  
  - Web-based, enabling cloud deployment and orchestration.

### *NRF – Network Repository Function*
- Maintains a registry of available NFs.
- Supports:
  - *Service Registration:* NFs register via HTTP PUT.
  - *Service Discovery:* Query available services via HTTP GET.
  - *Service Request:* Consumption of services via HTTP POST.

This design enables dynamic scaling, network slicing, and rapid feature deployment.

---

## 3. AMF – Access and Mobility Management Function

AMF is the *control-plane brain* for access, mobility, and session handling.

### *Core Functions*
1. *Registration Management*
   - Registers/deregisters UE.
   - Establishes UE context.
   - Periodically updates for mobility & capability changes.

2. *Connection Management*
   - Manages signaling between UE, gNB, and core.
   - Two states:
     - *CM-IDLE:* No signaling, UE reachable via paging.
     - *CM-CONNECTED:* Active control-plane connection.
   - Uses RRC (UE↔gNB) + N2 (gNB↔AMF) signaling.

3. *Mobility Management*
   - Tracks UE location.
   - Supports seamless handovers.
   - Maintains updated context to ensure uninterrupted service.

---

## 4. SMF – Session Management Function

SMF is responsible for *PDU Session lifecycle management* and *user-plane control*.

### *Key Responsibilities*
- Setup, modification, and release of PDU sessions.
- IP address allocation (IPv4, IPv6, dual-stack).
- Selects appropriate:
  - *UPF* (User Plane Function)
  - *PCF* (Policy Control Function)
- Handles charging (online & offline).
- Communicates with other NFs via AMF.

### *PDU Session Properties*
- Session Identifier
- Slice Identifier (S-NSSAI)
- Data Network Name (DNN)
- PDU Session Type (IP, Ethernet, or Unstructured)
- Service & Session Continuity (SSC)
- Security and QoS parameters

### *Session Continuity Modes*
- *SSC Mode 1:* Same IP, no break.
- *SSC Mode 2:* Break-before-make (IP changes).
- *SSC Mode 3:* Make-before-break (seamless transition).

---

## 5. UDM & UDR – Unified Data Management & Repository

These functions provide centralized data management.

### *UDR (Unified Data Repository)*
- Stores:
  - Subscription Data
  - Policy Data
  - Structured Data for Exposure
  - Application Data

### *UDM (Unified Data Management)*
- Front-end logic for UDR.
- Supports:
  - Authentication
  - Registration management
  - Access management
- Acts as the *brain* for subscription handling.

---

## 6. UPF – User Plane Function

UPF is the *anchor point of user data traffic* in 5G Core.

### *Key Functions*
- Interconnects UE with external data networks (Internet, IMS, Enterprise).
- Maintains session continuity during UE mobility.
- Generates charging data records & traffic usage reports.
- Performs:
  - Packet forwarding (PFCP, PDR, FAR)
  - QoS enforcement (QER)
  - Buffering (BAR)
  - Usage reporting (URR)

---

## Summary

| Function | Responsibility |
|---------|----------------|
| *Identifiers* | Secure device, subscription, and session recognition |
| *SBA* | Cloud-native service framework for flexibility and scaling |
| *AMF* | Registration, connection, and mobility management |
| *SMF* | PDU session setup and control-plane user-plane selection |
| *UDM/UDR* | Centralized subscription data storage & access control |
| *UPF* | Data forwarding, QoS, charging, and session anchoring |

---

# 5G Core Network - Policy Control Function (PCF)

## Overview
The *PCF (Policy Control Function)* is responsible for:
- Managing rules and policies for *users, sessions, and data flows*.
- Providing *policy control* to ensure optimal Quality of Service (QoS), charging rules, and session continuity.
- Enforcing both *session-related* and *non-session-related* policies.

---

## Policy Levels
Policies can be applied at multiple granularities:
1. *All Users* – Network-wide policies applicable to every subscriber.
2. *User-specific Services* – Policies tailored for all services of a particular user.
3. *Session/Data Flow Specific* – Granular control over individual sessions or service flows.

---

## Types of Policies
### 1. Non-session Management Related Policies
These policies are independent of an active session and ensure efficient mobility and access management:
- *Access and Mobility Management* – Controls user movement across networks.
- *Service Area Restrictions* – Limits services to defined geographical areas.
- *RAT/Frequency Selection Priority (RFSP)* – Guides device selection of Radio Access Technology and frequency.
- *UE Route Selection Policy (URSP)* – Determines the routing of traffic from the User Equipment.
- *Access Network Discovery and Selection Policy (ANDSP)* – Helps devices discover and select available access networks.
- *Packet Flow Descriptors* – Define characteristics of packet flows for appropriate handling.

### 2. Session Management Related Policies
These apply to ongoing sessions and control how traffic is handled:
- *Gating Control* – Blocks or allows specific IP packets based on service.
- *QoS Control* – Ensures authorized service quality for IP flows.
- *Policy and Charging Control (PCC) Rules* – Governs QoS and charging decisions.
- *Service Data Flow (SDF) Templates* – Define flow structures for service identification.
- *QoS Profiles & QoS Rules* – Provide fine-grained QoS enforcement and prioritization.

---

## PCF in the 5G Core Architecture
The PCF interacts with several key components of the 5G core:
- *AMF (Access and Mobility Management Function)* – Handles connection and mobility management.
- *SMF (Session Management Function)* – Manages session establishment, modification, and release.
- *UPF (User Plane Function)* – Enforces policies for traffic handling.
- *UDM (Unified Data Management)* – Provides subscription and authentication data.
- *AUSF (Authentication Server Function)* – Handles authentication procedures.
- *gNodeB (5G Base Station)* – Connects the User Equipment (UE) to the 5G Core.

---

## Key Concepts
- *QoS Rules & Profiles* – Define and enforce service quality.
- *PCC Rules* – Control both policy enforcement and charging.
- *SDF Templates* – Identify specific service flows for correct handling.
- *Routing & Mobility Policies* – Ensure seamless user experience and optimized resource use.

---
