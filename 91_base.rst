Base de données
####################
Liste des tables et de leurs champs
**************************************
.. csv-table::
   :header: Table,Nombre <br>de \n lignes,Champs
   :widths: 20,10, 70
   :width: 90%
   :class: striped

   aco_eta,10,aco_id / aco_eta_id / eta_aco_typ_id / aco_eta_date
   aco_fou,0,aco_id / fou_id / montant
   acompte,5,aco_id / mar_id / aco_libelle / aco_creation / aco_maj / aco_reference / aco_date_mandatement / aco_numero_mandatement / aco_montant_ttc / aco_date_situation / aco_annee_budgetaire / aco_qualification / aco_montant_penalite / aco_montant_indem / aco_montant_mora / aco_date_indice_in / aco_increment / aco_internet_mora / aco_repa_increment / age_id
   acompte_etat,5,aco_eta_id / aco_eta_libelle / aco_eta_creation / aco_eta_maj
   age_bud,0,age_id / bud_id / age_bud_montant
   age_mar,2114,age_id / mar_id
   agent,230,age_id / ser_id / age_qua_id / age_creation / age_maj / age_nom / age_prenom / age_email / age_passe / age_actif / age_archive / age_user
   agent_qualification,5,age_qua_id / age_qua_libelle / age_qua_code
   axe,175,axe_id / axe_libelle / axe_creation / axe_maj / axe_centre_financier / axe_domaine_fonctionnel / axe_actif / axe_archive
   bon_execution,92,bon_exe_id / com_id / bon_exe_libelle / bon_exe_creation / bon_exe_maj / bon_exe_date_situation / aco_id / age_id
   budget,665,bud_id / axe_id / ser_id / bud_libelle / bud_creation / bud_maj / bud_annee / bud_actif / bud_archive / bud_user
   cat_mar,122,cat_produit_id / mar_id
   categorie_produit,39,cat_produit_id / cat_produit_libelle / cat_produit_actif / cat_produit_archive / cat_produit_creation / cat_produit_maj
   com_eta_typ,26806,eta_com_id / com_id / eta_com_typ_id
   commande,13403,com_id / age_id / age_age_id / mar_id / com_libelle / com_creation / com_maj / com_date_emission / com_date_reception / com_numero_ej / com_date_delai / com_description / com_total_ht / com_archive / com_repd_increment / com_bud_annee / com_libelle2 / com_ser_annee_increment
   commande_livrable,45271,com_liv_id / liv_id / con_id / com_pro_id / com_liv_libelle / com_liv_creation / com_liv_maj / com_liv_delai / consliv_recu / consliv_valide
   commande_prestation,23305,com_pre_id / com_id / prop_pre_id / com_pre_libelle / com_pre_creation / com_pre_maj / com_pre_libelle2
   commande_produit,57523,com_pro_id / prod_id / com_pre_id / com_prod_creation / com_prod_maj / com_prod_quantite / com_prod_prix_ht / com_prod_tva / com_prod_taux / con_id
   commande_taux,2710,com_tau_id / com_pro_id / prod_id / com_tau_creation / com_tau_maj / com_tau_quantite / com_tau_prix_ht / com_tau_tva / com_tau_signe
   con_prod_aco,57073,con_id / com_pro_id / quantite_constate_tech / quantite_constate_admin / bon_exe_id
   con_tau_aco,2658,con_id / com_tau_id / bon_exe_id / quantite_constate_tech / quantite_constate_admin
   constat,22807,con_id / age_id / com_pre_id / con_typ_id / qua_con_id / per_id / con_libelle / con_creation / con_maj / con_description / con_date / con_archive / con_updatable / con_ind_mont / con_ind_desc / con_pen_mont / con_pen_desc / con_date_fintravaux / con_remarques
   constat_fichier,211,constat_fichier_id / constat_fichier_libelle / constat_fichier_path / con_id
   constat_type,3,con_typ_id / con_typ_libelle / con_typ_creation / con_typ_maj
   da_cat,4499,cat_produit_id / dem_ach_id
   demande_achat,5736,dem_ach_id / com_id / dem_ach_libelle / dem_ach_creation / dem_ach_maj / dem_ach_qualification / dem_ach_date_attribution / dem_ach_annee_budgetaire / dem_ach_montant_ttc / dem_ach_numero_ej / dem_ach_archive / dem_ach_ligne_gestion / dem_ach_libelle2 / aco_id / bud_id / ser_id / age_id
   ea_tempo,10568,ea_tempo_id / com_id / ea_tempo_num_facture / ea_tempo_date_reception / ea_tempo_facture_ht / ea_tempo_facture_ttc / ea_tempo_num_ea / ea_tempo_date_depart_cd / ea_tempo_num_rep_a / ea_tempo_solde_ej / ea_tempo_date_mandat / ea_tempo_num_mandat / ea_tempo_archive
   etat_acompte_type,2,eta_aco_typ_id / eta_aco_typ_libelle / eta_aco_typ_creation / eta_aco_typ_maj
   etat_commande,10,eta_com_id / eta_com_libelle / eta_com_creation / eta_com_maj
   etat_commande_type,2,eta_com_typ_id / eta_com_typ_libelle / eta_com_typ_creation / eta_com_typ_maj
   fou_mar,141,fou_id / mar_id / fou_qua_id
   fournisseur,121,fou_id / fou_libelle / fou_creation / fou_maj / fou_nom / fou_adresse / fou_cp / fou_ville / fou_pays / fou_chorus / fou_siret / fou_actif / fou_archive / fou_email
   fournisseur_qualification,3,fou_qua_id / fou_qua_libelle / fou_qua_creation / fou_qua_maj
   incr_fonctionnel,51852,prop_pre_id / com_id / mar_id / ser_id / entite / valeur / bud_annee
   increment_fonctionnel,4244,prop_pre_id / mar_id / ser_id / entite / valeur / bud_annee
   index_revision,3,ind_rev_id / ind_rev_nom / ind_rev_actif / ind_rev_archive
   indice_revision,17,indi_rev_id / ind_rev_id / indi_rev_creation / indi_rev_maj / indi_rev_date / indi_rev_valeur / indi_rev_provisoire
   interet_moratoire,0,int_mor_id / aco_id / int_mor_libelle / int_mor_montant / int_mor_qualification
   lieu,27,lieu_id / lieu_libelle / lieu_actif / lieu_archive
   lieu_ser,175,lieu_id / ser_id
   ligne_equipement,25,ligne_equ_id / ligne_equ_libelle / ligne_equ_actif / ligne_equ_archive / ligne_equ_creation / ligne_equ_maj
   livrable,11730,liv_id / prod_id / liv_libelle / liv_creation / liv_maj / liv_delai / liv_description
   mar_per,167,mar_id / per_id
   marche,114,mar_id / ind_rev_id / mar_libelle / mar_creation / mar_maj / mar_diminutif / mar_numero_mar / mar_numero_ej / mar_gestionnaire_cpcm / mar_gestionnaire_dirif / mar_date_initialisation / mar_date_fin / mar_date_cloture / mar_montant_mini / mar_montant_maxi / mar_montant_avance / mar_formule_revision / mar_formule_moratoire / mar_reconduction / mar_actif / mar_archive / mar_pen_tva / mar_pen_rev / mar_date_indice_io / mar_forme_prix / mar_date_debut_periode / mar_date_fin_periode / mar_reconduction_boolean
   message,5,mes_id / mes_date_debut / mes_date_fin / mes_message / mes_actif / mes_archive
   montant,1037,mon_id / bud_id / mon_auto_engagement / mon_cred_paiement / mon_libelle
   oper_ser,1,ser_id / operation_id
   operation,1,operation_id / operation_libelle / operation_archive
   parametre,1,par_id / par_libelle / par_creation / par_maj / par_valeur
   penalite_indemnite,0,pen_ind_id / com_id / pen_ind_libelle / pen_ind_creation / pen_ind_maj / pen_ind_numero / pen_ind_montant / pen_ind_descriptif
   personnel,168,per_id / fou_id / per_creation / per_maj / per_nom / per_prenom / per_email / per_actif / per_archive
   prestation_fichier,3973,presta_fichier_id / presta_fichier_libelle / presta_fichier_path / prop_pre_id
   prod_tau,0,prod_id / tau_id
   produit,11903,prod_id / mar_id / prod_designation / prod_creation / prod_maj / prod_code / prod_prix_ht / prod_unite
   proposition,14280,com_id2 / mar_id / com_id / age_id / bud_id / prop_libelle / prop_creation / prop_maj / prop_date_emission / prop_date_delai / prop_description / prop_etat / prop_total_ht / prop_archive / prop_libelle2 / rep_id / operation_id
   proposition_livrable,48781,com_liv_id2 / liv_id / com_pro_id2 / prop_liv_libelle / prop_liv_creation / prop_liv_maj / prop_liv_delai
   proposition_prestation,24875,prop_pre_id / age_id / com_id2 / com_pre_id / fou_id / mar_id / prop_pre_libelle / prop_pre_creation / prop_pre_maj / prop_pre_type / prop_pre_lg_equipement / prop_pre_date_previsionnelle / prop_pre_lieu_execution / prop_pre_condition_execution / prop_pre_num_gmao / prop_pre_archive / prop_pre_etat / prop_pre_montant / prop_pre_libelle2 / type_id / ligne_equ_id / lieu_id / prop_pre_coswin_state / prop_pre_ref_devis
   proposition_produit,60760,com_pro_id2 / prop_pre_id / prod_id / prop_prod_creation / prop_prod_maj / prop_prod_quantite / prop_prod_prix_ht / prop_prod_taux
   proposition_taux,2773,prop_tau_id / com_pro_id2 / prod_id / prop_tau_creation / prop_tau_maj / prop_tau_quantite / prop_tau_prix_ht / prop_tau_taux / prop_tau_signe
   qualification_constat,3,qua_con_id / qua_con_libelle / qua_con_creation / qua_con_maj
   repartition,1954,rep_id / mar_id / rep_libelle / rep_identifiant / bud_id / rep_datecreation / rep_datemaj / rep_archive / rep_active
   repartition_montant,4680,rep_mon_id / rep_id / rep_mon_montantttc / rep_mon_libelle
   revision,0,rev_id / mar_id / aco_id / indi_rev_id / rev_libelle / rev_creation / rev_maj / rev_montant / rev_qualification / rev_id2
   service,17,ser_id / ser_libelle / ser_creation / ser_maj / ser_centre_cout / ser_gestionnaire / ser_actif / ser_archive / ser_user / ser_adresse / ser_cp / ser_ville / ser_pays
   taux,0,tau_id / tau_libelle / tau_creation / tau_maj / tau_valeur
   type,7,type_id / type_libelle / type_actif / type_archive / type_creation / type_maj


