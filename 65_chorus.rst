Chorus
######################

.. toctree::
   :hidden:
   :maxdepth: 3

   652_engagements

Le DETT reçoit chaque semaine des fichiers issus de Chorus : jp51.ods et jp57.ods.
On note dans cette page la nature de ces fichiers et les exploitations que l'on a faites avec.

jp51 
***************************
Ce fichier contient les opérations d'engagemement pour tous les *Services* de la DIRIF. 

**Liste des champs (colonnes) de la table** :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
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

```
Services == 'STT / DIMET`'   ou

Centre de coûts == 'DIR94AR094'
```

**'Type de montant' & 'Type de montant.1'** : 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Le second champ 'Type de montant.1' est un code pour le premier.

.. csv-table::
   :header: Code du type, Nom du type , Nombre d'occurences en 2024 
   :widths: 10, 20,10
   :width: 40%

    100, Original, 1717
    150, Modification ,55
    200, Réduction ,2702
    350, Report exercice suivant (engagements) ,1582
    500, Ajustement par pièce suivante, 226
    600 ,Changement d'imputation émetteur ,819
    650 ,Changement d'imputation récepteur, 819

Les réductions (200) correspondent aux paiements et prennent à quelques exceptions près de svaleurs négatives. Il ne s'agit donc pas d'engagements.

Les reports d'engagement (350) interviennent en début d'année, leur date de mise à jour est le 1er janvier.

'Désignation du cpte budgétaire' : 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
ce champ permet d'identifier les rares dépenses immobilisées, 
il s'agit principalement d'opération suivies par DIMET ou le SEB, même si elle reste comptablement attribuées au DETT.

'Date de mise à jour Comptabilité budgéta'
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Cette date est celle de l'opération enregistrée en 2024.

'Date comptable'
^^^^^^^^^^^^^^^^^^
C'est la date de création de l'EJ, elle peut être ancienne quand l'EJ est réalimenté chaque année comme on le fait pour les fluides ou quand l'EJ n'a pas été supprimé quand bien même il n'est plus actif.






