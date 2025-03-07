## CISA
▪ **Protocole**

Acronyme de « *Cross-Input Signature Aggregation* ». C'est une proposition technique qui a pour objectif d'optimiser la taille des transactions Bitcoin en réduisant le nombre de signatures requises pour les valider.

Actuellement, sur Bitcoin, chaque input d'une transaction doit avoir une signature individuelle pour pouvoir être consommé. Cela permet de prouver que le propriétaire de l'UTXO en question autorise la transaction. Avec CISA, l'objectif est de combiner les signatures de tous les inputs d'une même transaction en une seule signature qui couvre l'ensemble des inputs. Cela permettrait de réduire la taille des transactions qui disposent de nombreux inputs, et donc d'en réduire également les frais. Ce serait notamment très utile pour les personnes qui réalisent des coinjoins ou des consolidations, tout en permettant de confirmer plus de transactions sur Bitcoin sans pour autant modifier la taille ou l'intervalle des blocs. CISA repose sur le protocole de Schnorr qui permet l'agrégation linéaire des signatures. Cela signifie qu'une seule signature peut prouver la possession de plusieurs clés indépendantes.

Cependant, l'implémentation de CISA sur Bitcoin est très complexe, car elle nécessite des modifications profondes dans la manière de fonctionner des scripts. Actuellement, la vérification des scripts sur Bitcoin se fait input par input. Passer à un modèle où une transaction entière est vérifiée d'un coup, comme le propose CISA, est loin d'être une modification anodine.

