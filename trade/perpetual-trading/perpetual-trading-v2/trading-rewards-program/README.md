---
description: ApolloX lancera le programme de récompenses de trading sur V2
hidden: true
---

# Programme de Récompenses de Trading

### Présentation du programme de récompenses

Les détails sont les suivants :

Période d'activité : Les dates varient d'un cycle à l'autre et selon les chaînes.

Heure de distribution des récompenses : Chaque cycle va de 00:00 (UTC) à 23:59 (UTC) quotidiennement. Les récompenses sont émises le lendemain vers 03:00 (UTC). Les utilisateurs ont 30 jours pour réclamer leurs récompenses après leur émission. Passé ce délai, la plateforme révoques les récompenses non réclamées.&#x20;

Montant des récompenses : Plafonné à 15 000 USD en APX par jour.

Règles d'activité : Les utilisateurs qui tradent sur V2 gagnent des récompenses d'un pool de prix. Ceux qui stakent des APX dans le DAO pour obtenir un veNFT bénéficieront de multiplicateurs de boost correspondant à la valeur Power calculée depuis le veNFT.&#x20;

| Valeur Power               | Multiplicateur de boost  |
| ------------------------- | -------------------- |
| 50 000 < Power =<100 000  | 1,5                  |
| 100 000 < Power =<300 000 | 2                    |
| Power > 300 000           | 2,5                  |

Formule de calcul des récompenses de trading :&#x20;

À la fin de chaque cycle de récompenses de trading, les frais de trading effectifs de l'utilisateur et le montant staké dans ce cycle seront calculés pour déterminer la pondération et le montant des récompenses APX. La formule est la suivante :

r = R\*W / sum(Wi)



Paramètres :

| r       | Récompense APX de l'utilisateur pour ce cycle                                                                                                                                                                                                                                                                                        |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R       | Déterminé par la contribution de l'utilisateur aux frais de trading V2 la veille et le dernier prix du token APX                                                                                                                                                                                                                     |
| W       | <p>Score de poids total individuel W=f*w, où ;</p><p>f désigne les frais de trading effectifs contribués par l'utilisateur dans ce cycle, convertis en USD.</p><p>w est le multiplicateur de boost obtenu par l'utilisateur dans ce cycle en stakant des APX dans le DAO. (Voir le tableau ci-dessus pour plus d'informations)</p> |
| sum(Wi) | Le score total de tous les utilisateurs. Wi représente le score d'un utilisateur individuel, et sum(Wi) représente la somme de tous les scores.                                                                                                                                                                              |

&#x20;

La formule de calcul de R est la suivante :

R=Min(Multiplicateur de valeur en dollars \* Frais de trading, Plafond de valeur en dollars) / Max(Dernier prix APX, Plancher de prix APX)

* Multiplicateur de valeur en dollars : 0,70 pour cette epoch
* Frais de trading : valeur des frais V2 de la veille convertis en USD
* Plafond de valeur en dollars : 15 000 selon la configuration système
* Dernier prix APX : Basé sur le dernier prix du token APX
* Plancher de prix APX : 0,04 pour cette epoch

Conditions générales

* Après la fin de chaque cycle, ApolloX peut ajuster les règles du programme en fonction des retours des utilisateurs et des conditions du marché. Les récompenses seront distribuées de manière non linéaire.
* Durant l'activité, la plateforme réduira le pourcentage des revenus de frais de trading V2 injectés dans le pool ALP de 50% à 20%. Les 30% restants seront utilisés pour racheter des APX.
* En raison des différences de frais de trading pour chaque paire V2, les récompenses reçues par les utilisateurs peuvent varier même si leurs volumes de trading effectifs sont identiques.
* Les récompenses à distribuer pour chaque cycle seront stockées à l'adresse de contrat suivante : 0x6bE863e01E17A226c945e3629D0D9Cb6E52Ce90E
* ApolloX se réserve le droit d'interprétation finale de cette activité.

Avertissement sur les risques : Le trading de futures crypto comporte des risques substantiels. Toutes les activités de trading sont effectuées à votre discrétion et à vos propres risques. Les informations ici présentes ne doivent pas être considérées comme des conseils financiers ou d'investissement de la part d'ApolloX. ApolloX ne sera pas responsable des pertes pouvant résulter de votre utilisation d'ApolloX.

### Réclamer les récompenses

Comme le programme de récompenses de trading est hébergé par nos partenaires d'ApolloX, veuillez suivre les étapes ci-dessous pour réclamer votre récompense :\
\
Étape 1 : Rendez-vous sur notre [page PancakeSwap Perpetuals](https://perp.pancakeswap.finance/en/futures/v2/).

Étape 2 : Cliquez sur l'onglet Trading Reward (V2) en haut de la page.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Trading%20Reward.png" alt=""><figcaption></figcaption></figure>

Étape 3 : Vous serez redirigé vers la page de réclamation des récompenses d'ApolloX pour vérifier votre statut de récompense actuel. Cliquez sur "Claim" pour réclamer vos récompenses pendant la période d'activité.

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/Screenshot%202023-06-29%20at%2010.26.11%20AM.png" alt=""><figcaption></figcaption></figure>
