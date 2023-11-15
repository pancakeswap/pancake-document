---
description: v2
---

# 彩票

## Contract info

**Contract name:** PancakeSwapLottery\
**Contract address:** 0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c\
**Random number generator address:** 0x8c6375Aab6e5B26a30bF241EBBf29AD6e6c503c2\
(_Random number generator contract must be deployed first_)

View [PancakeSwapLottery.sol on BscScan](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c#code).

View the [PancakeSwap: Lottery contract on BscScan](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c).

## Audits

The PancakeSwap Lottery V2 has been audited twice so far. View the results below:

[Peckshield's Lottery V2 Audit](https://github.com/peckshield/publications/blob/master/audit\_reports/PeckShield-Audit-Report-PancakeswapLottery-v1.0.pdf)

[Slowmist's Lottery V2 Audit](https://github.com/slowmist/Knowledge-Base/blob/master/open-report/Smart%20Contract%20Security%20Audit%20Report%20-%20PancakeSwap%20Lottery.pdf)

## Lottery Status states

The lottery has four `Status` states, `Pending`, `Open`, `Close`, and `Claimable`, that determine which actions can and cannot be taken at a given time.

## Read/View functions

### viewCurrentLotteryId

```
function viewCurrentLotteryId() external view override returns (uint256);
```

Returns the Id# of the current Lottery round as an integer. Round Id#s correlate to round number, and are incremental, e.g. the ninth round of Lottery will be `9`.

### viewLottery

```
function viewLottery(uint256 _lotteryId) external view returns (Lottery memory);
```

Returns information on specified Lottery round as tuple (see Lottery structure below).

```
        uint256 startTime;
        uint256 endTime;
        uint256 priceTicketInCake;
        uint256 discountDivisor;
        uint256[6] rewardsBreakdown; // 0: 1 matching number // 5: 6 matching numbers
        uint256 treasuryFee; // 500: 5% // 200: 2% // 50: 0.5%
        uint256[6] cakePerBracket;
        uint256[6] countWinnersPerBracket;
        uint256 firstTicketId;
        uint256 firstTicketIdNextLottery;
        uint256 amountCollectedInCake;
        uint32 finalNumber;
```

| Name                       | Type        | Description                                                                                                                                                                                                          |
| -------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `startTime`                | uint256     | Starting block for Lottery round.                                                                                                                                                                                    |
| `endTime`                  | uint256     | Ending block for Lottery round (approximately 12 hours after a round begins).                                                                                                                                        |
| `priceTicketInCake`        | uint256     | The price of a ticket in CAKE (approximately $5 USD).                                                                                                                                                                |
| `discountDivisor`          | uint256     | The divisor used to calculate bulk ticket discount.                                                                                                                                                                  |
| `rewardsBreakdown`         | uint256\[6] | The division of rewards across brackets (total must add up to 10,000).                                                                                                                                               |
| `treasuryFee`              | uint256     | Amount taken from funds raised per round that's moved to treasury address (maximum 3000).                                                                                                                            |
| `cakePerBracket`           | uint256\[6] | The amount of CAKE to distribute to winners of each bracket.                                                                                                                                                         |
| `countWinnersPerBracket`   | uint256\[6] | Moves through brackets, starting from the highest, accounting for winners when value > 0.                                                                                                                            |
| `firstTicketId`            | uint256     | Id of the first ticket, set with the opening of the Lottery round, that determines the range of eligible tickets for the current round.                                                                              |
| `firstTicketIdNextLottery` | uint256     | Id of the first ticket, set at the closing of current round, that determines the range of eligible tickets for the current round.                                                                                    |
| `amountCollectedInCake`    | uint256     | The amount of CAKE collected through ticket sales for the Lottery round.                                                                                                                                             |
| `finalNumber`              | uint32      | The final number determined by `randomResult` obtained from the number generator contract ([RandomNumberGenerator.sol](https://bscscan.com/address/0x8c6375Aab6e5B26a30bF241EBBf29AD6e6c503c2)) using Chainlink VRF. |

### viewNumbersAndStatusesForTicketIds

```
function viewNumbersAndStatusesForTicketIds(uint256[] calldata _ticketIds)
    external
    view
    returns (uint32[] memory, bool[] memory);
```

Returns the corresponding numbers and the statuses of `ticketIds` array of tickets defined by their `ticketId`.

### viewRewardsForTicketId

```
function viewRewardsForTicketId(
    uint256 _lotteryId,
    uint256 _ticketId,
    uint32 _bracket;
```

Calculates rewards for a ticket after draw given the `lotteryId`, `ticketId`, and `bracket`. Filling and querying will provide a link to detailed price information on [BscScan](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c#readContract).

| Name        | Type    | Description                                                           |
| ----------- | ------- | --------------------------------------------------------------------- |
| `lotteryId` | uint256 | The id of the Lottery.                                                |
| `ticketId`  | uint256 | The id of the ticket.                                                 |
| `bracket`   | uint32  | Bracket for the `ticketId` to verify the claim and calculate rewards. |

### viewUserInfoForLotteryId

```
    function viewUserInfoForLottery(
        address _user,
        uint256 _lotteryId,
        uint256 _cursor,
        uint256 _size
    )
        external
        view
        returns (
            uint256[] memory,
            uint32[] memory,
            bool[] memory,
            uint256
        )
```

Returns user `lotteryTicketIds`, `ticketNumbers`, and `ticketStatuses` of a user for a given Lottery (defined by `lotteryID`).

| Name        | Type    | Description                                    |
| ----------- | ------- | ---------------------------------------------- |
| `user`      | address | The address of the user.                       |
| `lotteryId` | uint256 | The id of the Lottery.                         |
| `cursor`    | uint256 | Cursor to start where to retrieve the tickets. |
| `size`      | uint256 | The number of tickets to retrieve.             |

### calculateRewardsForTicketId

```
    function _calculateRewardsForTicketId(
        uint256 _lotteryId,
        uint256 _ticketId,
        uint32 _bracket
    ) internal view returns (uint256);
```

Calculates rewards for a ticket after draw given the `lotteryId`, `ticketId`, and `bracket`.

| Name        | Type    | Description                                                           |
| ----------- | ------- | --------------------------------------------------------------------- |
| `lotteryId` | uint256 | The id of the Lottery.                                                |
| `ticketId`  | uint256 | The id of the ticket.                                                 |
| `bracket`   | uint32  | Bracket for the `ticketId` to verify the claim and calculate rewards. |

