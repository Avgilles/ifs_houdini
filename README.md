# Iterated Function System (IFS) sur Houdini
L'IFS est une méthode mathématique pour créer des fractale

## IFS entre fractale et L-System

L'IFS est une méthode mathématique développées par **Michael Barnsley** qui permet de créer des images fractales en répétant une série de transformations simples (comme des translations, rotations, etc.) sur une forme de base, encore et encore. Ces transformations sont choisies au hasard à chaque étape, ce qui donne une variété infinie de formes similaires à la forme de base, mais avec des détails différents. En utilisant cette méthode, on peut créer des images fascinantes qui ont des motifs répétés à différentes échelles, ce qui les rend très intéressantes à regarder.

## Quelques exemples & Artistes

![Scott Draves : Electric Sheep](/ifs_houdini/Untitled.png)

Scott Draves : Electric Sheep

![Paul DeCelle](/ifs_houdini/Untitled%201.png)

Paul DeCelle

## Intégrer à Houdini

![Untitled](/ifs_houdini/Untitled%202.png)

![https://i.imgur.com/SDNnMyE.png](https://i.imgur.com/SDNnMyE.png)

Petite vidéo fait avec amour :

<iframe width="100%" height="500" src="https://www.youtube.com/embed/Q48H8mu6nvs" title="YouTube video player" frameBorder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowFullScreen/>

## Explication de L’IFS Mathématique

Pour s’aider a comprendre les math, chatGPT est un super outils pour facilement avoir des explications. Voilà ce qu’il dit :

 

Un système de fonctions itérées est une méthode de génération de fractales en utilisant des transformations géométriques successives appliquées à un objet initial, appelé "ensemble de départ". Ces transformations peuvent être des translations, des rotations, des dilatations ou des symétries par rapport à des points ou des axes spécifiques. Le résultat de chaque transformation est ensuite appliqué à nouveau à l'ensemble de départ, créant ainsi une nouvelle version de l'ensemble initial.

Les fonctions utilisées pour les transformations sont souvent des transformations linéaires de la forme :

x' = ax + by + e

y' = cx + dy + f

où (x, y) sont les coordonnées d'un point dans l'ensemble de départ, (x', y') sont les coordonnées transformées du point et a, b, c, d, e, et f sont des constantes déterminant la transformation. Ces constantes sont souvent regroupées dans une matrice de transformation :

| a b |
| c d |

Les fonctions de transformation peuvent être choisies de manière aléatoire à partir d'un ensemble de transformations prédéfinies, ou bien être déterminées de manière déterministe pour créer des fractales spécifiques.. Il est également possible d'introduire des poids pour chaque transformation pour contrôler la fréquence à laquelle chaque transformation est appliquée.

En résumé, les systèmes de fonctions itérées sont une méthode puissante et flexible pour générer des fractales, en utilisant des transformations géométriques successives appliquées à un objet initial.

### Comprendre la formule :

Au début du projet, j'avais du mal à comprendre ce que faisait chaque paramètre, mais en décryptant, j'ai compris que les 4 premières valeurs permettaient de gérer les transformations de x et y, et le reste permettait de gérer les poids des probabilités.

![Untitled](/ifs_houdini/Untitled%203.png)

Pour le passer en attribut, je me suis basé sur une progression arithmétique. C'est un grand mot pour simplement trouver l'index de mon tableau par rapport à sa position. Si j'avais eu un tableau à plusieurs dimensions, je n'aurais pas eu besoin de faire ce genre de calcul, mais cela n'est pas possible pour les attributs à plusieurs dimensions.

[Arrays](https://www.sidefx.com/docs/houdini/vex/arrays.html#limitations)

![Untitled](/ifs_houdini/Untitled%204.png)

![Untitled](/ifs_houdini/Untitled%205.png)

---

Bibliographie :

- "Fractals, Chaos, Power Laws: Minutes from an Infinite Paradise" de Manfred Schroeder : Ce livre propose une introduction détaillée aux fractales et à leur création à travers les systèmes de fonctions itérées.
- "Chaos and Fractals: New Frontiers of Science" de Heinz-Otto Peitgen, Hartmut Jürgens, et Dietmar Saupe : Ce livre est une référence classique pour les fractales et leur application, y compris les systèmes de fonctions itérées.
- "Introduction to Iterated Function Systems" par Michael Barnsley : Cette publication est une introduction technique à l'utilisation des systèmes de fonctions itérées pour créer des fractales.
- "Iterated Function Systems" par Michael F. Barnsley et Stephen G. Demko : Cet article scientifique fondateur présente la théorie des systèmes de fonctions itérées.
- "Fractal Geometry and Computer Graphics" par Cliff Pickover : Ce livre aborde les concepts de fractales et d'IFS en relation avec la création de graphiques informatiques et d'animations.

Quelques liens cool :

[IFS Fractals Main Page](http://hiddendimension.com/FractalMath/IFS_Fractals_Main.html)

[IFS manual](http://paulbourke.net/fractals/ifs/)

[sub.blue](http://sub.blue/)

[[Houdini Tutorial] 0027 IFS Fractals (Slow version)](https://www.youtube.com/watch?v=-kne16jQszU)