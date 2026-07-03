# Arbitrum

Le 31 août 2023, PancakeSwap Perpetuals lancera le programme de récompenses de trading V2 sur Arbitrum. Les utilisateurs qui stakent des [ALP dans le Syrup Pool CAKE](https://pancakeswap.finance/pools?chain=arb) sur Arbitrum peuvent bénéficier de multiplicateurs de boost. De plus, il n'y a pas de période de vesting pour les récompenses gagnées dans ce programme. Les utilisateurs peuvent réclamer leurs récompenses en USDC à tout moment. Les détails sont les suivants :

Date de début : 31 août 2023, 08:00 (UTC)

Période d'activité (Epoch) : Chaque jeudi à 08:00:00 UTC jusqu'au jeudi suivant à 07:59:59, soit 1 semaine.

Heure de distribution des récompenses : Chaque cycle va de 00:00 (UTC) à 23:59 (UTC) quotidiennement. Les récompenses sont émises chaque jeudi vers 08:00 (UTC). Après la mise à jour du niveau de l'utilisateur, les récompenses seront calculées et distribuées. Les utilisateurs ont 30 jours pour réclamer leurs récompenses après leur émission. Passé ce délai, la plateforme révoque les récompenses non réclamées.&#x20;

Montant des récompenses : Pour les 5 premières semaines, 25% des frais de trading (en USDC). Ce pool de prix sera ensuite distribué selon les niveaux.

Règles d'activité : Les utilisateurs qui tradent sur PancakeSwap Perpetuals V2 sur Arbitrum seront éligibles au pool de prix.

### Répartition des niveaux

Chaque jeudi à 08:00:00 UTC, nous calculons les données de trading depuis le jeudi précédent à 08:00:00 UTC jusqu'à ce jeudi à 07:59:59, puis mettons à jour le niveau de l'utilisateur selon les règles de niveau suivantes (la configuration peut être modifiée) :

<table><thead><tr><th width="161">Niveau</th><th width="249.33333333333331">Description</th><th>Poids</th></tr></thead><tbody><tr><td>Diamant</td><td>Volume de trading de l'epoch >= 1M USD</td><td>5</td></tr><tr><td>Or</td><td>Volume de trading de l'epoch >= 500K USD</td><td>3</td></tr><tr><td>Argent</td><td>Volume de trading de l'epoch >= 250K USD</td><td>1</td></tr></tbody></table>

**Remarque : Les critères de niveau et les poids sont susceptibles d'être modifiés en fonction de la Liquidité du pool et de l'activité de trading globale sur la plateforme.**

Les récompenses seront distribuées équitablement entre tous les utilisateurs qui atteignent un certain niveau.

### Formule de calcul des récompenses de trading :&#x20;

À la fin de chaque cycle de récompenses de trading, le volume de trading effectif de l'utilisateur dans ce cycle sera calculé pour déterminer la pondération et le montant des récompenses en USDC.

La formule pour le nombre de récompenses spécifiques est : r = min{R \* W/Sum(Wi), R \* 20%\}, les paramètres sont les suivants :

<table data-header-hidden><thead><tr><th width="139"></th><th></th></tr></thead><tbody><tr><td>r</td><td>Montant de récompenses USDC à miner par l'utilisateur pour l'epoch en cours</td></tr><tr><td>R</td><td>La récompense de l'epoch en cours R=(valeur USDC des frais ETH + valeur USDC des frais DAI + valeur USDC des frais BTC + frais USDC)*0,25, dont 1% de frais Swap à déduire lors du règlement. Par exemple : si les frais ETH hebdomadaires sont de 1 et le prix ETH est de 2 000, la valeur USDC des frais ETH = 1 * 2000 * 0,99</td></tr><tr><td>W</td><td>Poids correspondant au niveau de l'utilisateur</td></tr><tr><td>Sum(Wi)</td><td>Score de poids total de tous les utilisateurs. Wi représente le poids d'un utilisateur, et sum(Wi) représente la somme des poids de tous les utilisateurs.</td></tr></tbody></table>

* Le partage maximum des revenus par utilisateur est plafonné à 20% des revenus réservés au programme.

Conditions générales

* En raison des différences de frais de trading pour chaque paire V2, les récompenses reçues par les utilisateurs peuvent varier même si leurs volumes de trading effectifs sont identiques.
* Les récompenses à distribuer pour chaque cycle seront stockées à l'adresse de contrat suivante :&#x20;
* PancakeSwap/ApolloX se réserve le droit d'interprétation finale de cette activité.



Avertissement sur les risques : Le trading de futures crypto comporte des risques substantiels. Toutes les activités de trading sont effectuées à votre discrétion et à vos propres risques. Les informations ici présentes ne doivent pas être considérées comme des conseils financiers ou d'investissement de la part de PancakeSwap/ApolloX. PancakeSwap/ApolloX ne sera pas responsable des pertes pouvant résulter de votre utilisation de PancakeSwap/ApolloX.

<br>
