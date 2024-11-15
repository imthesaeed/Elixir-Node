# Elixir-Node

Hardware Requirements
Most hardware is capable of running a validator node. However, it is recommended that you have a system that can be run 24 hours a day, with 8GB of memory and a reliable 100Mbit internet connection. Disk usage is minimal; in most cases, 100GB of storage should be enough.

Start
1- you need Evm wallet

2- need sepolia faucet

3- need MOCK Elixir Tokens On Sepolia
  https://testnet-3.elixir.xyz/

4- Stake Your MOCK Tokens

5- Start server
```
sudo apt update && sudo apt upgrade -y
sudo apt install jq -y

# install docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
docker version

# install docker-compose
VER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)

curl -L "https://github.com/docker/compose/releases/download/"$VER"/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

