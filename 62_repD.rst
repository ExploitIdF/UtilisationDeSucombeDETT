RepD
#############

En quoi consiste le repD ?
*******************************
Le repD est une table produite par Sucombe qui contient la liste des engagements budgétaires de l'année en cours.
On travaillera principalement sur les repD des 31/12/2023 &  31/12/2024, soit les années entières 2023 & 2024.
Les champs que l'on a renomés et exploités sont les suivants :

* 'noLC',Libellé de la commande (BDC/2024_...) 
* 'Date',
* 'Unité',
* 'MontantTTC', 
* 'Axe', 
* 'noEJ', 
* 'DateConstat',   
* 'PouT',
* 'MontantConstTTC',  
* 'dateRéception', 
* 'Solde EJ',
* 'Date du Mandat'

Traitements réalisés
**************************
Année 2024
========================
En 2024, le repD contient 1637 lignes dont 71 n'ont pas d'EJ et ne sont pas des commandes abouties.  

On identifie 1297 commande définitivement constatées, 149 commandes partiellement constatées et 120 commande encore non constatées.

Les montants engagées, constatés et payés enregistrés dans le repD figurent dans le tableau :

.. csv-table::
   :header: Niveau de constat, Engagé TTC,Constaté TTC,	Facturé TTC
   :widths: 30, 20,20,20
   :width: 80%
			
    Constaté,	22577	,21445,	17144
    Partiellement constaté,	5736,	3941,	2579
    Non constaté,	3720,	0,	0






