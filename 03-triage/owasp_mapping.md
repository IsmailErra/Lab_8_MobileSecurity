# Mapping OWASP

## FIND-001: Credentials hardcodes
- Categorie OWASP: MASVS-STORAGE
- Reference specifique: V2.1
- Justification: Les donnees sensibles doivent etre stockees de maniere securisee.

## FIND-002: Communication HTTP
- Categorie OWASP: MASVS-NETWORK
- Reference specifique: V5.1
- Justification: Les donnees en transit doivent etre chiffrees.

## FIND-003: Mode debug active
- Categorie OWASP: MASVS-CODE
- Reference specifique: V6.1
- Justification: Le mode debug ne doit pas etre actif en production.

## FIND-004: Backup active
- Categorie OWASP: MASVS-STORAGE
- Reference specifique: V2.8
- Justification: Les sauvegardes peuvent exposer des donnees sensibles.

## FIND-005: Possible Secret detecte
- Categorie OWASP: MASVS-STORAGE
- Reference specifique: V2.1
- Justification: Les secrets ne doivent pas etre exposes dans le code.