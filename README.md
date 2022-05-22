# 💎 Emerald Academy

## 🚩 Challenge 2: 🍀 Fungible Token 🤓

🎫 Deploy a FungibleToken  contract to learn the basics of the Flow blockchain and Cadence. You'll use:
- The local Flow emulator to deploy smart contracts. 
- The local Flow dev wallet to log into test accounts.
- A template Next.js app with sample scripts and transactions to interact with your contract.

🌟 The final deliverable is an app that lets users create their own fungible token and transfer them to another account on Flow testnet.

💬 Meet other builders working on this challenge and get help in the [Emerald City Discord](https://discord.gg/emeraldcity)!

---

# Checkpoint 0: 📦 Install 📚

Required: 
* [Git](https://git-scm.com/downloads)
* [Node](https://nodejs.org/dist/latest-v16.x/)  (🧨 Use Node v16 or a previous version as v17 may cause errors 🧨)

```sh
git clone https://github.com/emerald-dao/2-fungible-token.git
```

> in a terminal window, start your 📱 frontend:

```sh
cd 2-fungible-token
npm install
npm run dev
```

> in a second terminal window, start your 👷‍ local emulator:

```bash
cd 2-fungible-token
flow emulator start -v
```

> in a third terminal window, 💾 deploy your contract and 💸 start your local wallet:

```bash
cd 2-fungible-token
flow project deploy
flow dev-wallet
```

> You can `flow project deploy --update` to deploy a new contract any time.

📱 Open http://localhost:3000 to see the app

---

# Checkpoint 1: 👛 Wallets

> 🔥 We'll be using **the local Flow dev wallet** on localhost...

> 👛 Click the "Log In" button and notice a window appears with different accounts to select, each with their own FlowToken balance. Select the first account to log in to it.
You will see the user address now reflects the current logged in address

---

# Checkpoint 2: 📘 Minting Fungible Tokens

> In a terminal, run `npm run mint`. 

🚨🚨🚨 TODO: ADD IMAGE HERE 🚨🚨🚨
???

That will mint 30 tokens to the Service Account (0xf8d6e0586b0a20c7)

---

# Checkpoint 3: 📘 Setup empty user Vault 
???

> 👀 Click the 'Setup Vault' button to setup your empty collection:
???

/
🚨🚨🚨 TODO: ADD IMAGE HERE 🚨🚨🚨
???

---

# Checkpoint 4: 💾 Transfer tokens

📔 You can transfer the tokens to another account by pasting in another account’s address and clicking transfer

Before trying to transfer, make sure to set up the Vault on that user’s account by logging into that account and clicking 'Setup Vault'

---

# Checkpoint 5: 💾 Deploy it to testnet!

📔 Ready to deploy to a public testnet?!?

🚨🚨🚨 TODO: ADD IMAGE HERE 🚨🚨🚨

> 🔐 Generate a **deployer address** by typing `flow keys generate --network=testnet` into a terminal.

🚨🚨🚨 TODO: ADD IMAGE HERE 🚨🚨🚨

> 👛 Create your **deployer account** by going to https://testnet-faucet.onflow.org/, pasting in your public key from above, and clicking `CREATE ACCOUNT`: 

🚨🚨🚨 TODO: ADD IMAGE HERE 🚨🚨🚨

In your .env file, change the following:
1. `NEXT_PUBLIC_ACCESS_NODE` to `https://testnet.onflow.org`
2. `NEXT_PUBLIC_WALLET` to `https://fcl-discovery.onflow.org/testnet/authn` 
3. `NEXT_PUBLIC_CONTRACT_ADDRESS` to your generated testnet address

⛽️ Add your testnet account to `flow.json` as by modifying the following lines of code:

```json
"accounts": {
  "emulator-account": {
    "address": "f8d6e0586b0a20c7",
    "key": "dd6e0fd35190ee5aba55bb3c2ec1630c8a8fe75ef7e9a59f979e9e3a0518edb6"
  },
  "testnet-account": {
    "address": "YOUR GENERATED ADDRESS",
    "key": {
      "type": "hex",
      "index": 0,
      "signatureAlgorithm": "ECDSA_P256",
      "hashAlgorithm": "SHA3_256",
      "privateKey": "YOUR PRIVATE KEY"
    }
  }
},
"deployments": {
  "emulator": {
    "emulator-account": [
      "FungibleToken",
			"ExampleToken"
    ]
  },
  "testnet": {
    "testnet-account": [
      "ExampleToken"
    ]
  }
}
```

> Lastly, change the `PRIVATE_KEY` in .env to your testnet private key. NOTE: It is okay if you leak this private key, because this is a testnet account, and therefore not real. However, if you add a new line to the .gitignore file with ".env", you can prevent ever leaking your private key to things like GitHub.

🚀 Deploy your ExampleToken smart contract:

```sh
flow project deploy --network=testnet
```

---

# ⚔️ Side Quests

> 🏃 Head to your next challenge [here](https://github.com/emerald-dao/2-simple-marketplace).

> 💬 Meet other builders working on this challenge and get help in the [💎 Emerald City Discord](https://discord.gg/emeraldcity)!

> 👉 Problems, questions, comments on the stack? Post them to the [💎 Emerald City Discord](https://discord.gg/emeraldcity).
