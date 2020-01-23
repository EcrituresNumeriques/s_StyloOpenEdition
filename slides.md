## Stylo

#### éditeur sémantique pour les humanités


<!-- ##### remettre l'édition scientifique dans les mains de l'auteur -->

> Dans l'environnement numérique,  
> écrire = écrire + structurer.

&nbsp;
Nicolas Sauret, Marcello Vitali-Rosati et Servanne Monjour

<!-- .element: style="font-size:0.8em" -->

---


_Café OpenEdition_  
21 janvier 2020 | Open Edition

<!-- .element: style="font-size:1.5rem" -->

![logo CRCEN](img/LogoENDT10-2016.png) <!-- .element: class="logo" style="width:20%; background-color:ghostwhite;padding: 4px" --> ![CC-BY-SA](http://i.creativecommons.org/l/by-sa/4.0/88x31.png)

===


§§§§§SLIDEmoveDown§§§§§
<!-- .slide: data-background-image="graphics/equipeecrinum.png" data-background-size="contain" -->
<!--  .slide: class="hover"-->

## un travail d'équipe <!-- .element: style="padding-top:0.8em" -->

===


%%%%%%%%%%%%%%%%%%SECTIONmoveRight%%%%%%%%%%%%%%%%%%
### Philosophie de Stylo

> Mettre à profit les compétences sémantiques de l'auteur en lui redonnant la maîtrise de la structure et de la sémantique du texte

§§§§§SLIDEmoveDown§§§§§
### Pourquoi tant de _Word_ ?

2 problèmes :

1. propriétaire
2. manque de sémantique



%%%%%%%%%%%%%%%%%%SECTIONmoveRight%%%%%%%%%%%%%%%%%%
<!-- .slide: data-background-image="graphics/styloN_facebook.png" data-background-size="contain" data-transition="slide-out"-->
<!-- .slide: class="hover" -->

## Qu'est-ce que Stylo ? <!-- .element: style="padding-top:0.8em"  -->
===

Fondamentalement, Stylo est né de cette catastrophe, et de la conviction que, en tant qu'universitaire, il convenait de prendre autant soin des écrits que l'on étudiaient que de la chaine de production de l'écrit.

Stylo est notre expérimentation, notre bricolage local. C'est sans doute aussi un peu notre cheval de Troie dans l'Université, avec l'ambition justement d'institutionnaliser certaines pratiques d'écriture et d'édition déjà émergentes dans la communauté des SHS.

Et ça marche !

§§§§§SLIDEmoveDown§§§§§

### Un éditeur complet

- Continuité des données <i class="fa fa-arrow-right"></i> workflow fluide de l'auteur à l'éditeur
- WYSIWYM <i class="fa fa-arrow-right"></i> est affiché ce qui est _signifié_
- Balisage souple
- Sémantique <i class="fa fa-arrow-right"></i> alignement sur des autorités, balisage inline
- Plusieurs exports <i class="fa fa-arrow-right"></i> HTML5, XML-TEI, XML-ERUDIT, PDF, TEX, ODT, DOCX
- Publications multiples sans perte d'information <i class="fa fa-arrow-right"></i> CMS, Érudit, Indesign, Lodel (?)
- Environnement soutenable <i class="fa fa-arrow-right"></i> chaîne modulable basé sur des outils et des formats standards

<!-- .element style="font-size:0.7em" -->

§§§§§SLIDEmoveDown§§§§§
### Modularité

===
Ce que montre avant tout cet historique, c'est la modularité de la chaine, principe que l'on reprend des travaux d'Antoine Fauchié, modularité tant les formats utilisés, les outils qui implémentent ces formats, et les logiciels de traitements sont interchangeables.


§§§§§SLIDEmoveDown§§§§§

<i class="fa fa-arrow-right"></i> 3 éléments principaux + modules techniques :

<!-- .element: style="font-size:0.8em;" -->

1. **Éditeur de métadonnées**
  - yaml <!-- .element: style="color:Darkorange;" -->
  - DC, RDFa, Foaf,
    ScholarlyArticle, Google Scholar, Prism schema <!-- .element: style="color:Darkorange;" -->
  - Vocabulaire contrôlé
  - Alignement avec des autorités (Rameau, Wikidata, LOC)
  - Via l'API rechercheisidore (Huma-num)
2. **Éditeur de texte** avec balisage interne
  - Markdown enrichi <!-- .element: style="color:Darkorange;" -->
  - autres ?
3. **Gestion bibliographique**
  - BibTeX <!-- .element: style="color:Darkorange;" -->
  - Api Zotero

<!-- .element: style="font-size:0.6em; width:55%; float:left;" -->


1. **Conversion**
  - pandoc <!-- .element: style="color:Darkorange;" --> (vers html, LateX, pdf)
  - XSLT <!-- .element: style="color:Darkorange;" --> (vers TEI-LOD, Erudit)
2. **Versioning**
  - git <!-- .element: style="color:Darkorange;" -->
  - comparateur de versions
3. **Plateforme**
  - MongoDB (bdd)
  - GraphQL <!-- .element: style="color:Darkorange;" --> (backend)
  - ReactJS (frontend)
4. **API**


<!-- .element: style="font-size:0.6em; width:35%; float:left;padding-left:2rem;border:1px,solid,white;" -->

===
Sans m'y attarder, voici les différents briques logicielles, les différents formats, les différents services qui sont articulés dans Stylo.
Au fur et à mesure de la conception, nous avons pu remplacer un outil par un autre, nous avons pu améliorer ou optimiser tel ou tel aspect de la chaîne.

Autant la chaîne que Stylo ou Process sont des outils et des protocoles encore en friche.

Par ailleurs, ce que n'a pas montré cette chronologie, c'est l'enrichissement permanent depuis avril 2017 du modèle de données et de métadonnées des articles.


§§§§§SLIDEmoveDown§§§§§
### Interface d'édition

§§§§§SLIDEmoveDown§§§§§
<!-- .slide: data-background-image="graphics/stylo_3f.png" data-background-size="contain" -->

===
Stylo est à la fois un outil de rédaction de texte scientifique et un outil d'édition de document scientifique. Cet agencement est permis par l'articulation de trois fichiers au coeur de son fonctionnement.

§§§§§SLIDEmoveDown§§§§§
<!-- .slide: data-background-image="graphics/stylo_3f_marqued.svg" data-background-size="contain" data-transition="fade-in slide-out"-->

===
- Le corps de texte, au format markdown
- La bibliographie, au format bibtex
- Les métadonnées, au format yaml



§§§§§SLIDEmoveDown§§§§§
<!-- .slide: data-background-image="graphics/stylo_fullInterface_2019_cropped_marqued.png" data-background-size="contain" data-transition="slide-in"-->

===
Je vous montre ici l'interface complète, où l'on retrouve un éditeur de métadonnées, qui vient modifier le fichier yaml associé au document, un gestionnaire de références qui vient modifier le fichier bibtex assoié. Ce gestionnaire est capable de se synchroniser avec une collection zotero en ligne.

On retrouve le corps de texte au centre,

Ainsi que plusieurs modules outillant nos trois sources : ajoutant des fonctionnalités de versionning, la table des matières du corps de texte, des statistiques sur le document et non visible ici un comparateur de version.


§§§§§SLIDEmoveDown§§§§§
<!-- .slide: data-background-image="graphics/log_template.png" data-background-size="contain"-->

### Souplesse
===
Le choix du markdown/yaml et du html au détriment peut-être d'un modèle XML au schéma déclaré et stabilisé a été d'abord celui d'une extrême souplesse nécessaire à l'expérimentation. Ce processus d'élaboration d'un modèle éditorial, celui de la formalisation de nos métadonnées et des templates associés a été un processus itératif, souple et peu contraignant.

Cela nous a permis de démarrer très vite la production d'articles, d'identifier des cas de figure particulier, et de réintégrer dans la chaine : de nouvelles données, nouveaux champs et nouvelles balises.

La chaine md+yaml+bib existe depuis plus de 2 ans, 27 mois pendant lesquels les champs du yaml n'ont cessés d'être mis à jour au fur et à mesure des besoins identifiés. Stylo a largement bénéficié de ces itérations pendant sa conception.

Plus récemment, au début de l'année, nous avons procédé à une refonte complète de l'outil, tant sur le backend et la gestion de la base de données, que sur le frontend en redéveloppant entièrement l'application. Nous en avons profité pour génériciser les templates et le modèle de données des articles.

<!-- Cette souplesse a bien entendu sa limite. Itérer sur les données ou sur les templates suppose de rééditer, ou de mettre à jour, les articles antérieurs à l'itération et de relancer les conversions. Encore aujourd'hui, 2 ans après la mise en production de la chaîne, et 1 an après l'adoption de Stylo par l'équipe de Sens public, nous continuons d'améliorer certaines syntaxes, d'enrichir les templates, voir de créer des filtres ad-hoc pour gérer les multiples cas de figures. -->

§§§§§SLIDEmoveDown§§§§§

![enrich editorial](graphics/enrich_editorial.png) <!-- .element: width="90%" -->

===
Ainsi, la preuve de concept initiale s'est ramifiée au fil des enrichissements que nous intégrons au texte et aux métadonnées :

- utilisation d'autorités (orcid, Rameau) dans les métadonnées
- utilisation de services d'enrichissement (Isidore à la demande) pour qualifier les articles
- [next slide]

§§§§§SLIDEmoveDown§§§§§

![enrich editorial](graphics/enrich_thesis.png) <!-- .element: width="100%" -->
![enrich editorial](graphics/enrich_thesis_preview.png) <!-- .element: width="100%" -->


===

- sémantisation du corps de texte
- références structurées via l'api de zotero

Ce bricolage constant est important. Les éditeurs de la revue peuvent en témoigner, ils sont eux-mêmes obligés de se salir les mains. Mais ces mains pleines de cambouis, de balises, de commandes bash, de branches fusionnées, sont les témoins de leur capacitation, d'une nouvelle maîtrise qui va bien au-delà de l'édition d'un document.


%%%%%%%%%%%%%%%%%%SECTIONmoveRight%%%%%%%%%%%%%%%%%%

## Industrialisation

- Usage par plusieurs revues <i class="fa fa-arrow-right"></i> Sens Public, Études françaises, Nouvelles vues, Romantism on the Net, Itinéraires
- Intégration complète avec Érudit
- Intégration dans les services Huma-Num <i class="fa fa-arrow-right"></i> isidore.science et Nakala


%%%%%%%%%%%%%%%%%%SECTIONmoveRight%%%%%%%%%%%%%%%%%%
### Merci !

<i class="fa fa-arrow-right"></i> contribuer : [github.com/EcrituresNumeriques/stylo/](https://github.com/EcrituresNumeriques/stylo/)

<!-- .element: style="font-size:0.7em;" -->

<i class="fa fa-arrow-right"></i> écrire : [stylo.ecrituresnumeriques.ca](http://stylo.ecrituresnumeriques.ca/)

<!-- .element: style="font-size:0.7em;" -->

<i class="fa fa-arrow-right"></i> premiers pas : [stylo-doc.ecrituresnumerique.ca](http://stylo-doc.ecrituresnumerique.ca)

<!-- .element: style="font-size:0.7em;" -->

<i class="fa fa-arrow-right"></i> tuto : [youtu.be/qcwEqbcxBF8](https://www.youtube.com/watch?v=qcwEqbcxBF8)

<!-- .element: style="font-size:0.7em;" -->

---
![logo CRCEN](img/LogoENDT10-2016.png) <!-- .element: class="logo" style="width:25%; background-color:ghostwhite;padding: 7px" -->
![CC-BY-SA](http://i.creativecommons.org/l/by-sa/4.0/88x31.png)
