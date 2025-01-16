Répertoire A
########################

En quoi consiste le repA ?
*******************************
Le repA est une table produite par Sucombe qui contient la liste des factures et des payements de l'année en cours.
On travaillera principalement sur le repA du 31/12/2024.
Les champs que l'on a renomés et exploités sont les suivants :

* 'MontantTTC', Montant constaté 
* 'Objet', Libellé de la commande (BDC/...) 
* 'Date_CPCM', Date d'envoi par le BGA
* 'Date_paiement', 
* 'EJ', 
* 'payé', Montant payé
* 'Solde' , Solde de l'EJ


.. csv-table::
   :header: annee,MontantTTC,payé
   :widths: 30, 30,30
   :width: 80%


  21,73.3,68.1
  22,305.7,191.3
  23,4238.5,3663.6
  24,24302.7,8929.6


