## Plugin-uri utile VsCode
>Pentru browser
- Live Server - valabil doar pentru Javascript pentru browser, click dreapta in editor, undeva in text, si apoi alegeti "Open with Live Server"
>Pentru server
- NodeJS exec - valabil doar pentru Javascript pe server,  se selecteaza codul care se doreste a fi rulat si apoi F8
- Quokka.js - in general pentru Javascript pe server, pentru un fisier js: Apasă Ctrl+K Q → Start on Current File (sau din Command Palette: Ctrl+Shift+P → Quokka: Start on Current File)


## Plugin-uri mai avansate
> Prettier si ESLint sunt foarte utile in conditiile unor proiect de dimensiuni mari pentru formatare cod si verificare corectitudine cod. Dezavantajul e ca pot interfera cu setarile VSCode sau chiar intre ele. Deci e util un ghid de instalare.

>1️⃣ Trebuie mai intai instalate extensiile din VSCode de la sectiunea plugins

>2️⃣ Apoi trebuie instalate pachetele (packages) corespunzatoare direct in folderul de proiect folosind utilitarul npm:
`npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-prettier`
>☑ Detaliat de pe chatgpt:




## ✅Ghidul complet pentru instalare corecta Prettier si ESLint

>Intrebarea initiala pe chatgpt: Care sunt variantele de eslint si prettify pentru Vscode?

## 🧩 ESLint & Prettier în VS Code (actualizat 2025)

In VS Code există mai multe extensii **ESLint / Prettier**, iar unele pot crea confuzii (mai ales cele neoficiale).  
Hai să le luăm clar, actualizat la 2025:

---

## 🧩 1️⃣ ESLint

### 🔹 Varianta corectă / oficială:
- **Nume:** ESLint  
- **Publisher:** Microsoft  
- **ID:** `dbaeumer.vscode-eslint`  
- 🔗 [Link oficial pe Marketplace](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

### 🔧 Ce face:
- Integrează **linterul ESLint** direct în editor.  
- Marchează automat erori și „code style issues”.  
- Poate aplica automat reguli (ex: `--fix`) la salvare.  

### 🔧 Cum se activează:
Instalează extensia și adaugă în setările VS Code (sau verifică că sunt prezente):
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    },
    "eslint.format.enable": true

În proiect, ai nevoie de fișierul:
- `.eslintrc.json`  
  sau  
- `eslint.config.js`  

cu reguli (de ex. pentru airbnb, standard, react etc.)

---

## 💎 2️⃣ Prettier

### 🔹 Varianta corectă / oficială:
- **Nume:** Prettier - Code formatter  
- **Publisher:** Prettier (organizația oficială)  
- **ID:** `esbenp.prettier-vscode`  
- 🔗 [Link oficial pe Marketplace](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

### 🔧 Ce face:
- Formatează codul (indentare, spațiere, ghilimele, punct și virgulă etc.)  
- Funcționează pentru **JS, TS, HTML, CSS, JSON, Markdown**, etc.

### 🔧 Setări recomandate:
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true

---

## ⚖️ 3️⃣ ESLint + Prettier împreună (cea mai bună combinație)

Ca să nu se „certe” între ele (pentru că ambele pot schimba stilul de cod), folosește configurarea combinată.

### Instalează în proiect:
    npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-prettier

### În `.eslintrc.json`:
    {
      "extends": ["eslint:recommended", "plugin:prettier/recommended"]
    }

Asta spune ESLint-ului:
- „folosește Prettier pentru formatat codul”
- „nu aplica reguli care intră în conflict cu Prettier”

---

## 🧰 Alte variante secundare (nu recomandate, dar există)

| Extensie | Status | Observații |
|-----------|--------|-------------|
| `rvest.vs-code-prettier-eslint` | ❌ neoficială | combină ambele, dar nu e întreținută |
| `prettier-eslint` | ⚠️ CLI utilitar, nu extensie | poate fi folosit în scripturi npm |
| `beautify` | 🚫 învechit | nu se mai folosește pentru JS modern |

---

## ✅ Recomandarea curată pentru 2025:
- `dbaeumer.vscode-eslint` (**ESLint – Microsoft**)  
- `esbenp.prettier-vscode` (**Prettier – oficial**)  
- configurare comună: `"plugin:prettier/recommended"`

---

### 💡 Extra – Sugestie pentru `settings.json` complet:
    {
      "editor.formatOnSave": true,
      "editor.defaultFormatter": "esbenp.prettier-vscode",
      "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
      },
      "eslint.validate": ["javascript", "javascriptreact", "typescript", "typescriptreact"],
      "eslint.format.enable": true,
      "files.eol": "\n"
    }

> **Notă:** Dacă preferi, poți pune aceste setări fie în `User Settings` global, fie în `.vscode/settings.json` la nivel de proiect (recomandat pentru consistență în echipă).

---

### 📁 Structură minimă de proiect:
```
my-project/
├── package.json
├── .eslintrc.json
├── .prettierrc (opțional)
└── src/
    └── index.js
```

### Exemplu `.prettierrc` simplu:
    {
      "singleQuote": true,
      "semi": true,
      "trailingComma": "es5"
    }

---

## 🔧 Alte setări utile și fișiere de configurare

### Exemplu complet `package.json` (relevant pentru scripturi):
    {
      "name": "my-project",
      "version": "1.0.0",
      "private": true,
      "scripts": {
        "lint": "eslint . --ext .js,.jsx,.ts,.tsx",
        "lint:fix": "eslint . --ext .js,.jsx,.ts,.tsx --fix",
        "format": "prettier --write \"src/**/*.{js,jsx,ts,tsx,json,css,md}\""
      },
      "devDependencies": {
        "eslint": "^8.0.0",
        "prettier": "^2.0.0",
        "eslint-config-prettier": "^8.0.0",
        "eslint-plugin-prettier": "^4.0.0"
      }
    }

### Exemplu `.eslintrc.json` mai complet (React + Prettier):
    {
      "env": {
        "browser": true,
        "es2021": true,
        "node": true
      },
      "extends": [
        "eslint:recommended",
        "plugin:react/recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:prettier/recommended"
      ],
      "parserOptions": {
        "ecmaVersion": 12,
        "sourceType": "module"
      },
      "plugins": ["react", "@typescript-eslint"],
      "rules": {
        "react/prop-types": "off"
      }
    }

---

## 🔧 Flux recomandat de lucru (setup rapid)
1. Instalează extensiile VS Code:
   - `dbaeumer.vscode-eslint`
   - `esbenp.prettier-vscode`

2. În proiect:
    npm init -y
    npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-prettier

3. Configurează `.eslintrc.json` și `.prettierrc`.

4. Pune setările VS Code (în `.vscode/settings.json`) ca în exemplul `settings.json` de mai sus pentru a avea `formatOnSave` + `eslint fix on save`.

---

## 🔧 Troubleshooting rapid
- Dacă Prettier formatează, dar ESLint încă afișează probleme: adaugă `eslint-config-prettier` la `extends`.
- Dacă formatOnSave nu funcționează: verifică `editor.defaultFormatter` și că nu ai alt formatter activ pentru acea limbă.
- Pentru TypeScript, asigură-te că `eslint` și plugin-urile TS sunt instalate corect (`@typescript-eslint/parser`, `@typescript-eslint/eslint-plugin`).

---

## 🔎 Rezumat rapid

| Ce vrei să faci | Extensie | Config |
|-----------------|-----------|--------|
| Linting / reguli cod | ESLint (`dbaeumer.vscode-eslint`) | `.eslintrc.json` |
| Format automat cod | Prettier (`esbenp.prettier-vscode`) | `.prettierrc` |
| Integrare comună | `eslint-plugin-prettier` + `eslint-config-prettier` | `"extends": ["plugin:prettier/recommended"]` |

---

✅ **Recomandare finală pentru setup rapid:**

1. Instalează extensiile:
   - `dbaeumer.vscode-eslint`
   - `esbenp.prettier-vscode`

2. Instalează pachetele dev:
    npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-prettier

3. Creează `.eslintrc.json`:
    {
      "extends": ["eslint:recommended", "plugin:prettier/recommended"]
    }

4. Configurează `settings.json` ca mai sus.

---

Cu acest setup, VS Code îți:
- marchează erorile în timp real,
- formatează automat codul,
- și păstrează un stil consistent între membrii echipei 🚀

Dacă vrei, îți pot da acum:
- o versiune completă gata de pus în repo (toate fișierele: `.eslintrc.json`, `.prettierrc`, `.vscode/settings.json`, `package.json`) — într-un singur pachet copiat în continuare, sau
- doar fișierul `.vscode/settings.json` pentru proiectul tău.

Spune ce preferi și ți-l tai în formatul exact pentru repo.
```

