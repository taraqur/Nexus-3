# Nexus-3

# CLI Node Run Full Guide (PC)

### Offical Docs by Nexus Labs - https://docs.nexus.xyz/layer-1/testnet/cli-node



1️⃣ Dependencies for WINDOWS & LINUX
```
sudo apt update
sudo apt upgrade -y
```

2️⃣ Download Some Files
```
sudo apt install build-essential pkg-config libssl-dev git-all protobuf-compiler
```
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
- Then Just Press Enter
```
rustup target add riscv32i-unknown-none-elf
```
```
source $HOME/.cargo/env
```
```
sudo apt install pkg-config libssl-dev
```
```
sudo apt install -y protobuf-compiler
```


3️⃣ Install and Run Prover
```
curl https://cli.nexus.xyz/ | sh
```

4️⃣ Start Node
```
source ~/.bashrc
nexus-network start --node-id your-node-id
```

Like That  : source ~/.bashrc
nexus-network start --node-id 7751477

Replace "your-node-id" with your actual Node ID

---

### How to get Node ID

OPTION 1 - Using WEB

🍀Go: https://app.nexus.xyz/

- Click "Nodes" button
- Click "Add node" button
- Click "Add CLI node" button
- Then copy your Node ID & Paste in WSL



- after that write that START NODE command

## 🧩 GLIBC Compatibility Issue
Some systems may return the following error:

```bash
nexus-network: /lib/x86_64-linux-gnu/libc.so.6: version `GLIBC_2.39' not found
```
#### Check current version:
```bash
ldd --version
```

If you don’t have 2.39, install it manually:
```bash
sudo apt install gawk bison gcc make wget tar
wget https://ftp.gnu.org/gnu/glibc/glibc-2.39.tar.gz
tar -zxvf glibc-2.39.tar.gz
cd glibc-2.39 && mkdir glibc-build && cd glibc-build
../configure --prefix=/opt/glibc-2.39
make -j$(nproc)
sudo make install
```

Run CLI with Custom GLIBC Loader
```bash
/opt/glibc-2.39/lib/ld-linux-x86-64.so.2 \
--library-path /opt/glibc-2.39/lib:/lib/x86_64-linux-gnu:/usr/lib/x86_64-linux-gnu \
/root/.nexus/bin/nexus-network register-user --wallet-address your-wallet-address
```
- Replace "your-wallet-address" with your connected EVM wallet address

If unsure about the binary path, run:
```bash
which nexus-network
```

## 🔶For Next Day Run This Command

#1 Open WSL and Put this Command 
```
curl https://cli.nexus.xyz/ | sh
```
```
nexus-network start --node-id your-node-id
```

Replace "your-node-id" with your actual Node ID
