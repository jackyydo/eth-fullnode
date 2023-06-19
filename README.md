# eth-fullnode Local

## Installing Packages

`sudo apt update`

`sudo add-apt-repository -y ppa:ethereum/ethereum`

`sudo apt-get update`

`sudo apt-get install ethereum`


## Using Prysm and Connecting 


`mkdir prysm && cd prysm`

`curl https://raw.githubusercontent.com/prysmaticlabs/prysm/master/prysm.sh --output prysm.sh && chmod +x prysm.sh`

`./prysm.sh beacon-chain generate-auth-secret`

## Start service GETH server/node

`geth --http --http.api eth,net,engine,admin --authrpc.jwtsecret /root/prysm/jwt.hex`

## Start

`./prysm.sh beacon-chain --execution-endpoint=http://localhost:8551 --jwt-secret=/root/prysm/jwt.hex --suggested-fee-recipient=0x0...`


 Replace address
