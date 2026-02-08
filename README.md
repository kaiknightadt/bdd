# BDD — Board de Décision Digitale

Un board de conseillers virtuels propulsé par l'IA. Soumettez votre dilemme à des personnalités historiques, contemporaines et fictives — et recevez leurs perspectives uniques en temps réel.

## 🚀 Fonctionnalités

- **22 conseillers** aux personnalités distinctes (Gandhi, Steve Jobs, Beyoncé, Luffy...)
- **Streaming en temps réel** — chaque conseiller répond mot par mot
- **Résumé automatique** en une phrase par conseiller
- **Rapport de synthèse** qui croise toutes les perspectives
- **Interface dark luxury** avec sélection visuelle des conseillers

## 📁 Structure du projet

```
bdd/
├── app.py                      # Backend Flask + 22 system prompts
├── requirements.txt
├── Procfile                    # Config Render/Gunicorn
├── .env.example
├── .gitignore
├── templates/
│   └── index.html              # Interface de consultation (board)
├── static/
│   ├── img/                    # Portraits des conseillers
│   │   ├── gandhi.jpg
│   │   └── ...
│   └── landing/
│       ├── index.html          # Page de vente (landing)
│       └── demo.html           # Démo interactive
└── README.md
```

## 🔗 Routes

| URL | Description |
|-----|-------------|
| `/` | Landing page (page de vente) |
| `/demo` | Démonstration interactive |
| `/app` | L'application (board de consultation) |
| `/api/advisors` | Liste des conseillers (JSON) |
| `/api/consult` | Endpoint de consultation (POST, SSE) |
| `/api/report` | Rapport de synthèse (POST, SSE) |

## ⚙️ Installation locale

```bash
git clone https://github.com/ton-pseudo/bdd.git
cd bdd
pip install -r requirements.txt
cp .env.example .env
# Ajouter ta clé OpenAI dans .env
python app.py
```

Ouvrir http://localhost:5000

## 🌐 Déploiement sur Render

1. Push le repo sur GitHub
2. Créer un **Web Service** sur [render.com](https://render.com)
3. Connecter le repo GitHub
4. Settings :
   - **Build Command** : `pip install -r requirements.txt`
   - **Start Command** : `gunicorn app:app --bind 0.0.0.0:$PORT --timeout 120 --workers 2`
5. Ajouter la variable d'environnement `OPENAI_API_KEY`
6. Deploy 🚀

## 📜 Licence

Projet privé — tous droits réservés.
