Chorus
######################

.. toctree::
   :hidden:
   :maxdepth: 3

   652_engagements
   653_paiements

Le DETT reçoit chaque semaine des fichiers issus de Chorus : 

* jp51.ods et 
* jp57.ods.

On note dans cette page des informations sur la nature de ces fichiers et sur les exploitations que l'on a faites avec.

jp51 
***************************
Ce fichier contient les opérations d'engagemement pour tous les *Services* de la DIRIF. 

**Liste des champs (colonnes) de la table** :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
On recopie les entêtes des colonnes de la table :

```
'Exercice comptable', 'Centre financier', 'Domaine fonctionnel', 'Centre de coûts', 'Services',
'Numéro de pièce de la pièce de référence',  'Numéro de poste de la pièce de référence', 'Texte', 'Montant à contrôler en dev. transaction',
'Fournisseur', 'Nom 1', 'Type de montant', 'Type de montant.1', 'Activité','Programme de financement', 'Description du programme de financement',
'Période', 'Date de mise à jour Comptabilité budgéta', 'Date comptable',  'Désignation du cpte budgétaire', 'Saisi par', 'Type de valeur', 'Compte général'
```

Les lignes (opération d'engagement) qui concernent le DETT peuvent être identifiées indifféremment par les conditions :

```
Services == 'STT / DETT'   ou

Centre de coûts == 'DIR94ET094'
```

Pour DIMET ce serait :

``
Services == 'STT / DIMET`'   ou

Centre de coûts == 'DIR94AR094'
``

'Numéro de pièce de la pièce de référence'
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Le champ :code:`'Numéro de pièce de la pièce de référence'` désigne l'EJ et on emploiera ce dernier terme par la suite.

C'est par ce champ que l'on peut faire des liaisons avec le fichier des paiements ou avec les commandes enregistrées dans Sucombe (**RepD**).


**'Type de montant' & 'Type de montant.1'** : 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Le second champ **'Type de montant.1'** est un code pour le premier. 

La table suivante indique les codes et le nombre d'occurences de chaque **type de montant**.

.. csv-table::
   :header: Code du type, Nom du type , Nombre d'occurences en 2024 
   :widths: 10, 20,10
   :width: 80%

    100, Original, 1717
    150, Modification ,55
    200, Réduction ,2702
    350, Report exercice suivant (engagements) ,1582
    500, Ajustement par pièce suivante, 226
    600 ,Changement d'imputation émetteur ,819
    650 ,Changement d'imputation récepteur, 819

Les engagements simples avec création d'un EJ ont le type **Original** (code 100). Ce même type s'applique pour le premier engagement sur une EJ reporté de l'année précédente.

Le type  **Modification** (code 150) est utilisé en pour un engagement supplémentaire et parfois pour une réduction/correction.

Les réductions (200) correspondent aux paiements et prennent, à quelques exceptions près, des valeurs négatives. 
Il ne s'agit donc pas d'engagements.

Les reports d'engagements (code 350) interviennent en début d'année, leur date de mise à jour est le 1er janvier.

Presque 1300 EJs sont reportés, avec parfois plusieurs opérations de report pour le même EJ. 
Le montant total des reports est de 32,5M€ en 2024.

Les **changements d'imputation** (codes 600 et 650) sont le plus souvent utilisés simultanément car il s'agit de transfert entres lignes du DTT. Si les changements concerne un autre service, DIMET par exemple, on aura selement l'un ou l'autre des types.

'Désignation du cpte budgétaire' : 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ce champ permet d'identifier les rares dépenses immobilisées, 
il s'agit principalement d'opérations suivies par DIMET ou le SEB, même si elles restent comptablement attribuées au DETT.

'Date de mise à jour Comptabilité budgéta'
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Cette date est celle de l'opération enregistrée.

'Date comptable'
^^^^^^^^^^^^^^^^^^
C'est la date de création de l'EJ, elle peut être ancienne quand l'EJ est réalimenté chaque année, 
comme on le fait pour les fluides, ou lorsque l'EJ n'a pas été supprimé quand bien même il n'est plus actif.

jp57 
******
Ce fichier contient les opérations de paiement, pour tous les *Services* de la DIRIF. 

Champs (colonnes) de la table :
=================================
On recopie les entêtes des colonnes de la table :

```
'Exercice comptable', 'Période', 'Centre financier', 'Domaine fonctionnel', 'Centre de coûts', 'Services', 'Fournisseur',
'Nom 1', 'Type de montant', 'Programme de financement',       'Désignation du programme de financement',
'Description du programme de financement', 'Référence',       'Texte d'en-tête de pièce', 'Numéro de la pièce précédente',
'Poste de pièce précédente', 'Montant à contrôler en devise trans. ave',       'Date comptable', 'Nº pièce de paiement',
'Date de base pour le calcul de l'échéanc', 'Date pièce', 'Activité',       'Type de pièce', 'Texte type val.',
'Numéro de pièce comptabilité budgétaire',       'Numéro de pièce de la pièce de référence', 'Numéro de pièce RW',
'Type de valeur','Zone client', 'N° de transaction', 'Immobilisation','Désignation', 'Code ID bancaire', 'Compte bancaire', 'Clé R.I.B.'
```

Certains champs sont communs avec ceux du fichier **jp51**.

'Numéro de la pièce précédente'
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
le champs **'Numéro de la pièce précédente'** correspond à l'EJ pour lequel est réalisé le paiement. Ce champ permet de faire une liaison avec le fichier jp51 et le repD.

'Date comptable' & 'Date pièce'
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

 **'Date comptable'** est la date du paiement.

**'Date pièce'** semble être la date de transmission de la demande de paiement par le BGA au CGF.
Quand on peut faire la liaison avec le répertoire D, on observe que cette date est postérieur à la date du constat.

Quand on observe la distribution de la différence entre 'Date comptable' & 'Date pièce', on trouve une valeur médiane de 18 jours.
Dans 10% des cas, la différence est inférieure à 4 jours.

Valeurs négatives du montant du paiement
==========================================
Les montants des paiements sont presque toujours positifs. En 2024, sur près de 3000 lignes, on ne trouve que 10 valeurs inférieures à -100€.

On observe en particulier le montant -740k€ avec le fournisseur EDF (Sans EJ).

Une ligne avec un montant -3686.79€, avec le fournisseur OPEN (Sans EJ), comporte la mention PENALITE dans le champs **Texte_tête de pièce**. 

Les autres lignes, en 2024, ont un EJ, ce qui permet de les rapprocher des paiements qu'elles viennent corriger.

Liens entre jp51 et jp57
=========================
Les paiements de jp57 sont presque toujours liés à une ligne de type **Réduction** de jp51. 
On a observé un écart de 30 lignes sur les deux derniers jours de l'années, mais la raison est peut être que le fichier jp57 n'était pas complet.

Comme cela concerne des paiements importants, la différence d'estimation des paiements entre les deux fichiers est de 2,5M€.

Transition entre l'année N et l'année N+1
***********************************************
Les opérations d'engagement ne sont pas enregistrées pendant les premiers jours de l'année.
En 2024, les engagements sont enregistrées comptablement à partir du 16 janvier, mais en 2025 le premier engagement n'est enregistré qu'en février.
En fin d'année, des engagements sont enregistrés jusqau'au 31 décembre. 

Les opérations de paiement ne sont comptabilisées qu'à partir du 10 janvier environ et jusqu'au 31 décembre.
Les opérations de paiement qui sont réalisés dans les 10 derniers jours de décembre sont réparties entre les années N et N+1.

Pour les paiements, on compte dans l'année N des paiements dont la *date comptable* est le 30 décembre. 
Cependant, des paiements dont la *date comptable* est le 20 décembre sont comptés dans l'année N+1.

Même si le paiement est comptabilisé dans l'année N+1, si sa date comptable est en décembre, 
ce paiement donnera lieu à une réduction d'engagement apparaissant dans le journal des engagements (JP51) de l'année N. 
Le montant payé n'apparait pas dans les reports d'engagements sur l'année N+1.







