# 📦 MikroTik VPN Configuration Guide 📌

```plaintext
 ┣ 📂 docs               📄 Detailed documentation in Markdown
 ┣ 📂 scripts            🧩 Exported MikroTik RSC scripts
 ┣ 📂 images             🖼️ GUI screenshots
 ┣ 📜 README.md          📘 Project introduction
 ┣ 📜 LICENSE            ⚖️ Project license
 ┗ 📜 .gitignore         🚫 Exclude sensitive files
```

---

## 📖 Introduction

This guide provides step-by-step instructions for configuring **OpenVPN** and **WireGuard** on a **MikroTik Router** running RouterOS **7.18**. 🚀

---

## ⚙️ Prerequisites

- ✅ MikroTik router with **RouterOS 7.18** or later
- 🧠 Basic knowledge of **networking** and **firewall rules**
- 🖥️ Access to MikroTik **[WinBox](https://mikrotik.com/download)** or **CLI (SSH/Terminal)**

---

## 🛠️ Check Installed Packages

Before setting up VPN services, check if **OpenVPN** or **WireGuard** is installed:

```sh
/system package print
```

🌐 If missing, download RouterOS and extra packages from the [official site](https://mikrotik.com/download). 📥

---

## 🔐 OpenVPN Configuration

### 1️⃣ Enable OpenVPN Server

```sh
/interface ovpn-server set enabled=yes default-profile=default certificate=my-cert require-client-certificate=yes auth=sha1 cipher=aes128,aes256
```

### 2️⃣ Add Firewall Rules for OpenVPN

```sh
/ip firewall filter add chain=input protocol=tcp dst-port=1194 action=accept comment="Allow OpenVPN"
```

### 3️⃣ Create OpenVPN User

```sh
/ppp secret add name=user password=strongpassword service=ovpn
```

### 4️⃣ Apply Configuration and Restart

```sh
/system reboot
```

✅ [OpenVPN](https://openvpn.net/) is now configured!

---

## 🔐 WireGuard Configuration

### 1️⃣ Enable WireGuard

```sh
/interface wireguard add name=wg0
```

### 2️⃣ Generate Private & Public Keys

You can generate keys using tools like:

🔑 [WireGuard Key Generator](https://www.wireguardconfig.com/tools/private-key)

```sh
/interface wireguard peers add interface=wg0 public-key=PEER_PUBLIC_KEY allowed-address=0.0.0.0/0
```

### 3️⃣ Assign IP to WireGuard Interface

```sh
/ip address add address=10.10.10.1/24 interface=wg0
```

### 4️⃣ Configure Firewall Rules for WireGuard

```sh
/ip firewall filter add chain=input protocol=udp dst-port=51820 action=accept comment="Allow WireGuard"
```

### 5️⃣ Apply Configuration and Restart

```sh
/system reboot
```

✅ [WireGuard is now configured!](https://www.wireguard.com/)

---

## 🛡️ Security Considerations

🚨 Important tips:

- 🔐 **Use strong passwords and encryption**
- 🔥 **Limit access to VPN ports via firewall rules**
- 🔄 **Keep RouterOS and firmware updated:**
  🔗 [RouterOS Changelog](https://mikrotik.com/download/changelogs)

---

## 🧪 Tools & Resources

- 📚 [MikroTik Docs](https://help.mikrotik.com/docs/)
- 🧠 [MikroTik Forum](https://forum.mikrotik.com/)
- 🛠️ [OpenVPN Config Generator](https://www.vpnconfigurator.com/openvpn)
- 📄 [WireGuard Quickstart](https://www.wireguard.com/quickstart/)

---

## 🧾 License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details. ⚖️

---

## 📄 WireGuard Docs

🔗 You can find the official quickstart documentation [here](https://www.wireguard.com/quickstart/).

---

## ✉️ Contributing & Feedback

Feel free to fork the repo, suggest improvements, or submit issues. PRs are welcome! 🤝

---

## 📞 Need Help?

If you encounter issues, check MikroTik’s [official documentation](https://help.mikrotik.com/docs/) or visit community forums for support. 🎯

---
