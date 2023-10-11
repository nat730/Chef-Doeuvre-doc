```mermaid
graph TD
    subgraph Phase1
        A(Inscription et Connexion)
        B(Exploration du Catalogue)
    end

    subgraph Phase2
        C(Passer une Commande)
        D(Consultation de l'Historique des Commandes)
        E(Gestion du Compte Utilisateur)
    end

    subgraph Phase3
        F("Application Maitre - Traitement des Commandes")
    end

    subgraph Phase4
        G(Notifications en Temps Réel)
    end

    A --> B --> C --> D --> E --> F --> G
    ```
