# ❓ FAQ

### 1. Como funciona a tolerância de Slippage nos swaps Cross-chain?

Para swaps Cross-chain, a porcentagem de tolerância de Slippage selecionada é aplicada de forma independente aos swaps tanto na blockchain de origem quanto na de destino.

**Exemplo:**

* Swap de BNB na BNB Chain para ARB no Arbitrum
* Tolerância de Slippage configurada em 1%
* A rota poderia ser:
  1. Fazer swap de BNB para USDC na BNB Chain
  2. Fazer bridge de USDC da BNB Chain para o Arbitrum via Across
  3. Fazer swap de USDC para ARB no Arbitrum
* Nesse caso, a tolerância de Slippage de 1% se aplica separadamente a:
  * O swap na BNB Chain
  * O swap no Arbitrum

Isso garante que você esteja protegido contra movimentos de preço excessivos em ambas as etapas da transação, enquanto o processo de bridging em si não é afetado pelas configurações de Slippage.

### 2. O que acontece se minha transação falhar?

Se o seu swap Cross-chain encontrar uma falha em qualquer etapa, veja como ela é tratada:

1.  **Falha de Swap/Transação na Blockchain de Origem**

    ➝ Você receberá instantaneamente seu token original de volta na blockchain de origem.
2.  **Falha na Transação de Bridge**

    ➝ O Across processará um reembolso em até 90 minutos a 2 horas, e você receberá o ativo bridgeado de volta na blockchain de origem. Já o Relay processa o reembolso em menos de um minuto nesses cenários entre SOL <> EVM.
3.  **Falha de Swap na Blockchain de Destino**

    ➝ Você receberá o ativo bridgeado na blockchain de destino, sem o swap final para o token desejado.

{% hint style="info" %}
**Nota:** Você pode sempre verificar o status das suas transações através da aba de histórico de transações na interface de conexão da carteira.
{% endhint %}

### 3. Meus swaps Cross-chain são protegidos contra MEV?

O MEV Guard só é suportado na BNB Chain quando os swaps são iniciados diretamente de uma carteira conectada com o MEV Guard habilitado.

* Se o seu swap Cross-chain envolver um swap na BNB Chain como blockchain de origem, e você tiver o MEV Guard habilitado, esse swap será protegido contra MEV.
* Se a BNB Chain for a blockchain de destino, o swap é executado pelo relayer/sistema de bridging e não será protegido contra MEV, pois não é iniciado pela sua carteira conectada.

{% hint style="info" %}
**Nota:** Outras blockchains como Arbitrum e Base atualmente não suportam proteção MEV Guard na PancakeSwap.
{% endhint %}

### 4. Posso fazer swap de stablecoins entre blockchains?

Sim — você pode fazer swap e bridge de stablecoins como USDC, USDT e DAI diretamente entre quaisquer blockchains suportadas.

Você tem duas opções:

1.  **Bridge Direto:**

    Fazer bridge de stablecoins suportadas (como USDC, USDT, etc) diretamente de uma blockchain para outra.
2.  **Swap para Outros Tokens:**

    Você também pode fazer swap de uma stablecoin para qualquer outro token suportado na blockchain de destino usando os pools de liquidez da PancakeSwap — antes ou depois do bridging.

{% hint style="info" %}
**Nota:** As stablecoins suportadas para bridging direto podem variar por blockchain.
{% endhint %}

### 5. Meus swaps usarão PCSX?

Não — PCSX não é suportado para execução de swaps Cross-chain.

Os swaps Cross-chain na PancakeSwap são roteados exclusivamente por:

* **Pools de liquidez da PancakeSwap** (v2, v3, Infinity, StableSwap) para swaps on-chain, e
* **Protocolos Across & Relay** para bridging de ativos entre blockchains.

PCSX não pode ser usado para facilitar ou rotear nenhuma parte de uma transação de swap Cross-chain.

### 6. Existe um limite mínimo ou máximo para o valor do swap?

Sim — tanto limites mínimos quanto máximos se aplicam às transações Cross-chain.

* **Limite Máximo:**\
  Depende da liquidez de bridge disponível para o token e blockchain selecionados. Esse valor pode flutuar em tempo real com base nas condições de rede e liquidez.
* **Limite Mínimo:**\
  Definido para garantir que seja economicamente viável para os relayers processarem a transação de bridge.

{% hint style="info" %}
**Nota:** Os limites mínimos e máximos exatos variam conforme o token de bridge. Se o valor da sua transação estiver fora do intervalo permitido, a interface exibirá uma mensagem de erro clara e solicitará que você ajuste o valor.
{% endhint %}
