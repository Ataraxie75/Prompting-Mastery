# Suivi du Hardening de Sécurité

Ce fichier trace l'implémentation des correctifs de sécurité suite à l'audit.

## Historique des Patchs

*En attente du premier patch...*

### [✅] Patch 1 : Configuration des Security Headers Vercel
- Fichier impacté : `vercel.json`
- Description : Ajout des en-têtes HTTP de sécurité globaux.
- Correctifs :
  - **CSP** (Content-Security-Policy) : Restreint l'exécution de scripts tiers.
  - **X-Frame-Options** : `DENY` pour bloquer le Clickjacking.
  - **HSTS** : Implémenté pour forcer le HTTPS strict.
  - **Permissions-Policy** : Accès matériels désactivés (caméra, gps).
- Validation : Aucune régression visuelle.

### [✅] Patch 2 : Sécurisation des Liens Externes
- Fichier impacté : `index.html`
- Description : Protection contre le reverse tabnabbing.
- Correctif : Ajout des attributs `target="_blank" rel="noopener noreferrer"` sur les deux boutons d'achat menant à Payhip.
- Validation : Les liens s'ouvrent en sécurité dans de nouveaux onglets.
