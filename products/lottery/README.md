# 🎟 Lottery v2

![](../../.gitbook/assets/docs-masthead-3-%20%282%29.png)

Playing the PancakeSwap Lottery gives you a chance to win huge CAKE prizes! It's easy, fair, and you can enter as often as you like as long as you have the CAKE to buy a ticket.

[View smart contract](https://bscscan.com/address/0x5aF6D33DE2ccEC94efb1bDF8f92Bd58085432d2c)

## **Specifics:**

* Lottery ticket cost for 1 ticket: ~$5 USD in CAKE.
* Individual user Lottery entry limit: No overall limit, but only 100 tickets can be bought at a time.
* Paying for one ticket will give users a random 6-digit combination with each digit being between 0-9, for e.g. “1-9-3-2-0-4”. Match numbers from the left to win prizes—the more numbers that match, the bigger the prize pool you'll share in.
* Lottery uses Chainlink's implementation of VRF for true, secure randomness.

## Ticket costs and bulk purchase discount

Lottery ticket prices are set at the start of the new lottery round, and target $5 USD \(may vary slightly with sudden price fluctuations\).

Buying multiple Lottery tickets at once gives a bulk discount on your purchase. You can buy as many as 100 tickets in one purchase, with the discount starting small at 2 tickets, and scaling up to 4.95% at 100 tickets.

![](../../.gitbook/assets/image%20%2850%29.png)

## **How to win**

Match numbers, **from the left side of your ticket**, to the winning numbers drawn at the end of a Lottery round.

* Matching even just the first number will win you a small prize. 
* Match more numbers and win a share of a larger prize pool. 
* Matching the 6 numbers exactly and win a share of 40% of the total prizes raised!

## **‌**Prize eligibility

‌There are a total of six lottery balls, from 0 to 9, on each ticket. To win, your numbers need to match the drawn numbers in the same order as the lottery balls, starting from the left of the ticket. For example:

Drawn numbers

![Drawn Numbers](../../.gitbook/assets/image%20%2857%29.png)

Your ticket's numbers

![Your Ticket A](../../.gitbook/assets/image%20%2895%29.png)

In the example above, Ticket A, five of the ticket's numbers match the same drawn numbers, in the exact same order: all except the fourth one.

However, since the fourth digit does **not** match the drawn number, only the first three digits count as matching in order. This would win a "Match first 3" prize.

![Your Ticket B](../../.gitbook/assets/image%20%2851%29.png)

Example Ticket B. Here's an unlucky one. Even though the last five digits match, the first digit doesn't match, so this ticket doesn't win anything at all.

You will only share in prizes from the highest prize bracket you are eligible for. A ticket matching the first three numbers will only be eligible for prizes from the match-three bracket, and not for the match-one or match-two brackets.

**Remember: The digits must match in order, starting from left to right.**

## Prize sharing across prize brackets

‌After a round is drawn, and tickets with matching numbers are determined, the prizes are awarded. The amount won by each ticket will depend on how many other tickets won in the same prize bracket.

‌For example, if you have the only ticket that matched three numbers in order, and the predetermined share of the prize pool for your bracket was 2000 CAKE, you'll receive the full 2000 CAKE.

‌If, however, you and three other people match three numbers in order, the 2000 CAKE would be split between the four winning tickets, meaning you would receive 500 CAKE.

See the [Lottery FAQ for a breakdown of prizes](lottery-faq.md#how-are-prizes-broken-down-between-brackets) across each bracket.

