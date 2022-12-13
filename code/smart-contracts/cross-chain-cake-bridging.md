---
description: PancakeSwap uses LayerZero OFT for Cross Chain CAKE Bridging
---

# Cross Chain CAKE Bridging

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

| Name          | Type    | Description                                                                                                                                      |
| ------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `_from`       | address | From address. This should be the address calling the CakeProxyOFT                                                                                |
| `_dstChainId` | uint16  | `108` for Aptos mainnet                                                                                                                          |
| `_toAddress`  | bytes32 | The destination address on Aptos                                                                                                                 |
| `_amount`     | uint256 | Amount of CAKE in WEI. Please note that amounts less than 1e-8 will get dusted                                                                   |
| `_minAmount`  | uint256 | Minimum receiving amount. We do not charge any fee in CAKE. But this should not be larger than `_amount` after being rounded down to 8 decimals. |
| `_callParams` | tuple   | A set of call parameters used to define bridging behaviours. Continue reading for more detail.                                                   |

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

| Name                | Type    | Description                                                                                  |
| ------------------- | ------- | -------------------------------------------------------------------------------------------- |
| `refundAddress`     | address | Excess fee (BNB) will be returned to this address                                            |
| `zroPaymentAddress` | address | `0x0000000000000000000000000000000000000000`                                                 |
| `adapterParams`     | bytes   | A set of parameters to define destination gas airdropping. Continue reading for more detail. |

**How to form \`adapterParams\`**

```
{
    version,
    dstGasLimit,
    dstNativeGasTransferAmount,
    dstNativeGasTransferAddress
}
```

| Name                        | Type   | Description                                                                                                             |
| --------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------- |
| `version`                   | uint16 | Default is `2`                                                                                                          |
| dstGasLimit                 | uint   | Default is `200000`                                                                                                     |
| dstNativeGasTransferAmount  | uint   | Amount destination native gas token to airdrop. Use `0` if you don't need the bridge to convert BNB and airdrop you APT |
| dstNativeGasTransferAddress | bytes  | The destination address that receives native gas tokens on destination chain                                            |

```javascript
const adapterParams = utils.solidityPack(
    ["uint16", "uint", "uint", "bytes"],
    [2, 200000, 0, "0xYourAptosAddress"]
)
```

## Utilities

* [GUI - CAKE - Aptos PancakeBridge](https://bridge.pancakeswap.finance/aptos)
* [LayerZeroScan - track your crosschain txs](https://layerzeroscan.com/)
* [LayerZero Docs](https://layerzero.gitbook.io/docs/)
