RepD
#############

En quoi consiste le repD ?
*******************************
Le repD est une table produite par Sucombe qui contient la liste des engagements budgétaires de l'année en cours.
On a travaillé principalement sur les repD des 31/12/2023 &  31/12/2024, soit les années entières 2023 & 2024.
Les champs que l'on a renomés et exploités sont les suivants :

* 'noLC', Libellé de la commande ( du type : BDC/2024_...) 
* 'Date', Date de validation du bon de commande
* 'Unité',
* 'MontantTTC', 
* 'Axe', 
* 'noEJ', 
* 'DateConstat',   Autant de dates que de constats
* 'PouT', Le constat est il, non existant, partiel ou total
* 'MontantConstTTC',  Autant de montants que de constats
* 'dateRéception', 
* 'Solde EJ',
* 'Date du Mandat'

A quoi sert le rep D ?
***************************
Le rep D est l'un des principaux outils de suivi du budget. 
Les fluides et certaines dépenses ne sont pas suivis dans Sucombe, mais la plus grande partie des dépenses s'y trouve.

Etapes des saisies dans Sucombe qui contribuent à l'alimentation du rep D
===============================================================================
Tous les bons de commande validés par un chef d'unité *habilité* sont enregistrés dans le repD.

Le BGA doit recevoir par mail le scan du bon de commande signé, pour faire la DA dans Chorus. 

En général, moins de 15 jours après la saisie dans Chorus, le BGA reçoit un numéro d'EJ qu'il reporte *à la main* dans Sucombe.
Dès lors ce N° d'EJ apparait dans le rep D.

L'agent qui suit l'une des prestations qui composent la commande (un TDM par exemple)  édite un constat dans Sucombe. 
Le montant et la date du constat sont enregistrés dans le rep D  (La date du constat = date de fin de travaux).

Le BGA reçoit le constat **signé** et saisie dans Sucombe la date d'envoi au CGF.
Cette date figure dans la  colonne "date de réception" sur le REPD.

Par la suite, le BGA reporte dans Sucombe les dates des mandats et les montants mais cette information n'est pas systématiquement saisie.
Il semble que Sucombe (le rep D) ne soit pas la principale base du suivi des paiements. 

Situations de commandes  qui s'écartent du processus normal de traitement
===============================================================================
Le chef d'unité peut valider un bon de commande dans Sucombe mais ne pas donner suite. 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Le bon de commande ne parvient ni au BGA ni au prestataire. Il reste néanmoins dans Sucombe et figure dans le rep D.

Il n'y a pas de règle systématique pour identifier les lignes correspondantes, le plus souvent, 
le BGA écrit Annulé, après consultation de l'unité/pctt, là où devrait apparaitre l'EJ.

La commande est envoyée au prestataire et au BGA mais refusée par le CGF
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Dans ce cas, le BGA ne peut pas saisir un EJ dans Sucombe et le communiquer au prestataire.
On se trouve dans la situation délicate d'avoir passé une commande sans engagement financier enregistré dans Chorus.

Le BGA fait en sorte de régulariser la commande avec l'aide de l'unité d'origine et du destinataire, 
titulaire d'un marché ou attributaire d'une *commande simple*.

En fin d'année 2024, on avait une dizaine de commande qui avaient été constatées sans être engagées dans Chorus.

Le numéro d'EJ qui est reporté dans Sucombe est erroné
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Comme le numéro d'EJ est recopié à la main, il arrive qu'il y ait des erreurs de saisie.

Parfois, le CGF annule un EJ alors qu'une commande est en cours d'execution.
Un nouvel EJ peut être attribué mais ne pas être immédiatement reporté dans Sucombe.

Le BGA fait des efforts pour détecter ces anomalies et les corriger pour permettre les traitements qui mettent en jeu une liaison entre le répertoire D et le fichier des paiement jp57.

Calcul des dettes et charges
==============================
En fin d'année, UPMM fait une liaison entre le répertoire D et le fichier des paiement Chorus (jp57) pour connaitre le niveau des paiements pour chaque commande et le comparer au montant constaté.

Pour que ce calcul soit fiable, il faut que les EJ soient correctement renseignés, ce qui donne lieu à un travail de contrôle.



Traitements réalisés
**************************
Année 2024
========================
En 2024, le repD contient 1637 lignes dont 71 n'ont pas d'EJ et ne sont donc pas des commandes abouties.  

On identifie 1297 commandes définitivement constatées, 149 commandes partiellement constatées et 120 commandes encore non constatées.

Les montants engagées, constatés et payés enregistrés dans le repD figurent dans le tableau :

.. csv-table::
   :header: Niveau de constat, Engagé TTC,Constaté TTC,	Facturé TTC
   :widths: 30, 20,20,20
   :width: 80%
			
    Constaté,	22577	,21445,	17144
    Partiellement constaté,	5736,	3941,	2579
    Non constaté,	3720,	0,	0

Une partie des engagements constatés définitivement en dessous des engagements a pu être recyclée par annulation des AE au niveau de la DGFIP.

:doc:`57 des commandes qui n'ont pas fait l'objet d'un constat ont un montant supérieur à 10 000 €<621_nonC>`.

:doc:`46 des commandes qui  ont  fait l'objet d'un constat partiel ont un reste à constater supérieur à 10 000 €<622_partC>`.




