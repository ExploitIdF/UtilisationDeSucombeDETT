Signalisation dynamique - Comparaison des consommations avec le DE
####################################################################
Dans le cadre des bilans des marchés, avant leur renouvellement, Jonathan Cole a demandé que l'on compare les consommations effectives avec le détail estimatif du marché.

Dans cette page, on présente les exploitations réalisées pour répondre à cette demande. 
Le marché Signalisation dynamique est pris comme exemple pour établir le prototype de la procédure.

Extraction des consommations
********************************
L'application Sucombe permet d'exporter un fichier qui, pour chaque numéro de prix, comporte les quantités consommées, les prix unitaires et le prix total.

On appel cette table **ExportSucombe**, elle comporte 430 lignes.

En exploitant la base de données on pourrait accéder aux données par année et par unité (PCTT, UPMM, UIRC ...).


Importation du **Détail estimatif**
**********************************************
Dans le DCE, le DE apparait comme un fichier ODS : :code:`4a- DE SDY V1.ods` . 
Ce fichier contient 13 onglets, le premier étant une synthèse.

Dans un notebook Python, on peut lire chaque onglet, sélectionner et concatenner les lignes dont le premier champ commence par SDY.
On appelle la table ainsi constitué **DE2020**, elle comporte 373 lignes.

L'un des *code prix*, :code:`'SDY FS 401'`, présente une erreur manifeste que l'on corrige pour permettre la liaison avec la table ExportSucombe.

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
    
Prix présents dans le DE
==============================
Pour les prix qui étaient initialement présents dans le DE, on peut comparer les différences entre les montants prévus et les montants consommés.

La table suivante indique les 10 principaux prix pour lesquels la consommation est supérieure à la prévision.

.. csv-table::
   :header: codePrix,designation,prixHT,quantité DE,quantite effective,total DE k€,total effectif k€
   :widths: 15, 40,10,10,10,10,10
   :width: 100%

      SDY DOC 03,"Mise à jour de la documentation « Constructeur » ou « Exploitation » (notice d’exploitation, manuel de maintenance…), ou « Ingénierie » (dossier d’ouvrage, note de calcul…) pour un équipement ou un matériel quels que soient son type, sa technologie, sa situation et le volume de la documentation à mettre à jour, conformément à la Fiche N°9.Ce prix rémunère la modification de tous les documents de référence disponibles dans la base DTC de la DiRIF",2282.09,4,39,9,89
      SDY FS 08,"Fourniture d’un Pilote Informatique Contrôleur d’Accès (PICA) FARECO pour armoire CAC, avec soft de gestion inclus (Fareco UC Gallery).",9409.96,5,14,47,131
      SDY FS 256,Fourniture d’une carte UPP03 pour matériel SIGNATURE (Référence SVMS 100697).,578.34,3,170,1,98
      SDY ING 01,"Plus-value aux prix des séries SDY ING, SDY MEV et SDY DIV pour la réalisation des prestations de nuit entre 22h et 06h.",0.6,0,131838,0,79
      SDY MEV 01,"Installation, raccordement et paramétrage d’une interface de communication SHDSL quels que soient son type (point à point, anneau redondant...) et sa technologie (cuivre, Fibre Optique) en armoire de commande d’un équipement (PMV, SAV, CAC…), avec fourniture de l’ensemble des périphériques nécessaires comme son alimentation BT/TBT, son disjoncteur différentiel de protection, ses câbles et fileries d’alimentation et de transmission, ses cordons ré",1993.99,3,42,5,83
      SDY MEV 12,"Installation, raccordement et configuration d’un Pilote de panneau (PIP) de technologie LCR / TCP IP, de type carte pilote STS 311 et de ses interfaces éventuelles (carte UPP, carte injection...) en armoire de commande d’un équipement de signalisation dynamique (PMV, SAV…) quelle que soit sa situation, avec fourniture des périphériques comme son alimentation BT/TBT, son disjoncteur différentiel de protection, ses câbles et nappes (électrique, bus",1497.65,3,185,4,277
      SDY MP 104,Tunnel de Type 4 (Nombre de module supérieur à 40 et inférieur ou égal à 55).,11157.94,5,12,55,143
      SDY MP 202,Tunnel de Type 2 (Nombre de module supérieur à 10 et inférieur ou égal à 25).,10326.03,14,20,144,206
      SDY MP 204,Tunnel de Type 4 (Nombre de module supérieur à 40 et inférieur ou égal à 55).,17997.72,5,20,89,359
      SDY MP 205,Tunnel de Type 5 (Nombre de module supérieur à 55).,18499.46,1,6,18,110
            
La table suivante indique les 10 principaux prix pour lesquels la consommation est inférieure à la prévision.

.. csv-table::
   :header: codePrix,designation,prixHT,quantité DE,quantite effective,total DE k€,total effectif k€
   :widths: 15, 40,10,10,10,10,10
   :width: 100%

      SDY FS 407,"Fourniture d’un caisson de type « PMS » Grande Gamme, signaux XB14 (50 et 70) et XA1a décors normaux par bandes à diodes de diamètre 1050 mm environ (XB14) et 1250mm environ (base du XA1a), complet et prêt à fonctionner, de dimensions extérieures 1300x1300 mm et ouverture par la face avant, avec dispositifs de raccordement et de fixation (équerres, colliers, profilés et brides pour fixation sur PPHM.…) et mise en peinture (RAL sera définit par le",29939.01,1,0,29,0
      SDY MC 01,Unité de référence « recherche de défaut » (diagnostic).,504.97,1600,1285,807,648
      SDY MC 02,Unité de référence « intervention corrective » (dépannage).,661.43,1600,1144,1058,756
      SDY MEV 09,"Fourniture et installation du kit permettant l'adaptation mécanique de cartes afficheurs de nouvelle génération en lieu et place des cartes afficheurs existantes pour un PMV A SIRIUS SIGNATURE de type 2 lignes de 18 caractères Hc 320mm.Ce kit comprend les platines porte-afficheur, toutes les nappes de liaisons inter-caractères d’alimentation et de réseau de données, les interfaces entre les platines et le caisson du PMV…Ce prix rémunère égaleme",15144.84,2,0,30,0
      SDY MP 01,"Visite annuelle décrite dans la gamme SDY 001 pour un équipement installé sur une structure PPHM visitable et de type Panneau à Messages Variables multi-usage dit « Picto », de type Panneau à Messages Variables dit « Autoroutier », dit « Hors Autoroute » ou dit « Dédié ».",671.14,740,242,496,162
      SDY MP 02,Visite annuelle décrite dans la gamme SDY 002 pour un équipement installé sur mât simple ou support mural et de type Panneau à Messages Variables dit « PMS ».,294.57,100,3,29,0
      SDY MP 03,"Visite annuelle décrite dans la gamme SDY 001 pour une rampe de matériel installée sur une structure PPHM visitable et de type Signaux d’Affectation de Voies R21, quel que soit le nombre de caisson SAV (compris entre 2 et 5).",462.89,180,0,83,0
      SDY MP 04,"Visite annuelle décrite dans la gamme SDY 012 pour un équipement installé sur une structure PPHM non visitable et de type Panneau à Messages Variables, dit « Hors Autoroute » ou dit « Dédié ».",668.98,330,161,220,107
      SDY MP 05,"Visite annuelle décrite dans la gamme SDY 003 pour un matériel de régulation d’accès CAC Type A, B, C ou D (Feux R22 et pré-signalisation).",1117.84,225,78,251,87
      SDY MP 201,Tunnel de Type 1 (Nombre de module inférieur ou égal à 10).,4978.51,8,1,39,4
      
      











