Résumé du Cahier des Charges - Système de Commande en Ligne

Objectif de l'Application Client
Plateforme web pour passer des commandes de produits alimentaires avec fonctionnalité d'achat solidaire.
Achats à un prix sans marge, offrant des produits au RestauDuCoeur.
Fonctionnalités Principales Client
Front-end Client
Inscription et Connexion :

Inscription avec nom, e-mail et mot de passe.
Connexion avec e-mail et mot de passe.
Catalog de Produits :

Parcours de produits avec détails (nom, description, prix, image, quantité).
Passer une Commande :

Gestion du panier avec détails des articles.
Spécification du RestauDuCoeur pour récupérer la commande.
Gestion des Commandes :

Historique des commandes avec état (en cours, livrée, annulée, etc.).
Paiement en Ligne :

Paiement sécurisé via Stripe.
Panneau de Contrôle de l'Administration :

Gestion des produits, commandes et comptes utilisateurs.
Back-end Client
Serveur Node.js, base de données, websockets, authentification, gestion des stocks en temps réel.
Objectif de l'Application Maitre
Gestion des commandes, paiements et transactions pour le personnel de gestion.
Fonctionnalités Principales Application Maitre
Réception des Commandes :

Réception en temps réel des commandes via websockets.
Affichage des détails de chaque commande.
Traitement des Commandes :

Marquage des commandes (en préparation, en livraison, livrées, annulées, etc.).
Génération de preuves pour les commandes traitées.
Gestion des Transactions Financières :

Paiements en ligne sécurisés via Stripe.
Affichage des paiements et association aux commandes.
Notifications en Temps Réel :

Notifications pour les nouvelles commandes, commandes traitées et paiements reçus.
Visualisation instantanée de l'état des commandes.
Authentification Sécurisée :

Authentification sécurisée pour l'accès aux fonctionnalités de gestion.
Technologies Utilisées
Node.js, Express.js, Base de données (PostgreSQL), Vanilla.js, Socket.io, Stripe, Authentification (LaPosteConnect?), GitHub.
Livrables
Code source complet de l'application front-end et back-end.
Documentation d'installation, configuration et utilisation.
Calendrier
Phase de Conception, Développement, Tests, Mise en Production avec dates spécifiées.
Possibilité d'acheter uniquement pour l'association.




