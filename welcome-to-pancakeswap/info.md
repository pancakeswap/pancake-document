# 📈 Analytiques (Page Info)

## Page Info&#x20;

Consultez le site analytique natif de PancakeSwap ici : [https://pancakeswap.finance/info](https://pancakeswap.finance/info)

<figure><img src="https://raw.githubusercontent.com/pancakeswap/pancake-document/en/.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Toutes les données des indicateurs clés proviennent de l'indexeur interne de PCS, qui recueille à son tour les données à partir des événements déclenchés lors de l'appel aux contrats.&#x20;

Pour la dimension temporelle dans l'indexeur interne de PancakeSwap, nous utilisons l'heure internationale standard (UTC) pour les statistiques quotidiennes. Ainsi, lorsque l'axe horizontal du tableau de bord affiche une date, celle-ci correspond à la date en heure internationale standard (UTC).<br>

## Indicateurs Clés

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemXpjzW0IqGPjz6IISjhcIXzWWeeFyxXU7XLRumCxM6WQsr4IKMP_mwDhiMDGY9EUDtKZAKoeYsbYUXwRc2C2KBvoSRo_-tlxq09zOJ1ajIq00cXM6z_7-2RNv3rVWj_kBmLiY4Q?key=G7-HCtdmBA4wyp9ESrWifFqi" alt=""><figcaption></figcaption></figure>

**Volume (Volume de Trading) :** Nous surveillons les données quotidiennes pour chaque paire de Trading ainsi que les données de Trading journalières pour chaque token. Le volume de Trading journalier est déterminé en multipliant le volume de Trading de chaque token pour la journée par son prix.

**Total Value Locked :** Récupère tous les pools depuis l'indexeur interne et lit la valeur `reserve_usd` ou `total_value_locked_usd` de chaque pool.&#x20;

**Prix :** Dans l'indexeur interne de PCS, nous utilisons plusieurs pools de base pour calculer les prix en USD. Le pool principal est le pool de Trading en stablecoin, où nous utilisons le pool de Trading affichant le volume le plus élevé comme pool de base et calculons le prix en USD du stablecoin en fonction du poids du volume de Trading. De plus, le pool de Trading du token de base vers le stablecoin de la chaîne est également considéré comme un pool de base afin de fournir le prix en USD.

_Les tokens qui ne figurent pas sur la liste blanche ou qui ne sont pas associés à des tokens figurant sur cette liste sont exclus de ces calculs._

<br>
