# 🗺️ Roadmap — Les Amis de Marcel

Propositions d'évolutions de contenu pour enrichir le site, informer les familles et renforcer la vie de l'association, **sans surcharger la page**.

> 💡 Priorité donnée à des ajouts simples, utiles et faciles à maintenir.

---

## ✅ Déjà en place

- [x] Page d'accueil avec présentation de l'association
- [x] Agenda dynamique (flux iCal Nextcloud)
- [x] Présentation des activités (kermesse, sorties, collectes…)
- [x] Section "Les fonds" — à quoi servent les fonds collectés
- [x] Formulaire de contact
- [x] Interface d'administration
- [x] Synchronisation automatique de l'agenda Nextcloud via GitHub Actions (toutes les 30 min)
- [x] Rechargement sans cache HTTP des événements (`cache: 'no-cache'`) — les titres modifiés dans Nextcloud sont toujours affichés immédiatement
- [x] Réglage « nombre d'événements à afficher » (1 à 10) dans l'interface d'administration
- [x] Section "Actualités" (3 dernières nouvelles de l'association, mises à jour 3–4 fois/an)
- [x] Galerie photos — 6 emplacements avec placeholders, prêts pour des photos Nextcloud
- [x] Bilan annuel — tableau des recettes et reversements par année scolaire
- [x] Section "Adhésion" — tarif, avantages, lien HelloAsso et formulaire de contact
- [x] URLs de l'agenda Nextcloud centralisées dans `config.json` (`calendarViewUrl`, `calendarIcalUrl`)
- [x] Code JavaScript commenté (JSDoc) sur toutes les fonctions du site et de l'admin

---

## 🚀 Évolutions prioritaires

### 1. 📸 Galerie photos — remplacement des placeholders

Remplacer les 6 placeholders emoji par de vraies photos hébergées sur Nextcloud :

- Modifier chaque `<div class="galerie-placeholder">` par une balise `<img>` avec l'URL Nextcloud
- Format recommandé : WebP ou JPEG, ratio 4/3, ~800 px de large
- Attribut `loading="lazy"` pour les performances

---

### 2. 📝 Section "Actualités" — mise à jour régulière

La section est en place. La mettre à jour 3–4 fois par an directement dans `index.html` :

---

### 5. 📣 Intégration réseaux sociaux (optionnel)

Si l'association crée une page Facebook ou Instagram :

- Ajouter des liens sociaux dans le footer et la section contact
- Intégrer un fil des derniers posts (widget léger) ou un lien vers la page

---

## 💡 Idées futures (moyen terme)

| Idée | Description |
|---|---|
| 🗳️ Compte-rendu d'AG | Publication du compte-rendu de l'assemblée générale annuelle (PDF) |
| 📆 Permanences | Indiquer les dates et lieux de permanences des membres du bureau |
| 🎒 Troc & partage | Mini-section "objets à donner / à récupérer" entre familles |
| 🤲 Bénévolat | Formulaire pour s'inscrire comme bénévole à un événement spécifique |
| 📰 Newsletter | Abonnement à une lettre d'info mensuelle (Brevo, Mailchimp…) |

---

## 🔧 Améliorations techniques

| Amélioration | Priorité | Statut |
|---|---|---|
| Soumission du formulaire de contact fonctionnelle (Formspree, Netlify…) | 🔴 Haute | ⏳ À faire |
| Ajout de balises Open Graph pour un meilleur partage sur les réseaux | 🟡 Moyenne | ✅ Fait |
| Ajout d'un favicon | 🟡 Moyenne | ✅ Fait |
| Politique de confidentialité (RGPD) si formulaire fonctionnel | 🔴 Haute | ✅ Fait |
| Rechargement sans cache HTTP du fichier iCal (`cache: 'no-cache'`) | 🔴 Haute | ✅ Fait |
| Commentaires JSDoc sur toutes les fonctions JS | 🟡 Moyenne | ✅ Fait |
| URLs Nextcloud centralisées dans `config.json` | 🟡 Moyenne | ✅ Fait |
| Suppression du CSS mort (règles `.join*` inutilisées) | 🟢 Basse | ✅ Fait |
| Optimisation des images (format WebP, lazy loading) | 🟢 Basse | ⏳ À faire |

---

*Roadmap évolutive — à revoir à chaque début d'année scolaire avec le bureau de l'association.*
