# 🏕️ Inwentarz Harcówki IV SH

Aplikacja PWA do przeglądania i edycji inwentarza harcówki.
Hosting: **GitHub Pages** — darmowy, bezpośrednio z tego repozytorium.

---

## 🚀 Wdrożenie (~15 minut)

### 1. Utwórz repozytorium
- github.com → **New repository** → nazwa: `harcowka-ivsh` → **Public** → Create

### 2. Wgraj pliki
Wgraj na GitHub: `index.html`, `data.json`, `manifest.json`, `icon.svg`
(przeciągnij na stronę repo lub kliknij "uploading an existing file")

### 3. Włącz GitHub Pages
- Repo → **Settings** → **Pages** → Source: **Deploy from a branch** → Branch: **main / (root)** → Save
- Po ~1 minucie adres: `https://TWOJA-NAZWA.github.io/harcowka-ivsh/`

### 4. Skonfiguruj aplikację
W `index.html` znajdź `const CONFIG` i uzupełnij:
```javascript
GITHUB_REPO: 'TWOJA-NAZWA/harcowka-ivsh',
ADMIN_PASSWORD: 'twoje-haslo',
```
Zapisz i wgraj ponownie (lub edytuj bezpośrednio na GitHub — kliknij ✏️ przy pliku).

### 5. Tokeny dla edytorów
Każda osoba edytująca potrzebuje Personal Access Token:
- GitHub → avatar → Settings → Developer settings → Fine-grained tokens → Generate
- Repository access: tylko `harcowka-ivsh`
- Permissions → Contents: **Read and Write**
- Skopiuj token → wpisz w aplikacji przy pierwszym logowaniu

---

## 📱 Używanie

**Przeglądanie** — otwórz link / zeskanuj QR. Działa offline (PWA).

**Edycja** — kliknij ⚙️ Edytuj → hasło → token GitHub → dodaj/edytuj/usuń pozycje.
Zmiana zapisuje się do `data.json` w repo → strona odświeża się po ~30 sek.

---

## 🔄 Jak działa synchronizacja

```
Edytor zapisuje → PUT do GitHub API → nowy commit w data.json
                                    → GitHub Pages serwuje nowe dane
                                    → kolejny użytkownik widzi zmiany
```

Dane pobierane z `raw.githubusercontent.com` — szybko, bez limitów.
