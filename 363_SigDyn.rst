Signalisation dynamique - Comparaison des consommations avec le DE
####################################################################
Dans le cadre du bilans des marchés, avant leur renouvellement, Jonathan Cole a demandé que l'on compare les consommations avec le détail estimatif du marché.

Dans cette page, on présente les exploitations réalisées pour répondre à cette demande. 
Le marché Signalisation dynamique est pris comme exemple pour établir le prototype de la procédure.

Extraction des consommations
********************************
L'application Sucombe permet d'exporter un fichier qui pour chaque numéro de prix comporte les quantités consommées, les prix unitaires et le prix total.

On appel cette table **ExportSucombe**, elle comporte 430 lignes.

Importation du **Détail estimatif**
**********************************************
Dans le DCE, le DE apparait comme un fichier ODS : `4a- DE SDY V1.ods` . 
Ce fichier contient 13 onglets, le premier étant une synthèse.

Dans un notebook Python, on peut lire chaque onglet et sélectionner les lignes dont le premier champ commence par SDY.
On appelle la table ainsi constitué **DE2020**, elle comporte 373 lignes.

L'un des *code prix*, `'SDY FS 401'`, présente une erreur manifeste que l'on corrige pour permettre la liaison avec la table ExportSucombe.

Pour 24 prix, la quantité prise en compte dans le DE est nulle.
Ces prix représentent une dépense de 97 k€ ( 1% du total).

Comparaison entre les consommations et le DE
************************************************
Prix nouveaux
===============

57 prix utilisés n'apparaissent pas dans le DE et représentent une dépense de 2 848 k€ (30% du total).

Les 15 principaux prix en termes de montant dépensé sont présenté dans la table suivante, triée selon les numéros de prix.

.. csv-table::
   :header: codePrix,designation,unite,prixHT,quantite,totalHT
   :widths: 10, 40,10,10,10,10
   :width: 100%

    SDY FC 12,Fourniture d’un double modem 2 fils G.SHDSL-Bis (Référence CXR COPPERWAY-BIS-2TTX).,l'unité,1344.43,47.0,63188.21
    SDY FS 202 bis, Fourniture de 36 cartes afficheur à diodes DIM09-H320-1 (J4-A23-I40) pour PMV SIGNATURE (Référence SVMS 168782 (STS 120)).,Lot de 5,49137.66,7.6,373446.22
    SDY FS 203 bis, Fourniture de 54 cartes afficheur à diodes DIM09-H320-1 (J4-A23-I40) pour PMV SIGNATURE (Référence SVMS 168782 (STS 120)).,Lot de 5,73706.49,1.0,73706.49
    SDY FS 263,Fourniture d’une carte Pilote 17 STS – Gestion avec bus afficheur (PIP) pour matériel SIGNATURE (Référence SVMS 183660).,Lot de 5,7261.67,47.0,341298.49
    SDY FS 269,Fourniture de 144 cartes afficheur à diodes DIM16-H160x3-0 (J3-A60-I30) pour PMV SIGNATURE (Référence SVMS 170993).,Lot de 144,94787.0,1.25,118483.75
    SDY FS 272,Fourniture de 180 cartes afficheur à diodes DIM16-H200-1 (J1-A23-I33) pour PMV SIGNATURE (Ré- férence SVMS 169483).,Lot de 180,30991.0,2.0,61982.0
    SDY FS 276,Fourniture de 16 cartes afficheur à diodes GRA16-H352-QUADRI-44(WRJB) pour PMV Signature (Référence SVMS 14P05400202517),Lot de 16,21162.0,4.0,84648.0
    SDY FS 501,Fourniture de 270 (54x5) cartes afficheurs alphanumériques Hc 320mm Abéon SD-A321.,Lot de 270,56946.86,2.0,113893.72
    SDY FS 503,Fourniture de 80 (16x5) cartes afficheurs pictogrammes 16x16 R/J Abéon SD-H351,Lot de 80,51840.51,2.2,114049.12
    SDY MEV 08 bis,"Fourniture et installation du kit permettant l'adaptation mécanique de cartes afficheurs de nouvelle génération en lieu et place des cartes afficheurs existantes pour un PMV A SIRIUS SIGNATURE de type 3 lignes de 18 caractères Hc 320mm. Ce kit comprend les platines porte-afficheur, toutes les nappes de liaisons inter-caractères d’alimentation et de réseau de données, les interfaces entre les platines et le caisson du PMV… Ce prix rémunère égaleme",Lot de 5,73339.63,1.0,73339.63
    SDY MEV 09 bis,"Fourniture et installation du kit permettant l'adaptation mécanique de cartes afficheurs de nouvelle génération en lieu et place des cartes afficheurs existantes pour un PMV A SIRIUS SIGNATURE de type 2 lignes de 18 caractères Hc 320mm.Ce kit comprend les platines porte-afficheur, toutes les nappes de liaisons inter-caractères d’alimentation et de réseau de données, les interfaces entre les platines et le caisson du PMV…Ce prix rémunère égaleme",Lot de 5,68014.77,7.6,516912.25
    SDY MEV 16,"Installation, raccordement et configuration d’un Pilote de panneau (PIP) de technologie LCR / TCP IP, de type Abéon SD-341 et de ses interfaces éventuelles en armoire de commande et/ou caisson d’un équipement de signalisation dynamique de type PMV Picto SES SCU6 3 lignes de 18 caractères Hc 320mm + Pictogramme + 2 B14 + 2R2 quelle que soit sa situation.Ce prix comprend la fourniture des périphériques comme les protections électriques, des câbles",l'unité,5479.16,17.0,93145.72
    SDY MEV 19,"Installation, raccordement et configuration d’un Pilote de panneau (PIP) de technologie LCR / TCP IP, de type Abéon SD-341 et de ses interfaces éventuelles en armoire de commande et/ou caisson d’un équipement de signalisation dynamique de type Portique de présignalisation SES SCU6 2 B14 + 2R2 quelle que soit sa situation.Ce prix comprend la fourniture des périphériques comme les protections électriques, des câbles, nappes et/ou cordons (électriq",l'unité,5535.27,14.0,77493.78
    SDY MEV 21,Fourniture et installation du kit permettant l'adaptation de cartes afficheurs SVMS DIM 16 en lieu et place de toutes les cartes afficheurs existantes pour un PMV HA SIRIUS Signature de type 2 lignes de 18 caractères Hc 160mm.,Lot de 12,94341.0,1.25,117926.25
    SDY MEV 23,Fourniture et installation du kit permettant l'adaptation de cartes afficheurs SVMS DIM 16 en lieu et place de toutes les cartes afficheurs existantes pour un PMV HA SIRIUS Signature de type 2 lignes de 18 caractères Hc 200mm.,Lot de 5,44037.0,2.0,88074.0
    
Prix présents dans les DE
==============================
Pour les prix qui était initialement présents dans le DE, on peut comparer les différences entre les montants prévus et les montants consommés.

La table suivante indique les 4 principaux prix pour lesquels la consommation est inférieure à la prévision.

.. csv-table::
   :header: codePrix,designation,prixHT,quantité DE,quantite effective,total DE k€,total effectif k€
   :widths: 15, 40,10,10,10,10,10
   :width: 100%

      SDY MC 01,Unité de référence « recherche de défaut » (diagnostic).,504.97,1600.0,1285.0,807,648
      SDY MC 02,Unité de référence « intervention corrective » (dépannage).,661.43,1600.0,1144.0,1058,756
      SDY MP 01,"Visite annuelle décrite dans la gamme SDY 001 pour un équipement installé sur une structure PPHM visitable et de type Panneau à Messages Variables multi-usage dit « Picto », de type Panneau à Messages Variables dit « Autoroutier », dit « Hors Autoroute » ou dit « Dédié ».",671.14,740.0,242.0,496,162
      SDY MP 07,Maintenance préventive renforcée décrite dans la gamme SDY 005 pour un équipement installé sur une structure PPHM visitable et de type Panneau à Messages Variables dit « Autoroutier ».,759.62,190.0,165.0,144,125
      













