# 📦 Obsidian Sync with Syncthing via Docker

This project sets up a self-hosted [Syncthing](https://syncthing.net) server using Docker to synchronize [Obsidian](https://obsidian.md) vaults across devices (MacBook, Android, etc.) with a local copy always available on your home server.

## 🧭 Project Structure

```
.
├── docker-compose.yml
├── config/           # Syncthing config (auto-created at runtime)
└── data/             # Synced Obsidian vaults stored here
```

## 🚀 Quick Start

### 1. Clone the Repo

```bash
git clone https://github.com/Aleksey-Movchanyuk/obsidian-sync-docker
cd obsidian-sync-docker
```

### 2. Start the Syncthing Server

```bash
docker-compose up -d
```

Syncthing will start and be accessible at:  
📡 `http://<your-server-ip>:8384`

> Default ports:
> - Web UI: `8384`
> - Sync TCP/UDP: `22000`
> - Discovery: `21027/udp`

---

## 📱 Connect Your Devices

### MacBook / Desktop

1. Install Syncthing:
   - https://syncthing.net/downloads
2. Add the home server as a remote device using the Device ID.
3. Share your Obsidian vault folder with the server.

### Android

1. Install the Syncthing app:
   - https://play.google.com/store/apps/details?id=com.nutomic.syncthingandroid
2. Add the server's Device ID.
3. Set up a sync folder pointing to your Obsidian vault.
4. In the Obsidian mobile app, choose `Open folder as vault`.

---

## 🔐 Security Notes

- Devices must explicitly trust each other via Device IDs.
- Communication is encrypted end-to-end.
- For external access, consider adding:
  - 🔒 Web UI authentication
  - 🌐 Port forwarding or VPN (for remote sync)

---

## 💾 Backup & Persistence

- Syncthing config is stored in `./config/`
- Vault data is stored in `./data/`
- You can bind individual vault folders instead of using a shared `data/` directory.

---

## 🧠 Tips

- Works great offline: changes sync when back online.
- No cloud dependency, no storage limits.
- Add more devices any time by sharing Device IDs and folders.

---

## 📜 License

MIT License — do what you want, no warranty.

---

## 🙌 Credits

- [Syncthing](https://syncthing.net)
- [Obsidian](https://obsidian.md)