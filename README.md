# RL Swarm Node Run Full Guide (PC and VPS and Mac)

### Offical Docs Guide - https://github.com/gensyn-ai/rl-swarm?tab=readme-ov-file

### Dashboard (check ur points) - https://dashboard.gensyn.ai/ 

![image](https://github.com/user-attachments/assets/935a14ac-06f0-497a-b42d-5b3928038ee9)

1️⃣ Install Python and Other Tools
For Linux/Wsl
```
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof
```
For Mac
```
brew install python
```
Check Version
```
python3 --version
```
2️⃣

Install Node.js , npm & yarn 

For Linux/Wsl 
```
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt update && sudo apt install -y nodejs
```
Install Yarn (linux)
```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
```
```
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list > /dev/null
```
```
sudo apt update && sudo apt install -y yarn
```
For Mac
```
brew install node && corepack enable && npm install -g yarn
```
Check version (Linux/Mac)
```
node -v 
npm -v
yarn -v
```


3️⃣  Download Some Files
```
git clone https://github.com/gensyn-ai/rl-swarm/
```

For VPS Only
```
apt install screen -y
```
```
screen -S gensyn
```
```
cd rl-swarm
python3 -m venv .venv
source .venv/bin/activate
```

4️⃣ Install Left-over dependencies
```
cd modal-login
```
```
yarn install
```
```
yarn upgrade &&  yarn add next@latest &&  yarn add viem@latest
```
5️⃣  Run the swarm Node 🚀
```
cd rl-swarm
```
```
./run_rl_swarm.sh
```
After Running the Above command it will promt Would you like to connect to the Testnet? [Y/n] Enter Y

After than it will promt >> Which swarm would you like to join (Math (A) or Math Hard (B))? [A/b] Enter a

After than it will promt >> How many parameters (in billions)? [0.5, 1.5, 7, 32, 72]

👇See below and Choose the model Depends on Your System!

- Qwen 2.5 0.5B                - Recommended 4GB RAM, (1GB DOWNLOAD)
- Qwen 2.5 1.5B                - Recommended 8GB RAM, (4GB DOWNLOAD)
- Qwen 2.5 7B                  - Recommended 16GB RAM, (15GB DOWNLOAD)
- Qwen 2.5 32B (4 bit)         - Recommended 50GB RAM, (35GB DOWNLOAD)
- Qwen 2.5 72B (4 bit)         - Recommended 100GB RAM, (70GB DOWNLOAD)

Put answer 'Y' (just press enter)

Wait till you see waiting for UserData.json to be created

Then open Browser and Input & Login by Google - http://localhost:3000/

![1_qkd1ND0PxngzkxE4Z6VqBQ](https://github.com/user-attachments/assets/19ceac2c-b3ff-47d6-8a7c-f4f584288241)

Now It will promt Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N] Enter N

![1_zs7VHm5Fv_ZeFTsZdBGo9g](https://github.com/user-attachments/assets/123acf42-08bc-492b-aa13-d27359af9ce3)
![Screenshot 2025-05-05 184213](https://github.com/user-attachments/assets/34666357-8f50-428f-8cb1-2a4f74dbfda0)


Take note of Username

## Open Another Window for VPS to Login ur LocalHost

1️⃣ Download Some Dependencies 
```
sudo apt install ufw -y
```
```
sudo ufw allow 22
```
```
sudo ufw allow 3000/tcp
```

2️⃣ Enable ufw
```
sudo ufw enable
```
```
sudo ufw allow ssh
```
```
sudo ufw reload
```

3️⃣ Install Cloudflared
```
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
````
```
sudo dpkg -i cloudflared-linux-amd64.deb
```
```
cloudflared --version
```
- Make sure your Node is running on port 3000 in Previous Screen

4️⃣ Run the tunnel command
```
cloudflared tunnel --url http://localhost:3000
```
Access the Link from your local machine

![430651391-c5bdfec5-123d-4625-8da8-f46269700950](https://github.com/user-attachments/assets/93590db1-9d6b-4a86-9d44-337506b6c06c)



Then Login > Then Go to the Previous Screen to Check ur Logs

```
PRESS CTRL+A+D (to run ur node continuously)
```
- To check ur Node Again
```
screen -r gensyn
```
## 🔶For Next Day Run This Command (Windows or Mac)

#1 Open WSL or HomeBrew and Put this Command 
```
cd rl-swarm
```
```
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh
```

## How to update your node

```
cd rl-swarm
```
```
git pull
```
## Note if  you installing from  may  5th or later you no need to update node it directly install as latest version 0.4.2
