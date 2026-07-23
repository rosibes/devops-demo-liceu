# Ghid demo DevOps — GitHub Pages + Actions

Testează totul diseară, ca mâine să meargă din prima. Durează ~15 min prima dată.

## Ce ai nevoie
- Un cont GitHub (gratuit)
- Git instalat pe laptop (sau folosești interfața web a GitHub — vezi Varianta B)

---

## Varianta A — cu Git din terminal (recomandată pentru demo, arată "push"-ul real)

### 1. Creează repo-ul pe GitHub
- Intră pe github.com → butonul verde **New** (repository nou)
- Nume: `devops-demo` (sau ce vrei)
- Bifează **Public** (IMPORTANT — pe privat, Pages costă)
- NU adăuga README/gitignore, lasă gol
- **Create repository**

### 2. Urcă fișierele
În folderul cu `index.html` și `.github/`, rulează:

```bash
git init
git add .
git commit -m "Primul deploy"
git branch -M main
git remote add origin https://github.com/UTILIZATORUL-TAU/devops-demo.git
git push -u origin main
```

(înlocuiește `UTILIZATORUL-TAU` cu username-ul tău de GitHub)

### 3. Activează GitHub Pages
- În repo → **Settings** (sus) → în stânga **Pages**
- La "Build and deployment" → Source: alege **GitHub Actions**
- Gata, nu mai bifezi nimic

### 4. Verifică pipeline-ul
- Mergi la tab-ul **Actions** din repo
- Vezi workflow-ul "Deploy pe GitHub Pages" rulând (cerc galben → bifă verde)
- Când e verde, revii la **Settings → Pages** și vezi link-ul live sus:
  `https://UTILIZATORUL-TAU.github.io/devops-demo/`
- Deschide-l pe telefon. Ăsta e URL-ul pe care-l dai elevilor.

---

## Varianta B — fără terminal, doar din browser (mai simplă, dar fără "push" vizibil)

1. Creează repo-ul public (ca la pasul 1 de sus)
2. Butonul **Add file → Upload files** → trage `index.html`
3. Pentru workflow: **Add file → Create new file**, la nume scrie exact
   `.github/workflows/deploy.yml` și lipești conținutul din fișierul deploy.yml
4. Activează Pages ca la pasul 3 de sus

---

## Momentul "wow" în fața elevilor

Odată ce site-ul e live, arată-le că se schimbă singur:

1. Deschide `index.html` pe GitHub (sau local) → apeși creionul (Edit)
2. Schimbă textul, de ex. `Versiunea afișată: 1.0` → `2.0`
   sau titlul `Salut de la DevOps` → `Salut, clasa a XI-a!`
3. **Commit / push**
4. Elevii se uită pe telefon → în ~30-60 sec pagina se schimbă singură

**Asta e CI/CD**: n-a atins nimeni serverul manual. Push = live.

---

## Dacă vrei un QR code pentru elevi
Intră pe orice generator de QR (ex: qr-code-generator.com), lipești URL-ul
`.github.io`, îl proiectezi pe ecran. Elevii scanează și gata — mai rapid
decât să tasteze adresa.

---

## Ce spui în timp ce arăți (pe scurt)
- **index.html** = "codul aplicației" (ce vede utilizatorul)
- **deploy.yml** = "rețeta de automatizare" — instrucțiunile pe care robotul le
  execută la fiecare push (ia codul → împachetează → publică)
- **tab-ul Actions** = "banda de asamblare" care lucrează singură
- **URL-ul live** = rezultatul, accesibil oricui, de oriunde

Fără DevOps: cineva ar copia manual fișierele pe un server de fiecare dată.
Cu DevOps: scrii cod, dai push, restul se întâmplă automat și de fiecare dată la fel.
