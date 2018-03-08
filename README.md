# Bitcoin Core for Docker

A simple Docker image of bitcoin-core; suitable for learning bitcoin using regtest or testnet.

# Quick Start

## Using volume as datadir

 docker volume create --name=bitcoind-data
 docker run -v bitcoind-data:/root/.bitcoin --name=bitcoind -d \
     -p 18332:18332 \
     chaintope/bitcoin -testnet -printtoconsole
     
## Using host directory as datadir

 docker run -v ${pwd}/bitcoin:/root/.bitcoin --name=bitcoind -d \
     -p 18332:18332 \
     chaintope/bitcoin -regtest -printtoconsole