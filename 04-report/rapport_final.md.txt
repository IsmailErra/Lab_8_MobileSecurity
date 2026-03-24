# Rapport d'analyse de securite mobile

## A. Informations generales
- Date: 2026-03-22
- Analyste: Ismail
- Cible: DIVA Application
- Version/Hash: 5CEFC51FCE9BD760B92AB2340477F4DDA84B4AE0C5D04A8C9493E4FE34FAB7C5
- Outils utilises: BeVigil Web, Yaazhini GUI

## B. Resume executif
L analyse de l application DIVA a permis d identifier plusieurs vulnerabilites critiques.
Deux outils ont ete utilises: BeVigil pour l analyse externe et Yaazhini pour l analyse interne.
Un total de 10 constats ont ete identifies.
Les problemes les plus critiques concernent les credentials exposes et la communication non securisee.
Le niveau de risque global est considere comme eleve.

## C. Top 5 constats

### 1. Credentials hardcodes (FIND-001)
- Severite: High
- Preuve: APIcreds2Activity.java
- Impact: Acces non autorise possible aux services
- Remediation: Ne pas stocker les secrets dans le code
- Reference OWASP: MASVS-STORAGE-1

### 2. Communication HTTP (FIND-002)
- Severite: High
- Preuve: http://payatu.com
- Impact: Interception des donnees possible
- Remediation: Utiliser HTTPS
- Reference OWASP: MASVS-NETWORK-1

### 3. Mode debug active (FIND-003)
- Severite: Medium
- Preuve: AndroidManifest.xml
- Impact: Analyse facilitee de l application
- Remediation: Desactiver debug
- Reference OWASP: MASVS-CODE-1

### 4. Backup active (FIND-004)
- Severite: Medium
- Preuve: AndroidManifest.xml
- Impact: Extraction des donnees possible
- Remediation: Desactiver allowBackup
- Reference OWASP: MASVS-STORAGE-4

### 5. Improper provider export (FIND-010)
- Severite: Medium
- Preuve: AndroidManifest.xml
- Impact: Acces externe possible
- Remediation: Restreindre les composants exportes
- Reference OWASP: MASVS-PLATFORM-1

## D. Faux positifs notables
- Possible Secret detecte par BeVigil reste a confirmer
- Certains endpoints detectes ne sont pas necessairement exploitables

## E. Recommandations prioritaires
1. Supprimer tous les credentials du code source
2. Activer HTTPS pour toutes les communications
3. Desactiver debug et backup en production

## F. Annexes
- BeVigil: 01-bevigil/
- Yaazhini: 02-yaazhini/
- Triage: 03-triage/triage.csv