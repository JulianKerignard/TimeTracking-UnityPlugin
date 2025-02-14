# Project Time Tracker - Documentation

## Table des matières
1. [Présentation](#presentation)
2. [Installation](#installation)
3. [Structure du projet](#structure-du-projet)
4. [Personnalisation](#personnalisation)
5. [Guide d'utilisation](#guide-d-utilisation)
6. [Localisation](#localisation)
7. [Dépannage](#depannage)

## Presentation
Project Time Tracker est une extension Unity qui permet de suivre le temps passé sur vos projets Unity. Elle offre :
- Un suivi en temps réel
- Un support multilingue (Français, Anglais, Allemand, Russe)
- Une sauvegarde automatique
- Une interface utilisateur intuitive
- Un système de pause/reprise
- Une personnalisation du temps initial

## Installation

### Installation Simple
1. Téléchargez le package depuis l'Asset Store
2. Double-cliquez sur le package pour l'importer dans Unity
3. Dans Unity, allez dans Window > Project Time Stats

### Installation pour Développement
1. Créez un dossier `TimeTracker` dans votre dossier `Assets/Editor`
2. Créez les sous-dossiers suivants :
   ```
   Assets/
   └── Editor/
       └── TimeTracker/
           ├── Core/
           ├── UI/
           └── Localization/
   ```
3. Placez les fichiers source dans leurs dossiers respectifs :
   - `Core/` : ProjectTimeTrackerCore.cs
   - `UI/` : ProjectTimeWindow.cs
   - `Localization/` : LocalizationManager.cs

4. Créez un dossier `Localization` et ajoutez les fichiers de traduction :
   ```
   Localization/
   ├── lang_en.txt
   ├── lang_fr.txt
   ├── lang_de.txt
   └── lang_ru.txt
   ```

## Structure du Projet

### Fichiers Principaux

1. **ProjectTimeTrackerCore.cs**
   - Gestionnaire principal du temps
   - Système de sauvegarde
   - Gestion des événements
   ```c#
   namespace ProjectTimeTracker
   {
       [InitializeOnLoad]
       public class ProjectTimeTrackerCore
       {
           // Constantes importantes
           private const string SAVE_FILE_NAME = "project_time.txt";
           private const double UPDATE_INTERVAL = 2.0;
           private const double SAVE_INTERVAL = 10.0;
   ```

2. **LocalizationManager.cs**
   - Gestion des langues
   - Chargement des traductions
   - Événements de changement de langue

3. **ProjectTimeWindow.cs**
   - Interface utilisateur
   - Contrôles et affichage
   - Gestion des styles

## Personnalisation

### Modification de l'Interface
1. Ouvrez `ProjectTimeWindow.cs`
2. Localisez la section `SetupStyles()`
3. Personnalisez les styles :
   ```c#
   private void SetupStyles()
   {
       headerStyle = new GUIStyle(EditorStyles.boldLabel)
       {
           fontSize = 14,  // Modifier la taille
           alignment = TextAnchor.MiddleLeft,
           margin = new RectOffset(5, 5, 10, 10)
       };
   ```

### Ajout d'une Nouvelle Fonctionnalité
1. Dans `ProjectTimeTrackerCore.cs`, ajoutez votre nouvelle fonction :
   ```c#
   public static void MaNouvelleFonction()
   {
       // Votre code ici
   }
   ```
2. Ajoutez l'interface utilisateur dans `ProjectTimeWindow.cs` :
   ```c#
   private void DrawControls()
   {
       // Ajoutez votre nouveau bouton
       if (GUILayout.Button("Ma Nouvelle Fonction"))
       {
           ProjectTimeTrackerCore.MaNouvelleFonction();
       }
   }
   ```

### Modification du Système de Sauvegarde
Par défaut, la sauvegarde se fait dans un fichier texte. Pour modifier le format :

1. Localisez les méthodes dans `ProjectTimeTrackerCore.cs` :
   ```c#
   private static void SaveCurrentTime()
   private static void LoadSavedTime()
   ```
2. Modifiez le format de sauvegarde selon vos besoins (JSON, XML, etc.)

## Guide d'Utilisation

### Fonctionnalités de Base
1. **Lancer le tracker** : Window > Project Time Stats
2. **Pause/Reprise** : Bouton dans la fenêtre
3. **Changer de langue** : Boutons de langue en bas
4. **Réinitialiser** : Bouton avec confirmation

### Fonctionnalités Avancées
1. **Définir un temps initial** :
   - Entrez les heures, minutes, secondes
   - Cliquez sur "Set Time"

2. **Exportation des données** :
   - Le fichier est sauvegardé dans : `[Dossier Projet]/project_time.txt`
   - Format : Nombre de secondes total

## Localisation

### Ajouter une Nouvelle Langue
1. Créez un fichier `lang_[code].txt` dans le dossier Localization
2. Format des traductions :
   ```
   projectTime=Temps du Projet
   totalTime=Temps Total
   sessionTime=Temps de Session
   ```
3. Ajoutez la langue dans `LocalizationManager.cs` :
   ```c#
   public enum Language
   {
       English,
       French,
       German,
       Russian,
       VotreLangue // Ajoutez ici
   }
   ```

## Depannage

### Problèmes Courants

1. **Le temps ne s'incrémente pas**
   - Vérifiez que la fenêtre Unity est active
   - Vérifiez que le tracking n'est pas en pause
   - Consultez la console pour les erreurs

2. **Perte de données**
   - Vérifiez les permissions du dossier
   - Recherchez le fichier de backup : `project_time.txt.backup`
   - Consultez les logs d'erreur Unity

3. **Problèmes de traduction**
   - Vérifiez l'encodage des fichiers (UTF-8)
   - Vérifiez la syntaxe des fichiers de traduction
   - Redémarrez Unity après modification

### Support et Contact
Pour toute assistance supplémentaire :
- Commentaires sur l'Asset Store
- Email : [juliankerignard4@gmail.com]
- Documentation en ligne : [Voir la documentation]

[//]: # (Links)
