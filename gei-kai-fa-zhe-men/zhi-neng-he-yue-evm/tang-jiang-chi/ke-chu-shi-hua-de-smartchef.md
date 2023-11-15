---
description: SmartChefInitializable
---

# 可初始化的 SmartChef

## Contract Roles

| Role              | Description        |
| ----------------- | ------------------ |
| Owner (onlyOwner) | The contract owner |

### Owner

Address can be different depending on the pool, however, is usually `0xad9d97fc7bf0ac6dc68d478dcb3709454519b358`

This address controlled is by gnosis multisignature contract with a threshold of 3/6

## Functions

### `emergencyRewardWithdraw` - Owner

```typescript
    function emergencyRewardWithdraw(uint256 _amount) external onlyOwner {
        rewardToken.safeTransfer(address(msg.sender), _amount);
    }
```

In case of an emergency, the **Owner** can withdraw the rewards from a pool contract.

### `recoverWrongTokens` - Owner

```typescript
 function recoverWrongTokens(address _tokenAddress, uint256 _tokenAmount) external onlyOwner {
        require(_tokenAddress != address(stakedToken), "Cannot be staked token");
        require(_tokenAddress != address(rewardToken), "Cannot be reward token");

        IBEP20(_tokenAddress).safeTransfer(address(msg.sender), _tokenAmount);

        emit AdminTokenRecovery(_tokenAddress, _tokenAmount)
```

Used by the **Owner** to recover tokens other than the `stakedToken` and `rewardToken` in case they are mistakenly sent to the contract.

### `stopRewards` - Owner

```typescript
    function stopReward() external onlyOwner {
        bonusEndBlock = block.number;
    }
```

If a pool need stop distributing rewards prior to the intended end of the reward distribution, the **Owner** can call this function.

### `updatePoolLimitPerUser` - Owner

```typescript
function updatePoolLimitPerUser(bool _hasUserLimit, uint256 _poolLimitPerUser) external onlyOwner {
        require(hasUserLimit, "Must be set");
        if (_hasUserLimit) {
            require(_poolLimitPerUser > poolLimitPerUser, "New limit must be higher");
            poolLimitPerUser = _poolLimitPerUser;
        } else {
            hasUserLimit = _hasUserLimit;
            poolLimitPerUser = 0;
        }
        emit NewPoolLimit(poolLimitPerUser);
    }
```

**Owner** can call this function to update the staking limit for each pool. The staking limit can only be increased, never decreased. This ensures that no user ever has more staked than the staking limit.

### `UpdateRewardPerBlock` - Owner

```typescript
 function updateRewardPerBlock(uint256 _rewardPerBlock) external onlyOwner {
        require(block.number < startBlock, "Pool has started");
        rewardPerBlock = _rewardPerBlock;
        emit NewRewardPerBlock(_rewardPerBlock);
    }
```

Can be called by the **Owner**, but only prior to the start of the pool. This cannot be modified once the pool has begun.

### `updateStartAndEndBlocks` - Owner

```typescript
   function updateStartAndEndBlocks(uint256 _startBlock, uint256 _bonusEndBlock) external onlyOwner {
        require(block.number < startBlock, "Pool has started");
        require(_startBlock < _bonusEndBlock, "New startBlock must be lower than new endBlock");
        require(block.number < _startBlock, "New startBlock must be higher than current block");

        startBlock = _startBlock;
        bonusEndBlock = _bonusEndBlock;

        // Set the lastRewardBlock as the startBlock
        lastRewardBlock = startBlock;

        emit NewStartAndEndBlocks(_startBlock, _bonusEndBlock);
    }
```

Can be called by the **Owner**, but only prior to the start of the pool. This cannot be modified once the pool has begun.

### `transferOwnership` - Owner

```typescript
        transferOwnership(_admin);
    }
```

If the **Owner** needs to change the ownership of the contract, they can call this function.
