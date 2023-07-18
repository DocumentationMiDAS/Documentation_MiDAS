# Documentation_MiDAS

La documentation de l'appariement de données administratives Minima sociaux, Droits d'Assurance-chômage, parcours Salariés (MiDAS) mené par la Direction de l'animation de la recherche, des études et des statistiques (Dares), en collaboration avec la Cnaf et Pôle Emploi.

Pour consulter la documentation, cliquez sur [ce lien](https://documentationmidas.github.io/Documentation_MiDAS/).

## Site web quarto

Cette documentation prend la forme d'un site web conçu avec quarto. Un site web quarto correspond à un projet RStudio qui contient notamment :
- un fichier de configuration _quarto.yml, dans lequel est définie la structure du site : voir à ce sujet [Website Navigation](https://quarto.org/docs/websites/website-navigation.html) ;
- un fichier quarto markdown .qmd pour chaque page web, qui peut être structuré en sections et sous-sections : voir [Hello, Quarto](https://quarto.org/docs/get-started/hello/rstudio.html) et la section Authoring du [Guide](https://quarto.org/docs/guide/) pour la rédaction d'un document .qmd ;
- un fichier renv.lock car renv est utilisé dans ce projet pour l'intégrer dans un environnement virtuel entièrement reconstituable et garantir la reproductibilité du code. Sur l'utilisation de renv, voir ce [poste de blog](https://blog.statoscop.fr/gestion-des-packages-sur-r-avec-renv.html) ;

Le code source de ce site web documentaire est entièrement disponible dans ce dépôt GitHub, sur la branche main. 

## Organisation du code source

Le code source du site reproduit la structure du site web : un dossier à la racine du projet par grandes sections de navigation (barre de navigation en haut de la page web), un sous-dossier par section de navigation latérale au sein de ces grandes sections, si les pages web sont regroupées en section dans la navigation latérale.

Par exemple, le code source de la grande section Données Pôle Emploi est entièrement contenu dans le dossier Pole_Emploi à la racine du projet. Au sein de cette grande section :
- la page d'accueil de la grande section Données Pôle Emploi est à la racine du dossier Pole_Emploi ;
- le code source des pages web de la section Fichier Historique Statistique (FHS) est stocké dans le sous-dossier FHS de Pole_Emploi ;
- le code source des pages web de la section Fichier National des Allocataires (FNA) est stocké dans le sous-dossier FNA de Pole_Emploi.

Pour la grande section Données MMO, les pages ne sont pas regroupées en sous-section, le code source des pages web est donc directement stocké à la racine du dossier MMO, situé lui-même à la racine du projet.

Remarque : 
- la page d'accueil du site est rédigée dans le fichier index.qmd à la racine du projet ;
- la page de la section About est rédigée dans le fichier about.qmd à la racine du projet.

Chaque fichier .qmd doit correspondre à une page web.

## Rédaction du site

### Contribution

Pour contribuer au site :
- fork le projet github ;
- rédiger les modifications ;
- déposer une merge request.

### Utilisation du mode visual

Pour direction prévisualiser la page web lors de la rédaction du fichier .qmd correspondant, il est conseillé d'utiliser le mode Visual, qui est plus ergonomique et permet de faire du clique bouton pour les fonctionnalités principales (mettre en gras, ajouter un lien...)

Remarque : copier directement du texte (depuis Word par exemple) fonctionne mal avec le mode Visual, il vaut mieux utiliser le mode Source pour réaliser des copier-coller.

### Tableaux et figures

Pour créer facilement des tableaux qui peuvent être intégrés dans un fichier .qmd, il est possible d'utiliser [Tables Generator](https://tablesgenerator.com/markdown_tables) et l'option File/Paste table data qui permet de coller un tableau Word ou Excel et de générer le code source du tableau en markdown.

Pour intégrer une figure, voir [Figures](https://quarto.org/docs/authoring/figures.html).

## Publication du site

Le site est publié via le service Github Pages, selon un principe d'intégration continue des modifications sur le site web, via l'action Github .github/workflows/publish.yml, qui est exécutée à chaque push d'une modification.

