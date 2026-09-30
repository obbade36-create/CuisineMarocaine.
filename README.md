# 🇲🇦 Cuisine Marocaine V2

Application Android Kotlin + Jetpack Compose.

## Fonctionnalités

- Feed vidéo vertical façon TikTok.
- Défilement vertical avec `VerticalPager`.
- Lecture automatique de la vidéo correspondant à la page active.
- Boucle vidéo.
- Bouton ingrédients superposé à la vidéo.
- Favoris locaux.
- Recherche/administration à étendre.
- Écran administrateur pour ajouter et supprimer des recettes.
- Dépendances Firebase : Auth, Firestore, Storage.
- ExoPlayer / Media3 pour la vidéo.

## Firebase

Le projet est préparé pour Firebase mais nécessite votre propre configuration.

1. Créez un projet Firebase.
2. Ajoutez une application Android avec le package :

`ma.cuisinemarocaine.app`

3. Téléchargez `google-services.json`.
4. Placez-le ici :

`app/google-services.json`

5. Activez :
   - Authentication
   - Cloud Firestore
   - Storage

## Compilation Codespaces

Le projet utilise Gradle.

```bash
chmod +x gradlew
./gradlew assembleDebug
```

APK :

`app/build/outputs/apk/debug/app-debug.apk`

## Architecture V3 recommandée

Firestore :
`recipes/{recipeId}`

Champs :
- title
- category
- videoUrl
- thumbnailUrl
- description
- ingredients[]
- duration
- createdAt
- published

Storage :
`videos/{recipeId}.mp4`
`thumbnails/{recipeId}.jpg`

Pour la production, l'administration doit être protégée par Firebase Authentication et des règles Firestore/Storage.
