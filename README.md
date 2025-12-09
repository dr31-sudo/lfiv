# 🎄 LFIV – Soirée de Noël (QR & Scan)

Système complet pour la **gestion des accès familles** à la soirée de Noël du  
**Lycée Français International de Vientiane (LFIV)**.

- Envoi aux familles d’un **lien unique** + QR : `https://noel.lfiv.org/?c=XXXXX`
- Affichage d’une **carte d’invitation premium** (FR / LA / EN)
- **Scanner d’entrées** le soir de la fête, avec :
  - validation / rejet des codes
  - détection des doubles scans
  - export CSV des résultats (offline, localStorage)

---

## 🏗 Architecture

- **Google Sheets**
  - Génère les QR pour chaque famille
  - Génère les liens WhatsApp avec le bon code
- **GitHub Pages**
  - `index.html` → carte QR pour les familles
  - `scan.html` → scanner d’entrées pour l’équipe à l’entrée
- **Cloudflare**
  - DNS + SSL + cache pour `noel.lfiv.org`
  - Option de bypass cache pour `scan.html` en cas de mise à jour

---

## 📁 Structure du dépôt

```text
lfiv-noel/
├── index.html   # Page publique : carte d'invitation + QR (parents)
├── scan.html    # Page interne : scanner d'entrées + CSV (équipe LFIV)
├── CNAME    # CNAME DNS
└── README.md

## 📝 Licence

Projet interne LFIV – usage réservé au Lycée Français International de Vientiane.
Ne pas réutiliser tel quel en production sans adapter la sécurité, les textes et la gestion des données.
