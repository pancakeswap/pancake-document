---
description: Direct swap with Market Maker
---

# Market Maker Pool

## Contract info

**Contract name: MM Pool**



**BSC**

**Contract address:** [0xfEACb05b373f1A08E68235bA7FC92636b92ced01](https://bscscan.com/address/0xfEACb05b373f1A08E68235bA7FC92636b92ced01#code)

[View on BscScan](https://bscscan.com/address/0xfEACb05b373f1A08E68235bA7FC92636b92ced01)



**ETH**

**Contract address:** [0x9Ca2A439810524250E543BA8fB6E88578aF242BC](https://etherscan.io/address/0x9Ca2A439810524250E543BA8fB6E88578aF242BC#code)

[View on Etherscan](https://etherscan.io/address/0x9Ca2A439810524250E543BA8fB6E88578aF242BC)



### Example of Swapping

#### EIP 712 Signature

```
const domain = {
  name: "PCS MM Pool",
  version: "1",
  chainId: // 1 or 56,
  verifyingContract: // please refer to the address above,
};

const quoteType = {
  Quote: [
    { name: "nonce", type: "uint256" },
    { name: "user", type: "address" },
    { name: "baseToken", type: "address" },
    { name: "quoteToken", type: "address" },
    { name: "baseTokenAmount", type: "uint256" },
    { name: "quoteTokenAmount", type: "uint256" },
    { name: "expiryTimestamp", type: "uint256" },
  ],
};

const quoteValue = {
    nonce,
    user,
    baseToken,
    quoteToken,
    baseTokenAmount,
    quoteTokenAmount,
    expiryTimestamp,
};

// EIP 712 Signature
const signature = await mm._signTypedData(domain, quoteType, quoteValue);
```



<table><thead><tr><th width="214">Name</th><th width="123.33333333333331">Type</th><th>Description</th></tr></thead><tbody><tr><td>nonce</td><td>uint256</td><td>The user nonce can be called from <code>getUserNonce</code> in the contract</td></tr><tr><td>user</td><td>address</td><td>user address</td></tr><tr><td>baseToken</td><td>address</td><td>The token address that the user is sending to the market maker</td></tr><tr><td>quoteToken</td><td>address</td><td>The token address that the user is receiving from the market maker</td></tr><tr><td>baseTokenAmount</td><td>uint256</td><td>The amount of base token in the swap</td></tr><tr><td>quoteTokenAmount</td><td>uint256</td><td>The amount of quote token in the swap</td></tr><tr><td>expiryTimestamp</td><td>uin256</td><td>The expiry time of the signature in unix</td></tr></tbody></table>

#### swap

```
struct Quote {
    uint256 nonce;
    address user;
    address baseToken;
    address quoteToken;
    uint256 baseTokenAmount;
    uint256 quoteTokenAmount;
    uint256 expiryTimestamp;
}

function swap(
        address _mmSigner,
        Quote calldata _quote,
        bytes calldata _signature
    ) external payable
```

| Name        | Type    | Description                        |
| ----------- | ------- | ---------------------------------- |
| \_mmSigner  | address | The market maker address           |
| \_quote     | Quote   | The Quote struct                   |
| \_signature | bytes   | The signature generated from above |
