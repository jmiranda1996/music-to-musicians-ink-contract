
### Local node

Download binary steps:

```
wget $(curl -s https://api.github.com/repos/AstarNetwork/Astar/releases/latest | grep "tag_name" | awk '{print "https://github.com/PlasmNetwork/Plasm/releases/download/" substr($2, 2, length($2)-3) "/astar-collator-" substr($2, 3, length($2)-4) "-ubuntu-x86_64.tar.gz"}')
tar -xvf astar-collator*.tar.gz
```

Run command

```
./astar-collator --port 30333 --ws-port 9944 --rpc-port 9933 --rpc-cors all --alice --dev
```

### Setup development enviroment

```
rustup target add wasm32-unknown-unknown --toolchain nightly
rustup component add rust-src --toolchain nightly-x86_64-pc-windows-msvc
cargo install dylint-link
cargo install cargo-dylint
cargo install cargo-contract --force

```

### Develop and build
```
cargo contract new <name>
cargo +nightly contract build --release
```

### Resources
- https://ink.substrate.io/
- https://paritytech.github.io/ink/
- https://paritytech.github.io/contracts-ui
- https://docs.porta.network/developer-guide/smart-contracts/install-wasm-opt-version-101
- https://ink-playground.substrate.io/
- https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Frpc.shibuya.astar.network#/contracts