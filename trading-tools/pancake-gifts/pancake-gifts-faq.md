# FAQ dos Pancake Gifts

Este FAQ aborda como os Pancake Gifts funcionam nos bastidores, o que esperar em diferentes cenários e por que certas escolhas de design foram feitas.

***

## 1. 🔐 Comportamento e Acesso ao Código do Presente

### **1.1 Por que o código do presente não é armazenado?**

**Intencionalmente não armazenamos** o código do presente em:

* Armazenamento local do frontend
* Bancos de dados do backend

Isso protege:

* Privacidade do usuário
* Segurança contra comprometimento do dispositivo
* Resgates acidentais ou maliciosos de presentes

### **1.2 Posso regenerar ou recuperar o código do presente mais tarde?**

Não. O código do presente:

* É exibido **apenas uma vez** durante a criação
* Está incorporado no **link** ou **código QR** gerado
* **Não será exibido novamente** na interface ou no histórico

{% hint style="warning" %}
Se o código for perdido e você não salvou o link ou QR, o presente não pode ser resgatado manualmente. Em vez disso, para recuperar o valor do seu presente, você pode cancelá-lo manualmente.
{% endhint %}

### **1.3 O código do presente ainda estará incorporado no link ou QR de compartilhamento?**

Sim:

* O link de compartilhamento inclui o código do presente (ex.: `pancakeswap.finance/gift#code=xxxx`)
* O código QR também incorpora o código do presente, mas **não pode ser regenerado posteriormente.**&#x20;

{% hint style="success" %}
**Dica Profissional:** Baixe a imagem assim que ela for gerada
{% endhint %}

* Resgates manuais requerem o código real do presente — sem alternativa se o link/QR for perdido

## 2. 🎁 Status do Presente e Expiração

### **2.1 Posso verificar se um presente foi resgatado, cancelado ou expirado?**

Sim. A seção **Histórico de Presentes** mostra:

* Status: Pendente / Resgatado / Cancelado / Expirado / Não Resgatável
* Detalhes do presente (token, valor, tipo, rede, timestamps)

### **2.2 O que acontece quando um presente expira?**

Se um presente não for resgatado dentro do prazo padrão de **7 dias**:

* O **valor total do presente é reembolsado** à Carteira do criador
* A **taxa fixa de gas do resgate (\~$0,05) não é devolvida**

## 3. 🧠 Lógica de Resgate e Limitações

### **3.1 Os usuários podem resgatar um presente em uma rede diferente da qual foi criado?**

Não. Um presente está **vinculado à rede**:

* Um presente criado na **BSC** deve ser resgatado na **BSC**
* O envio de presentes cross-chain não é suportado atualmente

## 4. ⛽ Taxas de Gas e Design

### **4.1 Como é decidido o valor fixo de gas para criação do presente?**

Definimos um preço fixo de gas com base nas condições atuais da BNB Chain (\~5 vezes o valor de Gas recomendado atualmente).

Esse buffer:

* Protege contra picos repentinos de gas
* Garante que os presentes permaneçam resgatáveis sob volatilidade normal

\
Exemplo

* **Recomendado atualmente: 0,1 Gwei** (veja: [BNB Gas Tracker](https://bscscan.com/gastracker))
* **Portanto, Taxa fixa de gas do resgate = 0,1 Gwei x 5 = 0,5 Gwei**


