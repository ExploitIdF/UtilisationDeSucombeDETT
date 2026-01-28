Les prestations dans Sucombe
#################################

.. toctree::
   :hidden:
   :maxdepth: 3

   cp1_libelle
   cp2_id
   cp28_numOT
   cp3_lgnEq
   cp4_type
   cp5_lieu
   cp6_marche
   cp7_service

Lorsqu'un TDM crée un ordre de travail (OT) dans la GMAO CosWin, une prestation est automatiquement créée dans Sucombe. 
Pour être exact, cela concerne des OT isolés ou les OT *père*, les OT fils ne sont pas concernés.

La préstation est donc l'équivalent budgétaire et comptable de l'OT de la GMAO.
  
Table des prestations
**************************
La première table analysée est celle des **prestations** car elle contient des informations assez riches sur l'ensemble des commandes.
Le tableau ci-dessous fournit les nombres de prestations saisies dans Sucombe sur la période 2020-23.

.. csv-table:: Nombre de prestations saisies par Service et par an depuis 2020
   :file: _static/servAn.csv
   :widths: 20,  20, 20, 20, 20
   :header-rows: 1

Les :doc:`champs de cette table <champsPresta>` sont les suivants :
``'Action', 'Libellé', 'Identifiant', 'Date création', 'Numméro OT','Ligne d'équipement', 'Type', 'Lieu','Date prév.', 
'Montant prestation HT', 'Montant Constaté HT', 'Marché', 'Agent', 'Service', 'État'``
  
Dans cette partie, on présente les résultats de l'examen des principaux champs de la table des prestations.

On présente la nature du champ et la manière dont il est renseigné par les utilisateurs. Dans certains cas les observations sur les données conduisent à des préconisations adressées aux utilisateurs sur la manière de renseigner le champ.

Quand le champ est un choix dans une liste, on peut avoir des observations sur le contenue de cette liste. Ces observations sont adressées au configurateur de l'application Sucombe.

* Action
* :doc:`Libellé<cp1_libelle>`
* :doc:`Identifiant<cp2_id>`
* Date création
* :doc:`Numéro OT<cp28_numOT>`
* :doc:`Ligne d'équipements<cp3_lgnEq>`
* :doc:`Type<cp4_type>`
* :doc:`Lieu<cp5_lieu>`
* Date prév.
* Montant prestation HT
* Montant Constaté HT
* :doc:`Marché<cp6_marche>`
* Agent
* :doc:`Service<cp7_service>`
* État

















  


