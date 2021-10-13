# How to Use Farms with BscScan

![](<../../.gitbook/assets/docs-masthead-21- (2).png>)

Since it requires several steps, using Farms with PancakeSwap can seem intimidating at first. This guide will walk you through using the Farms contract directly through BscScan.

{% hint style="warning" %}
Please understand that using BscScan to interact with contracts is not recommended for beginners. If you're not feeling confident, we suggest using the [How to Use Farms guide](https://docs.pancakeswap.finance/products/yield-farming/how-to-use-farms) instead.
{% endhint %}

## Finding Farm process identifier

To interact correctly with the farming smart contract, you’ll need the matching process identifier (PID) for your LP pair. For now, the easiest way to locate this is to check GitHub.

1\. Open the [PancakeSwap website’s Farms code on GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Control**/**command** + **F** and search for your pair by ticker (not project name). For example, 'CAKE-BUSD'.

![](<../../.gitbook/assets/image (96).png>)

3\. Write down or copy the PID number—in this case 389—somewhere you can access it easily. You'll need this later.

## Depositing LP Tokens through BscScan

There are a few things involved in depositing LP Tokens using BscScan. We've broken it down into steps to make it easier to follow along.

### Getting the Main Staking Contract address

The address for the main staking contract is: **0x73feaa1eE314F8c655E354234017bE2193C9E24E**

But assuming you'd like to confirm that, visit the [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract). You'll see the address in the top-left. Click the **pages icon** to copy this to clipboard. You'll need it soon.

![](<../../.gitbook/assets/image (154).png>)

### Open the contract for your LP Token

You'll need to approve the smart contract for the LP Token you wish to commit to a farm before you can spend it.

### From the source code

1\. First, open [farms.ts on GitHub](https://github.com/pancakeswap/pancake-frontend/blob/master/src/config/constants/farms.ts).

2\. **Control**/**command** + **F** and search for your pair by ticker (not project name). For example, 'CAKE-BNB'

![](<../../.gitbook/assets/image (142).png>)

3\. When you have the code for the LP pair you're looking for up, find the address after "56:". This will be your contract address.

![](<../../.gitbook/assets/image (108).png>)

### From the UI

1\. First, visit the [PancakeSwap Farms page](https://pancakeswap.finance/farms) and search for your chosen pair using the "SEARCH" field in the top right. We're using CAKE-BUSD for this example.

![](<../../.gitbook/assets/image (106).png>)

2\. Click **Details** to expand the row to show more information.

![](<../../.gitbook/assets/image (34).png>)

3\. Click **View Contract** to open the smart contract on BscScan.

![](<../../.gitbook/assets/image (163).png>)

### Giving permission to the LP Token contract

Now that you have your LP Token's contract open on BscScan, you're going to approve the spending of your LP Tokens into the Farm.

1\. On the LP Token's contract page, go to **Contract**, and then **Write Contract**.

![](<../../.gitbook/assets/image (149).png>)

2\. Click **Connect to Web3** to connect MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

Confirm the connection.

3\. Under function 1, “approve”, you’ll see “spender:address”. Paste in the Main Staking Contract’s contract address you copied to clipboard earlier.

![](<../../.gitbook/assets/image (7).png>)

5\. You’re also going to need to approve the amount of LP Tokens the contract can spend. In the value field, you’ll need to enter the amount in Wei. You can use the [BscScan Unit Converter](https://www.bscscan.com/unitconverter) to easily change your amount into Wei. Here we'll use 5 CAKE-BUSD LP Tokens.

![](<../../.gitbook/assets/image (158).png>)

{% hint style="warning" %}
You can also use `-1` as the value to give unlimited spend approval. This does not mean you will spend everything by default, but only that a transaction of any size using this contract will be allowed by your wallet.
{% endhint %}

6\. Click **Write** and accept the action in your MetaMask wallet. You’re now able to commit LP Tokens to the Farm up to the amount you’ve approved.

### Deposit LP Tokens with the Main Staking Contract smart contract

With the Main Staking Contract now approved to spend your LP Tokens, it's time to make a deposit.

1\. Back on the [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), go to **Contract**, and then **Write Contract**.

![](<../../.gitbook/assets/image (149).png>)

2\. Click **Connect to Web3** to connect MetaMask.

3\. Scroll to function 2, "deposit", and type your PID into the "\_pid" field.

![](<../../.gitbook/assets/image (29).png>)

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

4\. Underneath \_pid you'll see "\_amount". Enter the amount for the LP contract to spend that you approved earlier.

![](<../../.gitbook/assets/image (27).png>)

5\. Check the information and click **Write**. Confirm your action in MetaMask.

![](<../../.gitbook/assets/image (41).png>)

6\. You can confirm your deposit worked by clicking **View your transaction**.

![](<../../.gitbook/assets/image (145).png>)

## Withdrawing from a Pool

Withdrawing your LP Tokens from a Pool is very similar to making a deposit. The difference is which function you'll interact with.

1\. Back on the [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), go to **Contract**, and then **Write Contract**.

![](<../../.gitbook/assets/image (149).png>)

2\. Click **Connect to Web3** to connect MetaMask.

3\. Scroll all the way down to function 15, "withdraw", and type your PID into the "\_pid" field.

![](<../../.gitbook/assets/image (146).png>)

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

4\. Underneath \_pid you'll see "\_amount". Enter the amount of LP you'd like to withdraw from the Pool.

![](<../../.gitbook/assets/image (83).png>)

5\. Check the information and click **Write**. Confirm your action in MetaMask.

![](<../../.gitbook/assets/image (41).png>)

6\. You can confirm your withdrawal worked by clicking **View your transaction**.

![](<../../.gitbook/assets/image (145).png>)



## **Making an emergency withdrawal**

‌Using the emergency withdraw function allows you to draw all your funds out of a pool when no other way is working.

{% hint style="danger" %}
**Using the emergency withdraw function will forfeit your CAKE rewards!**

The PancakeSwap team strongly suggests avoiding this function unless advised to do so officially by the PancakeSwap team, or if you are very comfortable interacting with smart contracts and understand the underlying code.
{% endhint %}

‌1. On the [PancakeSwap: Main Staking Contract BscScan page](https://bscscan.com/address/0x73feaa1ee314f8c655e354234017be2193c9e24e#writeContract), go to **Contract**, and then **Write Contract**.

![](<../../.gitbook/assets/image (149).png>)

2\. Click **Connect to Web3** to connect MetaMask.

![](https://lh4.googleusercontent.com/IRXfcKBWmlH8o7gDE9ThGrKuc2DHZSNb-SxF93VSTkCdv2JjtdvKciPb5jom4Uv-ngpPMrrGQI1XuM6H2SuN81NMxGLzoHAye5YgvUzR9YSM6ElZs6e3A-fpnMT21PKyJmV2F1IZ)

‌3. Scroll down to function 4, "emergencyWithdraw", and type your PID into the "\_pid" field.

![](<../../.gitbook/assets/image (99).png>)

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

5\. Check the information and click **Write**. Confirm your action in MetaMask.

![](<../../.gitbook/assets/image (41).png>)

6\. You can confirm your withdrawal worked by clicking **View your transaction**.

![](<../../.gitbook/assets/image (145).png>)
