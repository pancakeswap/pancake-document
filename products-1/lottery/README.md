# 🎟 Lottery

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-Mb9tAOu9rIhmt0lIx9B%2F-Mb9vDSB5AtWkkhkidXE%2Fdocs%20masthead%20%283%29.png?alt=media&token=d540b023-92e5-4716-a3db-dcb902d3d62a)

The PancakeSwap Lottery game works as you'd expect a lottery to work. Users can purchase a ticket with their CAKE between draws. The ticket will give them one entry into the lottery. After the winning numbers are drawn, if your ticket's numbers match the drawn numbers, you'll win stacks of CAKE!

The Lottery is temporarily disabled as changes are being made to the lottery system. Look forward to details of the new Lottery soon!

## **Specifics:** <a id="specifics"></a>

* Lottery Ticket Fee for 1 ticket: 1 CAKE
* Single User Lottery Entry Limit: No overall limit, but only 50 can be bought at one time through the UI
* Paying for one ticket will give users a random 4 digit combination with each digit being between 1-14, for e.g. “1-9-3-2”

## **How to win:** <a id="how-to-win"></a>

To win the lottery jackpot \(50% of the entire lottery pool\), users need to match all 4 numbers on their ticket in the **exact same order** as the 4 winning numbers.

If you don’t match all 4, no need to worry. As long as you match 2 or more numbers in the correct order, you are guaranteed to win a prize.

### **Winning ratio:** <a id="winning-ratio"></a>

* Match all 4 numbers in the exact order = win 50% of the pot \(or split the pot if more than 1 winner\).
* Match 3 numbers in the exact order = win or split 20% of the pot.
* Match 2 numbers in the exact order = win or split 10% of the pot.
* Burn the remaining 20% of the pot.

Please note - in the event that no participants were able to match 3 numbers on any draw, the 20% allocated to winners will then be burned accordingly.

For example, if the final 4 winning numbers are “1-9-3-2”:

* “2-3-9-1” = match 0
* **“1-9-3-2” = match all 4**
* “1-9-2-2” = match 3
* “2-3-3-2” = match 2
* “1-2-1-2” = match 2

## **Lottery phases:** <a id="lottery-phases"></a>

Each full lottery session is completed every 12 hours \(2 per day\), with the timings for each as below:

3 AM - 2 PM \(UTC\)

3 PM - 2 AM \(UTC\)

3 AM - 2 PM \(UTC\) - **20,000 CAKE tokens are injected into this lottery draw**

3 PM - 2 AM \(UTC\)

An example of a lottery session starting at 3 AM \(UTC\) is as below:

### **Phase 1 - Buy tickets \(3 AM to 2 PM\)** <a id="phase-1-buy-tickets-3-am-to-2-pm"></a>

* You have 1 hour to buy tickets.
* The lottery jackpot will accumulate at the top of the page with each ticket bought.
* Users will receive a ticket \(comprised of 4 digits\) for each 1 CAKE paid.

### **Phase 2 - Lottery draw! \(2 PM\)** <a id="phase-2-lottery-draw-2-pm"></a>

* The 4 winning lottery numbers are drawn and will appear on the page.
* Each participant’s winnings will be automatically calculated based on their ticket numbers and shown on the page.
* Users can claim winnings if they have any.
* Users will also be able to see the lottery results: How many users matched all 4 numbers, 3 numbers and 2 numbers.

### **Phase 3 - Celebration and sharing \(2 PM - 3PM\)** <a id="phase-3-celebration-and-sharing-2-pm-3pm"></a>

If you won, congrats! Share with your friends or in our community groups.

The next lottery will start in 1 hour!

## **How are ticket numbers drawn?** <a id="how-are-ticket-numbers-drawn"></a>

The lottery aims to be completely random. Even though the ticket numbers given out are determined by a front-end logic, there is an extremely low chance that anyone is able to determine the 4 winning numbers ahead of time.

* The 1st lottery number will be determined based on the %10 remainder of a hash encoded by the blockhash and the number of participating users at the entry deadline.
* The 2nd lottery number will be determined based on the %10 remainder of a hash encoded by the blockhash and the total pooled cake balance at the entry deadline.
* The 3rd lottery number will be determined based on the %10 remainder of a hash encoded by the blockhash and the timestamp of the last lottery participant at the entry deadline.
* The 4th lottery number will be determined based on the %10 remainder of a hash encoded by the blockhash and the block difficulty at the entry deadline.

