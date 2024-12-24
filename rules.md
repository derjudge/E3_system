# Système E3

Le **système E3** propose une mécanique simple mais simulationniste, inspirée du célèbre système Elo utilisé dans le classement des joueurs d’échecs.

Dans le cadre des échecs, le score Elo d’un joueur représente sa compétence à ce jeu. Une dizaine de parties suffisent généralement pour obtenir une évaluation fiable de cette compétence, qui pourrait être le score qui figure sur une fiche de personnage.

## Le principe d'Elo appliqué

Dans le système Elo, si deux adversaires, Alice et Bob, possèdent des scores Elo respectifs de \( A \) et \( B \), la probabilité qu’Alice l’emporte est donnée par la formule suivante :  
\[ P(A, B) = \frac{1}{1 + 10^{\frac{B - A}{k}}} \]  
où \( k \) est une constante définissant l’échelle de mesure, pour les échecs, \( k = 400 \). Dans le système E3, nous fixons \( k = 5 \) pour rendre le système utilisable avec nos dés.

**Exemple :**  
Si Alice possède une compétence d’escrime de 17 et Bob une compétence de 15, la probabilité qu’Alice l’emporte selon la formule est :  
\[ P(17, 15) = \frac{1}{1 + 10^{\frac{15 - 17}{5}}} \approx 71,5\% \]

## Résolution avec le système E3

Pour traduire cette probabilité en jeu, chaque personnage lance **3d6** et ajoute le résultat à son score de compétence. Voici comment cela fonctionne dans notre exemple :

- **Alice** : lance \( 3d6 \) et ajoute 17 (sa compétence d’escrime).  
- **Bob** : lance \( 3d6 \) et ajoute 15 (sa compétence d’escrime).  

Le vainqueur est celui qui obtient le score final le plus élevé.  

- En cas d’égalité, l’action peut être considérée comme un échec mutuel ou une impasse (selon le contexte narratif).  

Cette méthode produit une distribution probabiliste des résultats qui correspond étroitement à celle calculée avec le système Elo. Pour notre exemple, la probabilité que Bob dépasse Alice reste très proche de 28 %, comme attendu.

Pour faire la translation entre le système Elo aux échecs et le système E3 faites simplement  \[ \frac{Elo}{80} - 10 \]
Débutant un peu nul : 0
Débutant avec quelques parties : 2
Joueur Amateur : 5
Joueur intermédiaire : 8
Bon joueur de club : 10
Très bon joueur de club : 13
Candidat maître : 17
Maître : 19
maître international : 20
grand maître international : 21
Magnus Carlsen : 26
Stockfish : 32
Alphazero : 45

Pour mesurer l'échelle des compétences sur autre chose que les échecs :
débutant nul : 0
amateur (quelques dizaines d'heures) : 3
amateur intermédiare (une centaine d'heures d'étude et de pratiques) : 6
amateur éclairé (quelques centaines d'heures) : 10
professionnel moyen, doctorant : 13
professionnel, top 10% : 15
professionnel, parmi les top 0.1% : 20
The GOAT : 25+


## Difficultés et Résolution des Obstacles

Le système E3 ne se limite pas aux affrontements entre deux personnages. Lorsqu’un personnage doit surmonter un obstacle, on évalue son score par rapport à une difficulté fixe. Voici une échelle de référence pour les niveaux de difficulté :

### Échelle de Difficulté Fixe
- **Facile** : Faisable avec 50 % de chance pour un débutant. *(Difficulté : 10)*  
- **Typique** : Accessible pour un professionnel, mais difficile pour un débutant. *(Difficulté : 15)*  C'est le score de difficulté par défaut.
- **Difficile** : Nécessite environ mille heures d’entraînement pour réussir avec 50 % de chance. *(Difficulté : 20)*  
- **Très difficile** : Seuls les professionnels expérimentés y parviennent avec 50 % de chance. *(Difficulté : 25)*  
- **Héroïque** : Les meilleurs professionnels réussissent avec 50 % de chance. *(Difficulté : 30)*  
- **Très héroïque** : Une réussite à 50 % pour le meilleur du monde, d’un niveau exceptionnel. *(Difficulté : 35)*  

### Imprévus : Succès et Échecs Critiques
Lorsque les **trois dés affichent le même résultat** (par exemple, trois 4 ou trois 6), un événement spécial se produit. La probabilité d’un tel imprévu est de **2,77 %**.

- **En cas d’échec** : Il s’agit d’un **échec critique**. Une malchance notable frappe le personnage, avec des conséquences narratives ou mécaniques selon la situation.  
- **En cas de succès** : Il s’agit d’un **succès critique**. Le personnage obtient un avantage significatif, apportant un bonus ou un effet supplémentaire selon le contexte.
