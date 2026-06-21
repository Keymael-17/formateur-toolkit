# Boîte à outils formation — PWA

Application web progressive pour formateurs.
**Patrick Paumard** · Fichet Security Solutions

## Outils inclus

1. **Chronomètre** — temps écoulé, start/pause/reset
2. **Minuteur** — compte à rebours avec alarme sonore et vibration
3. **Tirage au sort** — pioche un stagiaire au hasard dans une liste
4. **Formation de groupes** — répartit les stagiaires en N groupes équilibrés
5. **Présence** — marqueur de présence avec stats (présents / absents / total)
6. **Notes** — bloc-notes de session avec sauvegarde automatique

## Fonctionnalités

- **Installable** sur l'écran d'accueil (Android / iOS / desktop)
- **Fonctionne hors-ligne** une fois installée (service worker)
- **Sauvegarde locale** des listes, présences et notes (localStorage)
- **Vibration** à la fin du minuteur (mobile)
- **Couleurs Fichet** : cyan #0bbbef sur fond dark #151d23

## Déploiement GitHub Pages

1. Créer un repo GitHub (ex. `formateur-toolkit`).
2. Pousser les 5 fichiers à la racine :
   - `index.html`
   - `manifest.json`
   - `service-worker.js`
   - `icon-192.png`
   - `icon-512.png`
3. Activer GitHub Pages : Settings → Pages → Source : `main` / root.
4. Attendre 1 à 2 min, puis ouvrir l'URL `https://<user>.github.io/formateur-toolkit/` sur ton téléphone.
5. Sur Android (Chrome) : menu ⋮ → "Installer l'application".
   Sur iOS (Safari) : bouton partage → "Sur l'écran d'accueil".

## Test local rapide

```bash
cd formateur-toolkit
python3 -m http.server 8080
```

Puis ouvrir `http://localhost:8080` (le service worker exige HTTP, pas `file://`).

## Mise à jour du cache

À chaque modification du code, incrémenter `CACHE_NAME` dans `service-worker.js` (ex. `v1` → `v2`) pour forcer le refresh côté utilisateur.
