# Caiet de Cântări – Tineret Betania

Bine ai venit! Aici găsești varianta actualizată a caietului de cântări, pregătită atât pentru citit pe telefon/tabletă, cât și pentru printare.

* **Vrei doar să descarci caietul gata făcut?** Apasă pe **[main.pdf](main.pdf)** și apoi pe butonul **Download raw file** (săgeata în jos din dreapta sus).
* **Vrei să editezi sau să adaugi cântări noi?** Urmează ghidul de mai jos.

---

## Pasul 1: Instalarea programelor necesare (se face o singură dată)

Pentru a transforma textul cântărilor în PDF, ai nevoie de trei programe gratuite. **Este foarte important să le instalezi în această ordine:**

### 1. Instalează MiKTeX (motorul care generează PDF-ul)
1. Intră pe [miktex.org/download](https://miktex.org/download) și descarcă varianta pentru sistemul tău (Windows / Mac).
2. Rulează programul de instalare și apasă **Next** până la final.
   * **Atenție la un pas important:** Când te întreabă *"Install missing packages on-the-fly"*, alege **Yes** (sau **Always**). Astfel, programul își va descărca singur pachetul pentru cântări (`songs`) fără să îți dea erori.

### 2. Instalează TeXstudio (programul în care scrii textul)
1. Intră pe [texstudio.org](https://www.texstudio.org/) și apasă pe butonul **Download now**.
2. Instalează programul normal (Next -> Install -> Finish).

### 3. Instalează GitHub Desktop (pentru a descărca și trimite modificările ușor)
1. Intră pe [desktop.github.com](https://desktop.github.com/) și instalează aplicația.
2. Conectează-te cu contul tău gratuit de GitHub.

---

## Pasul 2: Descărcarea proiectului în calculator

1. Pe această pagină (sus de tot), apasă pe butonul verde **<> Code** și alege **Open with GitHub Desktop**.
2. Aplicația se va deschide și te va întreba unde să salveze folderul pe calculatorul tău. Apasă **Clone**.
3. Acum ai toate fișierele proiectului în calculatorul tău!

---

## Pasul 3: Cum adaugi o cântare nouă și compilezi PDF-ul

Cântările sunt organizate pe litere în folderul **`cantari/`** (în subfolderele `A`, `B`, `C`, `D` etc.), iar apoi sunt legate în fișierul **`main.tex`**.

### A. Crearea fișierului pentru cântarea nouă
1. Intră în folderul proiectului din calculatorul tău, deschide folderul **`cantari`** și apoi intră în folderul corespunzător **primei litere din titlul cântării** (ex: dacă cântarea începe cu „B”, intră în folderul `B` - sau crează folderul `B`).
2. Creează acolo un fișier nou cu extensia `.tex` (poți copia un fișier deja existent din acel folder și să îl redenumești, fără diacritice sau spații, ex: `binecuvantat_sa_fii.tex`).
3. Deschide acest fișier în **TeXstudio** și scrie cântarea folosind modelul de mai jos:

```latex
\beginsong{Titlul Cântării}[by={Autor / Trupa}]
\beginverse
Primul vers al strofei întâi,
Al doilea vers al strofei întâi.
\endverse

\beginchorus
Aici se scrie refrenul cântării,
Care va apărea îngroșat în caiet.
\endchorus
\endsong
```
*(Dacă pui și acorduri de chitară, ele se scriu între paranteze drepte cu backslash în față, chiar înaintea silabei unde se schimbă acordul, de exemplu: `\[Am]Doamne, Îți mul\[G]țumesc`.)*

5. Salvează fișierul (`Ctrl + S`).

### B. Adăugarea cântării în caietul principal (`main.tex`)
1. Deschide în **TeXstudio** fișierul **`main.tex`** din folderul principal. *(Notă: Nu deschide `preamble.tex`, acela conține doar setările de design).*
2. Caută secțiunea literei respective în `main.tex` și adaugă în ordine alfabetică linia care include noul fișier, folosind comanda `\input{...}`:
```latex
\input{cantari/B/Binecuvantat_sa_fii}
```
*(Atenție: numele din `\input{...}` trebuie să fie identic cu numele fișierului, inclusiv litera mare de la început, dar fără extensia `.tex` la final).*

### C. Cum vezi rezultatul (PDF-ul)
1. Asigură-te că ești pe tab-ul **`main.tex`** în TeXstudio.
2. Apasă pe **săgeata dublă verde** (Build & View) din bara de sus a TeXstudio (sau apasă tasta `F5`).
   * *Prima dată când faci asta, este posibil să dureze 1-2 minute și să apară ferestre în care MiKTeX își descarcă automat pachetele necesare. Lasă-l să termine.*
3. În partea dreaptă a ecranului va apărea PDF-ul actualizat! Verifică să arate bine și salvează (`Ctrl + S`).

---

##  Pasul 4: Cum trimiți modificările înapoi pe GitHub (Push)

După ce ai terminat de adăugat cântarea și ai verificat în PDF că totul arată bine, trebuie să trimiți modificările pe GitHub ca să le vadă și ceilalți.

1. **Salvează tot în TeXstudio:** Apasă `Ctrl + S` (sau `File -> Save All`) ca să te asiguri că toate fișierele sunt salvate.
2. **Deschide aplicația GitHub Desktop:**
   * În partea stângă (la secțiunea **Changes**) vei vedea lista cu fișierele modificate de tine (fișierul nou din `cantari/`, `main.tex` și `main.pdf`).
   * Asigură-te că toate au căsuța bifată.
3. **Descrie pe scurt ce ai modificat (Commit):**
   * În colțul din stânga jos, în căsuța **Summary** (obligatoriu), scrie un mesaj scurt și clar (de exemplu: `Am adaugat cantarea Binecuvantat sa fii`).
   * Apasă pe butonul albastru **Commit to main**.
4. **Urcă modificările pe internet (Push):**
   * În partea de sus a ferestrei va apărea butonul **Push origin**. Apasă pe el.
   * Așteaptă câteva secunde până dispare bara de încărcare.

Gata! Dacă intri acum pe pagina de GitHub în browser și dai refresh, vei vedea cântarea ta nouă și PDF-ul actualizat.

> ** Foarte important pentru data viitoare:**
> De fiecare dată când vrei să începi să lucrezi la caiet, deschide mai întâi **GitHub Desktop** și apasă pe **Fetch origin** (și apoi **Pull origin**, dacă apare) în bara de sus. Astfel descarci ultimele cântări adăugate de ceilalți colegi și eviți suprapunerea fișierelor!

## Documentație și Referințe Oficiale

* **Ghid LaTeX pentru începători (Overleaf Learn):** [overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes) – *Explicații clare despre sintaxa de bază LaTeX.*
* **Manualul Oficial al Pachetului `songs`:** [songs.sourceforge.net/songsdoc/songs.html](http://songs.sourceforge.net/songsdoc/songs.html) – *Documentația completă a tuturor comenzilor (`\beginsong`, `\gtab`, `\transpose`, indexare etc.).*
* **Documentația TikZ & PGF (CTAN):** [ctan.org/pkg/pgf](https://ctan.org/pkg/pgf) – *Manualul oficial pentru grafică vectorială, chenare, linii decorative și elemente vizuale personalizate.*
* **Pachetul `pgfornament` (CTAN):** [ctan.org/pkg/pgfornament](https://ctan.org/pkg/pgfornament) – *Catalogul oficial cu ornamente tipografice vectoriale (viniete, separatoare de pagină, colțare decorative).*
* **Ghid GitHub Desktop:** [docs.github.com/en/desktop](https://docs.github.com/en/desktop) – *Documentația oficială pentru gestionarea modificărilor și rezolvarea conflictelor.*
