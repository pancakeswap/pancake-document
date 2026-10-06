# 🧙 Page 1

## How to Withdraw Your NFT from the PancakeSwap NFT Marketplace

The PancakeSwap NFT Marketplace pages are no longer available, but the marketplace smart contract is still live. If you listed an NFT for sale and it never sold, it is still held by the marketplace contract. You can get it back yourself by cancelling the listing directly on BscScan.

This takes a few minutes per NFT and only costs a small amount of BNB for gas.

### Before you start

You will need:

* **The same wallet you used to list the NFT.** Only the wallet that created a listing can cancel it.
* **A browser wallet** (for example MetaMask, Trust Wallet extension, or Binance Wallet extension) set to **BNB Smart Chain**.
* **A small amount of BNB** to pay gas. Each NFT is withdrawn in its own transaction.

Keep these addresses handy:

| Item                       | Address                                      |
| -------------------------- | -------------------------------------------- |
| Marketplace contract       | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Pancake Squad collection   | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Pancake Bunnies collection | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Stay safe**
>
> * Only interact with the marketplace contract `0x17539cCa21C7933Df5c980172d22659B8C345C5A`. Always check the address in the BscScan URL.
> * Withdrawing your NFT **never** requires sending BNB or tokens, and never requires signing an approval (`approve` or `setApprovalForAll`). If a website or person asks you to do this, it is a scam.
> * PancakeSwap will never DM you or ask for your seed phrase.

### Step 1: Find the NFTs you still have listed

For each NFT you want to withdraw, you need two pieces of information: the **collection address** and the **token ID**.

1. Open the marketplace contract's [Read Contract page](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) on BscScan.
2. Find and expand **`viewAsksByCollectionAndSeller`**.
3. Fill in the fields:
   * `collection`: the collection address from the table above (for example, Pancake Squad is `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller`: your wallet address
   * `cursor`: `0`
   * `size`: `100`
4. Click **Query**.
5. Look at the `tokenIds` result. These are the token IDs you still have listed in that collection, and they are the NFTs you can withdraw.
6. If you listed NFTs in more than one collection, repeat steps 3 to 5 for each collection.

**If `tokenIds` is empty (`[]`)**, you have no active listings in that collection. Your NFT was either sold (in which case you already received the BNB) or you cancelled the listing earlier (in which case it is already back in your wallet).

**If you have more than 100 listings** in one collection, the last number in the result is the next cursor. Query again using that number as the `cursor` to see the rest.

**If your NFT is from a collection other than Pancake Squad or Pancake Bunnies**, expand **`viewCollections`** on the same page, enter `cursor = 0` and `size = 100`, and click **Query** to see every collection the marketplace supports.

### Step 2: Withdraw your NFT

1. Open the marketplace contract's [Write Contract page](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) on BscScan.
2. Click **Connect to Web3** and connect the same wallet that listed the NFT. Make sure your wallet is on BNB Smart Chain.
3. Find and expand **`cancelAskOrder`**.
4. Fill in the fields:
   * `_collection`: the collection address from Step 1
   * `_tokenId`: the token ID from Step 1, as a plain number (for example `1234`)
5. Click **Write** and confirm the transaction in your wallet. You do not send any BNB; you only pay gas.
6. Once the transaction succeeds, the NFT is back in your wallet.
7. Repeat for each NFT you want to withdraw.

To confirm it worked, run Step 1 again. The token ID should no longer appear in the list.

### Troubleshooting

| Problem                                                   | What it means and what to do                                                                                                                                                                                |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Error: `Order: Token not listed`                          | The connected wallet did not list this token ID in this collection, or the NFT was already sold or withdrawn. Check that you are using the original wallet and the correct collection address and token ID. |
| The Write button does nothing                             | Your wallet is probably on the wrong network. Switch to BNB Smart Chain and reconnect.                                                                                                                      |
| Out of gas or insufficient funds                          | Add a small amount of BNB to your wallet to cover gas.                                                                                                                                                      |
| I no longer have access to the wallet that listed the NFT | Only the original wallet can cancel the listing. Nobody, including PancakeSwap, can withdraw it on your behalf.                                                                                             |
