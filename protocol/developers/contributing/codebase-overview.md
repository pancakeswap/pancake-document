---
description: Pancake Github पर अपना रास्ता खोजें
---

# Codebase Overview

## परिचय

हमारे सभी repositories [Github](https://github.com/pancakeswap) पर संग्रहीत हैं। उनमें से अधिकांश public हैं, और आप स्वतंत्र रूप से issue या pull request submit कर सकते हैं। सुनिश्चित करें कि आप इस पूरी guide और प्रत्येक repository के लिए specific guidelines पहले पढ़ें।

## Github repositories

* Frontend: मुख्य frontend। इसमें वे सभी features शामिल हैं जो नीचे सूचीबद्ध नहीं हैं।
  * [sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk) - Pancakeswap के ऊपर applications बनाने के लिए एक SDK
  * [aptos-swap-sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/aptos-swap-sdk) - Swap SDK का Aptos version
  * [swap-sdk-core](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk-core) - Swap SDK Shared code
  * [wagmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/wagmi) - [wagmi](https://github.com/wagmi-dev/wagmi) के लिए Extension, जिसमें bsc chain और binance wallet connector शामिल है
  * [awgmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/awgmi) - similar wagmi React hooks के साथ Aptos से connect करें। Wallet adapters सहित।
* Smart Contract: BSC और ETH पर deployed सभी smart contracts।
* Smart Contract: Aptos पर deployed सभी smart contracts के Move version।
* Subgraph: events और entities query करने के लिए GraphQL endpoint।



<table><thead><tr><th width="227">Project</th><th>Github</th><th data-hidden>Website</th></tr></thead><tbody><tr><td>Frontend Monorepo</td><td><a href="https://github.com/pancakeswap/pancake-frontend">https://github.com/pancakeswap/pancake-frontend</a></td><td><a href="https://pancakeswap.finance">🔗PancakeSwap</a></td></tr><tr><td>Smart Contract</td><td><a href="https://github.com/pancakeswap/pancake-smart-contracts">https://github.com/pancakeswap/pancake-smart-contracts</a></td><td></td></tr><tr><td>Smart Contract Move</td><td><a href="https://github.com/pancakeswap/pancake-contracts-move">https://github.com/pancakeswap/pancake-contracts-move</a></td><td></td></tr><tr><td>Subgraph</td><td><a href="https://github.com/pancakeswap/pancake-subgraph">https://github.com/pancakeswap/pancake-subgraph </a></td><td></td></tr></tbody></table>
