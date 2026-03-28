TP 10 : Formulaire de Connexion Personnalisé (Spring Security)
Ce projet porte sur la personnalisation du processus d'authentification dans une application JakartaEE / Spring Boot. L'objectif est de remplacer le formulaire par défaut de Spring Security par une interface utilisateur personnalisée et de gérer le flux de connexion de bout en bout.
🚀 Objectifs du TP
Développer un formulaire d'authentification HTML/Thymeleaf sur mesure.
Configurer Spring Security pour intercepter les requêtes via l'endpoint /authenticate.
Gérer les sessions utilisateur (connexion, déconnexion et erreurs).
Mettre en place des redirections dynamiques après succès ou échec.
🛠️ Étapes de Réalisation
1. Préparation du projet
Configuration des dépendances nécessaires dans le pom.xml (spring-boot-starter-security, spring-boot-starter-thymeleaf).
2. Configuration de la Sécurité
Mise à jour de la classe SecurityConfig pour déclarer le formulaire personnalisé :
java
.formLogin(form -> form
    .loginPage("/login")           // Vue personnalisée
    .loginProcessingUrl("/authenticate") // Endpoint de traitement
    .defaultSuccessUrl("/home", true)    // Redirection après succès
    .permitAll()
)
Use code with caution.

3. Contrôleur de Gestion des Vues
Création d'un ViewController pour mapper les routes /login, /home, et gérer les messages d'erreur via les paramètres de requête (?error).
4. Création du Formulaire de Login
Développement de la page login.html. Le formulaire doit pointer vers /authenticate avec les champs username et password.
5. Gestion des Redirections et Déconnexion
Configuration du bouton de déconnexion (/logout).
Création de pages spécifiques pour les différents rôles ou états de connexion.
📋 Résumé des Fonctionnalités
Formulaire HTML personnalisé.
Intégration Spring Security via /authenticate.
Gestion des messages d'erreur et de logout.
Redirections personnalisées.
Vérification des filtres de sécurité.
<img width="1919" height="875" alt="Screenshot 2026-03-28 145030" src="https://github.com/user-attachments/assets/5b1f3919-93bf-419d-9be2-988386a43b80" />
<img width="1882" height="866" alt="Screenshot 2026-03-28 145527" src="https://github.com/user-attachments/assets/2f616663-8e71-4cd5-b4ac-c24192b59a15" />
<img width="1915" height="895" alt="Screenshot 2026-03-28 145546" src="https://github.com/user-attachments/assets/a3f13b13-077f-46a1-b786-433ba6efabc3" />
<img width="1909" height="862" alt="Screenshot 2026-03-28 145608" src="https://github.com/user-attachments/assets/247a0e1e-1358-44c0-80e9-f2af304aeeb8" />
<img width="1909" height="862" alt="Screenshot 2026-03-28 145608" src="https://github.com/user-attachments/assets/9e7d46e6-8b07-4af3-aa86-0f7a969f7173" />
