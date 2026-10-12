# Jingluo : corps 3D

Le corps humain 3D affiché par l'appli Jingluo (atlas 3D des méridiens), publié sous licence
**CC BY-SA 4.0** (texte intégral : [`LICENSE`](LICENSE)).

C'est une adaptation de **Z-Anatomy**, avec des pièces de **BodyParts3D**. Ce dépôt contient seulement le corps :
ni les points d'acupuncture, ni les textes, ni le code de l'appli.

## Contenu

- `source/` : le corps retouché au format glTF binaire (`.glb`), un fichier par couche : `peau`, `muscles`, `squelette`,
  `organes`, `nerfs`, `arteres`, `veines`. Un objet par organe ou par pièce, avec son nom anatomique (en anglais, comme dans Z-Anatomy).
  Coordonnées en mètres. S'ouvre dans Blender (File > Import > glTF 2.0) ou tout lecteur glTF.
- `couches/` : les mêmes couches, au format que l'appli télécharge (`*-N.json`), et `manifest.json` :
  numéro de version du corps, et pour chaque couche la liste des fichiers, leur taille et leur somme de contrôle SHA-256.

### Format des fichiers `couches/*.json`

`{"chunks": [{nv, nt, pos, col, idx, tag?}]}`, données en base64 :
- `pos` : 3 × `uint16` par sommet, positions quantifiées dans la boîte englobante du corps ;
- `col` : un indice de couleur (`uint8`) par sommet ;
- `idx` : 3 × `uint16` par triangle ;
- `tag` (facultatif) : `"intime"` pour les organes génitaux externes, rangés à part.

## Crédits

D'après le document de licence de Z-Anatomy (« Z-LICENSE », Gauthier Kervyn) :

- **Z-Anatomy** : CC BY-SA 4.0. Auteurs des modèles 3D : Kousaku Okubo, Gauthier Kervyn, Colline Brassard, Christophe Céleste.
  Site : https://www.z-anatomy.com
- **BodyParts3D** : The Database Center for Life Science (DBCLS). Le document de Z-Anatomy indique CC BY 4.0 ;
  le site de BodyParts3D indique CC BY-SA 2.1 Japon, avec ce crédit :
  « BodyParts3D, Copyright© 2008 Life Science Integrated Database Center licensed by CC Display-Inheritance 2.1 Japan ».
  Licence : http://lifesciencedb.jp/bp3d/info_en/license/index.html
- **Modèles de référence repris par Z-Anatomy :**
  - « Brainder » : University of Washington. Aucune licence indiquée par Z-Anatomy ; le site de son auteur indique CC BY-SA 3.0.
  - « Cranial Nerves and Foramina » : University of Dundee, CAHID, CC BY 4.0.
  - « White matter » : University of Washington, aucune licence indiquée. **Retiré** de ce corps.
  - « Anatomy of the Inner Ear » : University of Dundee School of Medicine, CC BY-NC-SA 4.0 (non commercial). **Retiré** de ce corps.
  - « Kidney » : Lissie Cowley, CC BY-NC 4.0 (non commercial). **Retiré** de ce corps, remplacé par le rein de BodyParts3D.

## Ce qui a été changé par rapport à Z-Anatomy

- **Retirés :** le rein et le bassinet de Lissie Cowley (`Kidney`, `Renal pelvis`), l'oreille interne (cochlée, vestibule,
  canaux semi-circulaires), tout ce qui est rangé sous « White matter », et par prudence les artères et veines intrarénales.
- **Ajoutés :** rein et bassinet de BodyParts3D (FMA7204, FMA7205, FMA15571, FMA15572), posés à la place du rein d'origine,
  avec un raccord vers l'uretère de Z-Anatomy ; l'œsophage, que l'export d'origine laissait vide, converti en maillage.
- **Peau :** allégée (sommets regroupés), sans cheveux ; organes génitaux externes remplacés par une surface lisse.
- **Estomac :** la fenêtre de la paroi avant, faite pour montrer une muqueuse absente du fichier, est refermée.
- **Toutes les couches :** sommets confondus soudés (à 0,1 mm près, dans un même objet), une couleur par famille d'organes.
- Les étiquettes et lignes de légende de Z-Anatomy ne sont pas reprises.

## Licence

Ce corps adapté est publié sous **Creative Commons Attribution-ShareAlike 4.0 International** (CC BY-SA 4.0),
comme Z-Anatomy. Vous pouvez le partager et l'adapter, y compris commercialement, en créditant les auteurs ci-dessus
et en partageant vos adaptations sous la même licence.
