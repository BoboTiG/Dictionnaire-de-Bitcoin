## LABEL
▪ **Portefeuille**

► ***FR : ÉTIQUETTE***

Étiquette ou annotation attribuée à un UTXO dans un portefeuille Bitcoin pour se souvenir de sa provenance. Par exemple, si je possède un UTXO provenant d'un achat P2P sur Bisq avec Charles, je pourrais lui attribuer le label `Non-KYC Bisq Charles`. C'est une bonne pratique qui aide à se rappeler l'origine ou la destination prévue de cet UTXO, ce qui facilite la gestion des fonds et l'optimisation de la confidentialité. Le labelling est d'autant plus important lorsqu'il est utilisé avec le coin control. En effet, en permettant aux utilisateurs de différencier et de sélectionner précisément les UTXOs pour leurs transactions, cette pratique aide à éviter la fusion d'UTXOs provenant de sources différentes. Cela limite les risques associés à l'heuristique d'analyse de chaîne CIOH (*Common Input Ownership Heuristic*), qui peut révéler la propriété commune des entrées d'une transaction.

> ► *Pour plus d'informations, voir la définition de [**COIN CONTROL**](./C.md#coin-control).*

## LABEL (SILENT PAYMENTS)
▪ **Confidentialité**

► ***FR : ÉTIQUETTE (SILENT PAYMENTS)***

Dans le cadre du protocole Silent Payments, les labels sont des entiers utilisés pour modifier l'adresse statique initiale, afin de créer de nombreuses autres adresses statiques. L'utilisation de ces labels permet de ségréguer les paiements envoyés via Silent Payments, en employant des adresses statiques différentes pour chaque usage, sans augmenter excessivement la charge opérationnelle pour la détection de ces paiements (scanning). Bob utilise une adresse statique $B$, composée de deux clés publiques : $B_{\text{scan}}$ pour le scan et $B_{\text{spend}}$ pour la dépense. On ajoute le hachage de $b_{\text{scan}}$ et d'un entier $m$, multipliés scalairement par le point générateur $G$, à la clé publique de dépense $B_{\text{spend}}$ pour créer une sorte de nouvelle clé publique de dépense $B_m$ :

$$  B_m = B_{\text{spend}} + \text{hash}(b_{\text{scan}} \text{ ‖ } m) \cdot G  $$

Par exemple, la première clé $B_1$ est obtenue de cette manière :

$$  B_1 = B_{\text{spend}} + \text{hash}(b_{\text{scan}} \text{ ‖ } 1) \cdot G  $$

L'adresse statique publiée par Bob sera dorénavant composée de $B_{\text{scan}}$ et de $B_m$. Par exemple, la première adresse statique avec le label $1$ sera :

$$ B = B_{\text{scan}} \text{ ‖ } B_1 $$

On commence seulement à partir du label $1$, car le label $0$ est réservé pour le change. Alice, qui souhaite envoyer des bitcoins sur l'adresse statique labellisée transmise par Bob, va dériver l'adresse de paiement unique $P_0$ en utilisant la nouvelle $B_1$ à la place de $B_{\text{spend}}$ :

$$  P_0 = B_1 + \text{hash}(\text{inputHash} \cdot a \cdot B_{\text{scan}} \text{ ‖ } 0) \cdot G  $$

En réalité, Alice ne sait même pas forcément que Bob dispose d'une adresse labelisée, car elle utilise simplement la seconde partie de l'adresse statique qu'il lui a fourni, et en l'occurrence, c'est la valeur $B_1$ plutôt que $B_{\text{spend}}$. Pour scanner les paiements, Bob va toujours utiliser la valeur de son adresse statique initiale avec $B_{\text{spend}}$ de cette manière :

$$   P_0 = B_{\text{spend}} + \text{hash}(\text{inputHash} \cdot b_{\text{scan}} \cdot A \text{ ‖ } 0) \cdot G  $$

Puis, il va simplement soustraire la valeur qu'il trouve pour $P_0$ de chaque output un à un. Il vérifie ensuite si un des résultats de ces soustractions correspond à la valeur d'un des labels qu'il utilise sur son portefeuille. Si ça matche, par exemple, pour l'output #4 avec le label $1$, cela veut dire que cet output est un Silent Payment associé à son adresse statique labelisée $B_1$ :

$$ Out_4 - P_0 = \text{hash}(b_{\text{scan}} \text{ ‖ } 1) \cdot G $$

Cela fonctionne, car :

$$  B_1 = B_{\text{spend}} + \text{hash}(b_{\text{scan}} \text{ ‖ } 1) \cdot G  $$

Grâce à cette méthode, Bob peut utiliser une multitude d'adresses statiques (avec $B_1$, $B_2$, $B_3$...), toutes dérivées depuis son adresse statique de base ($B = B_{\text{scan}} \text{ ‖ } B_{\text{spend}}$), afin de bien séparer les usages. 

Attention toutefois, cette séparation des adresses statiques vaut uniquement d'un point de vue de gestion personnelle du portefeuille, mais ne permet pas de séparer les identités. Puisqu'elles disposent toutes du même $B_{\text{scan}}$, il est très facile d'associer toutes les adresses statiques ensemble et de déduire qu'elles appartiennent à une unique entité.

> ► *Pour plus d'informations, voir la définition de **[SILENT PAYMENTS](./S.md#silent-payments)**.*

## LATENCE
▪ **Réseau**

Délai entre l'émission et la réception d'une information. En informatique, elle représente le temps nécessaire pour que des données voyagent entre deux ordinateurs. Dans le contexte de Bitcoin, la latence peut être étudiée au niveau du délai de diffusion des blocs à travers le réseau. Une latence élevée peut entraîner des désavantages pour les mineurs isolés, car ceux-ci continuent de travailler sur des blocs déjà invalidés par de nouveaux blocs tant qu'ils n'ont pas reçu ces nouveaux blocs. La latence pousse donc naturellement au regroupement des mineurs. Elle réduit également la sécurité globale du système par le gaspillage de la recherche d'une preuve de travail valide. Le but de mettre une période de 10 minutes entre chaque bloc est une mesure pour réduire l'impact de la latence sur le système.

## LCB/FT
▪ **Économie et régulation**

La lutte contre le blanchiment des capitaux et le financement du terrorisme (LCB/FT) fait référence aux mesures réglementaires adoptées pour prévenir l'utilisation de Bitcoin dans des activités illégales. Ces mesures incluent l'identification et la vérification de l'identité des clients (KYC), la surveillance des transactions pour détecter des schémas « suspects », et la collaboration avec les autorités pour signaler des activités considérées comme illégales. Les plateformes d'échange régulées sont tenues de s'y conformer pour opérer dans de nombreuses juridictions, notamment en France.

## LDK (LIGHTNING DEV KIT)
▪ **Lightning Network**

Kit de développement (SDK) pour Lightning. LDK est une collection de bibliothèques et d'outils destinés aux développeurs pour intégrer facilement Lightning à leurs logiciels ou pour créer des applications Lightning en réduisant la complexité. LDK gère les aspects complexes de l'intégration de fonctionnalités liées à Lightning. Ce projet a été lancé par Spiral, une entreprise créée par Jack Dorsey, et s'est établie sur Rust-Lightning (RL).

## LEDGER
▪ **Portefeuille**

► ***FR : GRAND LIVRE / REGISTRE***

Nom parfois utilisé pour désigner le registre public et distribué qui enregistre toutes les transactions effectuées sur Bitcoin, c'est-à-dire, la blockchain. La publication et l'enregistrement des transactions sur le ledger permet de prévenir la double dépense sur Bitcoin, en s'assurant que chaque pièce qu'une transaction tente de dépenser n'a pas déjà été utilisée auparavant dans une autre transaction.

## LEVELDB
▪ **Protocole**

Bibliothèque de stockage de clés-valeurs légère, rapide et open-source, conçue par Google. On l'utilise sur Bitcoin pour stocker l'UTXO set, l'index des transactions et l'index des blocs. Ce système de base de données a été introduit en 2012 dans le cadre de la Pull Request « *Ultraprune* » visant à remplacer BerkeleyDB. Ce changement a eu des répercussions significatives, notamment la création d'une première division de la blockchain avec une réorganisation majeure de 24 blocs le 12 mars 2013. Cet incident a été détaillé dans le BIP50. Plus tard, ce changement de système a même conduit à un hard fork non intentionnel le 15 mai 2013.

## LIBBITCOIN
▪ **Protocole**

Ensemble de bibliothèques écrites en C++ conçues pour créer des applications en lien avec Bitcoin. Libbitcoin offre des bases indépendantes pour développer des applications mobiles, des logiciels et d'autres systèmes autour de Bitcoin. Libbitcoin dispose donc d'une architecture modulaire. L'intégralité des bibliothèques du projet sont distribuées sous licence libre AGPL.

Lancé en 2011 par une équipe de développeurs menée par Amir Taaki, Libbitcoin représente alors la deuxième implémentation complète de Bitcoin, après client originel de Satoshi. Aujourd'hui, Eric Voskuil est le mainteneur principal et le contributeur le plus actif du projet.

## LIBSECP256K1
▪ **Protocole**

Bibliothèque C de haute performance et de haute sécurité pour les signatures numériques et d'autres primitives cryptographiques sur la courbe elliptique `secp256k1`. Puisque cette courbe n'a jamais été largement utilisée en dehors de Bitcoin (contrairement à la courbe `secp256r1` souvent préférée), cette bibliothèque vise à être la référence la plus complète pour son utilisation. Le développement de libsecp256k1 a été principalement orienté vers les besoins de Bitcoin, et les fonctionnalités destinées à d'autres applications peuvent être moins testées ou vérifiées. Une utilisation appropriée de cette bibliothèque nécessite une attention particulière, afin de s'assurer qu'elle convienne aux objectifs spécifiques des autres applications que Bitcoin.

La bibliothèque libsecp256k1 offre une variété de fonctionnalités, notamment :
* La signature ECDSA-secp256k1 et la vérification, ainsi que la génération de clés cryptographiques ;
* Des opérations additives et multiplicatives sur les clés secrètes et publiques ;
* La sérialisation et l'analyse des clés secrètes, des clés publiques et des signatures ;
* La signature et la génération de clés publiques à temps constant et à accès mémoire constant ;
* Et une multitude d'autres primitives cryptographiques.

> ► *Pour plus d'informations, voir la définition de [**SECP256K1**](./S.md#secp256k1). Source : https://github.com/bitcoin-core/secp256k1.*

## LIGHTNING NETWORK
▪ **Lightning Network**

Protocole de couche supérieure, construit au-dessus du protocole Bitcoin, visant à permettre des transactions rapides et à faible coût. Il permet la création de canaux de paiement entre les participants, au sein desquels les transactions peuvent être effectuées presque instantanément et avec des frais minimes, sans avoir à enregistrer chaque transaction individuellement sur la blockchain. Les canaux peuvent rester ouverts quasi indéfiniment, et ne nécessitent des transactions sur la blockchain que lors de leur ouverture et de leur clôture. Le Lightning Network vise à améliorer la scalabilité de Bitcoin et à rendre possible son utilisation pour des paiements de faible valeur.

## LIGHTNING SERVICE PROVIDER
▪ **Lightning Network**

► ***FR : FOURNISSEUR DE SERVICE LIGHTNING***

Entreprise qui opère sur Lightning dont l'activité est de fournir des services de liquidité aux utilisateurs. 

Sur Lightning, les paiements sont réalisés off-chain via des canaux bidirectionnels, dont la capacité est limitée par les fonds bloqués dans le multisig 2/2 on-chain. Le rôle principal d'un LSP est de faciliter la gestion de cette liquidité, soit en aidant à convertir les fonds on-chain vers Lightning, soit en ouvrant de nouveaux canaux pour augmenter la capacité entrante des utilisateurs.

Ces services sont souvent utilisés par des portefeuilles non-custodiaux, afin que l'utilisateur puisse recevoir immédiatement des paiements Lightning sans devoir gérer lui-même l'ouverture et la gestion des canaux. En échange, le LSP facture des frais.

## LIMITE D'ÉMISSION
▪ **Protocole**

Plafond fixé pour la masse monétaire totale de BTC, établie à environ 21 millions d'unités. Cette limite est définie par la politique d'inflation dans le protocole Bitcoin. De nouveaux BTC sont créés et distribués aux mineurs via la subvention pour la validation de chaque bloc. Cette subvention est réduite de moitié tous les 210 000 blocs, un processus connu sous le nom de « halving ». Cette méthode garantit que la création monétaire décroîtra progressivement jusqu'à atteindre zéro.

## LIQUIDITÉS
▪ **Lightning Network**

► ***EN : LIQUIDITY (LIGHTNING)***

Désigne la capacité d’un canal de paiement Lightning à faire passer des transactions entre deux nœuds en fonction des bitcoins disponibles de chaque côté du canal. Il existe deux types de liquidités : entrante et sortante. La liquidité sortante représente les fonds que le nœud peut envoyer ou transférer via le canal. La liquidité entrante représente les fonds qu’il peut recevoir ou transférer dans le sens inverse. La liquidité peut aussi désigner la somme des liquidités disponibles dans tous les canaux d'un nœud.

## LIQUID NETWORK
▪ **Sidechain**

Sidechain de Bitcoin conçue par Blockstream pour fournir des transactions rapides et confidentielles. Contrairement à la blockchain principale de Bitcoin, Liquid utilise un mécanisme de consensus établi sur une fédération (un groupe sélectionné d'opérateurs de nœuds, généralement des entreprises liées à Bitcoin), remplaçant ainsi le mécanisme de consensus de Nakamoto. Cette approche accélère considérablement les transactions et réduit les coûts, tout en offrant des fonctionnalités plus avancées. Liquid permet aussi l'émission d'actifs numériques, y compris des jetons représentant d'autres cryptomonnaies. Les bitcoins sur Liquid, appelés L-BTC, sont liés au BTC grâce à un système d'ancrage bilatéral reposant sur une partie de la fédération. Les participants à cette fédération sont appelés des « fonctionnaires », et ils peuvent endosser à la fois le rôle de « gardien » (*watchmen*) et de « signataire de bloc » (*blocksigner*).

## LITTLE-ENDIAN
▪ **Informatique**

► ***FR : PETIT-BOUTISTE***

Format de stockage de données dans les systèmes informatiques où les octets les moins significatifs (les « petits bouts ») sont placés en premier dans l'ordre des adresses. Dans une séquence comportant plusieurs octets, l'octet ayant le plus petit poids (par exemple, les chiffres les plus à droite en hexadécimale) est stocké en premier.

## LND
▪ **Lightning Network**

Sigle de « *Lightning Network Daemon* ». C'est une implémentation majeure du protocole Lightning Network écrite en langage Go. Développée par Lightning Labs, LND permet la création et la gestion de canaux de paiement et de nœuds sur le réseau Lightning.

## LNURL
▪ **Lightning Network**

Protocole de communication qui spécifie un ensemble de fonctionnalités conçues pour simplifier les interactions entre les nœuds et les clients Lightning, ainsi que les applications tierces. Ce protocole repose sur HTTP et permet de créer des liens pour diverses opérations, comme une demande de paiement, une demande de retrait, ou d'autres fonctionnalités qui permettent d'améliorer l'expérience utilisateur. Chaque LNURL est une URL encodée en bech32 avec le préfixe `lnurl`, qui, une fois scannée, déclenche une série d’actions automatiques sur le portefeuille Lightning.

Par exemple, la fonctionnalité LNURL-withdraw (LUD-03) permet de retirer des fonds depuis un service en scannant un QR code, sans avoir besoin de générer manuellement une invoice. Ou encore, LNURL-auth (LUD-04) permet de se connecter à des services en ligne en utilisant une clé privée sur son portefeuille Lightning à la place du mot de passe.

## LOCK
▪ **Protocole**

Fichier utilisé dans Bitcoin Core pour le verrouillage du répertoire de données. Il est créé lorsque bitcoind ou Bitcoin-qt démarre pour éviter que plusieurs instances du logiciel accèdent simultanément au même répertoire de données. Le but est de prévenir les conflits et les corruptions de données. Si le logiciel s'arrête de manière inattendue, le fichier .lock peut éventuellement rester et doit être supprimé manuellement avant de redémarrer Bitcoin Core.

## LOGARITHME DISCRET
▪ **Cryptographie**

► ***EN : DISCRETE LOGARITHM***

Le logarithme discret est un problème mathématique qui est utilisé dans certains algorithmes cryptographiques à clé publique. Dans un groupe cyclique d’ordre $q$, avec un générateur $g$, si l'on a une équation de la forme $g^x = h$, alors $x$ est appelé le logarithme discret de $h$ par rapport à la base $g$, modulo $q$. En termes simples, il s’agit de déterminer l’exposant $x$ lorsqu’on connaît $g$, $h$, et $q$. Le logarithme discret est donc la réciproque de l'exponentielle dans un groupe cyclique fini. Cependant, pour de grandes valeurs de $q$, résoudre le problème du logarithme discret est considéré comme algorithmiquement difficile. Cette propriété est exploitée pour assurer la sécurité de nombreux protocoles cryptographiques, tels que le protocole de Diffie-Hellman pour l'échange de clés. 

Le logarithme discret est aussi utilisé dans la cryptographie à courbes elliptiques (ECC), entre autres dans l'algorithme ECDSA (*Elliptic Curve Digital Signature Algorithm*). Dans le contexte des courbes elliptiques, le problème du logarithme discret s'étend à la recherche d'un scalaire $k$ tel que $k \cdot G = K$, où $G$ et $K$ sont des points sur la courbe, et $\cdot$ représente l'opération de multiplication de points. Dans le contexte de Bitcoin, les scripts peuvent utiliser soit ECDSA, soit le protocole de Schnorr, afin de bloquer des UTXOs. Ils reposent tous deux sur l’impossibilité de calculer le logarithme discret.

## LOOP
▪ **Lightning Network**

Service développé par Lightning Labs conçu pour faciliter l'équilibrage de liquidités dans les canaux Lightning. Loop permet aux utilisateurs de transférer des fonds entre Bitcoin et le Lightning Network, sans avoir à fermer ou ouvrir un canal. Loop aide ainsi à optimiser sa liquidité et à réduire les frais de gestion de ses canaux.

## LUCK
▪ **Minage**

► ***FR : CHANCE***

Indicateur utilisé dans les pools de minage pour mesurer la performance d'une pool par rapport à ses attentes théoriques. Comme son nom l'indique, il évalue la chance qu'a la pool de trouver un bloc. La luck est calculée en comparant le nombre de shares théoriquement nécessaire pour trouver un bloc valide, établi sur la difficulté actuelle de Bitcoin, au nombre réel de shares produites pour trouver ce bloc. Un nombre de shares inférieur à celui attendu indique une bonne chance, tandis qu'un nombre supérieur indique une mauvaise chance.

En mettant en rapport la difficulté sur Bitcoin avec son nombre de shares produites chaque seconde et la difficulté de chaque shares, la pool peut calculer le nombre de shares qui sont théoriquement nécessaires pour trouver un bloc valide. Par exemple, supposons que théoriquement, il faut 100 000 shares pour qu'une pool trouve un bloc. Si la pool en réalité en produit 200 000 avant de trouver un bloc, sa luck est de 50 % :

```text
100 000 / 200 000 = 0.5 = 50 %
```

À l'inverse, si cette pool a trouvé un bloc valide après avoir seulement produit 50 000 shares, alors sa luck est de 200 % :

```text
100 000 / 50 000 = 2 = 200 %
```

La luck est un indicateur qui ne peut être actualisé qu'après la découverte d'un bloc par la pool, ce qui en fait un indicateur statique mis à jour périodiquement.

> ► *Pour plus d'informations, voir la définition de **[SHARES](./S.md#shares)**.*

## LUD
▪ **Lightning Network**

Acronyme de « *LNURL Document* ». Les LUD sont des documents qui définissent des protocoles standardisés utilisés dans le cadre de LNURL. Chaque LUD spécifie une fonctionnalité, comme les paiements (LUD-06), les retraits (LUD-03) ou l'authentification (LUD-04). Ils permettent donc d'avoir une bonne interopérabilité entre les différents services et clients Lightning utilisant LNURL.

> ► *Pour plus d'informations, voir la définition de **[LNURL](./L.md#lnurl)**.*
