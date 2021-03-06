# TP1 - Prise en main d'Unitex

## Exercice 1 - Prétraitement du Texte

### 1.1 - Analyse FSGraph

On peut observer des graphes qui correspondent à tous les choix possibles de mot lorsque la machine parcours la phrase.
    
Par exemple, si la machine tombe sur le mot "maison" elle a plusieurs choix possible comme "le" ou bien "la" mais la machine va pouvoir prendre "la" pour donner "la maison" car "le maison" n'est pas correcte.

Donc si on dit que A correspond a "la", B correspond a "le" et C correspond a "maison" si A fonctionne avec C alors la machine va exclure la possibilité de prendre B, inversement si B est correcte avec C alors A va être exclure.

### 1.2 - Analyse de l'automate
On peut voir un automate pour chaque phrase du texte.

Pour un automate, on peut voir chaques possibilité de mot que la machine à détecter et les choix que la machine à faite ce qui va mener à la construction de la phrase.

Exemple :
- phrase --> "Anglais, à coup sûr, Phileas Fogg n'était pas Londonner"
- Automate --> pour la partie "n'était" on peut voir qu'il était possible de mettre "n'être" au lieu de "n'était" ce qui aurait change la comprehension de la phrase.

Donc on a bien le choix "n'était" dans l'automate mais aussi "n'être" car c'est un choix possible.

## Exercice 2 - Recherche de motifs : expressions régulières

### 2.1 - Requêtes

    Requête <!DIC> :
    - détecte n’importe quel mot qui ne figure pas dans les dictionnaires du texte
    - 4 233 résultats trouvés.

    Requête <TOKEN> :
    - détecte n’importe  quelle  unité  lexicale  sauf  l’espace  utilisé  par  défaut pour les filtres morphologiques.
    - 95 315 résultats trouvés.

    Requête <UPPER> :
    - détecte n’importe quelle unité lexicale formée de lettres majuscules.
    - 1 028 résultats trouvés.

    Requête <.V> :
    - détecte toutes les entrées qui ont le code grammatical V.
    - 17 588 résultats trouvés.

    Chaque requêtes va rechercher dans tout le texte les mot qui respecte l'expression donnée, par exemple la requête <WORD>.

### 2.2 - Propre expressions régulières

#### A - Rêquete pour "Tous les adjectifs"
    On fait la Rêquete <A>
    On obtient 10 232 résultats.

#### B - Rêquete pour "Tous les occurences de la forme pouvoir"
    On fait la Rêquete pouvoir
    On obtient 8 résultats.

#### C - Rêquete pour "Tous les occurences de la forme savons"
    On fait la Rêquete savons
    On obtient qu'un seul résultat.

#### D - Rêquete pour "Tous les formes fléchies dont la forme canonique est le verbe pouvoir"
    On fait la Rêquete <pouvoir.>
    On obtient 362 résultats.
    On peut obtenir des "Puis" qui ne sont pas en lien avec pouvoir.
    Exemple : "Puis il sortie ..."

## Exercice 3 - Recherche de motifs : grammaires locales

### 3.1 - Recherche nombre dans le texte

    Après ajout du dictionnaire Dnum, on à pu faire la requête suivante :
    - Requêtes <Dnum>+<NB>
    - On obtient 2 564 résultats.

### 3.2 - Utilisez la Concordance obtenue pour construire un graphe hiraure.grf

    Voir image exercice_3-2.png