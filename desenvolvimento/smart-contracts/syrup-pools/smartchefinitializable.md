# SmartChefInitializable

function updateStartAndEndBlocks(uint256 \_startBlock, uint256 \_bonusEndBlock) external onlyOwner {

require(block.number < startBlock, "Pool has started");

require(\_startBlock < \_bonusEndBlock, "New startBlock must be lower than new endBlock");

require(block.number < \_startBlock, "New startBlock must be higher than current block");

startBlock = \_startBlock;

bonusEndBlock = \_bonusEndBlock;

// Set the lastRewardBlock as the startBlock

lastRewardBlock = startBlock;

emit NewStartAndEndBlocks(\_startBlock, \_bonusEndBlock);
