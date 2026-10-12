# Règles pour Claude dans ce dépôt

Dépôt **public** : le corps 3D de l'appli Jingluo, sous CC BY-SA 4.0. Le code de l'appli est dans le dépôt privé Jingluo (dossier voisin `../Jingluo`).

## Règle absolue

**Aucun fichier venant de `prototype/scripts/` de Jingluo, ni `points.json`, ni aucune fiche, ni aucun autre fichier de l'appli.**
Ce dépôt ne contient que : `source/*.glb`, `couches/*.json` (dont `manifest.json`), `LICENSE`, `README.md`, ce `CLAUDE.md`, `.gitignore`.

## Comment il est rempli

- Tout est écrit par `prototype/scripts/corps_public.py` du dépôt Jingluo, après `pack_full.py`. On ne modifie rien à la main,
  sauf `README.md` et ce fichier.
- Quand le corps change : augmenter `VERSION_CORPS` dans `corps_public.py`, relancer, mettre à jour « Ce qui a été changé » du `README.md`,
  envoyer, puis poser et envoyer l'étiquette `corps-vN` (N = la version). L'appli télécharge les fichiers d'une version par son étiquette :
  sans étiquette, elle ne peut pas les trouver. Ne jamais déplacer ni supprimer une étiquette déjà envoyée.
- Aucun objet non commercial ou sans licence écrite (rein de Lissie Cowley, oreille interne, « White matter ») : ils sont filtrés par
  `za_layers.py`. Vérifier avant chaque envoi.
- Pas de fichier de plus de 100 Mo (limite de GitHub).

## Façon de répondre

Réponses courtes, en français, en tutoyant.
