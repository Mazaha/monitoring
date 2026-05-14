# monitoring

Ce que fait le script oracle_static_monitoring.py :

Récupère les assets collectés depuis Elasticsearch (index collect_splunk_ip) — cherche les hosts qui ont envoyé des logs Oracle dans les dernières X heures
Compare avec le référentiel interne (list_oracle_static) par région : AMER, ASIA, EMEA, LUX, GSC, CGI, FRF, ASSU + une liste d'exclusion dataguard_down_blackout_backup
Génère un CSV oracle_static_collection_status.csv avec : date, domain, device, collected (True/False)
Sauvegarde le CSV dans PostgreSQL (mon_oracle_static_daily)
Envoie un email avec le CSV converti en Excel en pièce jointe
Supprime les fichiers temporaires
