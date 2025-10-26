### Summary of "Wireless and Mobile Networks" — Computer Networking: A Top-Down Approach (9th Edition, 2025)

This comprehensive chapter from Kurose and Ross's *Computer Networking: A Top-Down Approach* covers the principles, technologies, and architectures underpinning modern wireless and mobile networks. It spans foundational radio concepts, wireless access and core networks, mobility management, and specialized wireless systems like Bluetooth, satellite, and IoT. Below is a detailed synthesis organized by key themes and supported by the source content.

---

### 1. Overview and Context

- **Wireless networks dominate Internet connectivity**: As of 2019, there were more mobile-broadband-connected devices than fixed broadband devices worldwide. Approximately 60% of Internet traffic from major websites is destined for mobile devices.
- Wireless connectivity includes cellular (4G/5G), WiFi (used in 80% of broadband homes), Bluetooth, satellite, and IoT networks.
- Wireless networks serve diverse application areas such as wide-area mobile Internet, local-area wireless access, fixed wireless access, satellite communication, cable replacement, and IoT.

---

### 2. Wireless Network Architecture and Elements

- **Basic components of wireless networks**:
  - **Wireless hosts**: Devices like smartphones, laptops, IoT devices; can be mobile or stationary.
  - **Base stations**: Connect wireless hosts to wired infrastructure; examples include 4G/5G cell towers and WiFi access points.
  - **Wireless links**: Connect devices to base stations and can also serve as backbone links; multiple access protocols (random access, FDMA, TDMA, CDMA, polling) coordinate link access.
  - **Radios in devices**: Modern devices have multiple radios to support cellular, WiFi, Bluetooth, GPS, satellite, NFC, etc. (e.g., iPhone 16 has ~11 radios).

- **Ad hoc networks**: Wireless networks without fixed infrastructure, where devices organize themselves, e.g., Bluetooth piconets.

---

### 3. Radio and Physical Layer Fundamentals

- **Electromagnetic waves**: Wireless communication relies on transmitting and receiving electromagnetic (EM) waves characterized by wavelength, frequency, amplitude, and phase.
- **Signal properties**:
  - **Power**: Measured in watts or decibels (dBm); typical mobile device max transmit power ~24 dBm (250 mW).
  - **Bandwidth**: Frequency range used by a signal; wider bandwidth allows higher data rates.
  - **Signal-to-noise ratio (SNR)**: Ratio of signal power to noise power; key measure of channel quality.
  - **Channel capacity**: Shannon’s capacity formula relates bandwidth, SNR, and maximum data rate.

- **Wireless link characteristics**:
  - **Path loss**: Signal attenuation increases with distance and frequency; urban and indoor environments have higher path loss exponents.
  - **Hidden terminal problem**: Due to signal fading and path loss, some nodes cannot detect others, causing collisions.
  - **Multipath propagation**: Signals reflect off objects, causing multiple delayed copies to arrive at the receiver, affecting signal quality.
  - **Coherence time**: Time duration over which the channel’s properties remain stable; inversely related to frequency and receiver velocity.

- **Antennas and MIMO**:
  - Multiple antennas at transmitter and receiver (MIMO) increase reliability (spatial diversity) and data rate (spatial multiplexing).
  - Multi-user MIMO enables simultaneous transmissions to multiple users using directional beamforming.

---

### 4. Radio Spectrum and Frequency Bands

- Spectrum is a national resource regulated by government, divided into:
  - **Licensed bands**: Exclusive use by operators, often allocated via auctions.
  - **Shared spectrum**: Dynamically shared with priority to incumbents.
  - **Unlicensed spectrum**: Open for anyone under power and protocol rules (e.g., 2.4 GHz and 5 GHz WiFi bands).

- **WiFi spectrum bands**:
  - 2.4 GHz: 11-14 channels depending on country; supports 802.11b/g/n/ax.
  - 5 GHz: Over 150 channels; 802.11a/h/n/ac/ax.
  - 6 GHz: Recently added; supports 802.11ax/be with over 250 channels.

- **5G spectrum bands**:
  - **Low-band (<1 GHz)**: Long range, lower speeds.
  - **Mid-band (1–6 GHz)**: Balance of range (~5 miles) and speed (100–900 Mbps).
  - **High-band/mmWave (25–66 GHz)**: Very high speeds (up to 3 Gbps), short range, line-of-sight required.

---

### 5. Physical Layer Coding and Modulation

- **Coding**: Adds error detection and correction bits to improve reliability.
- **Modulation**: Converts bits into analog signals by varying amplitude, frequency, or phase of carrier waves.
- Common schemes:
  - ASK (Amplitude Shift Keying)
  - PSK (Phase Shift Keying) and QPSK (Quadrature PSK) – QPSK doubles data rate over BPSK by encoding 2 bits per symbol.
  - QAM (Quadrature Amplitude Modulation) combines amplitude and phase variations to encode multiple bits per symbol (e.g., 16-QAM, 64-QAM).
- Adaptive modulation adjusts modulation schemes dynamically based on channel conditions (SNR) to optimize throughput and reliability.

---

### 6. Wireless Access Networks: MAC Protocols and Channel Sharing

- **Multiple Access Protocols**:
  - **FDM/FDMA**: Frequency division multiple access.
  - **TDMA**: Time division multiple access.
  - **CDMA**: Code division multiple access.
  - **Random access**: Aloha, Slotted Aloha.
  - **CSMA/CA**: Carrier Sense Multiple Access with Collision Avoidance, used in WiFi.

- **WiFi MAC Layer** employs CSMA/CA with mechanisms like:
  - **DIFS and SIFS**: Inter-frame spaces for managing transmissions and acknowledgments.
  - **Random backoff**: Randomized wait times to reduce collisions after busy channel detection or failed transmissions.
  - **RTS/CTS (Request to Send / Clear to Send)**: Small reservation packets to mitigate hidden terminal problems.
  - **Multiuser RTS** extends RTS/CTS for OFDMA transmissions in WiFi 6/7, enabling simultaneous communication with multiple devices.

- **OFDMA (Orthogonal Frequency Division Multiple Access)**:
  - Divides channel into subcarriers which are orthogonal and partially overlapping.
  - Resource Blocks (RBs) bundle symbols in time and frequency; smallest scheduling unit.
  - Used in 4G LTE and 5G NR, with 5G supporting wider bandwidths and flexible subcarrier spacing.

---

### 7. WiFi Generations and Compatibility

| WiFi Generation | Year | Max Data Rate (Theoretical) | Frequency Bands (GHz) | Bandwidth (MHz) | PHY Technology       |
|-----------------|------|-----------------------------|----------------------|-----------------|---------------------|
| 802.11b         | 1999 | 11 Mbps                     | 2.4                  | 22              | Spread Spectrum      |
| 802.11g         | 2003 | 54 Mbps                     | 2.4                  | 20              | OFDM                |
| 802.11n (WiFi 4)| 2009 | 600 Mbps                    | 2.4, 5               | 20, 40          | OFDM, MIMO          |
| 802.11ac (WiFi 5)| 2013| 6.9 Gbps                    | 5                    | 20, 40, 80, 160 | OFDM, MIMO          |
| 802.11ax (WiFi 6)| 2020| 9.5 Gbps                    | 2.4, 5               | 20, 40, 80, 160 | OFDM, OFDMA, MIMO   |
| 802.11be (WiFi 7)| 2024| 30+ Gbps                    | 2.4, 5, 6            | 20–320          | OFDM, OFDMA, MIMO   |

- WiFi 6/7 APs support both OFDM and OFDMA to maintain compatibility with legacy devices that only support FDMA.

---

### 8. 5G Radio Access Network (RAN) and Core Network

- **5G RAN**:
  - Connects User Equipment (UE) like smartphones to base stations (gNodeB or gNB).
  - Provides link-layer service, analogous to WiFi LAN but controlled by a single operator.
  - Uses OFDMA with resource blocks for scheduling uplink/downlink transmissions.

- **5G Core Network**:
  - All-IP architecture with clear separation between control plane and user plane (Control-User Plane Separation, CUPS).
  - Key functions:
    - **AMF**: Access and Mobility Management Function for connection, reachability, authentication.
    - **SMF**: Session Management Function for managing sessions, IP address allocation, QoS.
    - **UPF**: User Plane Function acts as relay between device and Internet, enforcing policies.
    - Additional components: AUSF (Authentication), UDM (Unified Data Management), PCF (Policy Control), etc.
  - Control and user plane communicate via standardized interfaces (e.g., N1, N2, N3).

- **RAN Protocol Stack** includes layers: RRC, PDCP, RLC, MAC, and PHY, each with specific roles:
  - RRC: Control-plane signaling and configuration.
  - PDCP: Header compression, encryption.
  - RLC: Segmentation and retransmission.
  - MAC: Scheduling and multiplexing.
  - PHY: Modulation and coding.

- **Split RAN** architectures (e.g., O-RAN) separate RAN functionality into Central Unit (CU), Distributed Unit (DU), and Radio Unit (RU), enabling virtualization and software-defined networking (SDN) approaches.

- **Scheduling** at the base station:
  - Assigns Resource Blocks (RBs) to devices every millisecond.
  - Scheduling algorithms vary:
    - **Round Robin**: Fair but channel unaware.
    - **Maximum Throughput (MT)**: Channel aware, maximizes throughput.
    - **Blind Equal Throughput (BET)**: Fair throughput allocation.
    - **Proportional Fairness (PF)**: Balances throughput and fairness.
  - QoS Class Indicator (QCI) guides scheduling priorities for different service types (voice, gaming, video, web browsing).

---

### 9. Mobility Management

- **Types of mobility**:
  - Movement within the same network (e.g., within WLAN or RAN).
  - Movement among multiple networks and providers.
  - Devices may power down or maintain connections while moving.

- **WiFi mobility**:
  - Extended Service Set (ESS) allows roaming among multiple APs with the same SSID.
  - Fast re-authentication and AP suggestions improve handover.

- **5G handover**:
  - Mobile device switches point of attachment from source to target base station.
  - Handover involves signaling between source BS, target BS, AMF, SMF, and UPF.
  - Data path switched and resources reallocated with minimal service disruption.
  - Detailed timeline includes RRC reconfiguration, tunnel endpoint updates, and status transfer.

---

### 10. Specialized Wireless Networks

- **Bluetooth (BT)**:
  - Operates in 2.4 GHz ISM band with frequency hopping across 79 channels (Classic BT) or 40 channels (BLE).
  - Networks called piconets, with a central device controlling up to 7 peripherals.
  - Uses polling for channel access; no direct peripheral-to-peripheral communication.
  - Protocol stack differs significantly from Internet TCP/IP, lacking network and transport layers.
  - L2CAP layer manages logical link channels, reliability, and service discovery.

- **Satellite Networks**:
  - Applications include sensing, broadcast, GPS, Internet connectivity to underserved areas.
  - Two major types:
    - **GEO satellites**: Stationary relative to Earth, high altitude (~35,768 km), high latency (~800 ms RTT).
    - **LEO satellites**: Lower altitude (550–1200 km), mobile relative to Earth, lower latency (~30 ms RTT), require constellations for coverage.
  - Examples include Starlink (~7,239 satellites operational as of April 2025), with plans for tens of thousands more.
  - Satellite networking can be “bent pipe” (single-hop) or multi-hop with inter-satellite links.

- **Internet of Things (IoT)**:
  - Encompasses a vast range of devices monitoring environmental, industrial, health, and infrastructural parameters.
  - Devices vary widely in energy consumption, data rate (100s of bps to ~1 Mbps), and coverage range.
  - Communication technologies include short-range (WiFi, BLE, Zigbee) and cellular IoT (LTE-M, NB-IoT).
  - Energy efficiency is paramount; many devices operate for years on battery or energy harvesting.

---

### 11. Energy Management in Wireless Devices

- Wireless radios consume significant power when active (1000–3500 mW), but can reduce consumption by entering sleep modes (<15 mW).
- Sleep/wake cycles are coordinated between devices and base stations/APs to balance energy savings and latency.
- DRX (Discontinuous Reception) cycles in 5G allow devices to sleep and wake periodically for data reception.
- Tradeoffs exist between sleep duration, signaling overhead, and latency impacting higher-layer protocols like TCP.

---

### 12. Summary and Final Notes

- The chapter provides a **top-down view** of wireless and mobile networks, starting from physical radio principles to complex network architectures and protocols.
- It covers **WiFi and 5G** in detail, including their radio access networks, MAC protocols, and scheduling algorithms.
- Mobility, energy management, and specialized wireless systems (Bluetooth, satellite, IoT) are integral components reflecting the diversity and complexity of modern wireless communication.
- For in-depth study, additional resources are available at [https://gaia.cs.umass.edu/wireless_and_mobile_networks](https://gaia.cs.umass.edu/wireless_and_mobile_networks).

---

### Key Tables and Data

| Wireless Link Type           | Distance Range         | Typical Data Rate        | Example Technologies                    |
|-----------------------------|-----------------------|--------------------------|---------------------------------------|
| Indoor                     | 10-30 m               | 2 Mbps - 3.5 Gbps        | Bluetooth, WiFi (802.11ac, ax)        |
| Outdoor Midrange           | 50-200 m              | 600 Mbps - 54 Mbps       | 802.11n, 3.5G                         |
| Outdoor Long Range         | 200 m - 15 km         | Up to 10 Gbps            | 4G LTE, 5G eMBB                      |
| Space (Satellite)          | Hundreds of km        | *Varies*                 | GEO, LEO satellites                   |

| WiFi Generation | Year | Max Rate | Frequency Bands (GHz) | Bandwidth (MHz)          | PHY Technologies          |
|-----------------|------|----------|----------------------|-------------------------|--------------------------|
| 802.11b         | 1999 | 11 Mbps  | 2.4                  | 22                      | Spread Spectrum           |
| 802.11g         | 2003 | 54 Mbps  | 2.4                  | 20                      | OFDM                     |
| 802.11n (WiFi4) | 2009 | 600 Mbps | 2.4, 5               | 20, 40                  | OFDM, MIMO               |
| 802.11ac (WiFi5)| 2013 | 6.9 Gbps | 5                    | 20, 40, 80, 160         | OFDM, MIMO               |
| 802.11ax (WiFi6)| 2020 | 9.5 Gbps | 2.4, 5               | 20, 40, 80, 160         | OFDM, OFDMA, MIMO        |
| 802.11be (WiFi7)| 2024 | 30+ Gbps | 2.4, 5, 6            | 20, 40, 80, 160, 320    | OFDM, OFDMA, MIMO        |

| 5G Spectrum Bands   | Frequency Range          | Characteristics                               |
|---------------------|-------------------------|-----------------------------------------------|
| Low Band            | < 1 GHz                 | Long range (~tens of miles), lower speeds     |
| Mid Band            | 1 - 6 GHz               | Balanced range (~5 miles) and speed (100–900 Mbps) |
| High Band (mmWave)  | 25 - 66 GHz             | Very high speeds (<3 Gbps), short range (<1 mile), LOS required |

| 5G Core Components      | Function                                               |
|------------------------|--------------------------------------------------------|
| AMF                    | Access and Mobility Management, Authentication         |
| SMF                    | Session Management, IP address allocation, QoS         |
| UPF                    | User Plane forwarding, policy enforcement, tunneling   |
| AUSF                   | Authentication Server Function                          |
| UDM                    | User Data Management                                    |
| PCF                    | Policy Control                                          |

| Scheduling Algorithms       | Characteristics                                      |
|-----------------------------|----------------------------------------------------|
| Round Robin                 | Fair by turns, channel unaware                      |
| Maximum Throughput (MT)     | Channel aware, maximizes throughput, unfair         |
| Blind Equal Throughput (BET)| Fair throughput, semi channel aware                 |
| Proportional Fairness (PF) | Balances throughput and fairness                     |

---

### Key Insights

- **Wireless networking is inherently complex**, involving deep interaction between physical layer radio phenomena, MAC protocols, and network-layer mobility and core functions.
- **MIMO and OFDMA technologies are critical enablers** of modern high-speed, reliable wireless communication.
- **Mobility management in 5G is a sophisticated process**, requiring coordinated signaling across multiple network elements to ensure seamless handovers.
- **Energy efficiency remains a fundamental challenge** in wireless device design, especially for battery-powered and IoT devices.
- **WiFi and 5G continue to evolve** with backward compatibility considerations and increasingly flexible spectrum and resource management.
- Emerging wireless systems like **LEO satellite constellations and IoT networks** broaden the scope and coverage of wireless communications globally.

---

This summary synthesizes the chapter’s extensive content into a structured, detailed overview suitable for professionals and students seeking a thorough understanding of wireless and mobile networks as presented in the 9th edition of Kurose and Ross's textbook.
