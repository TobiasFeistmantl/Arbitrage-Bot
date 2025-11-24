![](log/ethereum-arbitrage-bot.png)

Ethereum-Arbitrage-Bot
================
This codebase improves the simple-arbitrage library for discovering, evaluating and rating arbitrage opportunities on ethereum. It is currently somewhat profitable, but may become progressively less so as the number of users increases. The reason for opening the source code is that I would like to get more suggestions, which would be very helpful!


Environment Variables
=====================
- **ETHEREUM_RPC_URL** - Ethereum RPC endpoint.

- **PRIVATE_KEY** - Private key for the Ethereum EOA that will be submitting Flashbots Ethereum transactions.

- **FLASHBOTS_RELAY_SIGNING_KEY** _[Optional, default: random]_ - Flashbots submissions require an Ethereum private key to sign transaction payloads. This newly-created account does not need to hold any funds or correlate to any on-chain activity, it just needs to be used across multiple Flashbots RPC requests to identify requests related to same searcher.

- **HEALTHCHECK_URL** _[Optional]_ - Health check URL, hit only after successfully submitting a bundle.

- **MINER_REWARD_PERCENTAGE** _[Optional, default 30]_ - 0 -> 100, what percentage of overall profitability to send to miner. After a month of use, 30 is a relatively balanced value.

- **Arbitrage_Amount** - The capital used for each arbitrage trade is denominated in WETH. I typically use 0.3 WETH; please adjust this amount according to your specific needs. (WETH does not require advance conversion; it will be automatically converted during arbitrage)

Usage
======================

Make sure you have the [node.js](https://nodejs.org/en/download) environment on your device before you start using it.

1. Clone this repository

```bash

git clone  https://github.com/TobiasFeistmantl/Arbitrage-Bot

```

2. Go to the folder(Can be accessed manually)

```bash

cd arbitrage-bot

```

3. Install project dependencies

```bash

npm install

```

4. Configuring .env parameters

- Go to `.env.example` and fill in `PRIVATE_KEY` as the private key of your primary ethereum account in a format that starts with 0x, as in the example.(This wallet requires ETH to cover the fees associated with arbitrage, so please ensure your current environment is secure.)

-  `BUNDLE_EXECUTOR_ADDRESS` is the Ethereum WETH contract address. WETH significantly accelerates transaction speeds during arbitrage, so this parameter should not be modified.

- Create a new Etherwallet for the `FLASHBOTS_RELAY_SIGNING_KEY` parameter and write the private key to it. (This wallet does not require any funds)

- `HEALTHCHECK_URL` Can be blank.

- `ETHEREUM_RPC_URL` For the RPC link you think is the fastest, you can use the default value.

- `MINER_REWARD_PERCENTAGE` You can use the default value or higher.

- `Arbitrage_Amoun` The amount of WETH used for arbitrage each time.

When all is done, change `.env.example` to `.env`.

5. start running

```bash

npm run start

```

Contact
======================

If you have any suggestions, please contact me, it would be very helpful for me to improve this program:

Discord: 0x_ethdev 
