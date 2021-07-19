# Lottery v2

## Contract info

**Contract name:** PancakeSwapLottery  
**Contract address:** 0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c  
**Random number generator address:** 0x8c6375Aab6e5B26a30bF241EBBf29AD6e6c503c2  
\(_Random number generator contract must be deployed first_\)

View [PancakeSwapLottery.sol on BscScan](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c#code).

View the [PancakeSwap: Lottery contract on BscScan](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c).

## Audits

The PancakeSwap Lottery V2 has been audited twice so far. View the results below:

[Peckshield's Lottery V2 Audit](https://github.com/peckshield/publications/blob/master/audit_reports/PeckShield-Audit-Report-PancakeswapLottery-v1.0.pdf)

[Slowmist's Lottery V2 Audit](https://github.com/slowmist/Knowledge-Base/blob/master/open-report/Smart%20Contract%20Security%20Audit%20Report%20-%20PancakeSwap%20Lottery.pdf)

## Lottery Status states

The lottery has four `Status` states, `Pending`, `Open`, `Close`, and `Claimable`, that determine which actions can and cannot be taken at a given time.

## Read/View functions

### viewCurrentLotteryId

```text
function viewCurrentLotteryId() external view override returns (uint256);
```

Returns the Id\# of the current Lottery round as an integer. Round Id\#s correlate to round number, and are incremental, e.g. the ninth round of Lottery will be `9`.

### viewLottery

```text
function viewLottery(uint256 _lotteryId) external view returns (Lottery memory);
```

Returns information on specified Lottery round as tuple \(see Lottery structure below\).

```text
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

| Name | Type | Description |
| :--- | :--- | :--- |
| `startTime` | uint256 | Starting block for Lottery round. |
| `endTime` | uint256 | Ending block for Lottery round \(approximately 12 hours after a round begins\). |
| `priceTicketInCake` | uint256 | The price of a ticket in CAKE \(approximately $5 USD\). |
| `discountDivisor` | uint256 | The divisor used to calculate bulk ticket discount. |
| `rewardsBreakdown` | uint256\[6\] | The division of rewards across brackets \(total must add up to 10,000\). |
| `treasuryFee` | uint256 | Amount taken from funds raised per round that's moved to treasury address \(maximum 3000\). |
| `cakePerBracket` | uint256\[6\] | The amount of CAKE to distribute to winners of each bracket. |
| `countWinnersPerBracket` | uint256\[6\] | Moves through brackets, starting from the highest, accounting for winners when value &gt; 0. |
| `firstTicketId` | uint256 | Id of the first ticket, set with the opening of the Lottery round, that determines the range of eligible tickets for the current round. |
| `firstTicketIdNextLottery` | uint256 | Id of the first ticket, set at the closing of current round, that determines the range of eligible tickets for the current round. |
| `amountCollectedInCake` | uint256 | The amount of CAKE collected through ticket sales for the Lottery round. |
| `finalNumber` | uint32 | The final number determined by `randomResult` obtained from the number generator contract \([RandomNumberGenerator.sol](https://bscscan.com/address/0x8c6375Aab6e5B26a30bF241EBBf29AD6e6c503c2)\) using Chainlink VRF. |

### viewNumbersAndStatusesForTicketIds

```text
function viewNumbersAndStatusesForTicketIds(uint256[] calldata _ticketIds)
    external
    view
    returns (uint32[] memory, bool[] memory);
```

Returns the corresponding numbers and the statuses of `ticketIds` array of tickets defined by their `ticketId`.

### viewRewardsForTicketId

```text
function viewRewardsForTicketId(
    uint256 _lotteryId,
    uint256 _ticketId,
    uint32 _bracket;
```

Calculates rewards for a ticket after draw given the `lotteryId`, `ticketId`, and `bracket`. Filling and querying will provide a link to detailed price information on [BscScan](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c#readContract).

| Name | Type | Description |
| :--- | :--- | :--- |
| `lotteryId` | uint256 | The id of the Lottery. |
| `ticketId` | uint256 | The id of the ticket. |
| `bracket` | uint32 | Bracket for the `ticketId` to verify the claim and calculate rewards. |

### viewUserInfoForLotteryId

```text
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

Returns user `lotteryTicketIds`, `ticketNumbers`, and `ticketStatuses` of a user for a given Lottery \(defined by `lotteryID`\).

| Name | Type | Description |
| :--- | :--- | :--- |
| `user` | address | The address of the user. |
| `lotteryId` | uint256 | The id of the Lottery. |
| `cursor` | uint256 | Cursor to start where to retrieve the tickets. |
| `size` | uint256 | The number of tickets to retrieve. |

### calculateRewardsForTicketId

```text
    function _calculateRewardsForTicketId(
        uint256 _lotteryId,
        uint256 _ticketId,
        uint32 _bracket
    ) internal view returns (uint256);
```

Calculates rewards for a ticket after draw given the `lotteryId`, `ticketId`, and `bracket`.

| Name | Type | Description |
| :--- | :--- | :--- |
| `lotteryId` | uint256 | The id of the Lottery. |
| `ticketId` | uint256 | The id of the ticket. |
| `bracket` | uint32 | Bracket for the `ticketId` to verify the claim and calculate rewards. |

### calculateTotalPriceForBulkTickets

```text
    function calculateTotalPriceForBulkTickets(
        uint256 _discountDivisor,
        uint256 _priceTicket,
        uint256 _numberTickets
    ) external pure returns (uint256);
```

Calculates the price for a set of tickets accounting for bulk discount.

discountDivisor:

$$totalPriceForBulkTickets = priceSingleTicket \cdot numberTickets \cdot \frac{(discountDivisor + 1 - numberTickets)}{discountDivisor}$$

Filling and querying will provide a link to detailed price information on BscScan.

| Name | Type | Description |
| :--- | :--- | :--- |
| `discountDivisor` | uint256 | The divisor for the discount. |
| `priceTickets` | uint256 | The price of a ticket in CAKE. |
| `numberTickets` | uint256 | The number of tickets to buy. |

## Write functions \(users\)

### buyTickets

```text
function buyTickets(uint256 _lotteryId, uint32[] calldata _ticketNumbers) external override notContract nonReentrant;
```

Buy tickets for the current `Open` Lottery round \(between 1 and 100 per purchase\). Calculates the price per ticket using `calculateTotalPriceForBulkTickets`.

| Name | Type | Description |
| :--- | :--- | :--- |
| `lotteryId` | uint256 | The id of the lottery. |
| `ticketNumbers` | uint32 | Array of ticket numbers between 1,000,000 and 1,999,999. |

### claimTickets

```text
    function claimTickets(
        uint256 _lotteryId,
        uint256[] calldata _ticketIds,
        uint32[] calldata _brackets
    ) external override notContract nonReentrant;
```

Claim a set of winning tickets for a `Claimable` Lottery round. Checks `lotteryId` to determine if round is claimable, ownership of `ticketId`, eligibility of ticket \(`ticketId` falls between `firstTicketId` and `firstTicketIdNextLottery`\), and whether `ticketId` falls within eligible prize `bracket` \(between 0 and 5\).

| Name | Type | Description |
| :--- | :--- | :--- |
| `lotteryId` | uint256 | The id of the Lottery. |
| `ticketIds` | uint32 | Array of `ticketId`s. |
| `brackets` | uint32 | Array of brackets for the ticket ids. |

## Write functions \(operator/admin\)

### closeLottery

```text
function closeLottery(uint256 _lotteryId) external override onlyOperator;
```

Closes the `Open` Lottery to `Close` state. Emits `LotteryClose` event.

| Name | Type | Description |
| :--- | :--- | :--- |
| `lotteryId` | uint256 | The id of the Lottery. |

### drawFinalNumberAndMakeLotteryClaimable

```text
    function drawFinalNumberAndMakeLotteryClaimable(uint256 _lotteryId, bool _autoInjection) external override onlyOperator nonReentrant;
```

Lottery must be in `Close` state. Draws the final Lottery number for results from `randomResult`, calculates the rewards for brackets after accounting for treasury fee, makes Lottery state `Claimable`, and transfers treasury fee to treasury address.

| Name | Type | Description |
| :--- | :--- | :--- |
| `lotteryId` | uint256 | The id of the Lottery. |
| `autoInjection` | bool | Automatic injection status. |

### changeRandomNumberGenerator

```text
    function changeRandomGenerator(address _randomGeneratorAddress) external onlyOwner;
```

Changes the random number generator contract address. Lottery must be `Claimable`.

| Name | Type | Description |
| :--- | :--- | :--- |
| `randomGeneratorAddress` | address | The random generator address. |

### injectFunds

```text
function injectFunds(uint256 _lotteryId, uint256 _amount) external override onlyOwner;
```

Inject funds into a Lottery. Lottery must be `Open`.

| Name | Type | Description |
| :--- | :--- | :--- |
| `lotteryId` | uint256 | The id of the Lottery. |
| `amount` | uint256 | Amount, in CAKE token, to inject. |

### startLottery

```text
    function startLottery(
        uint256 _endTime,
        uint256 _priceTicketInCake,
        uint256 _discountDivisor,
        uint256[6] calldata _rewardsBreakdown,
        uint256 _treasuryFee
    ) external override onlyOperator;
```

Starts the Lottery, setting it to `Open` state. Status must be `Claimable`.

| Name | Type | Description |
| :--- | :--- | :--- |
| `endTime` | uint256 | End time of the Lottery. |
| `priceTicketInCake` | uint256 | Price of a ticket in CAKE. |
| `discountDivisor` | uint256 | The divisor to calculate the discount magnitude for bulks. |
| `rewardsBreakdown` | uint256\[6\] | Breakdown of rewards per bracket \(must sum to 10,000\). |
| `trasuryFee` | uint256 | Treasury fee \(10,000 = 100%, 100 = 1%\). |

### recoverWrongTokens

```text
function recoverWrongTokens(address _tokenAddress, uint256 _tokenAmount) external onlyOwner;
```

Allows admin to recover incorrect tokens sent to address mistakenly. Cannot be CAKE tokens.

| Name | Type | Description |
| :--- | :--- | :--- |
| `tokenAddress` | address | The address of the token to withdraw. |
| `tokenAmount` | uint256 | The number of tokens to withdraw. |

### setMinAndMaxTicketPriceInCake

```text
function recoverWrongTokens(address _tokenAddress, uint256 _tokenAmount) external onlyOwner;
```

Allows admin to set upper and lower limit of ticket price in CAKE value. Minimum price must be lower than maximum price.

| Name | Type | Description |
| :--- | :--- | :--- |
| `minPriceTicketInCake` | uint256 | The minimum price in CAKE. |
| `maxPriceTicketInCake` | uint256 | The maximum price in CAKE. |

### setMaxNumberTicketsPerBuy

```text
function setMaxNumberTicketsPerBuy(uint256 _maxNumberTicketsPerBuy) external onlyOwner;
```

Set max number of tickets purchasable at a time \(presently 100\). Max number of tickets must be higher than 0.

| Name | Type | Description |
| :--- | :--- | :--- |
| `maxNumberTicketsPerBuy` | uint256 | Max number of tickets in one purchase. |

### setOperatorAndTreasuryAndInjectorAddress

```text
function setOperatorAndTreasuryAddresses(address _operatorAddress, address _treasuryAddress) external onlyOwner;
```

Sets the address of the Lottery operator.

| Name | Type | Description |
| :--- | :--- | :--- |
| `operatorAddress` | address | The address of the operator. |
| `treasuryAddress` | address | The address of the treasury. |
| `injectorAddress` | address | The address of the injector. |

## Events \(User\)

### TicketsPurchase

```text
TicketsPurchase(address indexed buyer, uint256 indexed lotteryId, uint256 numberTickets);
```

Lottery tickets are purchased.

Emitter: `buyTickets` [go to buyTickets](lottery-v2.md#buytickets)

### TicketsClaim

```text
TicketsClaim(address indexed claimer, uint256 amount, uint256 indexed lotteryId, uint256 numberTickets);
```

Lottery tickets are claimed post-draw.

Emitter: `claimTickets` [go to claimTickets](lottery-v2.md#claimtickets)

## Events \(admin\)

### AdminTokenRecovery

```text
AdminTokenRecovery(address token, uint256 amount);
```

Admin recovers incorrect tokens from Lottery address.

Emitter: `recoverWrongTokens` [go to recoverWrongTokens](lottery-v2.md#recoverwrongtokens)

### LotteryClose

```text
LotteryClose(uint256 indexed lotteryId, uint256 firstTicketIdNextLottery);
```

The Lottery is closed. lotteryId is indexed and `firstTicketIdNextLottery` is determined by `currentTicketId`.

Emitter: `closeLottery` [go to closeLottery](lottery-v2.md#closelottery)

### LotteryInjection

```text
LotteryInjection(uint256 indexed lotteryId, uint256 amount);
```

Funds are injected into Lottery.

Emitter: `injectFunds` [go to injectFunds](lottery-v2.md#injectfunds)

### LotteryOpen

```text
LotteryOpen(
        uint256 indexed lotteryId,
        uint256 startTime,
        uint256 endTime,
        uint256 priceTicketInCake,
        uint256 firstTicketId
    );
```

The Lottery is opened. `firstTicketId` is set from `currentTicketId`,

Emitter: `startLottery` [go to startLottery](lottery-v2.md#startlottery)

### LotteryNumberDrawn

```text
LotteryNumberDrawn(uint256 indexed lotteryId, uint256 finalNumber, uint256 countWinningTickets);
```

Lottery numbers are drawn for Lottery round.

Emitter: `drawFinalNumberAndMakeLotteryClaimable` go to [drawFinalNumberAndMakeLotteryClaimable](lottery-v2.md#drawfinalnumberandmakelotteryclaimable)

### NewOperatorAndTreasuryAndInjectorAddresses

```text
NewOperatorAndTreasuryAndInjectorAddresses(address operator, address treasury);
```

New operator address is set.

Emitter: `setOperatorAndTreasuryAndInjectorAddresses` [go to setOperatorAndTreasuryAndInjectorAddresses](lottery-v2.md#setoperatorandtreasuryandinjectoraddress)

### NewRandomNumberGenerator

```text
NewRandomGenerator(address indexed randomGenerator);
```

New random number generator address is set.

Emitter: `changeRandomGenerator` [go to changeRandomGenerator](lottery-v2.md#changerandomnumbergenerator)

