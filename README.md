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
```ruby
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

```ruby
docker pull elixirprotocol/validator:v3
```

```ruby
git clone https://github.com/fmsuicmc/elixir-metadata
```

```ruby
cd elixir-metadata

nano validator.env
```
STRATEGY_EXECUTOR_IP_ADDRESS : The public IP address

STRATEGY_EXECUTOR_DISPLAY_NAME : This is the public-facing name for you or your organization. This will be visible on Elixir Network dashboards and your uptime and performance metrics will be tied to this name.

STRATEGY_EXECUTOR_BENEFICIARY: Set this to the wallet address you want to receive your Elixir Network validator rewards (when available). This can be any wallet address — EOA, Hardware wallet, Multisig, etc..

SIGNER_PRIVATE_KEY : The private key that was generated in the Preparations steps above. This should be a new, never-used wallet and will never need funds.

Note: This field does not start with 0x

save nano :

Control X

y

Enter

start validator
```ruby
docker run -it \
  --env-file $Home/root/elixir-metadata/validator.env \
  --name elixir \
  elixirprotocol/validator:v3
```
logs is ok

close server

everything was good If you want to see the log
```ruby
docker logs --follow elixir 
```

