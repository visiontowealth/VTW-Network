# Installation Guide for VTW Blockchain

This document provides detailed instructions for installing and running the Vision to Wealth (VTW) Blockchain on a server. Follow these steps to set up your node on both MainNet and TestNet.

## Server Requirements

- **Operating System**: Ubuntu 20.04
- **Type**: Secured VPS
- **RAM**: 8 GB
- **Cores**: 4 Processing Cores
- **Disk**: 100 GB SSD

## Installation Instructions

### Step 1: Install Geth

Download and install the Geth client, which is required to run the VTW node:

```bash
sudo wget -O /usr/local/bin/geth https://github.com/visiontowealth/VTW-Network/releases/download/v1.0/geth
sudo chmod +x /usr/local/bin/geth
geth version
```

### Step 2: Running MainNet

#### 2.1 Download the MainNet Genesis File

```bash
wget https://github.com/visiontowealth/VTW-Network/releases/download/v1.0/visiontowealth.json
```

#### 2.2 Initialize the Data Directory for MainNet

```bash
geth --datadir "./.visiontowealth" init visiontowealth.json
```

#### 2.3 Run VTW MainNet Node

```bash
screen geth --datadir "./.visiontowealth" --networkid 2235 --port 5633 --syncmode 'full' --bootnodes enode://b72fadfef83eb60d3c18c502add745b01a167dfbe36caed2c835197df2a75ca3a8a3ed18a133a47eb1e97d3af99e221a1245d7f16d3d3fc26f68bdadb62e16df@64.176.11.92:5633
```

### Step 3: Running TestNet

#### 3.1 Download the TestNet Genesis File

```bash
wget https://github.com/visiontowealth/VTW-Network/releases/download/v1.0/visiontowealth_testnet.json
```

#### 3.2 Initialize the Data Directory for TestNet

```bash
geth --datadir "./.visiontowealth_testnet" init visiontowealth_testnet.json
```

#### 3.3 Run VTW TestNet Node

```bash
screen geth --datadir "./.visiontowealth_testnet" --networkid 4461 --port 15633 --syncmode 'full' --bootnodes 7a1d4fb6c5c65a5b2ec6407f32734c6bcf81862f7304562ccdc7d848d56c15371d96a164bade1909a738f071b20327f9ef92b796594c6908c7ab2f3e2494297a@149.248.54.126:15633
```

## Additional Resources

### Web3 Integration

For integrating Web3 with your applications, consult the Web3.js documentation:

[Web3.js Documentation](https://web3js.readthedocs.io/en/v1.2.2/getting-started.html#adding-web3-js)

### RPC Documentation

For detailed API interactions with the blockchain, refer to the Ethereum RPC documentation:

[Ethereum RPC Documentation](https://ethereum.github.io/execution-apis/api-documentation)