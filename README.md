# Google Dorks

Une **Google Dork** est une requête de recherche avancée utilisant les opérateurs spéciaux de Google pour affiner et cibler les résultats.

Contrairement à une recherche classique, un Google Dork permet de :

- 🎯 Filtrer par site ou domaine spécifique  
- 📂 Rechercher un type précis de fichier (PDF, XLS, DOC, etc.)  
- 📝 Chercher des mots dans le titre, l’URL ou le contenu d’une page  
- 📅 Filtrer par date  
- 🔎 Combiner plusieurs critères pour obtenir des résultats très ciblés  

En réalité, il s’agit d’une **utilisation avancée du moteur de recherche**. Elles permettent d'utiliser Google à son plein potetiel lorsque l'on effectue une recherche.

Les opérateurs avancés permettent de gagner du temps et d’obtenir des résultats beaucoup plus précis.  
C’est particulièrement utile pour :

- La recherche académique  
- La veille technologique  
- Le développement  
- L’analyse de marché

Par ailleurs, les Google Dorks sont largement utilisées dans l’OSINT pour trouver des documents publics, identifier des ressources exposées, collecter des informations ouvertes et accessibles légalement, etc.

Les comprendre permet de voir ce que Google indexe sur un site et permet donc de corriger les problèmes de configuration ou d'identifier les fichiers ou pages exposés par erreur. 

___
# Les Opérateurs
## Recherche de base

| Opérateur | Description | Exemple |
|-----------|------------|----------|
| `" "` | Recherche exacte | `"machine learning"` |
| `OR` | L’un ou l’autre | `python OR java` |
| `-` | Exclure un mot | `python -snake` |
| `*` | Joker (wildcard) | `"best * tools"` |
| `()` | Grouper les requêtes | `(python OR java) tutorial` |

## Filtrer par site / domaine

| Opérateur | Description | Exemple |
|-----------|------------|----------|
| `site:` | Limite à un domaine | `site:example.com` |
| `site:.gov` | Extension spécifique | `cybersecurity site:.gov` |
| `site:*.edu` | Sous-domaines | `research site:*.edu` |

## Types de fichiers

| Opérateur | Description | Exemple |
|-----------|------------|----------|
| `filetype:` | Type de fichier | `filetype:pdf` |
| `ext:` | Extension (équivalent) | `ext:xls budget` |

## Recherche dans l’URL

| Opérateur | Description | Exemple |
|-----------|------------|----------|
| `inurl:` | Mot dans l’URL | `inurl:login` |
| `allinurl:` | Tous les mots dans l’URL | `allinurl:admin panel` |

## Recherche dans le titre

| Opérateur | Description | Exemple |
|-----------|------------|----------|
| `intitle:` | Mot dans le titre | `intitle:"index of"` |
| `allintitle:` | Tous les mots dans le titre | `allintitle:login page` |

## Recherche dans le contenu

| Opérateur | Description | Exemple |
|-----------|------------|----------|
| `intext:` | Mot dans la page | `intext:"confidential"` |
| `allintext:` | Tous les mots | `allintext:internal use only` |

## Opérateurs avancés utiles

| Opérateur | Description | Exemple |
|-----------|------------|----------|
| `related:` | Sites similaires | `related:example.com` |
| `cache:` | Version en cache | `cache:example.com` |
| `define:` | Définition d’un mot | `define:cybersecurity` |
| `AROUND(X)` | Proximité entre mots | `python AROUND(3) security` |

## Filtrage par date

| Opérateur | Description | Exemple |
|------------|------------|----------|
| `before:` | Résultats publiés avant une date | `cybersecurity before:2022-01-01` |
| `after:` | Résultats publiés après une date | `AI after:2023-01-01` |

Format date : `YYYY-MM-DD`

## Intervalle numérique

| Opérateur | Description | Exemple |
|------------|------------|----------|
| `..` | Recherche dans une plage de nombres | `budget 1000..5000` |
| `..` | Intervalle d’années | `smartphone 2018..2022` |

## Google News spécifiques

| Opérateur | Description | Exemple |
|------------|------------|----------|
| `source:` | Source précise dans Google News | `AI source:bbc.com` |
| `location:` | Actualités par lieu | `cyberattack location:france` |

Fonctionne principalement dans Google News.

## Proximité entre mots

| Opérateur | Description | Exemple |
|------------|------------|----------|
| `AROUND(X)` | Deux mots proches de X mots | `python AROUND(3) security` |


___
# Exemples combinés

```bash
# Trouver des rapports PDF sur un site
site:example.com filetype:pdf "annual report"

# Pages de connexion
inurl:admin intitle:login

# Documents Excel sur domaine gouvernemental
filetype:xls "budget" site:.gov

# Pages contenant un terme sensible
intext:"internal use only" filetype:pdf

# Articles récents sur l'IA
AI after:2024-01-01 site:techcrunch.com

# Budget entre deux montants
"marketing budget" 5000..20000 filetype:pdf

# Terme précis proche d’un autre
"cloud" AROUND(5) "security"

# Trouver des profils Data Scientist Senior qui ont la compétence Dataiku sur Linkedin (et exclure ceux qui travaillent à Dataiku)
site:linkedin.com/in ("Senior Data Scientist") "Dataiku" -intitle:"Dataiku" -inurl:dataiku

```

___
# Sources et Sites


* Google Hacking Databse : https://www.exploit-db.com/google-hacking-database
* Awesome-Google-Dorks : https://github.com/Tobee1406/Awesome-Google-Dorks
* https://www.compass-security.com/fileadmin/Research/White_Papers/2017-01_osint_cheat_sheet.pdf
* Google recherche avancée : https://www.google.com/advanced_search



