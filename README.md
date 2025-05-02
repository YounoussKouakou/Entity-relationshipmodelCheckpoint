Gym Management System – Entity Relationship Model
🧾 Description
Ce projet propose un modèle entité-association (ER) destiné à moderniser la gestion des inscriptions dans une chaîne de gymnases. Il remplace le système manuel de cartes par une base de données relationnelle claire et scalable. Le système gère les gymnases, les membres, les sessions sportives, et les entraîneurs.

🧱 Entités Principales
1. Gymnasium
Identifiant unique (GymID)
Nom
Adresse
Numéro de téléphone
2. Member
Identifiant unique (MemberID)
Nom
Prénom
Adresse
Date de naissance
Genre
Inscrit à un gymnase (GymID)
3. Coach
Identifiant unique (CoachID)
Nom
Prénom
Âge
Spécialité
4. Session
Identifiant unique (SessionID)
Type de sport
Horaire
Associée à un gymnase (GymID)
🔗 Relations
Relation	Description
Gymnasium–Member	Un gymnase peut avoir plusieurs membres.
Gymnasium–Session	Un gymnase peut organiser plusieurs sessions sportives.
Session–Member	Une session accueille jusqu'à 20 membres. Représentée via Registration.
Session–Coach	Une session est dirigée par jusqu'à 2 entraîneurs. Représentée via SessionCoach.
Entités associatives :
Registration
SessionID
MemberID
Gère la relation N:M entre membres et sessions
➕ Contrainte : max 20 membres par session
SessionCoach
SessionID
CoachID
Gère la relation N:M entre sessions et entraîneurs
➕ Contrainte : max 2 coachs par session
