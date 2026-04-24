---
description: >-
  we understand you may have questions about our latest upgrade. We've compiled
  this comprehensive FAQ to address all your inquiries. Let's dive in:
---

# PancakeSwap Infinity FAQ

**Q1 How will PancakeSwap Infinity benefit traders and liquidity providers?**

**Ans:** PancakeSwap Infinity brings a lot of advantages for both traders and liquidity providers:

**1. Streamlined Operations and Gas Savings:** Through features like Singleton and Flash Accounting, PancakeSwap Infinity drastically reduces gas fees. Singleton consolidates all pools into a single contract, slashing deployment costs by 99%. Flash Accounting optimizes accounting processes by computing net balances for transactions, minimizing gas consumption.

**2. Direct Benefits from Advanced Features:** The integration of hooks allows for implementing dynamic fees, custom order types, and active liquidity management modules. Liquidity providers can enjoy mitigated impermanent loss (IL), MEV protection, and access to various fee tiers, ensuring more profitable and secure trading experiences.

\
**3. Flexibility in AMM Designs:** PancakeSwap Infinity supports multiple pool types, including CLAMM and the LBAMM, allowing traders and LP to pick different pool types. This inclusive approach also allows supporting any future assets requiring new pricing curves. Check out this blog to [learn more](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-15 at 16.16.56.png" alt=""><figcaption></figcaption></figure>

**Q2** How will PancakeSwap Infinity benefit developers and defi protocols?

**Ans:** PancakeSwap Infinity opens up a world of possibilities for developers and DeFi protocols.&#x20;

**1. Endless Customization Possibilities:** With PancakeSwap Infinity, developers can build Hooks to introduce custom functionalities; from dynamic fees to on-chain limit orders and custom oracles. PancakeSwap Infinity supports deploying new pool types (CLAMM, LBAMM, and any other pool types in the future), enhancing capital efficiency and trading flexibility.

**2. Access to Robust Liquidity and User Base:** With over 1.8 million active users and $2.1 billion in liquidity, developers and DeFi protocols have an unparalleled opportunity to tap into a vast and active community, fostering product development and adoption.

**3. Revenue Generation Opportunities:** Developers can establish a consistent revenue stream through hook fees, allowing them to set fees for utilizing their hooks. By monetizing their innovations with fees, developers can contribute to the growth and development of the PancakeSwap ecosystem. Check out this blog to[ learn more](https://blog.pancakeswap.finance/articles/everything-you-need-to-know-about-pancake-swap-v4-what-s-in-it-for-developers-traders-liquidity-providers-and-defi-protocols)

<figure><img src="../../.gitbook/assets/Screenshot 2024-03-15 at 09.40.42.png" alt=""><figcaption></figcaption></figure>

**Q3** What improvements does PancakeSwap Infinity bring compared to v3?

**Ans:** PancakeSwap Infinity introduces the capability to enhance liquidity pool functionalities with custom features without re-implementing the core protocol. It also supports the implementation of any pricing curve on the go and offers substantial gas savings for users.

**Q4** Will there be any changes to the user interface or user experience in PancakeSwap Infinity?

**Ans:** Users can swap on Infinity through PancakeSwap’s swapping page, just like the usual friendly experience. Traders and liquidity providers have multiple options to add liquidity across supported pool types, including CLAMM and LBAMM.

**Q5** How can the community get involved in testing or providing feedback for PancakeSwap Infinity?

**Ans:** If you're a community member, feel free to share your feedback through our socials on [Telegram](https://t.me/PancakeSwapAnn), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315), and [Twitter](https://twitter.com/PancakeSwap). If you're a developer, join our developer Discord community and share your thoughts.

**Q6** Where can users find more information about PancakeSwap Infinity and stay updated on its development progress?

**Ans:** Visit our official [website](https://pancakeswap.finance/v4?utm_source=v4announcementblog\&utm_medium=blog\&utm_campaign=v4announcementblog\&utm_id=v4announcementblog) , read our [whitepaper](https://github.com/pancakeswap/pancake-v4-core/blob/main/docs/whitepaper-en.pdf) , and follow us on social media for the latest updates and developments.  If you're a developer, join our developer Discord community.\
\
**Q7** What is the licensing mechanism for PancakeSwap Infinity?

**Ans:** PancakeSwap Infinity is committed to open-source principles. Our code will be released under an open-source license, empowering developers to innovate freely. However, As a part of our [Affiliate initiative](https://forum.pancakeswap.finance/t/discussion-on-pancakeswap-affiliates-a-multichain-expansion-strategy/395), DeFi protocols forking PancakeSwap will be warmly welcomed and officially recognized by the Kitchen.\
\
**Q8** How does PancakeSwap Infinity reduce gas fees?

**Ans:** PancakeSwap Infinity leverages the Singleton and Flash accounting mechanisms to reduce gas fees significantly. By consolidating all pools into a single contract (singleton), multi-pool transactions are simplified, making them more cost-effective. Flash Accounting replaces individual transfers with net balances, computed collectively at the end of each transaction, resulting in substantial gas savings. ERC-6909 further reduces gas for frequent users by letting users keep their funds within the protocol and use them when required, eliminating transfers to/from their wallets.\
\
**Q9** What are Hooks in PancakeSwap Infinity, and how do they enable innovation?

**Ans:** Hooks are customizable add-ons that enhance liquidity pool functionality, allowing developers to introduce custom features and fee management options. Deployed externally, Hooks can execute predefined logic during key pool actions, offering endless possibilities, including dynamic fees, order types, custom oracles, and active liquidity management strategies. Check out this blog to [learn more](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks)\
\
**Q10** What opportunities does PancakeSwap Infinity present for developers?

**Ans:** Developers can build innovative solutions, generate revenue through hook fees, and tap into PancakeSwap's extensive user base and deep liquidity. Read our dedicated [blog post](https://blog.pancakeswap.finance/articles/why-should-developers-build-on-pancake-swap-v4-and-how-to-build-hooks) on why developers should build on PancakeSwap.

**Q11** How does PancakeSwap Infinity contribute to the broader DeFi ecosystem?

**Ans:** PancakeSwap Infinity aims to address the shortcomings of current AMMs, enhance the DEX experience, and evolve into the highest-functionality DeFi platform supported by our open-source approach. Read our Head Chef, Chef Mochi's [vision for Infinity](https://blog.pancakeswap.finance/articles/chef-mochi-s-vision-for-pancake-swap-v4-a-leap-forward-in-de-fi-innovation) to learn more\
\
**Q12** Where can we find the hook template repository?

**Ans:** Hooks template can be found at [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) and example hooks at [https://github.com/pancakeswap/infinity-hooks](https://github.com/pancakeswap/infinity-hooks)\
\
**Q13** Can you explain the life cycles of hooks and their examples?

**Ans:** Hooks can be implemented before / after 5 key actions namely initialize, swap, addLiquidity, removeLiquidity, donate. For instance, when a user initiates a swap, the PoolManager contract checks if a beforeSwap hook callback exists. If it does, the logic under the beforeSwap method in the hook contract is executed; otherwise, the swap proceeds as usual. After the swap is completed, the same process occurs for the afterSwap callback.\
\
**Q14:** Do we need to perform address mining to ensure hooks are deployed at a specific address?\
**Ans:** Hooks can be deployed on any address like other contracts. Callback permissions are set at PoolKey. For more info, please see the faq for hooks here&#x20;

[https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook](https://developer.pancakeswap.finance/contracts/infinity/overview/custom-layer-hook)\
\
**Q15:** How can we verify a hook contract on etherscan?&#x20;

**Ans:** If you are using foundry, you can refer to the foundry guide here [https://book.getfoundry.sh/reference/forge/forge-verify-contract](https://book.getfoundry.sh/reference/forge/forge-verify-contract) \
Or if you are using hardhat, refer to the hard guide here [https://hardhat.org/hardhat-runner/docs/guides/verifying](https://hardhat.org/hardhat-runner/docs/guides/verifying)\
\
**Q16:** Should we use foundry or hardhat for hook development?

**Ans:** The template [https://github.com/pancakeswap/infinity-hooks-template](https://github.com/pancakeswap/infinity-hooks-template) is based on foundry; thus, we advise using foundry. Besides that, the foundry has been growing in popularity!&#x20;

**Q17:** What are pool keys?&#x20;

**Ans:** PoolKey is a struct that describes each pool. See more [here](https://developer.pancakeswap.finance/contracts/infinity/overview/amm-layer-poolmanager).\
\
\
PancakeSwap Infinity represents a significant milestone in the DeFi space, offering unparalleled benefits for traders, developers, liquidity providers, and the broader community. We're excited to embark on this journey with you and look forward to shaping the future of DeFi together. We hope this FAQ has answered your questions about PancakeSwap Infinity. If you have any further questions, feel free to reach out to us via  ([Twitter](https://twitter.com/PancakeSwap), [Discord](https://discord.com/channels/897834609272840232/1207724381212770315), and [Telegram](https://t.me/PancakeSwap)) or check our Dev [documentation](https://developer.pancakeswap.finance).
