# 📡 MikroTik WiFi Configuration

---

Welcome! In this guide, you'll learn how to configure WiFi on your MikroTik step by step. 🛠️🔧

---

## 🔗 1. Accessing MikroTik

1. Open **Winbox** and connect to your router using MAC or IP.

2. Go to the **Wireless** tab. 📶

## 🔐 2. Configuring WiFi Security

1. Navigate to **Wireless > Security Profiles**. 🔒
2. Create a new security profile and select:
   - **Mode:** dynamic keys ✅
   - **Authentication Type:** WPA2-PSK (recommended) 🔑
   - **Pre-Shared Key:** Enter a strong password 🛡️

## 🌍 3. Setting Up the WiFi Network

1. In **Wireless**, select **wlan1** and edit it. ✏️
2. Configure the following parameters:
   - **Mode:** AP Bridge 🏠
   - **Band:** 2.4GHz-B/G/N or 5GHz-A/N/AC depending on your router. 📡
   - **SSID:** Your WiFi network name ✨
   - **Security Profile:** Select the one you created earlier 🔑

## 🔄 4. Adding WiFi to the Bridge

1. Go to **Bridge > Ports**. 🌉
2. Add the **wlan1** interface to the bridge that uses ether1 (internet). 🌍

## ✅ 5. Save and Apply Changes

1. Enable the WiFi interface if it’s disabled. 🚀
2. Restart the router to apply all changes. 🔄

---

You're all set! Your MikroTik now has a working WiFi network with security and internet access. 🌐💡

If you encounter issues, check **IP > DHCP Server** to ensure wlan1 is receiving IP addresses. 🧐

---
