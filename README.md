# CTF CyberCaen

Plateforme CTF communautaire - [ctf.cybercaen.fr](https://ctf.cybercaen.fr)

## Presentation

CyberCaen est une plateforme CTF (Capture The Flag) destinee aux etudiants et passionnes de cybersecurite. Les challenges sont classes par categorie et difficulte, avec un systeme de progression et de roles Discord.

## Categories

| Categorie | Description |
|-----------|-------------|
| `crypto/` | Cryptographie, chiffrement, encodage |
| `linux/` | Administration systeme, privilege escalation |
| `web/` | Vulnerabilites web (XSS, SQLi, SSRF...) |
| `forensics/` | Analyse de fichiers, memoire, reseau |
| `reverse/` | Reverse engineering, analyse de binaires |
| `misc/` | OSINT, steganographie, divers |

## Structure d'un challenge

```text
categorie/nom-challenge/
├── Dockerfile        # Environnement Docker (si terminal)
├── challenge.json    # Metadata du challenge
├── files/            # Fichiers fournis aux participants
└── writeup.md        # Solution (optionnel, PR separee)
```

### challenge.json

```json
{
  "title": "Nom du Challenge",
  "slug": "nom-challenge",
  "description": "Description courte du challenge",
  "category": "crypto",
  "difficulty": "easy",
  "points": 50,
  "flag": "FLAG{exemple}",
  "hint": "Un indice pour aider",
  "cipher_text": "Texte ou enigme a resoudre",
  "has_terminal": false,
  "author": "pseudo"
}
```

## Contribuer

### 1. Fork et clone

```bash
git clone https://github.com/TON_USERNAME/ctf.cybercaen.fr.git
cd ctf.cybercaen.fr
```

### 2. Cree ton challenge

```bash
mkdir -p crypto/mon-challenge/files
```

### 3. Ajoute les fichiers requis

- `challenge.json` (obligatoire)
- `Dockerfile` (si challenge avec terminal)
- `files/` (fichiers donnes aux joueurs)

### 4. Teste localement

```bash
cd crypto/mon-challenge
docker build -t test-mon-challenge .
docker run -it --rm test-mon-challenge
```

### 5. Pull Request

```bash
git add .
git commit -m "Add: crypto/mon-challenge"
git push origin main
```

Puis ouvre une PR sur le repo principal.

## Niveaux de difficulte

| Niveau | Points | Description |
|--------|--------|-------------|
| easy | 20-50 | Debutant, introduction aux concepts |
| medium | 50-100 | Intermediaire, necessite des recherches |
| hard | 100-200 | Avance, techniques complexes |

## Regles

- Flag au format `FLAG{...}`
- Pas de contenu offensant
- Challenge testable avant soumission
- Documentation claire
- Les writeups doivent etre dans une PR separee

## Stack technique

| Composant | Technologie |
|-----------|-------------|
| Backend | Python / FastAPI |
| Database | SQLite |
| Auth | Discord OAuth2 |
| Containers | Docker + ttyd |
| Reverse Proxy | Nginx |

## Communaute

- **Discord** : [discord.gg/PtGJeV5Rra](https://discord.gg/PtGJeV5Rra)
- **Site** : [cybercaen.fr](https://cybercaen.fr)
- **CTF** : [ctf.cybercaen.fr](https://ctf.cybercaen.fr)

### Roles Discord

| Role | Points requis |
|------|---------------|
| Debutant | 10 |
| Initie | 50 |
| Hacker | 150 |
| Elite | 300 |

## Licence

MIT - Contributions bienvenues !
