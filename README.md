# 🏫 Les Amis de Marcel — Site web

> Site officiel de l'association de parents d'élèves de l'école Marcel Pagnol  
> à **Notre-Dame-des-Landes (44130)**, section de l'**Amicale Laïque**.

---

## 📋 Sommaire

- [Présentation](#-présentation)
- [Structure du site](#-structure-du-site)
- [Stack technique](#-stack-technique)
- [Organisation du dépôt](#-organisation-du-dépôt)
- [Développement local](#-développement-local)
- [Administration](#-administration)
- [Contact](#-contact)

---

## 🌟 Présentation

**Les Amis de Marcel** est une association de parents d'élèves (APE) engagée aux côtés de l'école Marcel Pagnol. Elle organise tout au long de l'année scolaire des événements festifs, des collectes de fonds et des activités pour soutenir les projets pédagogiques et améliorer le quotidien des enfants.

| 📍 Lieu | École Marcel Pagnol, Notre-Dame-des-Landes (44130) |
|---|---|
| 📧 Contact | contact@lesamisdemarcel.fr |
| 📅 Agenda | [Nextcloud Calendar](https://nxtcld.lesamisdemarcel.fr/apps/calendar/p/yFFj9TrYN2R8oCkT) |

---

## 🗂️ Structure du site

Le site est une **page unique (SPA-like)** organisée en sections :

| Section | Ancre | Description |
|---|---|---|
| 🏠 Accueil | `#accueil` | Hero avec présentation et appels à l'action |
| 🤝 Association | `#association` | Qui sommes-nous, nos valeurs |
| 📰 Actualités | `#actualites` | Dernières nouvelles de l'association (3–4 fois/an) |
| 📅 Agenda | `#agenda` | Prochains événements (fichier iCal synchronisé depuis Nextcloud) |
| 🎉 Activités | `#activites` | Kermesse, spectacles, sorties, collectes |
| 🖼️ Galerie | `#galerie` | Photos des événements de l'année |
| 💰 Les fonds | `#fonds` | À quoi servent les fonds collectés + bilan annuel |
| 🎫 Adhésion | `#adhesion` | Comment rejoindre l'association |
| ✉️ Contact | `#contact` | Formulaire de contact et coordonnées |

---

## 🛠️ Stack technique

Le site est volontairement **léger et sans dépendances externes** côté JavaScript :

| Composant | Technologie |
|---|---|
| Structure | HTML5 sémantique |
| Style | CSS3 (mobile-first, variables CSS, animations) |
| Interactivité | Vanilla JavaScript (ES6+) |
| Polices | [Google Fonts](https://fonts.google.com/) — *Playfair Display* & *Lato* |
| Calendrier | Flux iCal public Nextcloud |
| Hébergement | Fichiers statiques |

**Palette de couleurs :**

| Rôle | Couleur |
|---|---|
| Primaire | `#2563a8` (bleu) |
| Secondaire | `#f59e2e` (ambre) |
| Accent | `#f97316` (orange) |
| Fond | `#ede9e0` (beige chaud) |

---

## 📁 Organisation du dépôt

```
www-lesamisdemarcel/
├── agendas/
│   └── calendar.ics    # Agenda synchronisé depuis Nextcloud par GitHub Actions
├── index.html          # Page principale du site
├── css/
│   └── style.css       # Feuille de style (mobile-first)
├── admin/
│   └── index.html      # Interface d'administration (protégée)
├── config.json         # Configuration du site (maxEvents, URLs Nextcloud)
├── README.md           # Ce fichier
└── ROADMAP.md          # Évolutions et ajouts de contenu prévus
```

---

## 💻 Développement local

Aucun outil de build n'est requis. Il suffit d'ouvrir `index.html` dans un navigateur ou de servir le dossier via un serveur local :

```bash
# Avec Python 3
python3 -m http.server 8080

# Avec Node.js (npx)
npx serve .
```

Puis ouvrir [http://localhost:8080](http://localhost:8080).

---

## 🔐 Administration

Une interface d'administration est accessible via `/admin/`. Elle est protégée par mot de passe et permet de gérer les contenus du site.

### Réglages disponibles

| Réglage | Description |
|---|---|
| Nombre d'événements à afficher | Workflow GitHub Actions « Update site config » — sauvegardé dans `config.json` du dépôt |

> **Note :** Le fichier `config.json` est versionné dans le dépôt Git. Il contient :
> - `maxEvents` — nombre d'événements à afficher (1–10)
> - `calendarViewUrl` — lien public vers le calendrier Nextcloud (affichage)
> - `calendarIcalUrl` — lien iCal utilisé par la synchronisation GitHub Actions
>
> Pour modifier `maxEvents`, déclenchez le workflow **« Update site config »** depuis
> [GitHub Actions](https://github.com/lepekinoi/www-lesamisdemarcel/actions/workflows/update-config.yml)
> (bouton *Run workflow*, choix de la valeur 1–10). Le changement est effectif sur tous les navigateurs
> dès le prochain chargement du site.
> Les autres champs (`calendarViewUrl`, `calendarIcalUrl`) sont fixes et modifiables directement dans le fichier.

---

## 📬 Contact

Pour toute question sur le site ou l'association :

- **Email :** [contact@lesamisdemarcel.fr](mailto:contact@lesamisdemarcel.fr)
- **Adresse :** École Marcel Pagnol, Notre-Dame-des-Landes (44130)

---

*Fait avec ❤️ à Notre-Dame-des-Landes — © 2025 Les Amis de Marcel*
