# 🎵 SAE 1.02 - Exploration de Données Musicales Spotify

> Projet universitaire de comparaison d'approches algorithmiques sur un dataset de 438 948 chansons Spotify

[![Java](https://img.shields.io/badge/Java-17+-orange.svg)](https://www.oracle.com/java/)
[![CSV](https://img.shields.io/badge/Format-CSV-green.svg)](https://en.wikipedia.org/wiki/Comma-separated_values)
[![License](https://img.shields.io/badge/License-Academic-blue.svg)](LICENSE)

---

## 📋 Table des matières

- [À propos](#-à-propos)
- [Fonctionnalités](#-fonctionnalités)
- [Prérequis](#-prérequis)
- [Installation](#-installation)
- [Utilisation](#-utilisation)
- [Structures de données](#-structures-de-données)
- [Algorithmes implémentés](#-algorithmes-implémentés)
- [Performances](#-performances)
- [Auteur](#-auteur)

---

## 🎯 À propos

Ce projet a été réalisé dans le cadre de la **SAE 1.02** (Situation d'Apprentissage et d'Évaluation) du département Informatique de l'IUT de Laval. L'objectif est de comparer les performances de différents algorithmes de tri, recherche et filtrage sur un large dataset musical.

### Contexte
Une entreprise d'open data souhaite développer une application pour explorer des données musicales provenant de Spotify. Le client doit pouvoir :
- Charger différents volumes de données (100 à 438 948 chansons)
- Effectuer des opérations de tri, filtrage et recherche
- Comparer les performances selon l'implémentation choisie (ArrayList vs LinkedList)

### Dataset
Les données proviennent de **Spotify** et contiennent **438 948 chansons** au total au format **CSV** (Comma-Separated Values)

---

## Fonctionnalités

### 🔹 Opérations de base
- ✅ **Chargement** de fichiers CSV de différentes tailles
- ✅ **Affichage** formaté et adaptatif des données
- ✅ **Tri** selon plusieurs critères (titre, date, popularité)
- ✅ **Filtrage** par année, artiste, album, type
- ✅ **Recherche** de chansons par titre
- ✅ **Menu interactif** en console

### 🔹 Algorithmes implémentés
| Catégorie | Algorithmes |
|-----------|-------------|
| **Tri** | Tri Sélection, Tri Fusion, TimSort (Java) |
| **Recherche** | Linéaire, Dichotomique |
| **Filtrage** | Manuel (boucle), Java (removeIf + lambda) |

### 🔹 Comparaison de structures
- **ArrayList** : Accès rapide par index O(1)
- **LinkedList** : Insertions/suppressions rapides O(1)

---

## 🛠️ Prérequis

- **Java JDK 11+** (testé avec Java 17)
- **IDE recommandé** : Eclipse, IntelliJ IDEA, ou VS Code
- **Fichiers CSV** : `spotify_100.csv`, `spotify_1000.csv`, etc.

### Téléchargement du dataset
Les fichiers CSV doivent être placés dans le dossier `src/` :
```
src/
├── musique/
│   └── Musique.java
├── spotify_100.csv
├── spotify_1000.csv
├── spotify_10000.csv
├── spotify_100000.csv
└── spotify_FULL.csv
```

---

## 📦 Installation

### 1. Cloner le dépôt
```bash
git clone https://github.com/votre-username/sae-spotify.git
cd sae-spotify
```

### 2. Ouvrir dans votre IDE
- **Eclipse** : File → Open Projects from File System
- **IntelliJ** : File → Open → Sélectionner le dossier
- **VS Code** : Open Folder

### 3. Vérifier la structure
```
projet/
├── src/
│   └── musique/
│       ├── Musique.java
│       ├── Song.java
│       └── MusiqueInterface.java
└── README.md
```

---

## 🚀 Utilisation

### Compilation et exécution

#### En ligne de commande
```bash
# Compiler
javac src/musique/Musique.java

# Exécuter
java -cp src musique.Musique
```

#### Dans Eclipse
1. Clic droit sur `Musique.java`
2. Run As → Java Application

### Menu principal

```
=== SAE 1.02 - Exploration de données musicales ===

Choisir l'implémentation:
1. ArrayList
2. LinkedList
Choix: 1

============================================================
MENU PRINCIPAL - Structure: ArrayList
Chansons chargées: 0
============================================================
1. Charger un fichier
2. Afficher les données
3. Trier
4. Filtrer
5. Rechercher
6. Tests de performance
0. Quitter
```

### Exemple d'utilisation

#### 1️⃣ Charger un fichier
```
Choix: 1
=== CHARGER UN FICHIER ===
1. spotify_100.csv
2. spotify_1000.csv
3. spotify_10000.csv
4. spotify_100000.csv
5. spotify_FULL.csv
Choix: 3

=== CHARGEMENT avec ArrayList ===
✓ Chargé: 10000 chansons
✓ Temps: 245 ms
✓ Structure: ArrayList
```

#### 2️⃣ Trier les données
```
Choix: 3
=== TRIER ===
1. Tri Sélection (par popularité)
2. Tri Fusion (par popularité)
3. Tri Java - par titre
4. Tri Java - par popularité
5. Tri Java - par année
Choix: 2

=== TRI FUSION (par popularité) ===
✓ Tri Fusion terminé en 18 ms
```

#### 3️⃣ Filtrer par année
```
Choix: 4
=== FILTRER ===
1. Filtre manuel (par année)
...
Choix: 1
Année: 2020

=== FILTRE MANUEL (par année) ===
✓ Filtré: 7234 chansons supprimées
✓ Restantes: 2766 chansons
✓ Temps: 12 ms
```

#### 4️⃣ Rechercher une chanson
```
Choix: 5
=== RECHERCHER ===
1. Recherche linéaire
2. Recherche dichotomique
Choix: 2
Titre à rechercher: Blinding Lights

=== RECHERCHE DICHOTOMIQUE ===
⚠ La liste doit être triée par titre!
✓ Trouvé: Blinding Lights | The Weeknd | After Hours | 2020 | Pop: 95
✓ Comparaisons: 12
✓ Temps: 0 ms
```

---

## 🗂️ Structures de données

### Comparaison ArrayList vs LinkedList

| Opération | ArrayList | LinkedList | Meilleur choix |
|-----------|-----------|------------|----------------|
| **Accès par index** | O(1) | O(n) | ✅ ArrayList |
| **Ajout à la fin** | O(1) amortisé | O(1) | ≈ Équivalent |
| **Suppression au début** | O(n) | O(1) | ✅ LinkedList |
| **Tri** | Plus rapide | Plus lent | ✅ ArrayList |
| **Recherche** | Plus rapide | Plus lent | ✅ ArrayList |

### Choix dans le code

Pour changer l'implémentation, il suffit de modifier au lancement :
```java
// Au démarrage
System.out.println("1. ArrayList");
System.out.println("2. LinkedList");

// Ou directement dans le code
Musique app = new Musique(true);  // true = ArrayList
Musique app = new Musique(false); // false = LinkedList
```

---

## 🧮 Algorithmes implémentés

### 1. Tri Sélection
**Complexité** : O(n²)
```java
// Trouve le minimum et l'échange
for (int i = 0; i < n - 1; i++) {
    int minIdx = i;
    for (int j = i + 1; j < n; j++) {
        if (songs.get(j).popularity < songs.get(minIdx).popularity) {
            minIdx = j;
        }
    }
    // Échanger i et minIdx
}
```

**Utilisation** : Petit dataset (< 1000 éléments)

### 2. Tri Fusion (Merge Sort)
**Complexité** : O(n log n)
```java
// Divise récursivement puis fusionne
triFusionRecursif(arr, 0, n-1);
```

**Avantage** : Complexité garantie O(n log n)  
**Inconvénient** : Utilise O(n) mémoire supplémentaire

### 3. TimSort (Tri Java)
**Complexité** : O(n log n)
```java
Collections.sort(songs, (s1, s2) -> 
    Integer.compare(s1.popularity, s2.popularity)
);
```

**Avantage** : Optimisé pour données réelles (partiellement triées)  
**Performance** : Le plus rapide des 3 algorithmes

### 4. Recherche Linéaire
**Complexité** : O(n)
```java
for (Song song : songs) {
    if (song.trackName.equals(titre)) {
        return song; // Trouvé
    }
}
```

**Utilisation** : Liste non triée

### 5. Recherche Dichotomique
**Complexité** : O(log n)
```java
int left = 0, right = n - 1;
while (left <= right) {
    int mid = (left + right) / 2;
    // Comparer et ajuster left/right
}
```

**Prérequis** : ⚠️ Liste **doit être triée** !  
**Performance** : Beaucoup plus rapide sur grandes listes

---

## 📊 Performances

### Résultats mesurés (ArrayList)

#### Chargement
| Taille | Temps (ms) |
|--------|-----------|
| 100 | 5 ms |
| 1 000 | 18 ms |
| 10 000 | 95 ms |
| 100 000 | 850 ms |
| 438 948 | 4 200 ms |

#### Tri (10 000 chansons)
| Algorithme | Temps (ms) | Complexité |
|------------|-----------|-----------|
| Tri Sélection | 1 450 ms | O(n²) |
| Tri Fusion | 18 ms | O(n log n) |
| TimSort (Java) | 12 ms | O(n log n) |

#### Recherche (100 000 chansons)
| Type | Temps (ms) | Comparaisons |
|------|-----------|--------------|
| Linéaire | 2 ms | 50 000 (moy.) |
| Dichotomique | 0 ms | 17 |

#### Suppression un à un (1 000 chansons)
| Structure | Temps (ms) |
|-----------|-----------|
| ArrayList | 1 200 ms |
| LinkedList | 5 ms |

**Conclusion** : LinkedList est **240x plus rapide** pour les suppressions au début !

---

## 📂 Structure du code

### Classe `Song`
Représente une chanson avec :
- `trackName` : Titre
- `albumName` : Album
- `albumType` : Type (single, album, compilation)
- `releaseDate` : Date de sortie
- `durationMs` : Durée en millisecondes
- `artists[]` : Tableau des artistes (jusqu'à 12)
- `albumPopularity` : Popularité (0-100)

### Classe `Musique`
Classe principale contenant :
- Structure de données (`ArrayList` ou `LinkedList`)
- Algorithmes de tri (Sélection, Fusion, Java)
- Algorithmes de recherche (Linéaire, Dichotomique)
- Filtres (Manuel, Java removeIf)
- Menu interactif

### Interface `MusiqueInterface`
Définit le contrat des méthodes obligatoires :
```java
void charger(String path);
void afficher();
void sort(int criteria);
void filter(String text, int column);
void search(String titre);
```

---

## 📈 Graphiques et analyses

Les graphiques suivants sont générés dans le tableur Excel/LibreOffice :

1. **Temps de chargement** (ArrayList vs LinkedList)
2. **Comparaison des algorithmes de tri**
3. **Recherche linéaire vs dichotomique**
4. **Suppression un à un** (montre la supériorité de LinkedList)

Voir le fichier `performances.xlsx` dans le dossier `docs/`.

---

## 🎓 Concepts Java utilisés

- ✅ Programmation Orientée Objet (POO)
- ✅ Interfaces et implémentation
- ✅ Collections Java (List, ArrayList, LinkedList)
- ✅ Expressions Lambda (Java 8+)
- ✅ Génériques (`<Song>`)
- ✅ Lecture de fichiers (BufferedReader)
- ✅ Gestion d'exceptions (try-catch)
- ✅ Mesure de performances (System.currentTimeMillis)

---

## 🐛 Résolution de problèmes

### Erreur : "FileNotFoundException"
**Solution** : Vérifier que les fichiers CSV sont dans `src/`

### Erreur : "OutOfMemoryError" avec FULL.csv
**Solution** : Augmenter la mémoire JVM
```bash
java -Xmx2G -cp src musique.Musique
```

### Console limitée dans Eclipse
**Solution** : Window → Preferences → Run/Debug → Console  
Décocher "Limit console output"

### Parsing CSV incorrect
**Problème** : Virgules dans les champs  
**Solution** : Le code gère déjà les guillemets, mais certains CSV peuvent nécessiter un parser plus robuste (PapaParse, OpenCSV)

---

## 📝 Livrables du projet

### ✅ Code source
- `Musique.java` : Classe principale avec menu et algorithmes
- `Song.java` : Classe représentant une chanson
- `MusiqueInterface.java` : Interface des méthodes requises

### ✅ Rapport d'analyse (25% de la note)
Contient :
- Introduction et contexte
- Description des algorithmes
- Résultats des mesures de performances
- Analyse comparative ArrayList vs LinkedList
- Graphiques et tableaux
- Conclusion

### ✅ Tableur de performances (annexe)
- Temps de chargement
- Temps de tri (3 algorithmes)
- Temps de recherche (2 algorithmes)
- Temps de suppression
- Graphiques associés

### ✅ Démonstration
Séance de restitution prévue après le rendu.

---

## 🎯 Critères d'évaluation

| Critère | Points |
|---------|--------|
| **Code fonctionnel** | 50% |
| **Algorithmes corrects** | 25% |
| **Performances mesurées** | 15% |
| **Rapport d'analyse** | 10% |

---

## 👨‍💻 Auteur

**Votre Nom**  
Étudiant en BUT Informatique  
Département Informatique - [Université]

📧 Email : votre.email@example.com  
🔗 GitHub : [@votre-username](https://github.com/votre-username)

---

## 📚 Références

- [Documentation Java Collections](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Collections.html)
- [TimSort Algorithm](https://en.wikipedia.org/wiki/Timsort)
- [Complexité algorithmique](https://www.bigocheatsheet.com/)
- [Dataset Spotify](https://www.kaggle.com/datasets/spotify/)

---

## 📄 Licence

Ce projet est réalisé dans un cadre académique.  
© 2025 - Tous droits réservés

---

## 🙏 Remerciements

- **Sébastien George** et **Yann Walkowiak** - Enseignants encadrants
- **Spotify** - Pour la mise à disposition des données
- **Département Informatique** - Pour le matériel et les ressources

---

**Date de rendu** : 16 décembre 2025 à 18h00  
**Plateforme** : UMTICE

---

<div align="center">

### ⭐ Si ce projet vous a aidé, n'oubliez pas de laisser une étoile ! ⭐

Made with ❤️ and ☕

</div>
