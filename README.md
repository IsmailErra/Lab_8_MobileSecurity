# Lab_8_MobileSecurity
Tu es un assistant chargé d’organiser et renommer des captures d’écran pour qu’elles correspondent parfaitement aux références présentes dans un fichier README.md.

Contexte :

* Un dossier `screenshots/` contient plusieurs images nommées de façon aléatoire (ex: Screenshot 2026-03-22...).
* Un fichier README.md existe déjà et contient des références d’images sous la forme :
  `screenshots/nom_image.png`
* L’objectif est de faire correspondre les fichiers réels avec les noms utilisés dans le README.

---

Tâches à réaliser :

1. Lire le fichier README.md.

2. Extraire TOUS les noms d’images utilisés (ex : `apk_hash_sha256.png`, `upload_apk_bevigil.png`, etc.).

3. Analyser chaque capture d’écran fournie (contenu visuel).

4. Associer chaque image au bon nom en se basant sur :

   * le contenu affiché
   * le contexte du README
   * l’ordre logique des sections

5. Renommer chaque fichier du dossier `screenshots/` pour correspondre EXACTEMENT aux noms utilisés dans le README.

---

Contraintes strictes :

* Ne PAS inventer de nouveaux noms.
* Utiliser UNIQUEMENT les noms déjà présents dans le README.
* Respecter exactement :

  * minuscules
  * underscores `_`
  * extension `.png`
* Chaque image doit correspondre à UNE seule référence.
* Ne laisser AUCUNE image non utilisée.

---

Format de sortie attendu :

Donner uniquement une liste claire des renommages :

ancien_nom.png → screenshots/nom_final.png

Exemple :
Screenshot_2026_01.png → screenshots/upload_apk_bevigil.png

---

Important :

* Se baser sur le contenu visuel (interfaces MobSF, terminal, DIVA, logs, etc.)

* Être logique et cohérent avec les sections du README :

  * préparation
  * analyse statique
  * analyse dynamique
  * résultats

* Ne donner AUCUNE explication.

* Ne pas modifier le README.

* Ne pas ajouter de texte inutile.

Objectif final :

Avoir un dossier `screenshots/` parfaitement aligné avec les références du README.md, prêt pour rendu final.
