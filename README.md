<div align=center>
  <img src="https://github.com/TempGROX/TempGROX/blob/main/src/photos/rounded-in-photoretrica%20(2).png" width="150">
</div>

<h1 align=center>my_morph_guide</h1>
In this repository you can find a guide to the morph project, which was written by me. Guides are constantly updated!

# Download and Install
## System Requirements
Only the minimum system requirements are indicated here, if yours is below this, then you should not try to follow this guide!

### Geth

|KEY|VALUE|
|:--|:----|
|**CPU**|2 cores|
|**RAM**|4 GB|
|**Disk**|1 TB|
|**Ethernet**|8 MBit/sec|

### Node

|KEY|VALUE|
|:--|:----|
|**CPU**|1.4 GHz|
|**Disk**|25 GB|
|**RAM**|1 GB|

## Build from the source
```bash
mkdir -p ~/.morph 
cd ~/.morph
git clone https://github.com/morph-l2/morph.git
git checkout v0.1.0-beta

cd morph
git checkout v0.1.0-beta
```

### Build Geth
```bash
make nccc_geth
```

### Build Node
```bash
cd ~/.morph/morph/node 
make build
```

## Download and unzip Genesis File
```bash
cd ~/.morph
wget https://raw.githubusercontent.com/morph-l2/config-template/main/holesky/data.zip
unzip data.zip

cd ~/.morph
openssl rand -hex 32 > jwt-secret.txt
```

## Script to start Geth
```bash
./morph/go-ethereum/build/bin/geth --morph-holesky \
    --datadir "./geth-data" \
    --http --http.api=web3,debug,eth,txpool,net,engine \
    --authrpc.addr localhost \
    --authrpc.vhosts="localhost" \
    --authrpc.port 8551 \
    --authrpc.jwtsecret=./jwt-secret.txt \
    --miner.gasprice="100000000" \
    --log.filename=./geth.log
```

## Script to start Node
```bash
./morph/node/build/bin/morphnode --home ./node-data \
     --l2.jwt-secret ./jwt-secret.txt \
     --l2.eth http://localhost:8545 \
     --l2.engine http://localhost:8551 \
     --log.filename ./node.log
```

# The end!
If you liked this guide, please go to all my social networks)

<br>
<div id="badges" align="center">
  <a href="https://discord.com/users/961408999411048461">
    <img src="https://img.shields.io/badge/Discord-blue?style=for-the-badge&logo=https%3A%2F%2Fimg.icons8.com%2Fios%2F50%2Fmedium-logo.png&logoColor=white" alt="LinkedIn Badge"/>
  </a>
  <a href="https://medium.com/@James_Brandon">
    <img src="https://img.shields.io/badge/Medium-black?style=for-the-badge&logo=https%3A%2F%2Fimg.icons8.com%2Fios%2F50%2Fmedium-logo.png&logoColor=white" alt="Youtube Badge"/>
  </a>
  <a href="https://keybase.io/jamesbrandon">
    <img src="https://img.shields.io/badge/Keybase-orange?style=for-the-badge&logo=https%3A%2F%2Fimg.icons8.com%2Fios%2F50%2Fmedium-logo.png&logoColor=white">
  </a>
  <a href="https://x.com/JBTGrox">
    <img src="https://img.shields.io/badge/Twitter-blue?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter Badge"/>
  </a>
  <a href="https://linktr.ee/JBrandon_?utm_source=linktree_admin_share">
    <img src="https://img.shields.io/badge/Linktree-green?style=for-the-badge&logo=https%3A%2F%2Fimg.icons8.com%2Fios%2F50%2Fmedium-logo.png&logoColor=white">
  </a>
</div>
