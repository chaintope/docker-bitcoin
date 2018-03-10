# Bitcoin Core for Docker 
[![Docker Pull](https://img.shields.io/docker/pulls/chaintope/bitcoin.svg)](https://hub.docker.com/r/chaintope/bitcoin/ )

A simple Docker image of bitcoin-core; suitable for learning bitcoin using regtest or testnet.

# Quick Start

## Using volume as datadir

 docker volume create --name=bitcoind-data
 docker run -v bitcoind-data:/root/.bitcoin --name=bitcoind -p 18332:18332 \
     chaintope/bitcoin bitcoind -testnet -printtoconsole -rpcuser=bitcoin -rpcpassword=bitcoin
     
## Using host directory as datadir

 docker run -v ${pwd}/bitcoin:/root/.bitcoin --name=bitcoind -p 18332:18332 \
     chaintope/bitcoin bitcoind -regtest -printtoconsole -rpcuser=bitcoin -rpcpassword=bitcoin