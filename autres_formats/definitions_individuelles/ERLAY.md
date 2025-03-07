## ERLAY
▪ **Réseau**

Proposition de protocole réseau dont l'objectif est d'améliorer l'efficacité du relais des transactions non confirmées entre les nœuds Bitcoin.

Actuellement, chaque transaction est propagée via un système où chaque nœud diffuse la transaction dont il prend connaissance à l'ensemble de ses pairs. Le problème, c'est que cela entraîne de nombreuses redondances et une utilisation de la bande passante pour des doublons. De nombreuses diffusions de transactions s'avèrent inutiles, car le destinataire est déjà en connaissance de ces transactions et chaque nœud n'a besoin de connaître chaque transaction qu'une seule fois. Erlay propose de limiter par défaut à 8 le nombre de pairs auxquels un nœud envoie directement les transactions dont il prend connaissance, puis d'utiliser un processus de réconciliation basé sur la bibliothèque minisketch pour partager les transactions manquantes de manière plus efficace.

Erlay réduirait la consommation de bande passante d'environ 40 %, ce qui rendrait l'opération d'un nœud complet plus accessible aux utilisateurs avec des connexions Internet limitées, et ce qui favoriserait donc une meilleure décentralisation du réseau. Ce protocole maintiendrait aussi une consommation de bande passante quasi constante avec une augmentation du nombre de connexions. Cela signifie qu'il serait bien plus simple pour les opérateurs de nœuds d'accepter un très grand nombre de connexions de leurs pairs, ce qui renforcerait la sécurité du réseau Bitcoin en réduisant les risques de partitionnement, intentionnels ou accidentels. De plus, Erlay compliquerait la tâche de déterminer le nœud d'origine d'une transaction, ce qui augmenterait ainsi la confidentialité pour les utilisateurs de nœuds qui n'opèrent pas sous Tor.

Erlay est proposé dans le BIP330.

