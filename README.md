# Parking Moto - Application de cartographie communautaire

Application Flutter pour motards, scootéristes et livreurs permettant de trouver, signaler et visualiser les emplacements de stationnement deux-roues publics.

## 🚀 Fonctionnalités

### ✅ Implémentées
- **Carte interactive** avec Google Maps
- **Géolocalisation** automatique
- **Marqueurs colorés** selon le statut des emplacements
- **Interface moderne** avec Material Design 3
- **Architecture modulaire** avec Riverpod pour la gestion d'état
- **Service mock** pour le développement sans Firebase
- **Système de permissions** pour la localisation
- **Scripts de build** automatisés

### 🔄 En développement
- Interface d'ajout d'emplacement
- Système de signalement de problèmes
- Authentification utilisateur
- Synchronisation des données ouvertes

### 📋 Prévues
- Système communautaire (votes, commentaires, photos)
- Notifications push
- Mode hors ligne
- Plans cadastraux
- Support multilingue

## 🛠️ Architecture technique

### Frontend
- **Framework** : Flutter 3.x
- **Gestion d'état** : Riverpod
- **Carte** : google_maps_flutter
- **Géolocalisation** : geolocator
- **UI** : Material Design 3

### Backend (prévu)
- **Base de données** : Firebase Firestore
- **Authentification** : Firebase Auth
- **Stockage** : Firebase Storage
- **API REST** : Pour les données ouvertes

### Données
- **Sources officielles** : data.gouv.fr, APIs des villes
- **Données communautaires** : Rapports utilisateurs
- **Modèles** : ParkingSpot, UserReport

## 📱 Installation et lancement

### Prérequis
- Flutter SDK 3.x
- Android Studio / Xcode (pour mobile)
- Visual Studio (pour Windows desktop)
- PowerShell (pour les scripts de build)

### Installation
```bash
# Cloner le projet
git clone <repository-url>
cd parking_moto

# Installer les dépendances
flutter pub get

# Vérifier l'installation
flutter doctor
```

### Lancement

#### Développement (avec données mock)
```bash
# Lancer sur l'émulateur Android
flutter run -d emulator-5554

# Lancer sur Windows desktop
flutter run -d windows

# Lancer sur le web
flutter run -d edge
```

#### Build et déploiement
```bash
# Utiliser les scripts automatisés
.\scripts\build.bat release
.\scripts\build.bat android
.\scripts\build.bat windows
```

## 🏗️ Structure du projet

```
lib/
├── models/                 # Modèles de données
│   ├── parking_spot.dart
│   └── user_report.dart
├── services/              # Services et API
│   ├── parking_service_interface.dart
│   ├── parking_service.dart
│   ├── mock_parking_service.dart
│   └── auth_service.dart
├── providers/             # Gestion d'état Riverpod
│   └── parking_provider.dart
├── screens/               # Écrans de l'application
│   └── map_screen.dart
├── widgets/               # Composants réutilisables
│   ├── parking_marker.dart
│   └── parking_info_bottom_sheet.dart
├── utils/                 # Utilitaires
├── assets/                # Ressources
│   ├── images/
│   └── icons/
└── main.dart              # Point d'entrée

scripts/                   # Scripts de build et déploiement
├── build_and_deploy.ps1
├── build.bat
└── README.md
```

## 🔧 Configuration

### Google Maps
1. Obtenir une clé API Google Maps
2. Ajouter la clé dans `android/app/src/main/AndroidManifest.xml`
3. Configurer les restrictions de domaine

### Firebase (pour la production)
1. Créer un projet Firebase
2. Télécharger `google-services.json` (Android)
3. Configurer `firebase_options.dart`
4. Activer Firestore, Auth et Storage

### Données ouvertes
- **Paris** : API officielle de la ville
- **Lyon** : API Grand Lyon
- **Bordeaux** : API métropole de Bordeaux

## 🧪 Tests

### Tests unitaires
```bash
flutter test
```

### Tests d'intégration
```bash
flutter test integration_test/
```

### Analyse du code
```bash
flutter analyze
```

## 📊 Données mock

L'application utilise actuellement des données mock pour le développement :

- **Emplacements officiels** : 15 spots dans Paris
- **Emplacements communautaires** : 8 spots signalés par les utilisateurs
- **Statuts variés** : Libre, Occupé, En travaux, Inexistant
- **Types** : Officiel, Communautaire

## 🚀 Déploiement

### Android
```bash
flutter build apk --release
flutter build appbundle --release
```

### iOS
```bash
# Build per iOS (richiede Xcode e iOS 14.0+)
flutter build ios --release

# Build senza codesigning (per test)
flutter build ios --no-codesign

# Eseguire su dispositivo iOS
flutter run -d ios

# Installare le dipendenze iOS
cd ios && pod install
```

**Note**: Per iOS è necessario:
- Xcode 15.0+
- iOS 14.0+ (deployment target)
- CocoaPods installato
- Aprire sempre `ios/Runner.xcworkspace` (non `.xcodeproj`)

Vedi `ios/README.md` per istruzioni dettagliate.

### Web
```bash
flutter build web --release
```

### Windows
```bash
flutter build windows --release
```

## 🤝 Contribution

1. Fork le projet
2. Créer une branche feature (`git checkout -b feature/AmazingFeature`)
3. Commit les changements (`git commit -m 'Add some AmazingFeature'`)
4. Push vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrir une Pull Request

## 📝 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

## 📞 Support

Pour toute question ou problème :
- Ouvrir une issue sur GitHub
- Consulter la documentation Flutter
- Vérifier les logs de l'application

## 🔄 Roadmap

### Version 1.0 (MVP)
- [x] Carte interactive
- [x] Géolocalisation
- [x] Affichage des emplacements
- [ ] Ajout d'emplacement
- [ ] Signalement de problème
- [ ] Authentification basique

### Version 1.1
- [ ] Système communautaire
- [ ] Photos et commentaires
- [ ] Notifications
- [ ] Mode hors ligne

### Version 2.0
- [ ] Plans cadastraux
- [ ] Navigation intégrée
- [ ] Analytics
- [ ] Support multilingue
