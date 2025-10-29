# Program de vot online pentru Adunările Generale ale Acționarilor (AGA)

Acest program permite organizarea, desfășurarea și raportarea completă a voturilor din cadrul **Adunărilor Generale ale Acționarilor (AGA)** – inclusiv gestionarea prezenței, ponderarea automată a voturilor în funcție de numărul de acțiuni și generarea rapoartelor oficiale PDF.

Aplicația funcționează complet **local (HTML/JavaScript)** – fără server extern – și poate fi rulată direct din browser (Chrome, Edge, Firefox, Safari).

---

## 🔹 1. Acces și moduri de utilizare

La deschiderea fișierului `AGA_Vot_Online_V3.html`, utilizatorul alege modul de lucru:

- **Organizator** – acces complet, protejat prin parolă (implicit: `DESTINE2025`).
- **Vizualizare** – acces fără posibilitate de editare.
- **Votant** – acces individual prin link unic, generat automat.

---

## 🔹 2. Modul Organizator

### Setări generale
- Numele companiei și data ședinței (apare și în raportul PDF).
- Parola de administrare – poate fi modificată.
- Quorum minim (procent capital prezent necesar).
- Adresă de colectare voturi (opțional, pentru integrare cu Google Apps Script).
- Prefix link-uri (opțional, dacă pagina e găzduită extern – ex. pe GitHub Pages).

### Gestionare acționari
1. Importă lista de acționari dintr-un fișier `.csv` cu structura:
   ```
   Nume,Actiuni,Telefon,Email,ProcurăPentru
   ```
2. Fiecare acționar primește un **link unic de acces** (cu parametru `?mode=voter`).
3. La accesarea linkului:
   - Prezența este bifată automat („Prezent”).
   - Se salvează data și ora conectării.

### Trimiterea invitațiilor
- **💬 Trimite pe WhatsApp** – deschide conversația directă cu textul standard.
- **✉️ Trimite pe Email** – deschide clientul de e-mail cu mesajul precompletat.
- **💬📧 Trimite tuturor** – trimite automat pentru toți acționarii (WhatsApp + Email).

> 🔔 Asigură-te că **browserul permite deschiderea ferestrelor pop-up**, altfel mesajele multiple pot fi blocate.

---

## 🔹 3. Modul Votant

- Fiecare acționar accesează linkul unic trimis prin WhatsApp sau Email.
- Prezența este înregistrată automat la acces.
- Acționarul poate vota pentru fiecare punct de pe ordinea de zi:
  - ✅ DA
  - ❌ NU
  - ➖ Abținere
- Votul este ponderat automat în funcție de numărul de acțiuni.
- Dacă este configurat un endpoint, votul poate fi transmis automat prin HTTP POST.

---

## 🔹 4. Ordinea de zi și voturile

Organizatorul poate:
- adăuga, modifica sau șterge puncte de pe ordinea de zi;
- seta **tipul de majoritate necesară**:
  - Majoritate simplă (>50% din acțiunile prezente)
  - Majoritate de 2/3 din acțiunile prezente
  - Majoritate de 3/4 din acțiunile prezente
  - Majoritate absolută (>50% din capitalul social total)

---

## 🔹 5. Rezultate și raportare

- Rezultatele sunt afișate în timp real pentru fiecare punct.
- Raportul final include:
  - Prezența nominală completă
  - Cvorumul
  - Detaliile fiecărui punct (DA / NU / Abțineri)
  - Rezultatul (ADMIS / RESPINS)
- Poate fi **tipărit direct din browser (Ctrl+P)** sau exportat ca **PDF (A4, portret)**.

De asemenea:
- Export CSV – lista acționarilor cu linkurile individuale.
- Export JSON – sesiunea completă pentru arhivare sau reîncărcare ulterioară.

---

## 🔹 6. Publicarea pe GitHub Pages

1. Creează un repository nou (ex. `aga-vot`) pe GitHub.
2. Încarcă fișierul `AGA_Vot_Online_V3.html` și eventual `README.md`.
3. Activează **GitHub Pages**:
   - Settings → Pages → Branch: `main` / Root → Save
4. Adresa publică va fi, de exemplu:
   ```
   https://utilizatorul-tau.github.io/aga-vot/AGA_Vot_Online_V3.html
   ```

Poți trimite acest link acționarilor (completat automat în mesajele WhatsApp/Email).

---

## 🔹 7. Securitate și confidențialitate

- Datele se stochează **doar local** (în browser, în LocalStorage).
- Nu este necesar un server sau o bază de date externă.
- Poți șterge oricând datele locale cu butonul **„Reset total”**.
- Parola organizatorului se poate schimba oricând din interfață.

---

## 🔹 8. Suport și întreținere

Programul este conceput pentru utilizare internă în cadrul companiilor care organizează AGA.
Poate fi adaptat cu ușurință pentru alte societăți, asociații sau cooperative.

---

© 2025 – Destine Holding S.A.  
Realizat cu sprijinul echipei de coordonare și al colaboratorilor din rețeaua Destine Broker.
