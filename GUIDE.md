# Full Node Cloud

## Prepare 
### Docker
`sudo apt install apt-transport-https ca-certificates curl software-properties-common`

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

`sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"`

`apt-cache policy docker-ce`

`sudo apt install docker-ce`

`sudo systemctl status docker`

`sudo usermod -aG docker ${USER}`

`su - ${USER}`
## Docker compose
`sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`

`sudo chmod +x /usr/local/bin/docker-compose`

`docker-compose --version`

### Lodestar

`docker pull chainsafe/lodestar`

### jwt secret

`touch .jwtsecret`

## Install 

`docker run chainsafe/lodestar beacon --network mainnet --jwt-secret ~/.jwt-secret`

## Install GETH

Following guide to install GETH

`geth attach http://localhost:8545`

## Query

`curl -X POST http://localhost:8545/graphql -H "Content-Type: application/json" --data '{ "query": "query { block { number } }" }'`

`curl http://localhost:3500/eth/v1/node/syncing | jq`

## DNS domain 

www.eth-rpc.... nginx -> 8545
