# 🤖 Maskinlesbar Codespace & Telemetri Hub (`README.md`)

---
## [METADATA]
- **Project:** Multi-Technology Codespace & Telemetry Hub
- **Target Platform:** GitHub Codespaces
- **Supported Formats:** YAML, JSON, TOML
- **Supported Frameworks:** React, Node.js, Python
- **Environment:** Containerized Linux (Universal Devcontainer)
---

## 1. 🛠️ Hurtigstart (Codespace Installasjon)
For å starte miljøet programmatisk eller via web:
1. Naviger til repositoryets hovedside på GitHub.
2. Klikk **`<> Code`** -> **Codespaces** -> **`Create codespace on main`**.
3. Vent til containeren byggerferdig (`postCreateCommand` utføres automatisk).

---

## 2. 🐳 Container & Miljø (`Codespace Container & Miljø`)
Utviklingsmiljøet defineres i `.devcontainer/devcontainer.json`:

```json
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
  "postCreateCommand": "npm install && pip install -r requirements.txt",
  "remoteUser": "vscode"
}
```

---

## 3. 📂 Konfigurasjonsformater (YAML, JSON, TOML)
Parseres og valideres automatisk ved oppstart.

### Eksempel: TOML-konfigurasjon (`config.toml`)
```toml
[server]
host = "0.0.0.0"
port = 8080
mode = "deterministic"

[telemetry]
buffer_size = 4096
protocol = "modbus-tcp"
```

---

## 4. ⚙️ Kjøring av Ulike Teknologier

### A. Node.js & NPM (`Codespace Node` / `Codespace NPM`)
```bash
npm install
npm run start
```

### B. React (`Codespace React`)
```bash
npm run react:dev
```

### C. Python (`Codespace Python`)
```bash
pip install -r requirements.txt
python main.py
```

---