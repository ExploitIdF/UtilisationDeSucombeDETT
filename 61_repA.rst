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

Traitements réalisés
**************************
Montants constatés et payés en 2024
=======================================
On a extrait les années du libellé de commande (ce qui ne correspond par toujours à l'année budgétaire).
On calcule les montants présents dans le repA de fin 2024 par année de commande.  

Cela donne le volume des payements selon l'ancienneté des commandes.

.. csv-table::
   :header: Année,Montant constaté,Montant payé
   :widths: 30, 30,30
   :width: 80%

     21,73.3,68.1
     22,305.7,191.3
     23,4238.5,3663.6
     24,24302.7,8929.6

Date_CPCM,taux,totk
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

