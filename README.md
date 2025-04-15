
# 📚 Application de gestion académique – Sécurisée avec Flask et MySQL

## 📝 Description du projet

Cette application web a été développée dans le cadre d’un projet de sécurité des bases de données. Elle permet de gérer les utilisateurs d’une institution universitaire (étudiants, enseignants, secrétaires), les cours, les inscriptions, les notes, et les interactions pédagogiques (exercices, questions, etc.).

Le projet illustre l’intégration de bonnes pratiques de développement et de sécurité, notamment la protection contre l’injection SQL, la gestion des rôles utilisateurs, l’optimisation des performances, et le contrôle rigoureux des accès.

---

## 🚀 Installation et exécution

### 1. Cloner le dépôt

```bash
git clone <https://github.com/Derbyneon/tp_securite_de_base_de_donnees.git
cd tp_securite_de_base_de_donnees
```

### 2. Créer et remplir la base de données

Avant toute exécution, vous devez créer la base de données et l’alimenter avec les tables et les données initiales :

```bash
mysql -u <root -p gestion_utilisateur database.sql
```

> 🛡️ Assurez-vous que votre serveur MySQL est en marche et que les identifiants sont correctement renseignés dans la configuration Flask.

### 3. Installer les dépendances

Créez un environnement virtuel (recommandé) puis installez les dépendances :

```bash
python -m venv venv
source venv/bin/activate   # sous Linux/macOS
venv\Scripts\activate      # sous Windows

pip install -r requirements.txt
```

### 4. Lancer l’application

Une fois la base de données en place et les dépendances installées :

```bash
python run.py
```

L'application sera accessible sur [http://localhost:5000](http://localhost:5000)

---

## 🔐 Fonctionnalités de sécurité

- Authentification sécurisée via Flask-Login
- Rôles et permissions : Étudiant, Enseignant, Secrétaire
- Protection contre les injections SQL via les requêtes paramétrées
- Utilisation de tokens CSRF dans les formulaires
- Gestion des accès aux routes selon le rôle
- Logs des requêtes SQL activés
- Structure de la base normalisée, avec indexation et optimisation

---

## 🛠️ Technologies utilisées

- **Backend :** Flask (Python)
- **Base de données :** MySQL
- **Frontend :** HTML / CSS (Bootstrap ou custom)
- **ORM (optionnel) :** SQLAlchemy (intégrable)
- **Sécurité :** Flask-Login, CSRF protection

---

## 👤 Rôles et accès

| Rôle        | Permissions principales |
|-------------|--------------------------|
| Étudiant    | Consulter les cours, s’inscrire, voir ses notes, déposer des exercices |
| Enseignant  | Gérer les séances, noter les étudiants |
| Secrétaire  | Gérer les cours, enseignants, inscriptions |

---

## 📁 Arborescence

```
├── run.py
├── requirements.txt
├── database.sql
├── app/
│   ├── __init__.py
│   ├── routes/
│   ├── templates/
│   ├── static/
│   ├── models/
│   └── utils/
