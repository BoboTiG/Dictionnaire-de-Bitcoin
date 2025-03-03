## ATOMIC MULTI-PATH PAYMENTS
▪ **Lightning Network**

► ***FR : PAIEMENTS MULTICHEMINS ATOMIQUES***

Version améliorée des MPP (*Multi-Path Payments*) où chaque fragment de paiement possède un secret partiel distinct, ce qui garantie que la transaction est réglée de manière atomique, c’est-à-dire en entière ou pas du tout. 

Les MPP sont des techniques de paiement sur Lightning qui permettent de fractionner une transaction en plusieurs petites parties pour les acheminer via différentes routes. Autrement dit, chaque fraction de paiement emprunte un chemin de nœuds différent. Cela permet de contourner les limitations de liquidité sur un canal unique dans la route. Dans les MPP de base, chaque fraction de paiement partage le même secret, et donc le même hash dans les HTLCs. Cela peut rendre la transaction traçable si un observateur est présent sur plusieurs routes, car il peut faire un lien entre tous ces secrets identiques. De plus, du fait que le secret est unique pour toutes les fractions du paiement, celui-ci n'est pas atomique. Cela signifie que certaines parties du paiement peuvent être exécutées avec succès, tandis que d'autres peuvent échouer.

Dans les AMP, on utilise des secrets partiels uniques pour chaque fraction. Une fois tous les fragments reçus, ils permettent au destinataire de reconstituer le secret général d'origine et de réclamer l’intégralité du paiement. Cette méthode rend le règlement partiel du paiement impossible, car la possession de tous les secrets partiels est nécessaire pour débloquer le paiement complet. Cela garantit que le paiement est entièrement réussi ou entièrement échoué (c'est-à-dire, atomique). Les AMP améliorent aussi la confidentialité, car il n'y a plus de liens visibles entre les différentes routes.

Un avantage des AMP est qu'ils fonctionnent même si seuls le receveur et l'envoyeur ont implémenté cette méthode. Les nœuds intermédiaires traitent ces paiements comme des transactions classiques en utilisant des HTLCs, sans être conscients qu'ils traitent des fractions d'un paiement plus important.

> ► *On parle également parfois de « Atomic Multi-Part Payment » pour désigner cette même méthode. Pour plus d'informations, voir la définition de [**MULTI-PATH PAYMENTS (MPP)**](/dictionnaire/M.md#multi-path-payments-mpp).*

