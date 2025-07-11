# 🚀 GaiaNet Node Installation Guide – Qwen2.5-0.5B (Updated Feb 17, 2025)

This guide helps you install and run a GaiaNet node with the Qwen2.5-0.5B-Instruct model on Ubuntu 20.04–24.04.

---

## ✅ Minimum Requirements

- **OS**: Ubuntu 20.04–24.04 LTS
- **CPU**: 4 Cores
- **RAM**: 8GB
- **Storage**: ~10GB free
- **Network**: Stable public connection (no strict firewall)

---

## 🛠 Step-by-step Installation

### 1. Update System

```bash
sudo apt update && sudo apt upgrade -y
sudo reboot
```
2. Create Project Folder
```bash
cd $HOME
mkdir gaia-node-101
```
3. Install GaiaNet Node
```bash
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/install.sh' | bash -s -- --base $HOME/gaia-node-101
source $HOME/.bashrc
```
4. Initialize with Qwen2.5-0.5B-Instruct
```bash
gaianet init --base $HOME/gaia-node-101 --config https://raw.githubusercontent.com/GaiaNet-AI/node-configs/main/qwen2.5-0.5b-instruct/config.json
```

5. (Optional) Change API Port
```bash
gaianet config --base $HOME/gaia-node-101 --port 8102
gaianet init --base $HOME/gaia-node-101
```

6. Kill Conflicting Processes (if needed)
```bash
sudo lsof -t -i:8080 | xargs kill -9
sudo lsof -t -i:8101 | xargs kill -9
```

7. Start the Node

```bash
gaianet start --base $HOME/gaia-node-101
```

🧩 Upgrade Node (when new versions released)

```bash
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/install.sh' | bash -s -- --upgrade --base $HOME/gaia-node-101
```

🌐 Community
Discord: https://discord.gg/gaianet

GitHub: https://github.com/GaiaNet-AI

✅ Connect Your Node to GaiaNet Dashboard
1. Get Your Node Info
```bash
gaianet info --base $HOME/gaia-node-101
```
Copy your:

Node ID

Device ID

2. Open the Dashboard
Go to: https://dashboard.gaianet.ai

Login using your Web3 wallet

Go to the “Nodes” section

3. Register Your Node
Click "Add Node"

Paste your Node ID

Confirm and sign the message with your wallet

✅ Done!
Your node should show as Online if it’s running correctly.
If it shows Offline, check:

Node is running (gaianet start)

Port is not blocked

wasmedge and frpc are alive

No duplicate port or model issue


