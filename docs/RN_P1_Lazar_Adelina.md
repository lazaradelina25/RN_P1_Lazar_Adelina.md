# Rețele neuronale · Proiect · P1 – Propunerea de proiect

**UNSTPB · FIIR · Informatică industrială, anul III · 2026–2027**

> **Cum se completează fișa**
>
> - Redenumiți fișierul `RN_P1_Nume_Prenume.md` cu numele vostru, fără diacritice și fără spații (de exemplu `RN_P1_Popescu_Ion.md`).
> - Păstrați titlurile și numerotarea. Înlocuiți textele dintre paranteze drepte `[...]` cu răspunsuri proprii.
> - Scrieți concis, dar suficient de concret încât altă persoană să poată înțelege și verifica propunerea.
> - Pentru informațiile pe care nu le cunoașteți încă scrieți **„de verificat”** și treceți-le la secțiunea 7. Nu prezentați presupunerile drept fapte verificate.
> - La P1 se predă o **propunere argumentată**: nu se cer cod, model antrenat, date colectate sau rezultate.

---

## 0. Identificare

| Câmp | Răspuns |
|---|---|
| Nume și prenume | [Lazar Adelina-Cristina ] |# Rețele neuronale · Proiect · P1 – Propunerea de proiect

**UNSTPB · FIIR · Informatică industrială, anul III · 2026–2027**

## 0. Identificare

| Câmp | Răspuns |
|---|---|
| Nume și prenume | Lazar Adelina-Cristina |
| Grupa | 632AB |
| Versiunea fișei și data | 1 – 16.10.2026 |
| Titlul provizoriu al proiectului | Tema partener nr. 8 – Starea spațiului: ușă deschisă/închisă, încăpere ocupată/liberă
| Username GitHub | lazaradelina25 |
| Repository-ul proiectului | https://github.com/lazaradelina25/RN_P1_Lazar_Adelina.md |
| Invitația GitHub este acceptată | [Da / Nu – de verificat] |

## 1. Nevoia și utilizatorul

**1.1. Situația concretă.**

În clădiri precum facultăți, birouri sau spații industriale, verificarea stării ușilor poate necesita observarea directă a acestora. Dacă există mai multe încăperi, verificarea manuală poate deveni repetitivă. Proiectul propune o aplicație care analizează o imagine a unei uși și estimează dacă aceasta este deschisă sau închisă.

**1.2. Utilizatorul sau sistemul beneficiar.**

Utilizatorul vizat este o persoană responsabilă de verificarea sau monitorizarea încăperilor, de exemplu un administrator de clădire. Acesta ar putea încărca o fotografie în aplicație și ar putea consulta rezultatul clasificării pentru a decide dacă este necesară o verificare suplimentară.

**1.3. Dovada nevoii.**

Necesitatea verificării stării ușilor reprezintă motivația inițială a proiectului. Nu a fost realizat încă un studiu cu utilizatori și nu există măsurători proprii privind timpul necesar verificării manuale. Aceste aspecte sunt de verificat. Proiectul va testa dacă o rețea neuronală poate clasifica automat imagini ale ușilor în cele două categorii propuse.

## 2. Decizia sprijinită și costul erorilor

**2.1. Decizia sau acțiunea.**

Aplicația va estima dacă ușa din imagine este deschisă sau închisă. Utilizatorul va decide dacă rezultatul necesită o verificare suplimentară. Aplicația nu va controla fizic ușa și nu va lua automat măsuri de securitate.

**2.2. Costul erorilor.**

O clasificare greșită poate determina utilizatorul să creadă că ușa este închisă când, în realitate, este deschisă, sau invers. Într-un scenariu de monitorizare, ratarea unei uși deschise poate fi mai importantă dacă verificarea are un scop de securitate. Gravitatea reală depinde de contextul utilizării. În cadrul proiectului, ambele tipuri de erori vor fi analizate cu ajutorul matricei de confuzie și al preciziei pe fiecare clasă.

**2.3. Beneficiul urmărit.**

Se urmărește automatizarea parțială a verificării vizuale și obținerea unor rezultate consecvente pentru imaginile analizate. Beneficiul va fi evaluat prin compararea rezultatelor rețelei neuronale cu etichetele corecte și cu rezultatele unei metode bazate pe reguli. Se vor măsura acuratețea, precizia, recall-ul și timpul de clasificare.

## 3. Formularea problemei

| Element | Răspuns |
|---|---|
| Intrarea aplicației | O imagine digitală care conține o ușă, încărcată de utilizator sau selectată din setul de date. |
| Ieșirea rețelei neuronale | Una dintre cele două clase: `deschisă` sau `închisă`. |
| Rezultatul pentru utilizator | Imaginea analizată, clasa prezisă și scorurile de încredere pentru cele două clase, afișate într-o interfață web. |
| Tipul sarcinii | Clasificare binară de imagini, deoarece fiecare imagine primește una dintre două etichete. |
| Un exemplu | Exemplu ipotetic: o imagine în care ușa este vizibil întredeschisă este etichetată `deschisă`; rețeaua ar trebui să prezică aceeași clasă. |

**Formularea sintetică.**

„Pentru persoanele care verifică starea ușilor din clădiri, aplicația primește o imagine și produce o predicție privind starea ușii, pentru a sprijini verificarea vizuală, în condițiile în care ușa este suficient de vizibilă, iar imaginea permite stabilirea unei etichete corecte.”

## 4. Soluția actuală și reperul de comparație

**4.1. Cum se rezolvă problema astăzi.**

Într-o situație obișnuită, o persoană poate observa direct ușa și poate stabili dacă aceasta este deschisă sau închisă. Într-o aplicație informatică, verificarea poate fi realizată și prin reguli bazate pe caracteristici vizuale, dacă acestea pot fi identificate în imagine. Nu a fost verificată existența unui sistem automat utilizat efectiv în contextul ales; acest aspect este de verificat.

**4.2. Limita soluției actuale.**

Observarea umană presupune intervenția unei persoane. O metodă bazată pe reguli vizuale poate funcționa pentru anumite imagini, dar poate fi sensibilă la iluminare, unghiul fotografiei, culoarea ușii și aspectul încăperii. Ipoteza proiectului este că o rețea neuronală poate învăța caracteristici vizuale relevante din exemple etichetate și poate generaliza mai bine la imagini diferite decât o regulă simplă. Această ipoteză va fi testată experimental.

**4.3. Reperul automat.**

Ca reper de comparație se va implementa o metodă simplă bazată pe reguli vizuale, care va primi aceleași imagini ca rețeaua neuronală. Se va analiza dacă anumite caracteristici ale imaginii, precum contururile și distribuția zonelor vizibile ale ușii, pot fi utilizate pentru a diferenția cele două clase. Implementarea exactă și fezabilitatea acesteia sunt de verificat în etapa de dezvoltare.

Dacă metoda bazată pe reguli nu poate fi definită suficient de robust pentru datele disponibile, se va discuta cu îndrumătorul alegerea unui alt reper automat simplu, păstrând aceleași date de testare.

## 5. Datele

**5.1. Unitatea de date și răspunsul corect.**

Un exemplu de date este o imagine digitală în care o ușă poate fi identificată și clasificată. Fiecare imagine va primi una dintre etichetele `deschisă` sau `închisă`. Etichetele vor fi atribuite prin inspectarea imaginilor și vor fi verificate manual. Imaginile în care starea ușii nu poate fi stabilită clar vor fi excluse sau analizate separat.

**5.2. Sursele de date.**

| Sursa | Accesul (link, dispozitiv disponibil sau „de verificat”) | Contribuția proprie |
|---|---|---|
| Fotografii realizate personal în spații accesibile, de exemplu într-o încăpere sau într-un laborator | De verificat: accesul la spații și posibilitatea fotografierii | Realizarea fotografiilor, etichetarea și organizarea lor în cele două clase |
| Set de imagini publice cu uși deschise și închise | De verificat: identificarea unui set de date potrivit și verificarea licenței de utilizare | Selectarea imaginilor relevante, verificarea etichetelor și documentarea sursei |

**5.3. Planul de obținere.**

Inițial, se urmărește obținerea unui set de aproximativ 200–300 de imagini pentru fiecare clasă, dacă timpul și accesul la date permit. Volumul este o estimare de lucru, nu o cantitate deja colectată sau suficientă garantat pentru antrenare.

Fotografiile proprii vor fi realizate în condiții variate, pe cât posibil: unghiuri diferite, iluminare diferită și uși cu aspecte diferite. Imaginile vor fi etichetate și împărțite în seturi de antrenare, validare și testare, astfel încât imaginile foarte asemănătoare să nu apară simultan în seturi diferite.

**5.4. Alternativa.**

Dacă nu pot fi realizate suficiente fotografii proprii, se va utiliza un set de date public adecvat, cu sursa și licența declarate, completat cu un număr de fotografii proprii, dacă este posibil. Dacă nu se găsește un set potrivit, se va reduce dimensiunea proiectului și se va utiliza un set propriu mai mic, cu limitele corespunzătoare documentate.

## 6. Versiunea minimă și riscul principal

**6.1. Versiunea minimă demonstrabilă.**

Versiunea minimă va include clasificarea imaginilor în două clase: ușă deschisă și ușă închisă. Se va antrena și evalua o rețea neuronală, apoi se vor compara rezultatele sale cu cele ale reperului automat bazat pe reguli.

Pentru demonstrație, se urmărește realizarea unei aplicații web în care utilizatorul poate încărca o imagine și poate vedea predicția, scorul de încredere și rezultatele evaluării modelului sub formă de grafice. Graficele vor include, dacă implementarea permite, distribuția claselor și matricea de confuzie.

Nu intră în versiunea minimă controlul fizic al ușilor, monitorizarea video în timp real sau integrarea cu senzori și sisteme de securitate. Clasificarea încăperilor ca ocupate sau libere poate reprezenta o extindere ulterioară, dacă timpul permite și dacă este acceptată de îndrumător.

**6.2. Riscul principal.**

Principalul risc este obținerea unui set de imagini suficient de variat și corect etichetat. Dacă datele sunt prea asemănătoare sau insuficiente, modelul poate învăța particularitățile imaginilor de antrenare fără să clasifice corect imagini noi.

Riscul va fi verificat devreme prin căutarea unui set public potrivit și realizarea unui lot inițial de fotografii proprii. Ca variantă de rezervă, se va utiliza un set public verificat sau se va restrânge diversitatea scenariilor, păstrând ambele clase și o evaluare separată pe imagini nevăzute în timpul antrenării.

## 7. Ce nu este încă clar

| Întrebarea deschisă | Cum o verific | Până când |
|---|---|---|
| Ce set public de imagini poate fi utilizat legal și este suficient de potrivit? | Caut seturi de date, verific licențele și inspectez exemplele și etichetele. | Înainte de începerea colectării și antrenării |
| Pot realiza fotografii proprii în condiții variate? | Verific accesul la încăperi și condițiile de fotografiere. | Înainte de definitivarea setului de date |
| Ce arhitectură neuronală și ce instrumente de dezvoltare sunt potrivite? | Analizez dimensiunea datelor și resursele de calcul disponibile și discut cu îndrumătorul. | În etapa de proiectare |
| Ce metodă bazată pe reguli poate constitui un reper corect pentru aceleași imagini? | Testez dacă regulile vizuale pot separa clasele și documentez limitările lor. | Înainte de evaluarea comparativă |
| Este acceptată extinderea ulterioară către clasificarea încăperilor ocupate/libere? | Solicit feedbackul îndrumătorului. | La următoarea discuție de îndrumare |

## 8. Feedback și revizuire

**8.1. Recomandările primite în ședința P1.**

De completat după discuția cu îndrumătorul. Dacă discuția nu a avut loc încă, se va menționa acest lucru.

**8.2. Modificările față de versiunea anterioară.**

Prima versiune a propunerii. Tema a fost delimitată la clasificarea stării unei uși în două clase, pentru a menține un obiectiv clar și realizabil. Extinderea către clasificarea încăperilor ocupate/libere nu face parte din versiunea minimă.

## 9. Surse și folosirea asistenților AI

**9.1. Surse consultate.**

Nu au fost încă verificate surse externe pentru un set concret de date. Urmează să fie identificate și documentate:

- Un set public de imagini cu uși deschise și închise, dacă este disponibil și adecvat – titlul, autorul, linkul și licența sunt de verificat.
- Documentația tehnică a instrumentului sau bibliotecii utilizate pentru antrenarea rețelei neuronale – de completat după alegerea instrumentului.

Sursele efectiv utilizate vor fi adăugate înainte de predarea versiunii finale.

**9.2. Folosirea asistenților AI.**

Am folosit ChatGPT pentru structurarea și redactarea inițială a propunerii, delimitarea problemei, formularea obiectivelor și identificarea riscurilor posibile. Alegerea finală a temei, verificarea surselor și a licențelor, colectarea și etichetarea datelor, implementarea și evaluarea rezultatelor vor fi realizate și verificate personal. Conținutul fișei va fi revizuit astfel încât fiecare afirmație să poată fi explicată și susținută.

---

## Verificare înainte de predare

- [ ] Am completat numele, grupa și datele GitHub.
- [ ] Am acceptat invitația în organizația GitHub și am verificat repository-ul atribuit.
- [ ] Am argumentat nevoia, utilizatorul și decizia sprijinită.
- [ ] Am precizat intrarea, ieșirea și tipul sarcinii neuronale.
- [ ] Am descris soluția actuală și reperul automat de comparație.
- [ ] Am indicat sursele de date și contribuția proprie planificată.
- [ ] Am marcat informațiile necunoscute ca „de verificat”.
- [ ] Am documentat sursele efectiv consultate și folosirea asistenților AI.
- [ ] Am salvat fișa cu numele `RN_P1_Nume_Prenume.md`.
- [ ] Am încărcat fișierul în Moodle și în repository, în directorul `docs/`.

| Grupa | [632AB ] |
| Versiunea fișei și data | [1 – în ședința P1; 2, 3 … după feedback] · [data] |
| Titlul provizoriu al proiectului | [o formulare care indică problema și contextul, nu doar tehnologia] |
| Username GitHub | [ ] |
| Repository-ul proiectului | [https://github.com/FIIR-RN2026/...] |
| Invitația GitHub este acceptată | [da / nu – dacă nu, motivul] |

