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
