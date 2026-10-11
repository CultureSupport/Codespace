================================================================================
  MULTI-TECHNOLOGY CODESPACE & TELEMETRY HUB - README.md
================================================================================

  Velkommen til det fullautomatiserte utviklingsmiljøet for GitHub Codespaces.
  Denne guiden viser hvordan du setter opp, konfigurerer og kjører de ulike
  teknologiene i container-miljøet.

================================================================================
  1. HURTIGSTART (CODESPACE INSTALLASJON)
================================================================================

  [1] Gå til repositoryets Hovedside (GitHub).
  [2] Klikk på den grønne "<> Code"-knappen øverst til høyre.
  [3] Velg fanen "Codespaces".
  [4] Klikk "Create codespace on main".
  [5] Vent til containeren byggerferdig og postCreateCommand kjører automatisk.

================================================================================
  2. MILJØ OG CONTAINER (.DEVCONTAINER)
================================================================================

  Hele utviklingsmiljøet kjører i en isolert Linux-container.
  Konfigurasjonen finnes i .devcontainer/devcontainer.json:

  +------------------------------------------------------------------------+
  | .devcontainer/devcontainer.json (Eksempel)                             |
  +------------------------------------------------------------------------+
  | {                                                                      |
  |   "name": "Full-Stack Telemetry Codespace",                            |
  |   "image": "mcr.microsoft.com/devcontainers/universal:2",                |
  |   "customizations": {                                                  |
  |     "vscode": {                                                        |
  |       "extensions": [                                                  |
  |         "dbaeumer.vscode-eslint",                                      |
  |         "esbenp.prettier-vscode",                                      |
  |         "tamasfe.even-better-toml",                                    |
  |         "redhat.vscode-yaml",                                          |
  |         "ms-python.python"                                             |
  |       ]                                                                |
  |     }                                                                  |
  |   },                                                                   |
  |   "postCreateCommand": "npm install && pip install -r requirements.txt"|
  | }                                                                      |
  +------------------------------------------------------------------------+

================================================================================
  3. KONFIGURASJONSFORMATER (YAML, JSON, TOML)
================================================================================

  Systemet leser automatisk konfigurasjoner ved oppstart:
  
  * YAML (.yaml)  : Brukes til CI/CD-flyter, workflows og orkestrering.
  * JSON (.json)  : Standardiserte datautvekslingsstrukturer og oppsett.
  * TOML (.toml)  : Strukturerte oppsett for telemetri- og backend-tjenester.

  Eksempel på TOML-struktur (config.toml):
  [server]
  host = "0.0.0.0"
  port = 8080

================================================================================
  4. KJØRING AV ULIKE TEKNOLOGIER I CODESPACE
================================================================================

  A. Node.js & NPM (Backend / Verktøy)
     $ npm install
     $ npm run start

  B. React (Frontend / Dashbord)
     $ npm run react:dev

  C. Python (Skripting og Dataanalyse)
     $ pip install -r requirements.txt
     $ python main.py

================================================================================
  5. TEKNOLOGIOVERSIKT
================================================================================

  +-----------------------+-----------------------------+--------------------+
  | Komponent             | Teknologi                   | Status             |
  +-----------------------+-----------------------------+--------------------+
  | Container & Miljø     | Docker / Universal Dev      | [Aktiv / Klar]     |
  | Konfigurasjon         | YAML, JSON, TOML            | [Automatisk]       |
  | Backend / Pakkestyring| Node.js & NPM               | [Klar]             |
  | Frontend              | React                       | [Klar]             |
  | Skripting             | Python                      | [Klar]             |
  +-----------------------+-----------------------------+--------------------+

================================================================================





Her er en komplett og utvidet README.md-mal som dekker alle de spesifikke teknologiene og formatene (YAML, JSON, TOML, NPM, React, Python, Node, samt fullt miljø- og container-oppsett for GitHub Codespaces):
🚀 Multi-Technology Codespace & Telemetri Hub
Velkommen til det fullautomatiserte utviklingsmiljøet for GitHub Codespaces. Dette repositoryet integrerer lavnivå-telemetri, moderne web-grensesnitt (React/Node) og skripting (Python) med sømløs håndtering av YAML, JSON og TOML.
🛠️ Hurtigstart (Codespace Installasjon)
Miljøet klargjøres automatisk i skyen ved oppstart.
 * Klikk på <> Code øverst til høyre i repositoryet.
 * Velg Codespaces-fanen og klikk Create codespace on main.
 * Vent til containeren byggerferdig og postCreateCommand kjører automatisk.
📂 Konfigurasjonsformater (YAML, JSON, TOML)
Miljøet overvåker og leser konfigurasjoner automatisk ved oppstart:
 * YAML (.github/workflows/ eller config.yaml): Brukes til CI/CD-flyter og orkestrering.
 * JSON (config.json): Standardiserte datautvekslingsstrukturer og applikasjonsinnstillinger.
 * TOML (config.toml): Strukturerte oppsett for telemetri- og backend-tjenester.
⚙️ Kjøring av Ulike Teknologier
Hver teknologistakk har egne automatiserte oppstartsrutiner inne i Codespace-terminalen:
1. Node.js & NPM
For backend-tjenester og verktøy.
# Installer avhengigheter
npm install

# Start utviklingsserver / tjeneste
npm run start

2. React (Frontend / Dashboard)
For sanntids visualisering og telemetri-paneler.
# Gå til frontend-katalogen (eller kjør direkte fra rot)
npm run react:dev

3. Python
For dataanalyse, skripting og automatisering.
# Installer Python-avhengigheter
pip install -r requirements.txt

# Kjør hovedskript / telemetri-parser
python main.py

🐳 Container & Miljø (.devcontainer)
Hele miljøet kjører i en isolert Linux-container definert i .devcontainer/devcontainer.json. Dette sikrer identiske vilkår for alle utviklere.
Eksempel på .devcontainer/devcontainer.json
{
  "name": "Full-Stack Telemetry Codespace",
  "image": "mcr.microsoft.com/devcontainers/universal:2",
  "customizations": {
    "vscode": {
      "extensions": [
        "dbaeumer.vscode-eslint",
        "esbenp.prettier-vscode",
        "tamasfe.even-better-toml",
        "redhat.vscode-yaml",
        "ms-python.python"
      ]
    }
  },
  "postCreateCommand": "npm install && pip install -r requirements.txt && echo 'Codespace-miljøet er klart!'",
  "remoteUser": "vscode"
}

📋 Oversikt over Teknologimiljøet
| Komponent | Teknologi | Automatisk Håndtering |
|---|---|---|
| Container | Docker / Universal Devcontainer | 🟢 Full isolasjon og verktøypakke |
| Konfigurasjon | YAML, JSON, TOML | 🟢 Automatisk validering ved oppstart |
| Backend / CLI | Node.js / NPM | 🟢 Pakkestyring via npm install |
| Frontend | React (ESM / Vite) | 🟢 Interaktivt dashbord |
| Skripting | Python | 🟢 Virtuelt miljø / pip-integrasjon |


----------


