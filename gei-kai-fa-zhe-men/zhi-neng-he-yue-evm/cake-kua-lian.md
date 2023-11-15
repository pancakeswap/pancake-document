---
description: PancakeSwap uses LayerZero OFT for Cross Chain CAKE Bridging
---

# CAKE 跨链

## Contract info

#### **CAKE Bridging Contract**

**Contract name:** CakeProxyOFT\
**Contract address:** [0xb274202daBA6AE180c665B4fbE59857b7c3a8091](https://bscscan.com/address/0xb274202daBA6AE180c665B4fbE59857b7c3a8091#code)

[View on BscScan](https://bscscan.com/address/0xb274202daBA6AE180c665B4fbE59857b7c3a8091#code)

## Example of CAKE bridging to Aptos

**sendFrom**

{% code overflow="wrap" %}
```
    function sendFrom(address _from, uint16 _dstChainId, bytes32 _toAddress, uint _amount, uint _minAmount, LzCallParams calldata _callParams) external payable;
```
{% endcode %}

<table data-header-hidden><thead><tr><th width="195.33333333333331">Name</th><th width="128">Type</th><th>Description</th></tr></thead><tbody><tr><td>Name</td><td>Type</td><td>Description</td></tr><tr><td><code>_from</code></td><td>address</td><td>From address. This should be the address calling the CakeProxyOFT</td></tr><tr><td><code>_dstChainId</code></td><td>uint16</td><td><code>108</code> for Aptos mainnet</td></tr><tr><td><code>_toAddress</code></td><td>bytes32</td><td>The destination address on Aptos</td></tr><tr><td><code>_amount</code></td><td>uint256</td><td>Amount of CAKE in WEI. Please note that amounts less than 1e-8 will get dusted</td></tr><tr><td><code>_minAmount</code></td><td>uint256</td><td>Minimum receiving amount. We do not charge any fee in CAKE. But this should not be larger than <code>_amount</code> after being rounded down to 8 decimals.</td></tr><tr><td><code>_callParams</code></td><td>tuple</td><td>A set of call parameters used to define bridging behaviours. Continue reading for more detail.</td></tr></tbody></table>

{% hint style="info" %}
`sendFrom` is a payable function. You will need to pay around 0.005-0.01 in BNB for destination airdrop gas fees. This value will vary based on the price of BNB/APT.&#x20;

Please note that if you define extra gas being airdropped to your destination address, you will need to increase this number or tx will revert with `not enough natives for fees`
{% endhint %}

**How to form \`\_callParams\`**

```
{
    refundAddress,
    zroPaymentAddress,
    adapterParams
}
```

<table data-header-hidden><thead><tr><th width="220.33333333333331">Name</th><th width="128">Type</th><th>Description</th></tr></thead><tbody><tr><td>Name</td><td>Type</td><td>Description</td></tr><tr><td><code>refundAddress</code></td><td>address</td><td>Excess fee (BNB) will be returned to this address </td></tr><tr><td><code>zroPaymentAddress</code></td><td>address</td><td><code>0x0000000000000000000000000000000000000000</code></td></tr><tr><td><code>adapterParams</code></td><td>bytes</td><td>A set of parameters to define destination gas airdropping. Continue reading for more detail.</td></tr></tbody></table>

**How to form \`adapterParams\`**

```
{
    version,
    dstGasLimit,
    dstNativeGasTransferAmount,
    dstNativeGasTransferAddress
}
```

<table data-header-hidden><thead><tr><th width="220.33333333333331">Name</th><th width="128">Type</th><th>Description</th></tr></thead><tbody><tr><td>Name</td><td>Type</td><td>Description</td></tr><tr><td><code>version</code></td><td>uint16</td><td>Default is <code>2</code></td></tr><tr><td>dstGasLimit</td><td>uint</td><td>Default is <code>200000</code></td></tr><tr><td>dstNativeGasTransferAmount</td><td>uint</td><td>Amount destination native gas token to airdrop. Use <code>0</code> if you don't need the bridge to convert BNB and airdrop you APT</td></tr><tr><td>dstNativeGasTransferAddress</td><td>bytes</td><td>The destination address that receives native gas tokens on destination chain</td></tr></tbody></table>

```
const adapterParams = utils.solidityPack(
    ["uint16", "uint", "uint", "bytes"],
    [2, 200000, 0, "0xYourAptosAddress"]
)
```

## Utilities

* [GUI - CAKE - Aptos PancakeBridge](https://bridge.pancakeswap.finance/aptos)
* [LayerZeroScan - track your crosschain txs](https://layerzeroscan.com/)
* [LayerZero Docs](https://layerzero.gitbook.io/docs/)

## Audits

[OtterSec's PancakeSwap CAKE OFT (Bridging) security audit](broken-reference)
