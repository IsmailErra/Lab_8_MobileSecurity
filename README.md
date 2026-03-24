# Analyse de sécurité d’une application mobile Android

## 1. Présentation
Ce projet a pour objectif d'évaluer la posture de sécurité de l'application Android vulnérable "DIVA" (Damn Insecure and Vulnerable App) en exploitant des solutions d'analyse automatisée comme BeVigil et Yaazhini. Cette démarche permet de déceler les failles de conception, les vulnérabilités de configuration et les fuites potentielles de données avant tout déploiement.

## 2. Environnement
* **Système d'exploitation** : Windows
* **Outils utilisés** : BeVigil (analyse cloud), Yaazhini (analyse statique locale), PowerShell

## 3. Préparation
Avant de débuter l'inspection, nous avons réceptionné l'archive APK cible. La première étape a consisté à calculer son empreinte cryptographique (SHA-256) afin de garantir l'intégrité du fichier et d'assurer la traçabilité de nos analyses.

![Hash APK](screenshots/apk_hash_sha256.png)

## 4. Analyse avec BeVigil
L'application a d'abord été soumise à la plateforme BeVigil pour une reconnaissance globale. Après le téléversement et le lancement du scan, l'outil a généré un tableau de bord détaillant le niveau de risque de l'application ainsi que les principales alertes de sécurité détectées.

![Upload APK](screenshots/upload_apk_bevigil.png)
![Sélection fichier](screenshots/select_apk_file.png)
![Statut scan](screenshots/bevigil_scan_status.png)
![Tableau de bord et Résultats BeVigil](screenshots/bevigil_summary_dashboard.png)

## 5. Analyse avec Yaazhini
Afin de réaliser une inspection approfondie du code, Yaazhini a été exécuté en local. Après le chargement de l'APK, l'analyse statique a mis en évidence plusieurs vulnérabilités critiques, notamment au niveau des permissions du manifeste (mode debug, sauvegarde activée) et la présence d'informations sensibles codées en dur.

![Interface et Chargement APK](screenshots/yaazhini_apk_selection.png)
![Résumé de l'application](screenshots/yaazhini_app_summary.png)
![Vue globale et Problèmes manifest](screenshots/yaazhini_manifest_debug_backup.png)
![Credentials exposés en clair](screenshots/yaazhini_hardcoded_credentials.png)

## 6. Résultats consolidés
L'ensemble des anomalies identifiées lors de ces analyses a été centralisé et normalisé au sein d'un document de triage pour faciliter le suivi et la remédiation.

![Triage des vulnérabilités](screenshots/triage_results_csv.png)

Les faiblesses majeures confirmées sont :
* Présence de secrets exposés dans le code source (Hardcoded credentials).
* Utilisation de protocoles de communication non sécurisés (HTTP en clair).
* Configuration d'application non sécurisée (Mode debug actif et fonction de sauvegarde autorisée).

## 7. Structure du projet
L'arborescence du projet a été structurée pour séparer les différents outils d'analyse et les livrables associés :

![Structure des répertoires](screenshots/project_directory_structure.png)

## 8. Périmètre
![Définition du périmètre](screenshots/scope_definition.png)

## 9. Conclusion
En définitive, de multiples faiblesses altérant significativement la confidentialité et l'intégrité de l'application ont été mises en évidence. Il est indispensable d'appliquer de strictes pratiques de développement sécurisé (Secure Coding) et de corriger la configuration de l'application pour mitiger ces vulnérabilités.
