# Système E3

Le **système E3** propose une mécanique simple mais simulationniste, inspirée du célèbre système Elo utilisé dans le classement des joueurs d’échecs.

Dans le cadre des échecs, le score Elo d’un joueur représente sa compétence à ce jeu. Une dizaine de parties, contre plusieurs adversaires, suffisent généralement pour obtenir une évaluation fiable de cette compétence, qui pourrait être le score qui figure sur une fiche de personnage.

## Le principe d'Elo appliqué

Dans le système Elo, si deux adversaires, Alice et Bob, possèdent des scores Elo respectifs de $A$ et $B$, la probabilité qu’Alice l’emporte est donnée par la formule suivante :  
$$P(A, B) = \frac{1}{1 + 10^{\frac{B - A}{w}}},$$

où $w$ est une constante définissant l’échelle de mesure (appelé largeur ou width). Pour les échecs , on utilise généralement $w = 400$. Dans le système E3, nous fixons $w \approx 5$ pour rendre le système utilisable avec nos dés.

**Exemple :**  
Si Alice possède une compétence d’escrime de 17 et Bob une compétence de 15, la probabilité qu’Alice l’emporte selon la formule est :  
$$P(17, 15) = \frac{1}{1 + 10^{\frac{15 - 17}{5}}} \approx 0,7597 .$$

## Résolution avec le système E3

Pour traduire cette probabilité en jeu, chaque personnage lance **3d6** et ajoute le résultat à son score de compétence + caractéristique. Voici comment cela fonctionne dans notre exemple :

- **Alice** : lance 3d6 et ajoute 17 (sa compétence d’escrime + sa dextérité).  
- **Bob** : lance 3d6 et ajoute 15 (sa compétence d’escrime + sa dextérité).  

Le vainqueur est celui qui obtient le score final le plus élevé.  

- En cas d’égalité, l’action peut être considérée comme un échec mutuel, une impasse ou statu quo (selon le contexte narratif).  

Cette méthode produit une distribution de probabilités qui correspond assez étroitement à celle calculée avec le système Elo. 
Pour notre exemple, la probabilité que Bob dépasse Alice reste très proche de 25 %, comme attendu.
**NB:** On calcule cette probabilité et faisant (Nombre de cas où Bob gagne) / (Nombre de cas où Alice gagne + Nombre de cas où Bob gagne), de façon à ne pas tenir compte dans le calcul des cas d'égalité.

En fait, le delta entre la probabilité attendue et la probabilité effective (celle obtenue par le lancer des dés) est dans tout les cas inférieure à 2,15%.

Pour faire la translation entre le système Elo aux échecs et le système E3 on peut faire simplement  $\frac{Elo}{100} - 10$. Ce qui donne :
  - Débutant un peu nul : 0
  - Débutant avec quelques parties : 2
  - Joueur Amateur : 5
  - Joueur intermédiaire : 8
  - Bon joueur de club : 10
  - Très bon joueur de club : 13
  - Candidat maître : 17
  - Maître : 19
  - Maître international : 20
  - Grand Maître International : 21
  - Magnus Carlsen : 26
  - Stockfish : 32
  - Alphazero : 45

Pour mesurer l'échelle des compétences sur autre chose que les échecs, on peut s'inspirer de la précédente table et avoir :
  - débutant nul : 0
  - amateur (quelques dizaines d'heures) : 3
  - amateur intermédiaire (une centaine d'heures d'étude et de pratiques) : 6
  - amateur éclairé (quelques centaines d'heures) : 10
  - professionnel moyen, doctorant : 13
  - professionnel, top 10% : 15
  - professionnel, parmi les top 0.1% : 20
  - The GOAT : 25+


## Difficultés et Résolution des Obstacles

Le système E3 ne se limite pas aux affrontements entre deux personnages. Lorsqu’un personnage doit surmonter un obstacle, on évalue son score par rapport à une difficulté fixe. Voici une échelle de référence pour les niveaux de difficulté :

### Échelle de Difficulté Fixe
- **Facile** : Faisable avec 50 % de chance pour un débutant. *(Difficulté : 9)*  
- **Typique** : Accessible pour un professionnel, mais difficile pour un débutant. *(Difficulté : 15)*  C'est le score de difficulté par défaut.
- **Difficile** : Nécessite environ mille heures d’entraînement pour réussir avec 50 % de chance. *(Difficulté : 18)*  
- **Très difficile** : Seuls les professionnels expérimentés y parviennent avec 50 % de chance. *(Difficulté : 24)*  
- **Héroïque** : Les meilleurs professionnels réussissent avec 50 % de chance. *(Difficulté : 30)*  
- **Très héroïque** : Une réussite à 50 % pour le meilleur du monde, d’un niveau exceptionnel. *(Difficulté : 35)*  

### Imprévus : Succès et Échecs Critiques ("Oui Et" et "Non Et")
Lorsque les **trois dés affichent le même résultat** (par exemple, trois 4 ou trois 6), un événement spécial se produit. La probabilité d’un tel imprévu est de **2,77 %**.

- **En cas d’échec** : Il s’agit d’un **échec critique**. Une malchance notable frappe le personnage, avec des conséquences narratives ou mécaniques selon la situation.  
- **En cas de succès** : Il s’agit d’un **succès critique**. Le personnage obtient un avantage significatif, apportant un bonus ou un effet supplémentaire selon le contexte.

### Succès et Echec partiel ("Non Mais" et "Oui Mais")
Lorsque les **trois dés affichent une suite** (1-2-3, 2-3-4, 3-4-5 ou 4-5-6), un événement vient modérer le résultat. La probabilité d'un tel imprévu est **11,11%**.
Généralement, le succès vient avec un prix et les échecs viennent avec une petite compensation. 


