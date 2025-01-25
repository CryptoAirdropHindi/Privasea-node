# Privasea-node

# What is privasea?

DePIN & Privasea is a decentralized AI network that leverages Fully Homomorphic Encryption Machine Learning (FHEML) 
for secure data circulation. It utilizes distributed computing resources for FHE AI operations, supported by ZAMA's
concrete ML technology. The ecosystem is incentivized with $PRVA tokens, encouraging crowdsourcing efforts within the network.
------------------------------------------------------------------------------------------------------------------------------
## Minimum System Requirements

| **Component**             | **Requirement**                     |
|---------------------------|-------------------------------------|
| **Operating System (OS)** | Ubuntu (Recommended)                |
| **CPU Architecture**      | amd64 (x86 architecture)            |
| **Storage**               | 100GB available storage             |
| **Memory (RAM)**          | 4GB RAM                             |
| **Processor**             | 6 cores                             |

- [Arbitrum Sepolia](https://faucet.quicknode.com/arbitrum/sepolia)
- [Arbitrum Sepolia](https://faucets.chain.link/arbitrum-sepolia)
- [Arbitrum Sepolia](https://bwarelabs.com/faucets/arbitrum-sepolia)


Update the package list: This makes sure your system knows about the latest versions of packages.
```
sudo apt update
sudo apt upgrade -y
```

 First install `Docker` in your system if it is not already there by using below command
```
source <(wget -O - https://raw.githubusercontent.com/CryptoAirdropHindi/Tools/refs/heads/main/docker.sh)
```
```
sudo groupadd docker && sudo usermod -aG docker $(whoami) && newgrp docker
```
- First pull the docker image using the following command
```
docker pull privasea/acceleration-node-beta:latest
```
- Create a directory and navigate to it
```
mkdir -p ~/privasea/config && cd ~/privasea
```
- Run the below command to get a new wallet keystore
- Here you need input a password after running the below command, make sure to remember it for future use and also note down the `node address` as well
```
docker run --rm -it -v "$HOME/privasea/config:/app/config" privasea/acceleration-node-beta:latest ./node-calc new_keystore
```
- Move the keystore file to a new file
```
mv $HOME/privasea/config/UTC--* $HOME/privasea/config/wallet_keystore
```
- Now visit this [Privanetix Dashboard](https://deepsea-beta.privasea.ai/privanetixNode)
- Connect a wallet where you will recieve reward and then give the node any name, set up commission (I will use 1%), and then enter the `node address` you note down in above step and then click on **Set up my node** option
- Now run the below command to start your `Privasea Privanetix Node`, Make sure to replace **ENTER_YOUR_KEYSTORE_PASSWORD** with your **Keystore Password**, you provided in the above steps
```
KEYSTORE_PASSWORD=ENTER_YOUR_KEYSTORE_PASSWORD && docker run -d --name privanetix-node -v "$HOME/privasea/config:/app/config" -e KEYSTORE_PASSWORD=$KEYSTORE_PASSWORD privasea/acceleration-node-beta:latest
```
`Error,` # If you have successfully run the node and then docker container ID is not showing then follow the steps below


Docker container check
```
docker ps -a
```

# Then if the status shows `Exited` then use the following command
![Screenshot 2025-01-25 142607](https://github.com/user-attachments/assets/d8f5610f-e5e1-4213-8ae2-a19f18065617)

Docker container restart
```
docker restart <containerID>
```
![Screenshot 2025-01-25 142659](https://github.com/user-attachments/assets/ef2400e1-f192-4213-8422-ddbd698fa595)

# Then check the status again.

```
docker ps -a
```
![Screenshot 2025-01-25 142800](https://github.com/user-attachments/assets/f678ab20-28f6-4a33-a73f-0e9b6cb825b1)

# Then go to the dashboard and check if your status is online.

![Screenshot 2025-01-25 143530](https://github.com/user-attachments/assets/236dbc21-5c3b-4faa-864e-59111f574a5f)

- Now follow the guide from **Step 3 (Manage my Privanetix node)** from [this docs](https://www.privasea.ai/privanetix-node)

# Optional: Stop and Delete privanetix-node
```
rm -rf privasea && docker stop privanetix-node && docker rm privanetix-node
```
![Screenshot 2025-01-25 234430](https://github.com/user-attachments/assets/812b2957-cd91-47f5-b1fe-2693462dba48)
