# TP2 — Tests de contenus dynamiques avec Selenium

## Description

Ce projet automatise plusieurs scénarios de test sur le site de démonstration
The Internet by Herokuapp : [https://the-internet.herokuapp.com](https://the-internet.herokuapp.com)
à l’aide de **Python** et **Selenium WebDriver**.

L’objectif est de tester différents comportements dynamiques d’une application web :

- Contrôles dynamiques
- Chargement dynamique
- Notifications aléatoires
- Scroll infini

Le projet applique le modèle **Page Object Model (POM)** afin d’organiser le code de manière claire et maintenable.

---

# Technologies utilisées

- Python 3
- Selenium WebDriver
- Google Chrome
- ChromeDriver

---

# Structure du projet

```bash
project/
│
├── main.py
├── pages/
│   ├── base_page.py
│   ├── dynamic_controls_page.py
│   ├── dynamic_loading_page.py
│   ├── notification_page.py
│   └── infinite_scroll_page.py
└── README.md
```

---

# Fonctionnalités testées

## 1. Dynamic Controls

Page testée :
[https://the-internet.herokuapp.com/dynamic_controls](https://the-internet.herokuapp.com/dynamic_controls)

Scénarios automatisés :

- Vérification de la présence de la checkbox
- Suppression de la checkbox
- Vérification du message `"It's gone!"`
- Réapparition de la checkbox
- Vérification du message `"It's back!"`
- Activation d’un champ texte désactivé
- Saisie de texte dans le champ

---

## 2. Dynamic Loading

Page testée :
[https://the-internet.herokuapp.com/dynamic_loading/2](https://the-internet.herokuapp.com/dynamic_loading/2)

Scénarios automatisés :

- Vérification du bouton `Start`
- Déclenchement du chargement dynamique
- Attente de disparition du loader
- Vérification de l’affichage du texte `"Hello World!"`

---

## 3. Notification Message

Page testée :
[https://the-internet.herokuapp.com/notification_message_rendered](https://the-internet.herokuapp.com/notification_message_rendered)

Scénarios automatisés :

- Clic multiple sur `"Click here"`
- Vérification qu’un message est affiché
- Vérification que le message appartient aux valeurs attendues

---

## 4. Infinite Scroll

Page testée :
[https://the-internet.herokuapp.com/infinite_scroll](https://the-internet.herokuapp.com/infinite_scroll)

Scénarios automatisés :

- Vérification du contenu initial
- Scroll automatique vers le bas
- Vérification du chargement de nouveaux blocs de contenu

---

# Installation

## 1. Cloner le projet

```bash
git clone <https://github.com/Moha31170/TP2>
```

---

## 2. Créer un environnement virtuel (optionnel mais recommandé)

```bash
python -m venv venv
venv\Scripts\activate
```

---

## 3. Installer les dépendances

```bash
pip install selenium
```

---

# Prérequis

Avant d’exécuter le projet :

- Installer Google Chrome
- Installer ChromeDriver compatible avec votre version de Chrome
- Ajouter ChromeDriver au PATH système

Téléchargement :
[https://chromedriver.chromium.org/downloads](https://chromedriver.chromium.org/downloads)

---

# Exécution du projet

Lancer le fichier principal :

```bash
python main.py
```

---

# Résultats attendus

Le terminal affiche :

- Les étapes exécutées
- Les validations réussies
- Les éventuelles erreurs
- Un récapitulatif global des tests

Exemple :

```bash
============================================================
TP2 — TESTER DES CONTENUS DYNAMIQUES AVEC SELENIUM
============================================================

--- Partie 1 — Dynamic Controls ---
OK — Checkbox présente
OK — Checkbox supprimée
OK — Checkbox réapparue
...

============================================================
RÉSULTAT GLOBAL : TP2 RÉUSSI
============================================================
```

---

# Gestion des erreurs

En cas d’échec :

- Une capture d’écran est automatiquement générée
- Les screenshots sont stockés dans le dossier :

```bash
/screenshots
```

---

# Architecture du projet

Le projet suit le modèle **Page Object Model (POM)** :

- `BasePage` contient les méthodes génériques :
  - attentes Selenium
  - scroll
  - screenshots

- Chaque page métier possède :
  - ses locators
  - ses actions
  - ses vérifications

Cette approche permet :

- une meilleure lisibilité
- une maintenance simplifiée
- une réutilisation du code
