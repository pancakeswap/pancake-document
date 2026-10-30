# 🧙 Página 1

## Como sacar seu NFT do NFT Marketplace da PancakeSwap

As páginas do NFT Marketplace da PancakeSwap não estão mais disponíveis, mas o contrato inteligente do marketplace continua ativo. Se você listou um NFT para venda e ele nunca foi vendido, ele ainda está retido pelo contrato do marketplace. Você mesmo pode recuperá-lo cancelando a listagem diretamente no BscScan.

Isso leva alguns minutos por NFT e custa apenas uma pequena quantia de BNB em gas.

### Antes de começar

Você vai precisar de:

* **A mesma carteira que você usou para listar o NFT.** Somente a carteira que criou uma listagem pode cancelá-la.
* **Uma carteira de navegador** (por exemplo, MetaMask, extensão da Trust Wallet ou extensão da Binance Wallet) configurada na **BNB Smart Chain**.
* **Uma pequena quantia de BNB** para pagar o gas. Cada NFT é sacado em uma transação própria.

Deixe estes endereços à mão:

| Item                       | Endereço                                     |
| -------------------------- | -------------------------------------------- |
| Contrato do marketplace    | `0x17539cCa21C7933Df5c980172d22659B8C345C5A` |
| Coleção Pancake Squad      | `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA` |
| Coleção Pancake Bunnies    | `0xDf7952B35f24aCF7fC0487D01c8d5690a60DBa07` |

> **Mantenha-se seguro**
>
> * Interaja somente com o contrato do marketplace `0x17539cCa21C7933Df5c980172d22659B8C345C5A`. Sempre confira o endereço na URL do BscScan.
> * Sacar seu NFT **nunca** exige o envio de BNB ou tokens, e nunca exige a assinatura de uma aprovação (`approve` ou `setApprovalForAll`). Se um site ou pessoa pedir isso, é golpe.
> * A PancakeSwap nunca vai enviar DM nem pedir sua frase semente.

### Passo 1: Encontre os NFTs que você ainda tem listados

Para cada NFT que você quer sacar, você precisa de duas informações: o **endereço da coleção** e o **token ID**.

1. Abra a [página Read Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#readContract) do contrato do marketplace no BscScan.
2. Encontre e expanda **`viewAsksByCollectionAndSeller`**.
3. Preencha os campos:
   * `collection`: o endereço da coleção da tabela acima (por exemplo, o Pancake Squad é `0x0a8901b0E25DEb55A87524f0cC164E9644020EBA`)
   * `seller`: o endereço da sua carteira
   * `cursor`: `0`
   * `size`: `100`
4. Clique em **Query**.
5. Veja o resultado de `tokenIds`. Esses são os token IDs que você ainda tem listados naquela coleção e são os NFTs que você pode sacar.
6. Se você listou NFTs em mais de uma coleção, repita os passos 3 a 5 para cada coleção.

**Se `tokenIds` estiver vazio (`[]`)**, você não tem listagens ativas naquela coleção. Seu NFT foi vendido (nesse caso, você já recebeu o BNB) ou você cancelou a listagem anteriormente (nesse caso, ele já está de volta na sua carteira).

**Se você tem mais de 100 listagens** em uma coleção, o último número do resultado é o próximo cursor. Faça a consulta novamente usando esse número como `cursor` para ver o restante.

**Se o seu NFT é de uma coleção diferente de Pancake Squad ou Pancake Bunnies**, expanda **`viewCollections`** na mesma página, insira `cursor = 0` e `size = 100` e clique em **Query** para ver todas as coleções compatíveis com o marketplace.

### Passo 2: Saque seu NFT

1. Abra a [página Write Contract](https://bscscan.com/address/0x17539cCa21C7933Df5c980172d22659B8C345C5A#writeContract) do contrato do marketplace no BscScan.
2. Clique em **Connect to Web3** e conecte a mesma carteira que listou o NFT. Verifique se sua carteira está na BNB Smart Chain.
3. Encontre e expanda **`cancelAskOrder`**.
4. Preencha os campos:
   * `_collection`: o endereço da coleção do Passo 1
   * `_tokenId`: o token ID do Passo 1, como um número simples (por exemplo, `1234`)
5. Clique em **Write** e confirme a transação na sua carteira. Você não envia nenhum BNB; você paga apenas o gas.
6. Quando a transação for concluída com sucesso, o NFT estará de volta na sua carteira.
7. Repita para cada NFT que você quer sacar.

Para confirmar que funcionou, execute o Passo 1 novamente. O token ID não deve mais aparecer na lista.

### Solução de problemas

| Problema                                                  | O que significa e o que fazer                                                                                                                                                                                |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Erro: `Order: Token not listed`                           | A carteira conectada não listou este token ID nesta coleção, ou o NFT já foi vendido ou sacado. Verifique se você está usando a carteira original e o endereço da coleção e o token ID corretos. |
| O botão Write não faz nada                                | Provavelmente sua carteira está na rede errada. Troque para a BNB Smart Chain e reconecte.                                                                                                                      |
| Sem gas ou saldo insuficiente                             | Adicione uma pequena quantia de BNB à sua carteira para cobrir o gas.                                                                                                                                                |
| Não tenho mais acesso à carteira que listou o NFT         | Somente a carteira original pode cancelar a listagem. Ninguém, nem mesmo a PancakeSwap, pode sacá-lo em seu nome.                                                                                             |
