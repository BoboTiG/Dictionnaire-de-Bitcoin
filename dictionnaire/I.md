## I2P
▪ **Réseau**

Réseau de communication anonyme conçu pour assurer la confidentialité des échanges sur Internet. Comme TOR, I2P chiffre les données du réseau et utilise un système de routage appelé « mix network ». Cette méthode garantit l'anonymat des communications en les faisant passer par des serveurs intermédiaires qui redirigent les informations sans connaître l'identité de l'émetteur ni celle du destinataire. Tout comme TOR, I2P peut être utilisé sur un nœud Bitcoin, afin de sécuriser ses communications réseau.

> ► *Le sigle « I2P » signifie « Invisible Internet Project ».*

## IMMERSION COOLING
▪ **Minage**

► ***FR : REFROIDISSEMENT PAR IMMERSION***

Technique de refroidissement utilisée dans le cadre du minage, où les ASICs sont immergés dans un liquide non-conducteur pour dissiper la chaleur qu'ils produisent. L'immersion présente plusieurs avantages par rapport au refroidissement à l'air. Tout d'abord il n'y a pas besoin d'utiliser des ventilateurs, ce qui réduit ainsi la consommation énergétique. Aussi, les machines sont protégées de la poussière, ce qui améliore leur performance et leur longévité. L'immersion permet également une meilleure dissipation de la chaleur, car les composants sont directement en contact avec le fluide de refroidissement.

## IMPLÉMENTATION DE BITCOIN
▪ **Protocole**

► ***EN : BITCOIN IMPLEMENTATION***

Fait référence à un logiciel qui applique et suit les règles définies par le protocole Bitcoin. Ce que l’on appelle « Bitcoin », c’est généralement le système d’argent électronique. C’est un protocole qui spécifie des règles. Il est représenté, concrètement, par des nœuds qui forment un réseau. Ce système ne dispose pas spécifiquement de code. C’est simplement un ensemble de grandes règles tacites imposées par le consensus des utilisateurs via leurs nœuds. En revanche, ceux qui disposent de code informatique, et qui peuvent donc être développés, maintenus et modifiés, ce sont plutôt les logiciels de nœuds Bitcoin. Ce sont des implémentations indépendantes du protocole Bitcoin, qui peuvent se connecter au reste du réseau.

Parmi les implémentations de Bitcoin, Bitcoin Core est de loin la plus répandue, puisqu'elle représente environ 99 % du réseau de nœuds. Cependant, il existe aussi des implémentations minoritaires telles que BTCsuite, Bcoin, et Bitcoin Knots. Malgré la diversité des clients logiciels disponibles, la prédominance de Bitcoin Core sur le réseau lui confère une influence presque exclusive sur l'application du protocole Bitcoin. On dit donc que Bitcoin Core représente dans les faits le protocole Bitcoin lui-même.

## INBOUND CAPACITY
▪ **Lightning Network**

► ***FR : CAPACITÉ ENTRANTE***

Désigne la quantité maximale de bitcoins qu'un nœud peut recevoir à travers un canal spécifique sur le Lightning Network. Elle dépend des fonds que le nœud pair a engagés dans le canal lors de son ouverture, ou que l'on a envoyé lors d'un paiement Lightning sortant.

## INDEX (KEY)
▪ **Portefeuille**

► ***FR : NUMÉRO DE CLÉ***

Dans le contexte d'un portefeuille HD, fait référence au numéro séquentiel attribué à une clé enfant générée à partir d'une clé parent. Cet index est utilisé en combinaison avec la clé parent et le code chaîne parent pour dériver de manière déterministe des clés enfants uniques. Il permet une organisation structurée et la génération reproductible de multiples paires de clés enfants sœurs depuis une même clé parent. C’est un entier de 32 bits utilisé dans la fonction de dérivation `HMAC-SHA512`. Ce nombre permet donc de différencier les clés enfants sœurs au sein d’un portefeuille HD.

## INDEXES/TXINDEX/
▪ **Protocole**

Fichiers dans Bitcoin Core qui sont dédiés à l'indexation de toutes les transactions présentes dans la blockchain. Cette indexation permet de rechercher rapidement des informations détaillées sur une transaction en utilisant son identifiant (TXID), sans avoir à parcourir l'intégralité de la blockchain. La création de ces fichiers d'indexation est une option non activée par défaut dans Bitcoin Core. Si cette fonctionnalité n'est pas activée, votre nœud indexera uniquement les transactions associées aux portefeuilles rattachés à votre nœud. Pour activer l'indexation de toutes les transactions, il faut régler le paramètre `-txindex=1` dans le fichier `bitcoin.conf`. Cette option est particulièrement utile pour les applications et les services qui font des recherches fréquentes dans l'historique des transactions de Bitcoin.

## INFLATION
▪ **Économie et régulation**

Désigne l'augmentation de la masse monétaire en circulation, entraînant une baisse de la valeur de chaque unité de monnaie et une hausse des prix des biens et services. Pour les monnaies étatiques, ce phénomène survient lorsque les banques centrales émettent de nouvelles unités monétaires.

Dans le contexte de Bitcoin, l'inflation est contrôlée par le protocole. De nouveaux bitcoins sont générés à chaque validation de bloc via la subvention attribuée au mineur victorieux. Cette subvention était initialement de 50 BTC par bloc et elle est réduite de moitié tous les 210 000 blocs lors d'un événement connu sous le nom de « halving ». L'émission totale de bitcoins est plafonnée à environ 21 millions d'unités, ce qui signifie que l'inflation monétaire du BTC est décroissante et s'arrêtera une fois que le nombre maximal d'unités sera atteint.

## INITIAL BLOCK DOWNLOAD (IBD)
▪ **Protocole**

► ***FR : SYNCHRONISATION INITIALE***

Fait référence au processus par lequel un nœud télécharge et vérifie la blockchain depuis le bloc de Genèse, et se synchronise aux autres nœuds du réseau Bitcoin. L'IBD doit être réalisée au lancement d'un nouveau nœud complet. Au début de cette synchronisation initiale, le nœud ne dispose d'aucune information sur les transactions précédentes. Il télécharge donc chaque bloc depuis les autres nœuds du réseau, vérifie sa validité, puis l'ajoute à sa version locale de la blockchain. Il convient de noter que l'IBD peut être longue et exigeante en ressources en raison de la taille croissante de la blockchain et de l'UTXO set. La rapidité de son exécution dépend des capacités de calcul de l'ordinateur qui héberge le nœud, de ses capacités en RAM, de la vitesse du dispositif de stockage et de la bande passante. Pour vous donner une idée, si vous disposez d'une connexion internet puissante, et que le nœud est hébergé sur le dernier MacBook avec beaucoup de RAM, l'IBD ne prendra que quelques heures. En revanche, si vous utilisez un micro-ordinateur comme un Raspberry Pi, l'IBD pourra prendre une semaine ou plus.

> ► *En français, il est globalement admis de parler directement d'un(e) IBD. La traduction parfois employée est « synchronisation initiale », ou « téléchargement initial des blocs ».*

## INPUT
▪ **Protocole**

► ***FR : ENTRÉE***

Dans le contexte de Bitcoin, un input (entrée) au sein d’une transaction fait référence aux UTXOs (*Unspent Transaction Outputs*) utilisés comme fonds d'origine pour satisfaire les sorties (outputs). Chaque input contient des références aux UTXOs précédents, qui seront alors consommés par la transaction. Ces inputs sont utilisés pour alimenter de nouveaux UTXOs qui seront créés comme outputs de la transaction, et qui peuvent ensuite être dépensés dans des transactions futures. 

Le rôle de la transaction Bitcoin est donc de consommer des UTXOs en entrées, et de créer des nouveaux UTXO en sorties. La différence entre les deux correspond aux frais de transactions qui peuvent être récupérés par le mineur qui valide le bloc. 

D'un point de vue plus large, en informatique, le terme « input » ou « entrée » désigne généralement les données fournies à une fonction, un algorithme, ou un système en tant qu'opérandes ou informations requises pour effectuer une opération ou un calcul. Dans ce sens, le terme est utilisé de manière plus générique pour décrire tout ce qui est fourni à un processus en vue d'obtenir un résultat ou une sortie (output). Par exemple, lorsque l’on passe une donnée dans une fonction de hachage cryptographique, cette information est nommée « entrée » ou « input ».

## INSCRIPTIONS
▪ **Couche supérieure**

Dans le cadre de la théorie des Ordinals, les inscriptions sont des contenus arbitraires gravés sur des sats, transformant ces derniers en artefacts numériques natifs de Bitcoin. Les inscriptions sont effectuées via des transactions qui exposent le contenu de l'information dans le script d'un input Taproot de cette manière :

```text
OP_0
OP_IF
<la data ici>
OP_ENDIF
```

Ces artefacts numériques, comme des NFTs, peuvent être échangés et conservés.

> ► *Pour plus d'informations, voir les définitions de **[ORDINALS THEORY](./O.md#ordinals-theory)** et de **[DIGITAL ARTIFACTS](./D.md#digital-artifacts)**.*

## INTERFACE
▪ **RGB**

Dans le cadre du protocole RGB, l’Interface désigne l’ensemble des instructions qui décodent les données binaires compilées dans un Schema ou au sein des opérations et états d’un contrat. Elle sert de couche d’interprétation, afin de transformer les informations brutes en une représentation lisible par l’utilisateur ou son wallet.

## INTERFACE IMPLEMENTATION
▪ **RGB**

Dans le cadre du protocole RGB, l’Interface Implementation désigne l’ensemble des déclarations établissant la correspondance entre une Interface et un Schema. Elle permet de réaliser la traduction sémantique des données binaires d’un contrat, afin d'assurer leur interprétation correcte par l’utilisateur ou par les applications, telles que les wallets.

## INVOICE LIGHTNING
▪ **Lightning Network**

Requête de paiement Lightning générée par le destinataire, qui contient toutes les informations nécessaires pour réaliser la transaction. 

Une invoice Lightning contient la destination du paiement sous la forme de la clé publique du nœud destinataire, mais également un préfixe `ln`, le montant, un temps avant expiration, le hachage du secret utilisé dans le cadre des HTLCs, ainsi que d'autres métadonnées, pour certaines optionnelles, comme des options relatives au routage. Ces invoices sont définies par la norme BOLT11. Une fois payée, une invoice Lightning ne peut plus être réutilisée.

> ► *En français, on pourrait traduire « invoice » par « facture », mais on utilise généralement le terme anglais même en français.*

## INVOICE RGB
▪ **RGB**

Dans le cadre du protocole RGB, une Invoice se présente sous la forme d’une URL encodée en base58, qui intègre les informations indispensables à la construction d’une State Transition par le payeur. En pratique, il s’agit d’une facture qui permet à la contrepartie de générer la transition adéquate pour transférer un actif ou actualiser l’état d’un contrat.

## IOU
▪ **Économie et régulation**

Sigle de l'anglais _I Owe You_ (« Je te dois ») utilisé dans le contexte de Bitcoin pour désigner des actifs numériques qui sont adossés à des actifs sous-jacents auxquels ils devraient normalement être indexés. Ce terme s'applique notamment aux stablecoins ou aux représentations de BTC sur des systèmes externes à Bitcoin, tels que les sidechains, les drivechains, les plateformes d'échange, ou encore les ETFs. Ces actifs numériques représentent une promesse de valeur équivalente à celle de l'actif sous-jacent.

## IP_ASN.MAP
▪ **Réseau**

Fichier utilisé dans Bitcoin Core pour stocker l'ASMAP qui permet d'améliorer le bucketing (c'est-à-dire, le regroupement) des adresses IP, en se basant sur les numéros de systèmes autonomes (ASN). Plutôt que de regrouper les connexions sortantes par préfixes de réseau IP (/16), ce fichier permet de diversifier les connexions en établissant une carte d'adressage IP vers les ASN, qui sont des identifiants uniques pour chaque réseau sur Internet. L'idée est d'améliorer la sécurité et la topologie du réseau Bitcoin en diversifiant les connexions pour se prémunir contre certaines attaques (notamment l'attaque Erebus).

## IP REPORT
▪ **Minage**

Bouton présent sur les ASICs qui permet de trouver rapidement l'adresse IP de la machine sur le réseau local. Pour utiliser cette fonctionnalité, il faut appuyer sur le bouton *IP Report* de l'ASIC pendant quelques secondes. Ensuite, en utilisant un logiciel spécialisé sur un ordinateur connecté au même réseau, l'adresse IP du mineur sera affichée à l'écran. Ce bouton permet notamment de localiser facilement une machine sur le réseau local lorsque l'on a plusieurs machines.

## ISSUE
▪ **Informatique**

Dans le cadre de Github et d'autres plateformes d'hébergement de code, une issue est un rapport qui signale un bug, propose une amélioration ou suggère une nouvelle fonctionnalité. Elle sert de point de discussion pour les contributeurs et permet de suivre les tâches à accomplir ou les problèmes à résoudre dans le projet. En tant qu'utilisateur de Bitcoin, vous pouvez aider les logiciels open source que vous utilisez en signalant d'éventuels bugs via des issues sur le dépôt du projet.
