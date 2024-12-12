Outils de saisie du *Certificat de pénalité*
###############################################
Dans le cadre de la mise en place par **UPMM** de la procédure pour l'application des pénalités, on a envisagé de réaliser une application qui serait mise à la disposition des TDM pour éditer les **Certificats de pénalité**.
Un prototype de l'application est accessible par le lien suivant : 

`<https://penalite-pdf.web.app/>`_

Actions à réaliser sur l'application :
========================================
1) Le TDM choisi un marché dans une liste déroulante

2) Le TDM choisi l'une des pénalités prévue par le marché dans une liste déroulante

3) le TDM saisie le montant de la pénalité qu'il a calculé

4) le TDM saisie la custification et les commentaires qu'il veut faire figurer sur le certificat.

5) le TDM télécharge le certificat sous la forme d'un PDF.

L'application a besoin d'un fichier de configuration qui pour chaque marché indique la liste des pénalité avec la référence de l'article du CCAG correspondante.

Le fichier de configuration, pour faciliter la phase de développement est une Google Sheet, placée ici :

`Table des données de configuration <https://docs.google.com/spreadsheets/d/1hdLrf8yLg34iHIghAHqkxu8x2CsYkpKpy2dhXyVMYos/edit?gid=0#gid=0>`_

A ce stade, des valeurs de  test ont été introduites.

Pour fonctionner de manière plus réaliste, il faudrait faire le travail de recencement des pénalités dans tous les marchés concernés.











