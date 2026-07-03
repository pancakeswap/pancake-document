---
description: Orientati su Github di Pancake
---

# Panoramica del Codebase

## Introduzione

Tutti i nostri repository sono archiviati su [Github](https://github.com/pancakeswap). La maggior parte sono pubblici e puoi liberamente inviare una issue o una pull request. Assicurati di leggere questa intera guida e le linee guida specifiche di ogni repository prima.

## Repository Github

* Frontend: Il frontend principale. Contiene tutte le funzionalità non elencate di seguito.
  * [sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk) - Un SDK per costruire applicazioni su PancakeSwap
  * [aptos-swap-sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/aptos-swap-sdk) - Versione Aptos dello Swap SDK
  * [swap-sdk-core](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk-core) - Codice condiviso dello Swap SDK
  * [wagmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/wagmi) - Estensione per [wagmi](https://github.com/wagmi-dev/wagmi), inclusa la chain BSC e il connettore per il wallet Binance
  * [awgmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/awgmi) - connettiti ad Aptos con hook React simili a wagmi, inclusi gli adattatori per portafoglio.
* Smart Contract: Tutti gli smart contract distribuiti su BSC ed ETH.
* Smart Contract: Tutti gli smart contract in versione Move distribuiti su Aptos.
* Subgraph: Endpoint GraphQL per interrogare eventi ed entità.



<table><thead><tr><th width="227">Progetto</th><th>Github</th><th data-hidden>Sito web</th></tr></thead><tbody><tr><td>Frontend Monorepo</td><td><a href="https://github.com/pancakeswap/pancake-frontend">https://github.com/pancakeswap/pancake-frontend</a></td><td><a href="https://pancakeswap.finance">🔗PancakeSwap</a></td></tr><tr><td>Smart Contract</td><td><a href="https://github.com/pancakeswap/pancake-smart-contracts">https://github.com/pancakeswap/pancake-smart-contracts</a></td><td></td></tr><tr><td>Smart Contract Move</td><td><a href="https://github.com/pancakeswap/pancake-contracts-move">https://github.com/pancakeswap/pancake-contracts-move</a></td><td></td></tr><tr><td>Subgraph</td><td><a href="https://github.com/pancakeswap/pancake-subgraph">https://github.com/pancakeswap/pancake-subgraph </a></td><td></td></tr></tbody></table>
