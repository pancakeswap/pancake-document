# Cómo Participar en una IFO \(BscScan\)

![](../../.gitbook/assets/docs-masthead%20%288%29.png)

Joining IFOs can be exciting and very rewarding. The [PancakeSwap website’s IFO page](https://pancakeswap.finance/ifo) is an easy way to join an IFO. But some users may prefer to interact directly with smart contracts on the BscScan website. Using BscScan will let you see a contract's code, review its analytics and events in real-time, and find other useful information.

Currently, only MetaMask or WalletConnect wallets can interact directly with BscScan. WalletConnect is still in beta, so for now we recommend using MetaMask.

Interacting directly with smart contracts is not something we’d recommend to beginners. If you’d like to join an IFO without the complicated steps, we have a [How to Participate in an IFO guide](https://docs.pancakeswap.finance/get-started/ifo-guide) to help you through the process using the PancakeSwap website.

## Before the IFO <a id="before-the-ifo"></a>

Before you can join an IFO there are a few things you will need to do to get ready. Follow the steps below to make sure you're ready to buy when the IFO event goes live.

### Create your PancakeSwap profile <a id="create-your-pancakeswap-profile"></a>

To take part in an IFO, you'll need a PancakeSwap profile. Having a profile protects the security of the IFO and makes it fair for everyone. The small cost of a profile also helps keep the total CAKE supply down by burning a little CAKE from each profile created. To create a profile, you can follow our [How to Set Up an NFT Profile guide](https://docs.pancakeswap.finance/get-started/profile-guide).

### Get CAKE-BNB Liquidity Tokens <a id="get-cake-bnb-liquidity-tokens"></a>

Once you have a profile, you will also need to provide liquidity to get some CAKE-BNB LP Tokens. These will be used to buy the tokens being offered in the IFO. To provide liquidity and get some CAKE-BNB LP Tokens, you can follow our [How to Add/Remove Liquidity guide](https://docs.pancakeswap.finance/get-started/liquidity-guide).

## Once the IFO is live <a id="once-the-ifo-is-live"></a>

While an IFO is live, you will have 1 hour to participate. If you have prepared your CAKE-BNB LP Tokens it doesn’t take long at all to buy the new token.

### Getting the IFO’s smart contract address <a id="getting-the-ifos-smart-contract-address"></a>

You’re going to need the IFO’s smart contract address to join the IFO. You can find a link to the contract’s BscScan page on the IFO page of the [PancakeSwap website](https://pancakeswap.finance/ifo) underneath the Unlimited Sale section.

![](https://lh4.googleusercontent.com/s8oMeBKH5SRo21DhAA9ZyAm3pTKRKBbrDY4zpdpc5mKlPTNtuezL_fxCPc0dZvMlGfXy4IcwOmib1Gs-nc4Oe58v3UH7_1JYuHM6GgiVERzkPQN_viUF17dmPRFOYFHuXNrm78eZ)

On the contract page, in the top-left area you’ll find the contract address. Copy the address to clipboard.

![](https://lh3.googleusercontent.com/ez27bQvXXBaRHcVZnrV-GHJdswGjs4AbT0l6QXkcd4f00VbQMQdvwMSaAuWt4hgPsWuaZ0j-upAxz3IDxBb0BfY_NJAVr5mr214Ka6PKpnb726tgXZCP5eFOADD2OImI63BTWChx)

### Approving the IFO contract <a id="approving-the-ifo-contract"></a>

Before you’re able to spend into the IFO, you’ll need to approve the contract spending your LP Tokens.

1. Open a new tab and visit the [PancakeSwap LP BscScan contract page](https://bscscan.com/address/0x0ed7e52944161450477ee417de9cd3a859b14fd0#writeContract) and make sure you’re on **Contract**, **Write Contract**.

![](https://lh6.googleusercontent.com/eZ2wGzH7GC1pighXt5ZbxrroqPGqjG6dItDAATI715riqZy8a-GOMp7hxG1YaZl7mOcuS62KLM4O_-vXJBNhj2lAqfsgnJe6mSdn0OskAkT48mzP1kWNzwZKNnb0a7jbnUrfm-Nu)

2. Click **Connect to Web3** to connect MetaMask.![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Confirm the connection.

3. Under function 1, “approve”, you’ll see “spender:address”. Paste the IFO’s contract address you copied to clipboard earlier.

![](https://lh5.googleusercontent.com/suC6le1V6Vt_YzpQ8DzxhseaZOTC6tZpmMO97l9rcHt5fnP3aP7vUI1udXdvy_VMHyik5IIqXxYIjNsvfaXBzyDvS_vD_baAuzo3felLC-QnA9XAU2quS1CifbdumgV85LImK2WD)

5. You’re also going to need to approve the amount of LP Tokens the contract can spend. In the value field, you’ll need to enter the amount in Wei. You can use the [BscScan Unit Converter](https://www.bscscan.com/unitconverter) to easily change your amount into Wei.

![](https://lh6.googleusercontent.com/h0ywzo2JofyPdJYUQr63vb5gaPsgjIFWXl-cSBzPE7UgthMWfHFZrFOLso5D7vIdEmOKmxa-MtxQAPj3jya1e-hqqRzlRLEcdULB58D8r2FYRjEzqFyPRxiHtLCp7ywNsMUgkJi6)

6. Click **Write** and accept the action in your MetaMask wallet. You’re now able to buy into the IFO up to the amount you’ve approved.

### Buying into the IFO’s Basic Sale <a id="buying-into-the-ifos-basic-sale"></a>

Now that you’ve approved the IFO to spend your Pancake LP Tokens, you’re ready to buy into the IFO.

1. Go back to the tab you have open with the IFO contract. Click onto **Contract**, and then onto **Write Contract**.

2. Under function 1, depositPool, you’ll see “\_amount”. Type or paste your Wei value from before into the field.

![](https://lh6.googleusercontent.com/185gWOjqWA_gZLpyy8TSGdKtk7m-l3HSyXkzx883Cf3Cmnq7DAl6-wOnhn7knU_-lKbyFsnEBXgPhbv7dyRzly0dDa81562jlXcapItkADA0AA5q4fJWnwtSFDsjHSxXD2EHO3pq)

3. Under the \_amount field you’ll see “\_pid”. This will tell the contract which sale you want to buy into between the Basic Sale and Unlimited Sale. If you’re not sure which sale to choose, you can read about them in [How to Participate in an IFO guide](https://docs.pancakeswap.finance/get-started/ifo-guide#which-type-of-sale-should-i-choose-basic-or-unlimited).

To buy into the Basic Sale, type 0 into the \_pid field.

![](https://lh5.googleusercontent.com/eLKY976MLUYSbh3g70EJkpccTfip27QnOCXlc3rQ_Kr9fu4wAIT1K4qg-DB8HYHzFCFb_zbFXoWZNdncWBsNoevbp0YGbEU-yJ4x8xRIG5v-ha1rrfWO9AjGBrf8y5sc021ydALG)

4. Check you typed the right information then click the **Write** button. Confirm your action in MetaMask.![](https://lh3.googleusercontent.com/OMk0rZt6CyLRPDcGjwZnVFHOHNLriLuwJBZ6E8koNFinvBTuSxA4qm6bBdxs_28zmK-b_1NrjjtldgUDhXha8bYpmPc7z72PEiiEthaOU8cteBAYfbwYzhvR3dh9cl5c58mqbY2j)

5. A **View your transaction** button will appear. You can click the button to view your transaction on the BscScan explorer to confirm it worked.![](https://lh6.googleusercontent.com/SHgXqiNtNXoXitNbNY4fBkuXC5UjHJTiQ8rwDp4SEXtzM1zNANHtMQ6PzwmP2zQwp2xVL8gRHKSBrgp4qyMJALrZmq9s0EddnC0eAQcvV4eqMObym__T5tPamtdSJMiUVMn5BYJn)

You can also check the IFO page on PancakeSwap’s website to see your deposit.

![](https://lh6.googleusercontent.com/9tFTlSwXmoSDruTPjhe_IH7o87YOFIdeHyafIs0aBjaZeRv9jP43xjZ7_IMdW6q5jP2U_eN4RxBEm00O1dKP9Pp0Me1Eb6rI6pHXxKIFtgsUpSgNvCrq24_q4c_xNWGYDm4wPk22)

### Buying into the IFO’s Unlimited Sale <a id="buying-into-the-ifos-unlimited-sale"></a>

1. To buy into the Unlimited Sale, follow the same steps as in the Basic Sale until you are entering an amount into the “\_pid” field of the IFO contract.

2. Here, instead of typing 0, type 1. This will deposit your funds into the Unlimited Sale. From here click **Write** and confirm your action in MetaMask.

![](https://lh6.googleusercontent.com/08zKELQHScE0z9TFQRb7SgyvJbVFxelLxxz3AcvOEBP3ocYQIp_pxNkiM7XcBndgDgdPOPI3uUukK7JYDGCnnZQ_J4NZ638YgGLWN9_cqJSeQD5yJ-kH2z5Za-0uyEmWnQupKLIB)

3. You can click **View your transaction**, or visit the PancakeSwap IFO page to confirm your transaction.

![](https://lh6.googleusercontent.com/uqXq-9wHZ-v9HVsqphUVzpzR1DArrSeMx8sCKvLfOIKlWjnKIcg7UbVAX6xL4HvCiMVc6LyxslQ6bRVCBV1raapQcd0hnripO6csNJcUs2CDPtoXj5tjGtkxTccTKTmS0fZHzcpQ)

## After the IFO has ended <a id="after-the-ifo-has-ended"></a>

When the IFO has ended, you will be able to collect your new tokens. How many you will get depends on how many people participated in the IFO. Any extra LP Tokens you have committed to the IFO that aren't used to buy new tokens will be returned to you.‌

### Collecting your new tokens <a id="collecting-your-new-tokens"></a>

1. To collect your new tokens, you’ll need to visit the IFO contract page on BscScan, and click **Contract**, then **Write Contract**.

2. You’ll have to connect MetaMask to WEB3 by clicking on **Connect to Web3**. Confirm the action with MetaMask.

3. Scroll down to function 3, harvestPool. Here you’ll find “\_pid” and a field to type into. Just like earlier, you can type 0 to collect your tokens from the Basic Sale, and 1 to collect your tokens from the Unlimited Sale.

![](https://lh3.googleusercontent.com/QS7BsbQC8NJVU1pLD70Ia8AlmPLvy2rHQe9RWVWEpGAd1NGrZmCdQxCBc9W7kfpoaB6t_zjoPfYwX8I2kIQLJAqhyk2_pNEP1gY3xt2C_6vv7sfA3-1uksAiMT-XH7_odaHqILPU)

Type 0 or 1 and click **Write**. Confirm your action in MetaMask.

4. You can click **View your transaction** or visit the PancakeSwap IFO page to confirm your tokens have been collected.

![](https://lh4.googleusercontent.com/yIrEbfJBxo2diu9RhYk3Shy8nsb37Y2voVZFVTNp7sa8RTnG9DPLFKdHo1hfEEDt8uWj22zmZADwiiGMOuY1vdH1qGGDe9nBMZeeoHfb7b-oiK7QvdY6_79KdOBMoWEn6ka2sUAC)

All done! Your new IFO tokens will be in your wallet, and any unspent LP Tokens will be returned to you.  


