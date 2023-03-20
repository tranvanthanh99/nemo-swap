# Whirlpools

Whirpools is an open-source concentrated liquidity AMM contract on the Solana blockchain.
This repository contains the Rust smart contract as well as the Typescript SDK (`@orca-so/whirlpools-sdk`) to interact with a deployed program.

The contract has been audited by Kudelski and Neodyme.

## Requirements

- Anchor 0.20.1
- Solana 1.9.3
- Rust 1.59.0

## Setup

Install Anchor using instructions found [here](https://book.anchor-lang.com/getting_started/installation.html#anchor).

Set up a valid Solana keypair at the path specified in the `wallet` in `Anchor.toml` to do local testing with `anchor test` flows.

`$NODE_PATH` must be set to the `node_modules` directory of your global installs.
For example, using Node 16.10.0 installed through `nvm`, the $NODE_PATH is the following:

```
$ echo $NODE_PATH
/Users/<home_dir>/.nvm/versions/node/v16.10.0/lib/node_modules
```

## Usage

Instructions on how to interact with the Whirlpools contract is documented in the [Orca Developer Portal](https://orca-so.gitbook.io/orca-developer-portal/orca/welcome).

## Tests

- Run "cargo test --lib" to run Rust unit tests

---

# Whirlpool SDK

Use the SDK to interact with a deployed Whirlpools program via Typescript.

## Installation

In your package, run:

```
yarn add `@orca-so/whirlpools-sdk`
yarn add "@project-serum/anchor"
yarn add "decimal.js"
```

## Usage

Read instructions on how to use the SDK on the [Orca Developer Portal](https://orca-so.gitbook.io/orca-developer-portal/orca/welcome).

## Run Typescript tests via local validator
Run test validator:
```
solana-test-validator --faucet-sol --reset
```

In the nemo-swap folder, run:

```
solana config set --url http://127.0.0.1:8899 

export ANCHOR_PROVIDER_URL=http://127.0.0.1:8899

export ANCHOR_WALLET=/<<userpath>>/.config/solana/id.json // Keypair Path when run solana config get
```
```
solana program deploy /<<path>>/nemo-swap/target/deploy/whirlpool.so
```
Copy Program Id and paste to Anchor.toml file. Line whirlpool = "<< Program Id >>"
```
anchor test
```

## Generate TypeDoc

In the `sdk` folder, run `yarn run docs`

---

# Support

**Integration Questions**

Have problems integrating with the SDK? Pop by over to the Orca [Discord](https://discord.gg/nSwGWn5KSG) #integrations channel and chat with one of our engineers.

**Feedback**

Got ideas on how to improve the system? Open up an issue on github with the prefix [FEEDBACK] and let's brainstorm more about it together!

# License

[Apache 2.0](https://choosealicense.com/licenses/apache-2.0/)
