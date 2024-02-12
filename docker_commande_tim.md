On va utiliser docker car:
- Les appications se lance dans un environnement isolé 
    - Ceci permet de lancer les apps sur des serveurs differents
    - Tout le necessaire à l'execution s'instale dans l'environnement (dans le container)

La meme app on peut etre lancer dans des différents container pour partager la charge

La BDD peut etre installé à l'interieur de container 

### Le c'est la plus petite unité de docker et l'element principale est il est fait à partir de l'image 

composant de docker:
- CLient 
- Daemon 
- Host 
- Container
- Image
- Repository
- Registry (docker Hub)

Comment fonctionne les container

    Container aura une partie isolé (pour lancer quelque chose) dans le disk dur mais accessible uniquement à ce container , cela donne la possibilité de lancer plusieur container.
    * Si on cree plusieur container à partir d'une seul image alors les container vont utiliser une seul partie du disk (cela permet utiliser moins de capacité de disk et donc le decharger un peu)


Docker Desktop - c'est une solution pour pouvoir lancer docker dans mac ou windows - autrement ,  une machine vertuel se créer grace à docker desktop, dedans se lance docker deamon.

- A partir d'une image , on peut creer plusieur containers

- on peut telecharger une image(python par ex) à a partir de docker hub et puis utiliser pour lancer des application(fait en python) 
 
une image et statique et un container est dinamique

toutes les couches du container sont "read-only"

- chaque image est un ensemble de fichier 

les images sont stocker dans un repository

il existe des image officiel et communetaire 

- qu'est ce que un repository dans le docker sont ont le même but que ceux de github


Commandes :
```bash
    docker version ### montre la version du docker server et client
    docker ps -a ###lister les container
    docker ps ### montre uniquement les container qui sont lancé 
    docker images ###lister toutes les images locales
    docker run -d "nom de l'image" ### cree un container si l'image porant ce nom n'est pas presente sur localement docker va chercher  sur docker hub et si l'image est trouvé - docker va la telecharger et va la lancer , l'option "-d" permet lancer le container en "detaché"
    docker run -d --name my_nginx nginx ### permet ajouter un nom personnalisé au container
    docker rm "container id" ### supprime le container 
    docker run -it ### permet lancer le terminal interactive
    docker container prune ### supprimer tous les container en arret 
    docker inspect "container id/nom du container" ###conntainer les details sur le container si on ajout "| grep IPAddress /ou autre info du detail/" ceci permet avoir uniquement ce qu'on a indiqué dans le greo
    docker stop "container id/nom du container"/ docker kill "container id/nom du container" ### permet arreter le container, on peut ecrire les ids à la suite
    docker exec -it "container id" bash ### commande permet lancer un processus en plus - ici on demande de lancer bash
        hostname/ hostname -i ### à l'interieur de bash permet avoir des info comme le ipaddress ou l'id du container (en soi on peut utiliser les commandes standard de linux du type: cd, mkdir...)
    docker run -v ${PWD}:/usr/share/nginx/html -p 8080:80 -d nginx ### permet de modifier ici l'index par defaut par celui qu'on a créer. Dans cette commande nous avons 3 options : -v, -p, -d; ${PWD} peut etre remplaçé par la route absolut, -p: mapping de port; -v: modification de l'index par defaut; -d : permet lancer l'image en détaché.
    docker run -it --rm "container id/nom du container" ### permet de supprimer le container apres son arrêt 
    ### On peut ecrire les commandes de docker sur plusieur ligne, pour cela il faut mettre \ à la fin de chaque ligne : 
    docker run \
        --name my-ngnix \
        -v ${PWD}:/usr/share/nginx/html \
        -p 8888:80 \
        -d \
        --rm \
        nginx

```