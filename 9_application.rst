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
La création d'une prestation donne lieu à un enregistrement dans la table `proposition_prestation`. Les champs renseignés sont :

* 'age_id' via la table agent,
* 'fou_id', via la table fournisseur,
* 'mar_id', 'prop_pre_libelle', 'prop_pre_creation',
* 'prop_pre_lg_equipement',    
* 'prop_pre_date_previsionnelle', 
* 'prop_pre_lieu_execution',       
* 'prop_pre_condition_execution', 
* 'prop_pre_num_gmao', 'prop_pre_archive',
* 'type_id', 



