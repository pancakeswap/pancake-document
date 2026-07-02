# Como usar Ordens Limitadas

As ordens limitadas com geração de taxas na PancakeSwap funcionam de forma diferente das ordens limitadas tradicionais. Quando um usuário coloca uma ordem limitada, ele está efetivamente fornecendo **liquidez unilateral** a um pool PancakeSwap Infinity.

À medida que o preço de mercado se move, os swaps no pool podem usar a liquidez do usuário. Quando isso acontece, os tokens depositados são totalmente convertidos nos tokens de saída, e o usuário recebe:

* Os tokens de saída, e
* As taxas de negociação ganhas com os swaps executados contra sua liquidez.

***

**Exemplo: Vendendo BNB por USDT**

* **Preço atual no pool BNB/USDT:** 600 USDT por BNB
* **Preço alvo / limite do usuário:** 700 USDT por BNB

Processo:

1. O usuário define uma ordem limitada para vender BNB a 700 USDT.
2. Seu BNB é depositado no tick mais próximo do preço de 700 USDT por BNB no pool.
3. Quando o preço de mercado externo atingir 700 USDT, o preço do pool se ajusta para corresponder (devido a oportunidades de arbitragem / melhor precificação).
4. Nesse ponto, o BNB do usuário é convertido em USDT.
5. Durante esse processo, o usuário ganha taxas de cada swap que consome sua liquidez.
6. Uma vez que a liquidez é totalmente consumida, o USDT convertido (mais as taxas) é automaticamente retirado e enviado para a carteira do usuário.

***

### Guia passo a passo

Escolha um par de tokens (ex.: BNB/CAKE) e o valor que deseja vender / comprar

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.07%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Defina seu preço alvo / limite

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.07.35%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Coloque a ordem limitada e "Confirme". A liquidez é colocada em seu nome no tick mais próximo do preço limite

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%2011.08.49%20AM.png" alt="" width="375"><figcaption></figcaption></figure>

Quando o preço do pool atingir seu alvo, sua ordem é executada. Os tokens de saída desejados + taxas são automaticamente retirados e enviados para sua carteira.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%201.01.47%20PM.png" alt="" width="370"><figcaption></figcaption></figure>



### Status da Ordem

Você pode ver o status da sua ordem clicando aqui

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202025-09-28%20at%202.12.50%20PM.png" alt="" width="375"><figcaption></figcaption></figure>

**Sua ordem pode estar em um dos seguintes estados:**

| Status               | Descrição                                                                                            |
| -------------------- | ---------------------------------------------------------------------------------------------------- |
| Pendente             | Aguardando o preço atingir seu alvo                                                                  |
| Executada            | Ordem executada e fundos enviados para sua carteira                                                  |
| Parcialmente Execut. | Apenas parte da sua ordem foi executada. Você manterá ambos os tokens (ex.: parte BNB, parte USDT)  |
| Cancelada            | Você cancelou a ordem. Todos os seus fundos são devolvidos a você                                    |

### FAQs

**P: Preciso pagar taxas para colocar uma ordem limitada?**

R: Não. Em vez disso, você ganha 0,1% em taxas de negociação quando sua ordem é executada.

**P: Posso colocar ordens para qualquer par?**

R: No lançamento, apenas pares selecionados são suportados. Mais pares serão adicionados posteriormente.

**P: Qual é o tamanho mínimo da ordem?**

R: $50. Isso evita ordens muito pequenas que poderiam resultar em excesso de gas.&#x20;

**P: O que acontece se apenas parte da minha ordem for executada?**

R: Você manterá ambos os tokens. Você pode cancelar a qualquer momento e retirar ambos os tokens mais as taxas ganhas.

**P: Minha ordem foi executada, mas ainda não recebi os fundos na minha carteira?**

R: Em cenários muito raros isso pode acontecer, mas seus fundos estão sempre seguros. Basta usar o botão "Sacar" nos detalhes da ordem para reivindicar os fundos manualmente.
