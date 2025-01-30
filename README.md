### 1️⃣ Privasea Privanetix Node
**Description:** A step-by-step guide for setting up and running a Privasea Privanetix Node.
- **Tech Stack:** Docker, Linux, Blockchain
- **Features:**
  - Secure keystore generation
  - Automated node deployment
  - Staking integration

#### 🔤 Install Docker (Skip if already installed)
```bash
source <(wget -O - https://raw.githubusercontent.com/zunxbt/installation/main/docker.sh)
sudo groupadd docker && sudo usermod -aG docker $(whoami) && newgrp docker
```

#### 🔤 Pull the Docker Image
```bash
docker pull privasea/acceleration-node-beta:latest
```

#### 🔤 Create Directory
```bash
mkdir -p ~/privasea/config && cd ~/privasea
```

#### 🔤 Retrieve Keystore and Node Address (Save this securely)
```bash
docker run --rm -it -v "$HOME/privasea/config:/app/config" privasea/acceleration-node-beta:latest ./node-calc new_keystore
```

#### 🔤 Move Keystore
```bash
mv $HOME/privasea/config/UTC--* $HOME/privasea/config/wallet_keystore
```

#### 🔤 Set Up on the Web
1. Go to [Privanetix Node Setup](https://deepsea-beta.privasea.ai/privanetixNode)
2. Connect your wallet
3. Claim Faucet (ARB Sepolia & Deepsea)
4. Click "Privanetix Node - Setup Now"
5. Enter Node Name
6. Set up Commission
7. Enter Node Address
8. Click "Create"

#### 🔤 Run the Privasea Node
```bash
KEYSTORE_PASSWORD=ENTER_YOUR_KEYSTORE_PASSWORD && docker run -d --name privanetix-node -v "$HOME/privasea/config:/app/config" -e KEYSTORE_PASSWORD=$KEYSTORE_PASSWORD privasea/acceleration-node-beta:latest
```
*Replace `ENTER_YOUR_KEYSTORE_PASSWORD` with your actual password.*

#### 🔤 Check Node Status on Web or you can check docker healt
```bash
docker logs -f (code after your run node)
```

🔗 [Repository Link](https://github.com/yourgithub/privasea-node)

## 🚀 How to Contribute
Feel free to fork this repository, suggest improvements, or open issues for discussions. Collaboration is always welcome!

## 📧 Contact
- GitHub: [@Bagasdwipa](https://github.com/Bagasdwipa)
- Twitter: [@bagasdwiprtama](https://twitter.com/bagasdwiprtama)

---

### ⭐ Star this repository if you found it useful! ⭐
