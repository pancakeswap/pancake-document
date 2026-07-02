# Como as Taxas do CAKE.PAD Funcionam nas Vendas Overflow – Com Exemplo

1. As taxas são cobradas apenas **se o** evento CAKE.PAD **estiver sobresubscrito**
   1. Sobresubscrição = Depósitos totais de todos os usuários > Valor da meta de captação.
   * A taxa é deduzida apenas dos fundos excedentes comprometidos pelos participantes. Nenhuma taxa é paga pelo projeto parceiro CAKE.PAD.
   * O projeto parceiro CAKE.PAD recebe 100% do valor alvo de captação.
   * As taxas CAKE.PAD são coletadas em CAKE, e 100% delas serão queimadas.
   * As taxas são baseadas na **taxa total de subscrição do pool** (% da meta de captação):

**Taxa de Sobresubscrição <> Nível de Taxa**&#x20;

<table data-full-width="false"><thead><tr><th>Taxa de Sobresubscrição</th><th>Nível de Taxa</th></tr></thead><tbody><tr><td>≥ 0x</td><td>1,00%</td></tr><tr><td>≥ 50x</td><td>0,80%</td></tr><tr><td>≥ 100x</td><td>0,60%</td></tr><tr><td>≥ 150x</td><td>0,50%</td></tr><tr><td>≥ 200x</td><td>0,40%</td></tr><tr><td>≥ 250x</td><td>0,30%</td></tr><tr><td>≥ 300x</td><td>0,25%</td></tr><tr><td>≥ 400x</td><td>0,20%</td></tr><tr><td>≥ 500x</td><td>0,15%</td></tr><tr><td>≥ 650x</td><td>0,12%</td></tr><tr><td>≥ 800x</td><td>0,10%</td></tr><tr><td>≥ 1500x</td><td>0,05%</td></tr></tbody></table>



2. **Período de tempo – Quando a taxa é cobrada**

* A taxa é cobrada no **final do** evento CAKE.PAD, quando o usuário resgata sua alocação.
* Mesmo se um usuário subscrever cedo (ex.: quando a subscrição está em 30% da meta de captação), a taxa final é baseada no **nível final de sobresubscrição do pool**.
  * Exemplo: Se o pool terminar com 50x de sobresubscrição, a taxa aplicável é o nível de 50x (0,8%).

#### Passos de Cálculo

1.  **Alocação do usuário** = % do pool total de tokens parceiros CAKE.PAD que o usuário recebe

    ```jsx
    user_allocation = user_deposit_amount / totalAmountPool
    ```
2.  **Valor pago pelo usuário** = Porção do depósito do usuário usada para resgatar tokens parceiros CAKE.PAD

    ```jsx
    user_pay_amount = raisingAmountPool * user_allocation
    ```
3.  **Valor de reembolso** = Excesso do depósito do usuário não usado para compra de tokens parceiros CAKE.PAD

    ```jsx
    refund_amount = user_deposit_amount - user_pay_amount
    ```
4.  **Valor da taxa** = Dedução aplicada no valor reembolsado do usuário

    * O nível de taxa é baseado na % da meta de captação (veja a tabela acima).

    ```jsx
    tax_amount = fee tier * refund_amount
    ```
5.  **Resultado final para o usuário**

    ```jsx
    1. Alocação de tokens = user_allocation * totalTokensOffered
    2. Valor da taxa do usuário = tax_amount
    3. final_refund = refund_amount - tax_amount (se aplicável, caso contrário = refund_amount)
    ```

#### Exemplo Numérico

* **Meta de captação (raisingAmountPool):** 100 CAKE
* **Seu depósito (user\_deposit\_amount):** 10 CAKE
* **Depósitos totais incl. do seu depósito (totalAmountPool):** 5.100 CAKE (51x subscrito = 5.100% da meta de captação, implica taxa de sobresubscrição de 50x)
  * Nível de taxa correspondente = 0,80% (baseado na tabela de taxa acima)

**Passos:**

1. `user_allocation = 10 / 5.100 = 0,00196 (0,196% de alocação no pool)`
2. `user_pay_amount = 100 × 0,00196 = 0,196 CAKE`
3. `refund_amount = 10 − 0,196 = 9,804 CAKE`
4. `tax_amount = 9,804 × 0,008 = 0,0784 CAKE`
5. `final_refund = 9,804 − 0,0784 = ~9,72 CAKE`

**Valores finais recebidos pelo usuário**

1. **Alocação de tokens:** 0,196 CAKE equivalente em tokens parceiros CAKE.PAD
2. **Reembolso final:** \~9,72 CAKE (de 10 CAKE depositados − 0,196 CAKE para alocação de tokens − 0,0784 CAKE de taxa)
