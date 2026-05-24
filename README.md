# 📦 Inventaire TMB - Scanner mobile

Web app de scan EAN pour faire l'inventaire physique de la boutique TMB.

## Fonctionnalités

- 📷 Scan caméra continu (EAN-13, EAN-8, UPC, Code-128)
- ⌨️ Saisie manuelle si EAN illisible
- 🔢 Compteur quantité avec boutons +/−
- 📝 Ajout d'un nom de produit (optionnel)
- 💾 Sauvegarde locale (localStorage) — persiste si on ferme l'app
- 🔍 Recherche dans la liste scannée
- ✏️ Édition et suppression possibles
- 📥 Export CSV (UTF-8 BOM, compatible Excel)
- 🔊 Bip + 📳 Vibration au scan réussi

## Déploiement GitHub Pages (5 min)

1. Crée un repo GitHub **public** (ex: `tmb-inventaire`)
2. Upload le fichier `index.html` à la racine
3. Settings → Pages → Source = `main` branch / `/ (root)`
4. Attends ~1 min, ton URL = `https://<ton-user>.github.io/tmb-inventaire/`
5. Ouvre cette URL dans Chrome/Safari sur ton smartphone
6. Au premier scan, autorise l'accès caméra

## Format CSV exporté

```
ean;qty;name;first_scan_iso;last_scan_iso
3700654291812;5;HP 303XL noir;2026-05-24T15:30:00.000Z;2026-05-24T15:42:11.000Z
```

Encodage : UTF-8 avec BOM, séparateur `;` (compatible Excel français).

## Workflow inventaire TMB

1. Maxime/regis ouvre l'app sur le smartphone
2. "▶ Démarrer le scan" → autorise la caméra
3. Pour chaque produit en rayon : scan → modifier qty → ✓ OK
4. Si EAN illisible : "Saisie manuelle" + tape l'EAN à la main
5. À la fin : "📥 Export CSV" → fichier téléchargé sur le smartphone
6. Transfert le CSV vers le PC (email, USB, drive)
7. Côté PC, on traite l'inventaire pour nettoyer la base Hiboutik

## Sécurité

- L'app fonctionne **100% côté navigateur**
- Aucune donnée envoyée à un serveur
- Tout reste en local (localStorage du téléphone)
- Pas de credentials Hiboutik dans le code
