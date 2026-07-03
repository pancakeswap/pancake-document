---
description: Encontre o seu caminho no Github da Pancake
---

# Visão Geral do Código Base

## Introdução

Todos os nossos repositórios são armazenados no [Github](https://github.com/pancakeswap). A maioria deles é pública e você pode enviar livremente um problema ou um pull request. Certifique-se de ler todo este guia e as diretrizes específicas para cada repositório antes.

## Repositório do Github

* Front-end: O front-end principal. Ele contém todos os recursos que não estão listados abaixo.&#x20;
  * [sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk) - Um SDK para criar aplicativos em cima da Pancakeswap&#x20;
  * [aptos-swap-sdk](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/aptos-swap-sdk) - versão Aptos do SDK do Swap&#x20;
  * [swap-sdk-core](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/swap-sdk-core)  - Código do SDK compartilhado  do Swap
  * [wagmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/wagmi)  - Extensão para [wagmi](https://github.com/wagmi-dev/wagmi), incluindo bsc  chain e conector de carteira binance&#x20;
  * [awgmi](https://github.com/pancakeswap/pancake-frontend/blob/develop/packages/awgmi) - conecte-se à Aptos com hooks semelhantes do wagmi React. Incluindo adaptadores de carteira.
* Contrato Inteligente: Todos os contratos inteligentes implantados na BSC e ETH.&#x20;
* Contrato Inteligente: Toda a versão Move de contratos inteligentes implantados na Aptos.&#x20;
*   Subgraph: Endpoint do GraphQL para consultar os eventos e entidades.





| Projeto             | Github                                                                                                                                                                        | Stack                                                                                                                                                                                                                                                                    | Website                                            |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------- |
| Frontend Monorepo   | <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image%20%283%29%20%285%29.png" alt="" data-size="line">[https://github.com/pancakeswap/pancake-frontend](https://github.com/pancakeswap/pancake-frontend) | <img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/download.svg" alt="" data-size="line"><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/ts-logo-round-128.svg" alt="" data-size="line">                                                                                                                    | [🔗Netlify](https://pancakeswap-uikit.netlify.app) |
| Smart Contract      | [https://github.com/pancakeswap/pancake-smart-contracts](https://github.com/pancakeswap/pancake-smart-contracts)                                                              | <img src="https://ludu-assets.s3.amazonaws.com/lesson-icons/26/OS6xpcvmIL6y0G3ZQW99" alt="" data-size="line"><img src="https://hardhat.org/apple-touch-icon.png" alt="" data-size="line"><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/ts-logo-round-128.svg" alt="" data-size="line"> |                                                    |
| Smart Contract Move | [https://github.com/pancakeswap/pancake-contracts-move](https://github.com/pancakeswap/pancake-contracts-move)                                                                |                                                                                                                                                                                                                                                                          |                                                    |
| Subgraph            | [https://github.com/pancakeswap/pancake-subgraph](https://github.com/pancakeswap/pancake-subgraph)                                                                            | <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/GraphQL_Logo.svg/1200px-GraphQL_Logo.svg.png" alt="" data-size="line">                                                                                                                               |                                                    |

