# 🏆 Générateur d'Attestations de Formation

Un générateur automatisé d'attestations de formation en PDF utilisant JavaScript et jsPDF. Cette application web permet de générer en masse des attestations personnalisées à partir d'images de template et d'une liste de participants.

## ✨ Fonctionnalités

- **Génération automatique** : Création en lot d'attestations personnalisées
- **Support multi-genre** : Templates différents pour Monsieur et Madame
- **Interface intuitive** : Interface web moderne avec barre de progression
- **Statistiques en temps réel** : Affichage du nombre total de participants par genre
- **Logs détaillés** : Suivi en temps réel du processus de génération
- **Export PDF** : Téléchargement automatique du fichier PDF final

## 📋 Prérequis

### Fichiers requis dans le même dossier :
- `attestation-generator.html` - Application principale
- `leadersnames.js` - Données des participants
- `Attestation Ngazidja Mr.png` - Template pour les hommes
- `Attestation Ngazidja Mme.png` - Template pour les femmes

### Navigateur web moderne supportant :
- Canvas API
- ES6 JavaScript
- Local file access

## 🚀 Installation et Utilisation

### 1. Préparation des fichiers

**Étape 1 :** Placez les templates d'attestation dans le dossier :
- `Attestation Ngazidja Mr.png` (pour les hommes)
- `Attestation Ngazidja Mme.png` (pour les femmes)

**Étape 2 :** Configurez vos données dans `leadersnames.js` :
```javascript
const leaders = {
  Ngazidja: {
    "Jean Dupont": "H",      // H ou M pour Homme/Monsieur
    "Marie Martin": "F",     // F pour Femme/Madame
    "Pierre Durand": "H",
    "Sophie Lefebvre": "F"
    // ... ajoutez vos participants
  }
};
```

### 2. Lancement de l'application

1. Ouvrez `attestation-generator.html` dans votre navigateur web
2. Vérifiez que les statistiques affichent le bon nombre de participants
3. Cliquez sur "📄 Générer le PDF des Attestations"
4. Attendez la fin de la génération
5. Le PDF sera téléchargé automatiquement

## ⚙️ Configuration

### Format des données (`leadersnames.js`)
```javascript
const leaders = {
  Ngazidja: {           // Région/Groupe
    "Nom Complet": "Genre"
  }
};
```

**Codes de genre acceptés :**
- `"H"` ou `"M"` : Homme/Monsieur (utilise le template Mr.)
- `"F"` : Femme/Madame (utilise le template Mme.)

### Dimensions des templates
- **Format recommandé :** A4 paysage (1123 x 794 pixels)
- **Résolution :** 96 DPI minimum
- **Format :** PNG avec transparence supportée

### Position du nom sur le template
Le nom est automatiquement centré horizontalement à la position Y=415px. Pour ajuster cette position, modifiez la variable `nameY` dans le code JavaScript.

## 📊 Interface utilisateur

### Tableau de bord
- **Total des noms** : Nombre total de participants
- **Femmes (Mme.)** : Nombre de participantes féminines
- **Hommes (Mr.)** : Nombre de participants masculins

### Barre de progression
- Progression en temps réel (pourcentage et nombre)
- Détails de l'opération en cours
- Logs horodatés de chaque étape

## 🛠️ Technologies utilisées

- **HTML5** : Structure et Canvas API
- **CSS3** : Interface moderne avec dégradés et animations
- **JavaScript ES6** : Logique de génération
- **jsPDF** : Génération de fichiers PDF
- **Canvas API** : Manipulation d'images et rendu

## 📁 Structure du projet

```
attestation/
├── attestation-generator.html    # Application principale
├── leadersnames.js              # Données des participants
├── Attestation Ngazidja Mr.png  # Template pour hommes
├── Attestation Ngazidja Mme.png # Template pour femmes
└── README.md                    # Documentation
```

## 🔧 Personnalisation

### Modifier les couleurs
Les couleurs principales peuvent être modifiées dans le CSS :
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

### Changer la police du nom
Modifiez la propriété font dans le JavaScript :
```javascript
ctx.font = 'bold 36px Times, serif';
ctx.fillStyle = '#8B4513'; // Couleur
```

### Ajuster la position du nom
Modifiez les coordonnées dans la fonction `generatePDF()` :
```javascript
const nameX = pageWidth / 2;  // Position horizontale (centré)
const nameY = 415;            // Position verticale
```

## ❗ Résolution de problèmes

### Erreurs courantes

**"Les images ne sont pas encore chargées"**
- Vérifiez que les fichiers PNG sont dans le même dossier
- Vérifiez l'orthographe exacte des noms de fichiers

**"leadersnames.js non trouvé"**
- Assurez-vous que le fichier `leadersnames.js` est présent
- Vérifiez la syntaxe JavaScript du fichier

**PDF vide ou noms mal positionnés**
- Vérifiez les dimensions des images templates
- Ajustez les coordonnées `nameX` et `nameY`

### Conseils d'optimisation

- **Images lourdes :** Optimisez vos templates PNG (taille < 2MB recommandée)
- **Grand nombre de participants :** Le processus peut prendre quelques minutes
- **Navigation :** Ne fermez pas l'onglet pendant la génération

## 📄 Format de sortie

- **Nom du fichier :** `Attestations_Formation_YYYY-MM-DD.pdf`
- **Format :** PDF multi-pages (une attestation par page)
- **Orientation :** Paysage (A4)
- **Qualité :** Haute définition adaptée à l'impression

## 🤝 Contribution

Pour améliorer cette application :
1. Testez avec différents formats d'images
2. Proposez des améliorations d'interface
3. Optimisez les performances pour de gros volumes
4. Ajoutez des fonctionnalités (dates, signatures, etc.)

## 📞 Support

En cas de problème :
1. Vérifiez la console du navigateur (F12) pour les erreurs
2. Consultez les logs dans l'interface de l'application
3. Testez avec un petit échantillon de données d'abord

## 📜 Licence

Ce projet est libre d'utilisation pour des fins éducatives et non commerciales.

---

*Dernière mise à jour : Août 2025*
