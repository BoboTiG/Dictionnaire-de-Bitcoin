## BCH CODE
▪ **Cryptographie**

► ***FR : CODE BCH***

Classe de codes de correction d'erreurs utilisés pour détecter et corriger des erreurs dans une séquence de données. Autrement dit, les codes de correction d'erreur BCH permettent de trouver et de corriger des erreurs aléatoires dans des informations transmises, afin de garantir qu'elles arrivent intactes à leur destination. Le sigle « BCH » représente les initiales des noms des inventeurs de ces codes : Bose, Ray-Chaudhuri, et Hocquenghem.

On utilise cet outil dans de nombreux domaines de l'informatique, notamment dans les SSD, les DVD ou encore les QR codes. Par exemple, grâce à ces codes de correction d'erreurs, même si un QR code est partiellement recouvert, il est toujours possible de récupérer les informations qu'il encode.

Dans le cadre de Bitcoin, les codes BCH sont utilisés pour la somme de contrôle dans les formats d'adresses Bech32 et Bech32m (post-SegWit). Ils représentent un meilleur compromis entre la taille et la capacité de détection d'erreurs de la checksum par rapport aux simples fonctions de hachage utilisées précédemment sur les adresses Legacy. Dans le contexte de Bitcoin, les codes BCH sont utilisés uniquement pour la détection d'erreurs, et non pour la correction d'erreur. Ainsi, les logiciels de portefeuille Bitcoin identifieront et signaleront à l'utilisateur toute erreur dans une adresse de réception, mais ne modifieront pas l'adresse incorrecte automatiquement. Ce choix est motivé par le fait que l'intégration de la correction d'erreur affecte inévitablement les capacités de détection d'erreur de l'algorithme.

