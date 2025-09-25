# Secure IoT/IT Network Convergence Project

## Objective
This project designed and implemented a secure IoT/IT converged network infrastructure using enterprise-grade security principles. The goal was to create a zero-trust architecture that could securely authenticate diverse devices, segment network traffic, and monitor IoT sensor data while preventing lateral movement between network zones.

### Skills Learned
- **Network Security Architecture:** Designed and implemented segmented network zones using PfSense firewall
- **Certificate-Based Authentication:** Deployed and managed EAP-TLS authentication using FreeRADIUS and OpenLDAP
- **802.1X Network Access Control:** Configured hostapd on Raspberry Pi for secure wireless authentication
- **IoT Security Protocols:** Implemented secure data pipelines for sensor data collection and visualization
- **Hybrid Network Testing:** Bridged virtual and physical infrastructure for real-world testing
- **Troubleshooting & Analysis:** Used Wireshark for packet-level debugging of authentication issues

### Tools Used
- **Firewall & Networking:** PfSense, VLANs, SquidGuard proxy
- **Authentication:** FreeRADIUS, OpenLDAP, EAP-TLS certificates
- **IoT Infrastructure:** Raspberry Pi, Arduino, DHT22 sensor, hostapd
- **Monitoring & Visualization:** TICK stack (Telegraf, InfluxDB, Chronograf)
- **Analysis Tools:** Wireshark, ICMP testing utilities

## Steps

### 1. Network Architecture Design
The foundation was a segmented network with four security zones managed by PfSense firewall: IoT, Users, DMZ, and WAN. This provided isolation and controlled communication paths.
*Ref 1: Network Segmentation Diagram*
![Network Diagram](imgsrc) *PfSense firewall configuration showing the four security zones and inter-zone routing rules.*

### 2. Authentication Infrastructure Setup
Deployed OpenLDAP for directory services and FreeRADIUS for authentication, implementing certificate-based (EAP-TLS) for IoT devices and credential-based for users.
*Ref 2: RADIUS Server Configuration*
![RADIUS Setup](imgsrc) *FreeRADIUS configuration showing EAP-TLS settings and LDAP integration for user authentication.*

### 3. Secure Wireless Access Point
Configured hostapd on Raspberry Pi with 802.1X support to create a secure wireless network requiring device authentication before network access.
*Ref 3: Hostapd 802.1X Configuration*
![AP Config](imgsrc) *Hostapd configuration file showing EAP authentication settings and RADIUS server integration.*

### 4. IoT Device Integration
Connected Raspberry Pi with Arduino and DHT22 sensor to the network, implementing certificate authentication and data collection pipeline.
*Ref 4: IoT Device Authentication*
![IoT Auth](imgsrc) *Certificate installation and configuration on Raspberry Pi for EAP-TLS network authentication.*

### 5. Monitoring & Data Visualization
Deployed TICK stack (Telegraf, InfluxDB, Chronograf) to collect, store, and visualize sensor data with proper JSON transformation for data normalization.
*Ref 5: Sensor Data Dashboard*
![Dashboard](imgsrc) *Chronograf dashboard showing real-time environmental data from DHT22 sensors.*

### 6. Security Validation & Testing
Conducted comprehensive testing including ICMP validation, Wireshark packet analysis, and security control verification to ensure proper segmentation and authentication.
*Ref 6: Network Segmentation Test*
![Testing](imgsrc) *Wireshark capture showing filtered traffic between VLANs demonstrating proper isolation.*

## Challenges & Solutions
**Challenge:** 802.1X handshake failures between hostapd and FreeRADIUS
**Solution:** Used Wireshark to analyze EAPOL packets and RADIUS debug logs to identify misconfigured certificate parameters

**Challenge:** Bridging virtual PfSense firewall with physical access point
**Solution:** Implemented Windows network bridge with careful firewall rule adjustments

**Challenge:** IoT sensor data format incompatibility with InfluxDB
**Solution:** Developed JSON transformation pipeline to normalize data before ingestion

## Outcomes
- ✅ Successful certificate-based authentication for all IoT devices
- ✅ Complete network segmentation preventing lateral movement
- ✅ Functional zero-trust architecture prototype
- ✅ Real-time environmental monitoring dashboard
- ✅ Enterprise-grade security using open-source tools

This project demonstrated that robust IoT/IT security is achievable through proper architecture, authentication mechanisms, and persistent troubleshooting.
