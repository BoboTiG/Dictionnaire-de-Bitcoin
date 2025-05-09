## EMBRANCHEMENT NATUREL
▪ **Protocole**

► ***EN : NATURAL BRANCHING / CHAINSPLIT***

Séparation temporaire de la blockchain résultant de la diffusion quasi simultanée de plusieurs blocs par différents mineurs à une même hauteur. Cette situation se produit lorsque deux blocs, désignés comme $A$ et $B$, sont trouvés presque simultanément, entraînant une division temporaire du réseau. Puisque chaque nœud considère comme valide le premier bloc qu'il a reçu, mais que tout le monde n'a pas reçu le même bloc en premier, une partie des nœuds suit la chaîne contenant le bloc $A$, tandis que l'autre suit celle avec le bloc $B$. Cet embranchement est résolu lorsqu'une des deux chaînes concurrentes dépasse l'autre en termes de travail accumulé. À ce moment-là, tous les nœuds du réseau s'accordent automatiquement sur la chaîne la plus longue (avec le plus de travail accumulé), un processus que l'on appelle la réorganisation ou la resynchronisation. Ces embranchements naturels sont inhérents au fonctionnement distribué de Bitcoin. Ils sont parfaitement normaux et se résolvent spontanément au bout de quelques blocs (généralement un seul). S'ils sont trop nombreux, ces embranchements peuvent tout de même être délétères, car ils entrainent un gaspillage de la puissance de calcul sur une branche qui deviendra finalement obsolète.

