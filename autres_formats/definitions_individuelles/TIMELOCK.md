## TIMELOCK
▪ **Protocole**

► ***FR : VERROUILLAGE TEMPOREL***

Primitive de contrat intelligent qui permet de définir une condition temporelle à remplir pour qu'une transaction puisse être ajoutée à un bloc. Il existe deux types de timelocks sur Bitcoin : 
* Le timelock absolu, qui spécifie un moment précis avant lequel la transaction ne peut être incluse dans un bloc ; 
* Le timelock relatif, qui définit un délai à partir de l'acceptation d'une transaction antérieure. 
Le timelock peut être défini soit sous la forme d'une date exprimée en temps Unix, soit sous la forme d'un numéro de bloc. Enfin, le timelock peut s'appliquer soit à un output de transaction grâce à l'utilisation d'un opcode spécifique dans le script de verrouillage (`OP_CHECKLOCKTIMEVERIFY` ou `OP_CHECKSEQUENCEVERIFY`), soit à une transaction entière grâce à l'utilisation de champs de transaction spécifiques (`nLockTime` ou `nSequence`).

> ► *On parle également parfois d'un « locktime » pour évoquer un timelock. Pour plus d'informations, voir la définition de [**OP_CHECKLOCKTIMEVERIFY (0XB1)**](/dictionnaire/O.md#op_checklocktimeverify-0xb1), [**OP_CHECKSEQUENCEVERIFY (0XB2)**](/dictionnaire/O.md#op_checksequenceverify-0xb2), [**NLOCKTIME**](/dictionnaire/N.md#nlocktime) et [**NSEQUENCE**](/dictionnaire/N.md#nsequence).*

