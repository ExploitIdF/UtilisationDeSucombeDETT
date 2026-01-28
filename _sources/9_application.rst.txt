Analyse de  l'application Sucombe
#####################################
.. toctree::
   :hidden:
   :maxdepth: 3

  91_base

Dans cette partie, on documente le fonctionnement de l'application et en particulier, la manière dont les informations sont enregistrées dans la base de données.

Base de donnée  PostgreSQL
***************************
J'ai eu accès à la base au travers de fichiers **dump** créé pour la sauvegarde de la base.  
A partir d'un fichier dump, le programme psql recré la base dans son état au moment de l'enregistrement.
la base s'appelle `sucombe` et les 60 tables sont dans un *schéma* qui s'appelle aussi `sucombe`.

Actions effectuées sur l'application
***************************************
Création d'une prestation
=============================
Les utilisateurs de Sucombe, tels que les TDM, on le droit de créer des prestations.

La création d'une **prestation** donne lieu à un enregistrement dans la table `proposition_prestation`. 

Les champs renseignés sont :

* 'fou_id', via la table fournisseur,
* 'mar_id', via la table marche,   
* 'prop_pre_date_previsionnelle', 
* 'prop_pre_lieu_execution' via la table lieu,       
* 'prop_pre_num_gmao' qui peut être rempli automatiquement quand la prestation est créée par un  OT dans Coswin, 
* 'type_id' (Préventif, Curatif ...) via la table type, 

Les champs suivants sont générés par l'application :

* 'age_id' agent authentifié sur l'application, via la table agent,
* 'prop_pre_libelle'  PRESTA/<annee>_<Unité>_<marché>_<incrément> par exemple PRESTA/2024_PCTT Nord_Ventilation_6, 
* 'prop_pre_creation' date de création,

La prestation comporte plusieurs lignes correspondant à des **produit**, leur numéros de prix et leurs quantités.

Chacune de ces lignes donne lieu à un enregistrement dans la table `proposition_produit`.

Les champs renseignés sont :

	

* prod_id, l'identifiant du produit via la table produit,  prop_prod_creation prop_prod_maj 
* prop_prod_quantite, la quantité commandée 

Les champs suivants sont générés par l'application :
* com_pro_id2 , identifiant de la prestation élémentaire,
* prop_pre_id , identifiant de la prestation,
* prop_prod_prix_ht, prix connu par l'application  # prop_prod_taux


