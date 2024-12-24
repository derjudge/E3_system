## Système E3

J'essaie de concevoir un système simple mais simulationniste.
Le principe de résolution se base sur une transcription de la mesure de Elo en échec.
Le score Elo mesure notre capacité à jouer aux échecs. Une fois qu'on a joué une dizaine de parties sur chess.com on a une bonne évaluation de notre compétence "échecs" 
sur notre fiche de personnage.
 
En Elo si on a deux adversaires Alice et Bob, dont le talent est mesuré par les scores de Elo de a et b respectivement,
alors la probabilité pour Alice de gagner est :
P(a, b) = 1/(1 + 10 ^ ((B - A) / k))
où k est une constante qui dépend de l'échelle de notre Elo.
Pour notre système E3 on va avoir k = 5. Pour information le k utilisé aux échecs est k=400.

Ainsi si Alice et Bob se confrontent à l'escrime et que Alice a 17 en escrime et Bob a 15 on arriverait à une victoire d'Alice avec une probabilité de 
1/(1 + 10^((15-17)/5)) =  0.715% avec le système Elo.

Pour simuler ça avec le système E3, Alice va lancer 3d6 et ajouter à sa compétence (17) tandis que Bob va lancer 3d6 et additioner le résultat à sa compétence (15).
En cas d'égalité on peut considérer qu'un tour est perdu et qu'il n'y a pas de gagnant dans la passe d'armes.
On voit que la probabilité d'avoir le score de Bob strictement supérieur au score de Alice est de 0.28 soit quasiment la probabilité qui a été calculée avec le système Elo.

Pour faire la translation entre le système Elo aux échecs et le système E3 faite (Elo/80) - 10
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


Echelle de difficulté fixe :
Facile (faisable avec 50% de chance un débutant) : 10
Typique (un débutant a peu de chance, un professionnel y arrive sans problème) : 15
Difficile (quelqu'un avec un millier d'heure d'entrainement y arrive avec 50% de chance) : 20
Très difficile (les professionnels y arrivent avec seulement 50% de chance) : 25
Héroïque (les meilleurs professionnels y arrivent avec seulement 50% de chance) : 30
Très héroïque (le meilleur du monde y arrive avec 50% de chance, mais il est très bon) : 35 

Imprévu : 
quand les trois dés ont le même résultat (2,77% si vous voulez savoir) il se passe un truc cool.
Si c'est un échec alors c'est un échec critique, si c'est un succès alors c'est un succés critique.
