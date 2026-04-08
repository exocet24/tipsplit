# TipSplit

Calculateur de pourboire et partage de facture — Simple, rapide, sans pub, offline.

## Fonctionnalités

- ✅ Calcul de pourboire avec présets (10%, 15%, 18%, 20%, 25%)
- ✅ Pourcentage personnalisable
- ✅ Partage de facture jusqu'à 99 personnes
- ✅ Arrondir vers le haut ou le bas
- ✅ Historique des 20 derniers calculs
- ✅ Copier le résultat
- ✅ Sauvegarde du pourboire préféré
- ✅ 100% offline
- ✅ Aucune pub, aucun tracking

## Guide de pourboire

| Service | Pourboire suggéré |
|---------|-------------------|
| Service OK | 10-12% |
| Bon service | 15% |
| Excellent | 18-20% |
| Exceptionnel | 25%+ |

## Publication sur Google Play Store

### 1. Compte développeur

1. Va sur [Google Play Console](https://play.google.com/console)
2. Crée un compte (25$ USD one-time)
3. Complète la vérification d'identité

### 2. Héberger en HTTPS

**Option A — GitHub Pages (gratuit)**
```bash
# Crée un repo et push les fichiers
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/tonuser/tipsplit.git
git push -u origin main
# Puis active GitHub Pages dans Settings
```

**Option B — Ton serveur**
- Upload dans `/var/www/tipsplit`
- Configure Nginx + Let's Encrypt

### 3. Générer l'AAB avec PWABuilder

1. Va sur https://pwabuilder.com
2. Entre ton URL HTTPS
3. "Package for stores" → "Android"
4. Configure:
   - Package ID: `ca.konstruct.tipsplit`
   - App name: `TipSplit`
   - Version: `1.0.0`
5. Télécharge l'AAB

### 4. Assets Play Store

**Requis:**
- [ ] 2+ screenshots (1080x1920)
- [ ] Icône 512x512 (✅ déjà fait)
- [ ] Description courte
- [ ] Description complète
- [ ] URL politique de confidentialité

**Description courte (max 80 car.):**
```
Calculateur de pourboire et partage de facture. Simple et sans pub.
```

**Description complète:**
```
TipSplit — le calculateur de pourboire le plus simple et le plus rapide.

✓ Calcul instantané du pourboire
✓ Partage de facture entre amis
✓ Présets rapides: 10%, 15%, 18%, 20%, 25%
✓ Arrondir vers le haut ou le bas
✓ Historique de vos calculs
✓ Fonctionne hors ligne
✓ Aucune publicité
✓ Aucune collecte de données

Parfait pour:
• Restaurant, bar, café
• Sortie entre amis
• Calculer le pourboire exact
• Partager équitablement la facture

Marre des apps de pourboire bourrées de pubs? TipSplit est là pour vous.

Simple. Rapide. Privé. Gratuit.

Développé au Québec 🍁
```

### 5. Soumettre

1. Play Console → Créer une application
2. Catégorie: Finance ou Outils
3. Upload le fichier AAB
4. Ajoute les screenshots
5. Configure privacy policy URL
6. Soumets pour review (1-3 jours)

## Structure des fichiers

```
tipsplit/
├── index.html              # App principale
├── privacy.html            # Politique de confidentialité
├── manifest.json           # Config PWA
├── sw.js                   # Service Worker
├── icon.svg                # Icône vectorielle
├── icon-192.png            # Icône standard
├── icon-512.png            # Icône haute-res
├── icon-maskable-192.png   # Icône Android 8+
├── icon-maskable-512.png   # Icône Android 8+ haute-res
└── README.md               # Ce fichier
```

## Test local

```bash
cd /chemin/vers/tipsplit
python3 -m http.server 8080
```

Ouvre `http://IP_LOCAL:8080` sur ton phone.

**Installation PWA en HTTP:**
1. Chrome → `chrome://flags`
2. "Insecure origins treated as secure" → ajoute `http://IP:8080`
3. Relaunch → Menu ⋮ → "Installer l'application"

## Stack technique

- HTML/CSS/JS vanilla
- Zéro dépendance
- localStorage pour préférences et historique
- Service Worker cache-first
- Compatible Android 5+, iOS 11.3+

## Améliorations futures possibles

- [ ] Mode sombre/clair
- [ ] Partage inégal (quelqu'un paie plus)
- [ ] Taxes incluses/exclues
- [ ] Widget Android
- [ ] Export des calculs

## Licence

© 2025 Konstruct / Atelier. Tous droits réservés.
