probleme d'acces image : les images doivent se situer en dehors du dossier source car dans le dossier source rien ne peut etre "recuperer" par le code.

probleme usestate : les usestate ne se mettent a jour qu'a la fin de la "boucle". si necessaire log en dehors du usestate.

probleme algorithme : mauvaises gestion de l'algo et des props

many to many genere une table de donnees supp.

orm = surcouche de la bdd pour eeviter d'interagir avec directement 

n'oubliez pas de supprimer branche quand unused

devops: yaml/docker/github/codecove/git/

C1: utiliser GIT + github pour garantir le bon code dans une equipe

C2: linter (regle de grammaire pour appliquer les regle de syntaxe),bdd test et .env. bibliotheque de test pour e2e et unitaire.codecove,

C3: github action/automatisation des test

C4 : mise en place dockerisation (docker a 95%), localement avec des configs matricielle, bdd de test pour ne pas ecraser les donnees client

C5 : faire du multi services et expliquer pourquoi

C6: veille techno + monitoring (faire de la veille sur son application pour asssurer la maintenance)

C7: faire une veille techno sur l'histoire du devops