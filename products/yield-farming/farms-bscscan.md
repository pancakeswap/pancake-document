# Cómo usar Farms \(BscScan\)

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-MbogOPu7Z3t4IPYr_NO%2Fdocs%20masthead%20%2821%29.png?alt=media&token=b49d7ec9-439e-4670-b32a-b0ec4ade041c)

Since it requires several steps, using Farms with PancakeSwap can seem intimidating at first. This guide will walk you through using the Farms contract directly through BscScan.

Please understand that using BscScan to interact with contracts is not recommended for beginners. If you're not feeling confident, we suggest using the [How to Use Farms guide](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) instead.

## Finding Farm process identifier <a id="finding-farm-process-identifier"></a>

To interact correctly with the farming smart contract, you’ll need the matching process identifier \(PID\) for your LP pair. For now, the easiest way to locate this is to check GitHub.

1. Open the [PancakeSwap website’s Farms code on GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2. **Control**/**command** + **F** and search for your pair by ticker \(not project name\). For example, 'CAKE-BUSD'.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-MbouIhyaIRlEhCs9AjM%2Fimage.png?alt=media&token=50c95e71-3b4e-4f72-b618-0a33bf493f89)

3. Write down or copy the PID number—in this case 389—somewhere you can access it easily. You'll need this later.

## Depositing LP Tokens through BscScan <a id="depositing-lp-tokens-through-bscscan"></a>

There are a few things involved in depositing LP Tokens using BscScan. We've broken it down into steps to make it easier to follow along.

### Getting the Main Staking Contract address <a id="getting-the-main-staking-contract-address"></a>

The address for the main staking contract is: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

But assuming you'd like to confirm that, visit the [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). You'll see the address in the top-left. Click the **pages icon** to copy this to clipboard. You'll need it soon.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp1nXv8BY_GqBCaIhY%2Fimage.png?alt=media&token=d2d5c5f1-d0f8-4a16-9d5c-670ff7054441)

### Open the contract for your LP Token <a id="open-the-contract-for-your-lp-token"></a>

You'll need to approve the smart contract for the LP Token you wish to commit to a farm before you can spend it.

### From the source code <a id="from-the-source-code"></a>

1. First, open [farms.ts on GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2. **Control**/**command** + **F** and search for your pair by ticker \(not project name\). For example, 'CAKE-BNB'

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-McgveN_06WzVRLK1FeR%2F-McgwmGUCIjvdfLKU9VR%2Fimage.png?alt=media&token=a8e11b39-4458-4e87-9f17-4e01ac4d192b)

3. When you have the code for the LP pair you're looking for up, find the address after "56:". This will be your contract address.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-McgveN_06WzVRLK1FeR%2F-McgxJyVDFAxh9cZhEqt%2Fimage.png?alt=media&token=0638fe99-b1d5-4be3-8fd7-c1b68ca59032)

### From the UI <a id="from-the-ui"></a>

1. First, visit the [PancakeSwap Farms page](https://pancakeswap.finance/farms) and search for your chosen pair using the "SEARCH" field in the top right. We're using CAKE-BUSD for this example.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-MboxfvCzzhDYucewEJM%2Fimage.png?alt=media&token=a2340e87-0ac4-4db7-8868-3c021fcabe13)

2. Click **Details** to expand the row to show more information.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-MboyRav88nxt7uoSMcm%2Fimage.png?alt=media&token=4368c32c-79bf-477b-8853-bdfab36b88cb)

3. Click **View Contract** to open the smart contract on BscScan.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mboz8UGShU9TSD7lct4%2Fimage.png?alt=media&token=d5b90a00-3fb2-4a4f-b77f-c5709b904ee5)

### Giving permission to the LP Token contract <a id="giving-permission-to-the-lp-token-contract"></a>

Now that you have your LP Token's contract open on BscScan, you're going to approve the spending of your LP Tokens into the Farm.

1. On the LP Token's contract page, go to **Contract**, and then **Write Contract**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp2ObHkQgjgI-W5oHd%2Fimage.png?alt=media&token=bd3301ee-86d4-4899-8256-467a591104a8)

2. Click **Connect to Web3** to connect MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Confirm the connection.

3. Under function 1, “approve”, you’ll see “spender:address”. Paste in the Main Staking Contract’s contract address you copied to clipboard earlier.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp7nSuoGINXJV4b3rm%2Fimage.png?alt=media&token=a07d5f8b-df85-4df8-8c33-8c9d74f20ff3)

5. You’re also going to need to approve the amount of LP Tokens the contract can spend. In the value field, you’ll need to enter the amount in Wei. You can use the [BscScan Unit Converter](https://www.bscscan.com/unitconverter) to easily change your amount into Wei. Here we'll use 5 CAKE-BUSD LP Tokens.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp7ayxZbb60iG9uHfV%2Fimage.png?alt=media&token=7fb50d56-32fc-4577-b96a-1ddf6ab74940)

You can also use `-1` as the value to give unlimited spend approval. This does not mean you will spend everything by default, but only that a transaction of any size using this contract will be allowed by your wallet.

6. Click **Write** and accept the action in your MetaMask wallet. You’re now able to commit LP Tokens to the Farm up to the amount you’ve approved.

### Deposit LP Tokens with the Main Staking Contract smart contract <a id="deposit-lp-tokens-with-the-main-staking-contract-smart-contract"></a>

With the Main Staking Contract now approved to spend your LP Tokens, it's time to make a deposit.

1. Back on the [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), go to **Contract**, and then **Write Contract**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp2ObHkQgjgI-W5oHd%2Fimage.png?alt=media&token=bd3301ee-86d4-4899-8256-467a591104a8)

2. Click **Connect to Web3** to connect MetaMask.

3. Scroll to function 2, "deposit", and type your PID into the "\_pid" field.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbsxc1rAB8T2_R8rrzR%2Fimage.png?alt=media&token=03aeb1e2-feba-4f82-b3dc-74ff9f435a19)

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

4. Underneath \_pid you'll see "\_amount". Enter the amount for the LP contract to spend that you approved earlier.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-MbsyWOLP4b1bMdQyTnA%2Fimage.png?alt=media&token=3cb0d014-8174-420a-ad4f-1ebd6e3619dc)

5. Check the information and click **Write**. Confirm your action in MetaMask.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbsyp72o0h6GheA90EF%2Fimage.png?alt=media&token=5e6148e4-a6ec-48f0-8cba-752b3b9d499e)

6. You can confirm your deposit worked by clicking **View your transaction**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbt6-zveDG6pEb5on0q%2Fimage.png?alt=media&token=28a9f6aa-25cf-4089-b111-f3486a3b88ad)

## Withdrawing from a Pool <a id="withdrawing-from-a-pool"></a>

Withdrawing your LP Tokens from a Pool is very similar to making a deposit. The difference is which function you'll interact with.

1. Back on the [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), go to **Contract**, and then **Write Contract**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp2ObHkQgjgI-W5oHd%2Fimage.png?alt=media&token=bd3301ee-86d4-4899-8256-467a591104a8)

2. Click **Connect to Web3** to connect MetaMask.

3. Scroll all the way down to function 15, "withdraw", and type your PID into the "\_pid" field.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-MbtAvbr6T5eY7FhtaMv%2Fimage.png?alt=media&token=61031f79-8b18-4a09-9153-09d4e41703a2)

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

4. Underneath \_pid you'll see "\_amount". Enter the amount of LP you'd like to withdraw from the Pool.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-MbtBD8bokfhbBDKKTpT%2Fimage.png?alt=media&token=b3410b45-e71b-4881-85f5-1cb3c7e8c6c9)

5. Check the information and click **Write**. Confirm your action in MetaMask.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbsyp72o0h6GheA90EF%2Fimage.png?alt=media&token=5e6148e4-a6ec-48f0-8cba-752b3b9d499e)

6. You can confirm your withdrawal worked by clicking **View your transaction**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbt6-zveDG6pEb5on0q%2Fimage.png?alt=media&token=28a9f6aa-25cf-4089-b111-f3486a3b88ad)

## **Making an emergency withdrawal** <a id="making-an-emergency-withdrawal"></a>

‌Using the emergency withdraw function allows you to draw all your funds out of a pool when no other way is working.

**Using the emergency withdraw function will forfeit your CAKE rewards!**

The PancakeSwap team strongly suggests avoiding this function unless advised to do so officially by the PancakeSwap team, or if you are very comfortable interacting with smart contracts and understand the underlying code.

‌1. On the [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), go to **Contract**, and then **Write Contract**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbmNofkorR92isGZtMh%2F-Mbp2ObHkQgjgI-W5oHd%2Fimage.png?alt=media&token=bd3301ee-86d4-4899-8256-467a591104a8)

2. Click **Connect to Web3** to connect MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Scroll down to function 4, "emergencyWithdraw", and type your PID into the "\_pid" field.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-MbtDrETo2rkolLkREKD%2Fimage.png?alt=media&token=6f0afd56-5d00-461d-bfd5-32290f83106c)

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

5. Check the information and click **Write**. Confirm your action in MetaMask.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbsyp72o0h6GheA90EF%2Fimage.png?alt=media&token=5e6148e4-a6ec-48f0-8cba-752b3b9d499e)

6. You can confirm your withdrawal worked by clicking **View your transaction**.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbpARe5bzCMd5XORkuR%2F-Mbt6-zveDG6pEb5on0q%2Fimage.png?alt=media&token=28a9f6aa-25cf-4089-b111-f3486a3b88ad)

