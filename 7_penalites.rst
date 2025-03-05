Outils de saisie du *Certificat de pénalité*
###############################################
Dans le cadre de la mise en place par **UPMM** de la procédure pour l'application des pénalités prévues par les marchés du DETT, 
on a envisagé de réaliser une application qui serait mise à la disposition des TDM pour éditer les **Certificats de pénalité**.  
Un prototype de l'application est accessible par le lien suivant :  

`<https://penalite-pdf.web.app/>`_

Est-ce la bonne solutions ?
==============================
Le choix de s'appuyer sur une telle application peut rendre le travail plus facile pour le TDM, mais il représente aussi une charge pour UPMM qui doit tenir à jour la configuration de l'application lors des renouvellement des marchés. L'application, même si elle est artisanale, comporte également un besoin d'administation informatique qui n'est pas assuré de manière durable dans la configuration actuelle.

Pour les pénalités de retard, il existe un formulaire non obligatoire que l'on pourrait utiliser. 
https://www.economie.gouv.fr/files/directions_services/daj/marches_publics/formulaires/EXE/imprimes_exe/EXE13.doc

Pour faciliter le travail des TDM, les formulaires établis pourraient être classés et partagés sur RESANA, afin de pouvoir être réutilisés quand les mêmes circonstances se reproduisent.


Actions à réaliser par le TDM sur l'application :
=================================================
1) Le TDM choisi un marché dans une liste déroulante

2) Le TDM choisi l'une des pénalités prévue par le marché dans une liste déroulante

3) le TDM saisie le montant de la pénalité qu'il a calculé

4) le TDM saisie la custification et les commentaires qu'il veut faire figurer sur le certificat.

5) le TDM télécharge le certificat sous la forme d'un PDF.

Fichier de configuration
=================================
L'application a besoin pour fonctionner que soit renseigné un `fichier de configuration` qui, pour chaque marché, indique la liste des pénalités prévues, avec, pour chaque pénalité, la référence de l'article du CCAG correspondant.

Le fichier de configuration, pour faciliter la phase de développement, est une Google Sheet, placée ici :

`Table des données de configuration <https://docs.google.com/spreadsheets/d/1hdLrf8yLg34iHIghAHqkxu8x2CsYkpKpy2dhXyVMYos/edit?gid=0#gid=0>`_

A ce stade, des valeurs de  test ont été introduites dans le fichier de configuration.

Pour fonctionner de manière opérationnelle, UPMM devra faire le travail de recencement des pénalités de tous les marchés concernés,
afin de les reporter dans un fichier de configuration de production.

Dévelopement de l'application 
===============================
Les développements sont faits par O. Nalin et documentés ici (repo privé voir ON) :
https://github.com/ExploitIdF/penalite-pdf

















