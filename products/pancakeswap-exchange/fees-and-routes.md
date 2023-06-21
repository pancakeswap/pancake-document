# Fees and Routes

<figure><img src="../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

In Exchange V3, on default, PancakeSwap Smart Router will utilize liquidity from V3, V2, StableSwap (BNB Chain), and the AMM and market makers (BNB Chain & Ethereum), to execute trades and find the best price for traders.

However, users are always able to customize their trade by choosing which liquidity sources the router shall utilize, and enable or disable multihops and split routing.

### **Check the fee rate and fee amount that is currently applied**

![](<../../.gitbook/assets/image (42).png>)

To check how much trading will be charged on your current swap, check out the “Fee” section in the swap detail section.

![](<../../.gitbook/assets/image (11) (2).png>)

To check which type of pool and the fee tier your trade is currently routed through, check out the “Route” section.

![](<../../.gitbook/assets/image (27).png>)

To learn more detail, click the magnifier icon to bring out the full trading route displays.



### **Customize liquidity sources**

![](<../../.gitbook/assets/image (23) (2).png>)

At the top of the “Customize Routing” interface, you may choose which liquidity source the route shall use while routing your trade. To bring up this interface, you can:

* Click “Customize Routing” at the bottom of the trading route displays.
* Click the cog icon in the swap interface, and then click “Customize Routing” at the bottom.

By default, all of the liquidity sources are enabled and Smart Router will take full advantage of all the available liquidities within PancakeSwap.

Please note that the router will NOT route trades between AMM liquidity pools and MM market makers. When your trade is executed by MM market makers, it will not go through any AMM liquidity pools.

![](<../../.gitbook/assets/image (26).png>)

You can click the “Reset” button on the top right-hand corner to reset the configurations to default.



### **Customize routing preferences**

![](<../../.gitbook/assets/image (9) (3).png>)

At the bottom of the “Customize Routing” interface, you can customize your routing preferences by enabling or disabling multihops and split routing.

Multihops allow tokens to swap through multiple hops between serval liquidity pools to achieve the best deal. Turning it off will restrict trades to direct swaps, which may cause higher slippage or even fund loss.

Split routing enables token swaps to be broken into multiple routes to achieve the best deal. Turning it off will restrict trades from being executed with a single route, which may result in low efficiency or higher slippage.

{% hint style="warning" %}
When your trade can not be executed due to a customized trading configuration, a warning will appear, you can click “Check your settings” to quickly bring up the“Customize Routing” interface. Or choose “Reset to default” to quickly reset your configurations back to default.
{% endhint %}
