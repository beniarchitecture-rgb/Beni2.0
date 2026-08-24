# PRD — BENI Architecture (site vitrine)

## Problem statement (original)
"Créer une page d'atterrissage : https://github.com/Johnnyxtr/Beni-archi2.0.git"
Le dépôt GitHub étant privé (404), l'utilisateur a fourni le projet complet en zip. Choix confirmés : restaurer le site complet tel quel ; formulaire de contact = stockage en base uniquement (pas d'email).

## Architecture
- Frontend: React 19 + CRACO, Tailwind, shadcn/ui, react-router-dom v7, three.js + @react-three/fiber (héros 3D), GSAP, custom cursor, i18n FR/EN maison.
- Backend: FastAPI (routes préfixées /api), Motor/MongoDB.
- Contenu centralisé dans `frontend/src/data/siteConfig.js` (projets, i18n, réseaux sociaux).

## Personas
- Client potentiel (institutionnel/résidentiel/commercial) cherchant un cabinet d'architecture en Côte d'Ivoire.
- Visiteur découvrant le portfolio et prenant contact.

## Core requirements
- Site multi-pages bilingue FR/EN (Vision, Portfolio, Architecture, Développement, Construction, Actualités, Contact, détail projet).
- Héros animé (reveal masqué, compteurs, backdrop WebGL), reveals au scroll.
- Formulaire de contact -> POST /api/contact (persistance MongoDB).

## Implemented (2026-08-24)
- Restauration complète du projet depuis le zip dans /app.
- Installation deps 3D/anim: three, @react-three/fiber, gsap (drei retiré: incompatible Node 20).
- Backend server.py (endpoints /api/, /api/status, /api/contact GET+POST) — vérifié via curl (POST persiste).
- Frontend compilé (1 warning eslint non bloquant). Home vérifiée par screenshot: héros + portfolio OK.

## Backlog / remaining (P1/P2)
- P2: og:image pointe vers un ancien domaine preview (beni-preview...) — cosmétique/SEO.
- P2: warning eslint useEffect dep dans HomePage.jsx.
- P1 (si demandé): envoi email des messages de contact (Resend).

## Notes
- Pas d'authentification dans ce projet (aucun credential à gérer).
