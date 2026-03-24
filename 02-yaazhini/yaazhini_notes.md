# \# Notes d'analyse Yaazhini

# 

# \## Éléments identifiés

# 

# \### Élément 1: Communication non sécurisée (HTTP)

# \- \*\*Localisation\*\*: APIcreds2Activity.java

# \- \*\*Description\*\*: L'application utilise une URL en HTTP au lieu de HTTPS

# \- \*\*Impact potentiel\*\*: Les données peuvent être interceptées par un attaquant

# \- \*\*Remédiation suggérée\*\*: Utiliser HTTPS pour sécuriser les communications

# 

# \---

# 

# \### Élément 2: Credentials hardcodés

# \- \*\*Localisation\*\*: APIcreds2Activity.java

# \- \*\*Description\*\*: Des identifiants sont présents directement dans le code (\[MASQUÉ])

# \- \*\*Impact potentiel\*\*: Un attaquant peut récupérer ces informations et accéder aux services

# \- \*\*Remédiation suggérée\*\*: Ne jamais stocker les secrets dans le code, utiliser un stockage sécurisé

# 

# \---

# 

# \### Élément 3: Mode debug activé

# \- \*\*Localisation\*\*: AndroidManifest.xml

# \- \*\*Description\*\*: android:debuggable="true"

# \- \*\*Impact potentiel\*\*: L'application peut être analysée facilement par un attaquant

# \- \*\*Remédiation suggérée\*\*: Désactiver le mode debug en production

# 

# \---

# 

# \### Élément 4: Backup activé

# \- \*\*Localisation\*\*: AndroidManifest.xml

# \- \*\*Description\*\*: android:allowBackup="true"

# \- \*\*Impact potentiel\*\*: Les données de l'application peuvent être extraites

# \- \*\*Remédiation suggérée\*\*: Désactiver le backup si non nécessaire

# 

# \---

# 

# \### Élément 5: Stockage externe utilisé

# \- \*\*Localisation\*\*: Permissions (WRITE\_EXTERNAL\_STORAGE)

# \- \*\*Description\*\*: L'application utilise le stockage externe

# \- \*\*Impact potentiel\*\*: Les données peuvent être accessibles par d'autres applications

# \- \*\*Remédiation suggérée\*\*: Limiter l'utilisation du stockage externe

