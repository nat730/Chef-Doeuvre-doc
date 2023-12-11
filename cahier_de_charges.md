# Cahier des charges - Système de Commande en Ligne

## Objectif Application Client

L'objectif de ce projet est de développer une plateforme web permettant aux utilisateurs de passer des commandes pour des produits alimentaires et d'autres produits de base avec une fonctionnalité d'achat solidaire, permettant aux utilisateurs d'acheter des produits à un prix légèrement plus élevé, mais d'en offrir au RestauDuCoeur le plus proche.

## Fonctionnalités Principales Client

### Front-end Client

1. **Inscription et Connexion** :
    - Les utilisateurs peuvent s'inscrire en fournissant leur nom, leur adresse e-mail et un mot de passe.
    - Les utilisateurs peuvent se connecter en utilisant leur adresse e-mail et leur mot de passe.

2. **Catalogue de Produits** :
    - Les utilisateurs peuvent parcourir un catalogue de produits.
        - Chaque produit affiche son nom, sa description, son prix, une image et la quantité disponible.
 
3. **Passer une Commande** :
    - Les utilisateurs ont la possibilité d'acheter des produits au prix normal pour eux meme (minimifier au maximum en evitant au maximum les couts) ou en no marge pour une association
    - Panier d'achat permet ajouter, supprimer et modifier des articles, aussi affiche le detail des produts que la personne va recevoir et le detail des produits qui seront envoyé au RestauDuCoeur.

4. **Gestion des Commandes** :
    - Les utilisateurs peuvent consulter l'historique de leurs commandes passées.
    - Ils peuvent voir l'état de chaque commande (en cours, livrée, annulée, etc.).

5. **Paiement en Ligne** :
    - Les utilisateurs peuvent effectuer des paiements en ligne de manière sécurisée via Stripe. 

6. **Panneau de Contrôle de l'Administration** :
    - Les administrateurs peuvent gérer les produits disponibles dans le catalogue.
    - Ils peuvent voir les commandes en cours et mettre à jour leur statut.
    - Ils peuvent gérer les comptes des utilisateurs.

### Back-end Client

- Serveur Node.js pour gérer les demandes des clients.
- Base de données pour stocker les produits, les commandes et les informations clients.
- Websockets pour la communication en temps réel avec l'application "maitre".
- Authentification des clients.
- Gestion des stocks en temps réel.

### Objectif Application Maitre

L'objectif de l'application "Maitre" est de gérer les commandes, les paiements et les transactions financières en temps réel pour le système de commande en ligne. Cette application est destinée à être utilisée par le personnel de gestion des commandes.

## Fonctionnalités Principales

1. **Réception des Commandes** :
    - L'application "Maitre" doit être capable de recevoir en temps réel les commandes passées par les clients via des websockets.
    - Elle doit afficher les détails de chaque commande, y compris les produits commandés, la quantité, l'adresse de livraison et l'heure de la commande.

2. **Traitement des Commandes** :
    - L'application doit permettre aux utilisateurs autorisés de traiter les commandes en les marquant comme en cours de préparation, en cours de livraison, livrées, annulées, etc.
    - Elle doit générer une preuve de chaque commande traitée, par exemple, une photo de la commande préparée.

3. **Gestion des Transactions Financières** :
    - L'application doit gérer les paiements en ligne sécurisés via Stripe et enregistrer les transactions financières.
    - Elle doit afficher les paiements reçus et les associer aux commandes correspondantes.
    - Elle doit pouvoir générer les coupons de réduction d'impot pour les clients 

4. **Notifications en Temps Réel** :
    - L'application doit envoyer des notifications en temps réel aux utilisateurs autorisés pour les informer des nouvelles commandes, des commandes traitées et des paiements reçus.
    - Elle doit permettre aux utilisateurs de voir instantanément l'état de chaque commande.

5. **Authentification Sécurisée** :
    - L'application doit mettre en place un système d'authentification sécurisé pour garantir que seuls les utilisateurs autorisés peuvent accéder aux fonctionnalités de gestion des commandes et de traitement des paiements.


## Technologies à Utiliser

Le développement de la plateforme sera basé sur les technologies suivantes :

- **Node.js et Express.js** pour la création du backend de l'application.
- **Base de données** pour stocker les informations des utilisateurs, des produits et des commandes (par exemple, PostgreSQL).
- **Vanilla.js** pour le développement de l'interface utilisateur frontend.
- **Socket.io** pour la mise en œuvre de la communication en temps réel pour les notifications de commandes et de paiements.
- **Système de Paiement en Ligne** paiement par carte bancaire (Stripe).
- **Authentification** pour sécuriser les comptes utilisateurs (par exemple, LaPosteConnect?).
- **GitHub** pour le suivi des versions du code.

## Livrables

- Code source complet de l'application front-end client.
- Code source complet de l'application back-end client.
- Documentation décrivant l'installation, la configuration et l'utilisation du système.

## Calendrier
(peut etre integrer ici GanttDiagram fait sur mermaid?)
- Phase de Conception : [Dates]
- Phase de Développement : [Dates]
- Phase de Tests : [Dates]
- Mise en Production : [Dates]

## Fonctionnalités supplémentaires si en avance sur le planning 

**Passer une Commande** :
- L'utilisateur peut choisir d'acheter uniquement pour l'association.
