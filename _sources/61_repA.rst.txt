Répertoire A
########################

En quoi consiste le repA ?
*******************************
Le repA est une table produite par Sucombe qui contient la liste des factures et des payements de l'année en cours.
On travaillera principalement sur le repA du 31/12/2024.
Les champs que l'on a renomés et exploités sont les suivants :

* 'MontantTTC', Montant constaté 
* 'Objet', Libellé de la commande (BDC_2024_...) 
* 'Date_CPCM', Date d'envoi par le BGA
* 'Date_paiement', 
* 'EJ', 
* 'payé', Montant payé
* 'Solde' , Solde de l'EJ

A quoi ça sert ?
********************
Comme on le voit ci-dessous, la saisie des paiements dans Sucombe n'est pas systématique.

La saisie des dats d'envoie au CPCM/ CGF est elle plus systématique ?

En quoi cette table apporte-elle une plus value par rapport à jp57, tables des paiements Chorus ?



Traitements réalisés
**************************
Montants constatés et payés en 2024
=======================================
On a extrait les années du libellé de commande (ce qui ne correspond par toujours à l'année budgétaire).
On calcule les montants présents dans le repA de fin 2024 par année de commande.  

Cela donne le volume des payements selon l'ancienneté des commandes.

.. csv-table::
   :header: Année,Montant constaté,Montant payé
   :widths: 20, 30,30
   :width: 60%

     2021,73.3,68.1
     2022,305.7,191.3
     2023,4238.5,3663.6
     2024,24302.7,8929.6

Le faible montant des paiements relatif au constat est lié au fait que, sur la deuxième partie de l'année, la plus grande partie des constats ne font pas l'objet de payement reporté dans le repA. Il est possible que ces paiements aient eu lieu mais que cela ne soit pas enregistré.

La table suivante indique pour chaque mois de l'année 2024, le taux de constats payés (selon le repA) et le montant total constaté.

.. csv-table::
   :header: Mois,Taux de montants payés (%),Total des montants envoyés
   :widths: 20, 30,30
   :width: 50%
   
   01,96,1150
   02,96,745
   03,76,824
   04,84,1313
   05,81,1088
   06,92,2323
   07,83,2185
   08,78,1654
   09,45,1305
   10,43,3733
   11,22,3657
   12,3,8937

