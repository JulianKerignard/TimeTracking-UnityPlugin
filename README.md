# TimeTracking-UnityPlugin
My first Plugin on unity 


#Système de suivi du temps de projet
Ce système permet de suivre le temps passé sur un projet Unity, avec des fonctionnalités de pause/reprise, de réinitialisation et de localisation.
Architecture
Le système est composé de 3 classes principales :
ProjectTimeTrackerCore : Gère la logique principale de suivi du temps, le chargement/sauvegarde des données et les événements liés au temps.
ProjectTimeWindow : Fenêtre d'éditeur pour afficher les informations de temps et interagir avec le système (pause, reprise, réinitialisation).
LocalizationManager : Gère la localisation des chaînes de texte pour prendre en charge plusieurs langues.

#Fonctionnalités

Suivi automatique du temps lorsque l'éditeur Unity est actif et qu'une fenêtre a le focus
Possibilité de mettre en pause et de reprendre le suivi
Réinitialisation du temps total avec confirmation
Sauvegarde et chargement automatiques du temps total
Support de la localisation (anglais, français, allemand, russe)

#Utilisation

Ajoutez les scripts dans un dossier "Editor" de votre projet Unity.
Créez un dossier "Localization" dans le dossier "Editor/TimeTracker" et ajoutez-y les fichiers de traduction (lang_en.txt, lang_fr.txt, lang_de.txt, lang_ru.txt).
Ouvrez la fenêtre "Project Time Stats" via le menu "Window" de l'éditeur Unity.
Le temps total et le temps de session seront affichés et mis à jour automatiquement.
Utilisez les boutons "Pause/Resume Tracking" et "Reset Time" pour contrôler le suivi.
Changez la langue via les boutons de sélection de langue dans la fenêtre.

#Gestion des erreurs
Le système intègre une gestion robuste des erreurs à chaque étape clé (initialisation, chargement/sauvegarde, mise à jour du temps, etc.). Les erreurs sont enregistrées dans la console Unity avec des messages clairs pour faciliter le débogage.

#Extensibilité

Le système est conçu de manière modulaire pour faciliter l'ajout de nouvelles fonctionnalités ou langues :
Pour ajouter une langue, créez un nouveau fichier de traduction dans le dossier "Localization" et mettez à jour l'enum Language et les méthodes associées dans LocalizationManager.
Pour étendre les fonctionnalités, vous pouvez ajouter des méthodes dans ProjectTimeTrackerCore et mettre à jour l'interface utilisateur dans ProjectTimeWindow.
