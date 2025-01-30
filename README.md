# 🚀 Crypto & Node Project Portfolio

## 📌 About This Portfolio
This repository highlights my expertise in cryptocurrency and blockchain node projects. Inside, you'll find various implementations, scripts, and documentation covering node deployment, staking, and validator setups.

## 📂 Projects

### 1️⃣ Privasea Privanetix Node
**Description:** This guide will walk you through setting up and running a Privasea Privanetix Node from scratch. No prior experience is needed—just follow the steps carefully!

- **Tech Stack:** Docker, Linux, Blockchain
- **Features:**
  - Secure keystore creation
  - Automated node initialization
  - Staking functionality

### 🛠 Step-by-Step Setup

#### 1️⃣ Install Docker (Skip if already installed)
Docker is required to run the node in an isolated environment. Run the following command to install Docker:
```bash
source <(wget -O - https://raw.githubusercontent.com/zunxbt/installation/main/docker.sh)
```
After installation, add your user to the Docker group so you can run it without `sudo`:
```bash
sudo groupadd docker && sudo usermod -aG docker $(whoami) && newgrp docker
```

#### 2️⃣ Download the Privasea Node Docker Image
Now, pull the official Privasea Node image from Docker Hub:
```bash
docker pull privasea/acceleration-node-beta:latest
```
This will ensure you are running the latest version of the node software.

#### 3️⃣ Create a Configuration Directory
Before setting up your node, create a folder to store its configuration files:
```bash
mkdir -p ~/privasea/config && cd ~/privasea
```
This directory will hold important files such as your wallet keystore.

#### 4️⃣ Generate Your Keystore and Node Address
Next, generate your keystore and node address by running this command:
```bash
docker run --rm -it -v "$HOME/privasea/config:/app/config" privasea/acceleration-node-beta:latest ./node-calc new_keystore
```
⚠ **Important:** Save the generated keystore file and node address securely. You will need them to run your node.

#### 5️⃣ Move the Keystore File
To keep things organized, move the keystore file to the correct directory:
```bash
mv $HOME/privasea/config/UTC--* $HOME/privasea/config/wallet_keystore
```

#### 6️⃣ Configure Your Node on the Website
1. Open [Privanetix Node Setup](https://deepsea-beta.privasea.ai/privanetixNode) in your browser.
2. Connect your wallet (use MetaMask or another supported wallet).
3. Claim Faucet tokens (ARB Sepolia & Deepsea) for staking.
4. Click **Privanetix Node - Setup Now**.
5. Enter a name for your node.
6. Set the commission rate (the fee you take from delegators).
7. Input your generated node address.
8. Click **Create** to finalize the setup.

#### 7️⃣ Start Your Privasea Node
Now, it’s time to launch your node. Run the following command, replacing `YOUR_PASSWORD_HERE` with your actual keystore password:
```bash
KEYSTORE_PASSWORD=YOUR_PASSWORD_HERE && docker run -d --name privanetix-node -v "$HOME/privasea/config:/app/config" -e KEYSTORE_PASSWORD=$KEYSTORE_PASSWORD privasea/acceleration-node-beta:latest
```
Your node is now running in the background!

#### 8️⃣ Check Your Node Status
Visit the [Privasea Web Dashboard](https://deepsea-beta.privasea.ai/privanetixNode) to monitor your node’s activity and performance.

#### 9️⃣ Check Node Health
To ensure your node is running properly, check the logs with:
```bash
docker logs -f privanetix-node
```
If everything is set up correctly, you should see the following messages in the logs:
```
read keystore info is ok
read mgrNodeInfo info is ok
calc service started successfully!!!
```
If you see these messages, congratulations! Your node is running successfully.

🔗 [Repository Link](https://github.com/yourgithub/privasea-node)

## 🚀 How to Contribute
Feel free to fork this repository, suggest improvements, or open issues for discussions. Collaboration is always welcome!

## 📧 Contact
- GitHub: [@Bagasdwipa](https://github.com/Bagasdwipa)
- Twitter: [@bagasdwiprtama](https://twitter.com/bagasdwiprtama)

---

### ⭐ Star this repository if you found it useful! ⭐
