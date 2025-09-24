# Getting Started with ParkEase

Welcome to **ParkEase** — an AI and Cloud-powered parking management system developed by **SLTMobitel Innovation Center – The Embryo**.  
This guide will walk you through the process of setting up **hardware, edge devices, and cloud components**, so you can begin managing your parking facility with **automated entry, real-time monitoring, and smart billing**.

---

## 1. System Requirements

Before installing ParkEase, ensure that the following requirements are met:

- **Stable Power Supply** — uninterrupted power for cameras, sensors, gates, and edge devices.  
- **Internet Connectivity** — reliable 24/7 internet connection for cloud services and live updates.  
- **Controlled Entry/Exit Point** — ideally one designated entrance and exit for vehicles.  
- **Operator Console** — a PC/monitor for administrators to manage the system.  
- **Vehicle Database (Optional)** — list of pre-registered vehicles for access control.


---

## 2. Hardware Setup

To deploy ParkEase at a new location, the following hardware is required:

- Remotely controllable **gate barrier**  
- **Two ANPR cameras** (IMOU Bullet 2E 4MP or equivalent)  
- **Edge Device** (Jetson Nano-based controller)  
- **Ultrasonic Sensor (SR04 waterproof)** for gate safety  
- **Two LED Displays** for entry and exit instructions  
- Power supplies for all components  
- Internet router / LAN connectivity  

![Hardware Setup](images/hardware-setup.png)
<!-- *Figure : Hardware Setup*  -->

### Steps:
1. Mount cameras at the entrance/exit for optimal plate visibility.  
2. Place ultrasonic sensor at the gate to detect vehicles under the barrier.  
3. Connect LED panels at both gates.  
4. Connect edge device to cameras, sensors, and gate relays.  
5. Ensure stable power and network connections.

---

## 3. Edge Device Setup

The **Edge Device** (Jetson Nano) processes ANPR, controls the gate, and communicates with the cloud.

### Initial Configuration:
1. Burn the Jetson Nano OS image to an SD card.  
2. Boot the device and complete the initial setup.  
3. Connect the edge device to the local network.  
4. Install ParkEase edge software package (provided separately).  

![Edge Device Setup](images/edge-device.jpg)  
<!-- *Figure : Edge Device* -->
---

## 4. Camera Configuration

ParkEase relies on **RTSP video feeds** for ANPR.

### Steps to Configure:
1. Connect each camera to the LAN via Ethernet.  
2. Use the **Dahua ConfigTool** (or equivalent) to discover the camera.  
3. Assign a **static IP** to each camera.  
4. Retrieve RTSP URL format: "rtsp://admin:password@ipaddress/cam/realmonitor?channel=1&subtype=00"
5. Update the edge device configuration with the RTSP links.

![Camera Config](images/camera-config.png)
![Camera Config](images/camera-config1.png)  
<!-- *Figure : Example camera configuration tool* -->

---

## 5. Cloud & Console Setup

ParkEase’s **Cloud Console** is where operators manage the system.

### Key Modules:
- **Dashboard** — overview of parking usage  
- **Parking Map** — real-time availability view  
- **Billing** — payments & user account management  
- **Security Logs** — entry/exit history  

To set up: 

1. Deploy ParkEase backend on your server (on-prem or cloud).  
2. Connect edge devices to the backend using provided API keys.  
3. Configure operator accounts in the console.  

<!-- ![Console Dashboard](images/console-dashboard.jpg)  
*Figure 5: ParkEase operator dashboard* -->

---

## 6. First Run

Once hardware and cloud are connected:

1. Drive a vehicle to the gate.  
2. Camera captures the license plate.  
3. Edge device recognizes plate, checks availability/permissions.  
4. LED panel displays instructions (e.g., *"Proceed to Spot A12"*).  
5. Gate opens automatically.  

🎉 You’ve successfully installed ParkEase!

---

## 7. Troubleshooting

- **Gate not opening?** Check relay connections in the edge device.  
- **Camera not recognized?** Confirm IP addresses and RTSP URLs.  
- **No data in console?** Ensure internet connectivity and API configuration.  

See the [Troubleshooting Guide](troubleshooting.md) for details.

---

## Next Steps

👉 Continue with:  
- [**Console Features →**](console/dashboard.md)  
  

