# Rețele neuronale · Proiect · P2 – Datele

**UNSTPB · FIIR · Informatică industrială, anul III · 2026–2027**

## 0. Identificare

| Câmp | Răspuns |
|---|---|
| Nume și prenume | Lazar Adelina-Cristina |
| Grupa | 632AB |
| Titlul proiectului (actualizat, dacă s-a schimbat față de P1) | Clasificarea stării ușii și a încăperii pentru sprijinirea navigării unui robot mobil |
| Tema este o temă propusă de partener? | Da, tema nr. 8 |
| Repository-ul proiectului | https://github.com/lazaradelina25/RN_P1_Lazar_Adelina.md |
| Versiunea fișei și data | Sprintul 1 · 22.10.2026 |

## 1. Ce vreau să decid?

**1.1. Decizia.**

Sistemul de planificare a traseului al unui robot mobil folosește rezultatul pentru a decide dacă poate continua pe traseul planificat sau trebuie să îl replanifice. Dacă ușa este clasificată ca închisă, robotul trebuie să caute un traseu alternativ. Dacă încăperea este clasificată ca ocupată, robotul poate amâna sarcina până când spațiul este liber. Clasificarea este un sprijin pentru decizie, nu o garanție de siguranță.

**1.2. Exemplul și momentul deciziei.**

Un exemplu este un cadru individual extras din fluxul video al camerei montate pe robot, în timp ce acesta se apropie de o încăpere dintr-o clădire. Pentru acel cadru se estimează simultan starea ușii și starea încăperii. Rezultatul este util înainte ca robotul să decidă dacă intră în încăpere sau își modifică traseul.

**1.3. Intrarea și ieșirea.**

| | Răspuns |
|---|---|
| Ce date am în momentul deciziei (format, sursă) | Un cadru video RGB capturat de camera robotului în apropierea unei uși. Accesul la un robot și posibilitatea de a înregistra în condiții permise sunt de verificat. |
| Ce ajunge efectiv la model (de exemplu: 4 valori; o imagine 224×224; o fereastră de 200 de eșantioane) | O imagine color redimensionată la o dimensiune stabilită în etapa de implementare, de exemplu 224×224 pixeli. |
| Ce produce modelul (clasele, mărimea și unitatea sau casetele) | Două etichete: starea ușii — `deschisă` / `închisă`; starea încăperii — `ocupată` / `liberă`. Pentru fiecare predicție se poate afișa și un scor de încredere. |
| Ce face restul aplicației cu rezultatul (o propoziție) | Aplicația afișează cele două predicții și oferă sistemului de planificare informații pentru replanificarea traseului sau amânarea sarcinii. |

## 2. Cum știu răspunsul corect?

**2.1. Sursa răspunsului corect.**

Pentru fiecare cadru, etichetele corecte vor fi stabilite prin inspectarea imaginii și aplicarea unor reguli scrise. Ușa este etichetată `deschisă` dacă se vede clar că nu este în poziția închisă și `închisă` dacă este clar închisă. Încăperea este etichetată `ocupată` dacă în imagine se observă clar cel puțin o persoană în interior și `liberă` dacă zona relevantă este vizibilă și nu se observă nicio persoană. Dacă imaginea nu permite o concluzie sigură, exemplul va fi marcat ca neclar și nu va fi folosit ca etichetă sigură.

Etichetele vor fi stabilite manual, separat de predicția modelului. Este necesar să fie clară zona încăperii care trebuie evaluată și să nu se considere automat că o încăpere este liberă doar pentru că nicio persoană nu este vizibilă într-o imagine parțială. Condițiile exacte de adnotare și colectare trebuie verificate cu îndrumătorul, în special pentru imaginile în care apar persoane.

**2.2. Exemplul real examinat.**

| | Răspuns |
|---|---|
| Ce exemplu am examinat (descriere sau cale către fișier) | Nu am examinat încă un fișier real din camera unui robot. Exemplul de lucru ales este un cadru video cu o ușă și zona vizibilă a încăperii; un fișier concret trebuie obținut și inspectat înainte de Sprintul 2. |
| De unde provine (sursa; aceeași cu cea din care va veni testul?) | Planificată: înregistrare proprie din camera unui robot sau dintr-un dispozitiv care reproduce perspectiva camerei robotului, într-un spațiu accesibil și cu permisiune. Accesul și condițiile de înregistrare sunt de verificat. Datele de test trebuie să provină din condiții comparabile cu cele de utilizare. |
| Grupul: obiectul, persoana, locul sau sesiunea din care provine | De completat după obținerea fișierului; se va nota locul și sesiunea de înregistrare, fără date personale. |
| Momentul în care a fost obținut | De completat la colectarea efectivă. |
| Răspunsul corect pentru acest exemplu (sau „încă indisponibil”, cu motivul) | Încă indisponibil: nu există momentan un fișier real inspectat și etichetat. |
| Ce am observat (caz clar, caz neclar, problemă) | De verificat după examinarea primului cadru real; nu presupun că ușa și zona încăperii vor fi suficient de vizibile. |

Dacă nu am acces la un robot sau la date permise, voi contacta îndrumătorul în prima săptămână după ședință pentru a stabili o alternativă acceptată. Nu voi prezenta imagini inventate sau generate cu AI ca date reale.

## 3. Pot construi o primă soluție?

**3.1. Datele pe care le pot strânge.**

Voi începe cu un pilot de câteva zeci de cadre reale, dacă accesul și timpul permit. Cadrele trebuie să surprindă combinații diferite ale stării ușii și ale încăperii, precum și variații de perspectivă și iluminare. Pentru a evita ca pilotul să conțină doar cadre aproape identice, voi înregistra din mai multe poziții sau sesiuni. Numărul final de exemple și timpul necesar pentru captură și etichetare sunt de verificat după o primă sesiune. Nu voi colecta imagini cu persoane identificabile înainte de a stabili cu îndrumătorul condițiile permise și nu voi încărca date personale în repository.

**3.2. Reperul simplu și greșeala importantă.**

Ca reper fără rețea neuronală, voi testa reguli vizuale simple sau o verificare manuală a imaginilor, folosind aceleași exemple etichetate. Fezabilitatea unei reguli automate bazate pe contururi și pe geometria ușii este de verificat; aceasta poate eșua când ușa este văzută dintr-un unghi dificil sau când iluminarea este slabă.

Greșeala importantă indicată în descrierea temei este clasificarea unei uși închise ca fiind deschisă: robotul ar putea încerca să continue pe un traseu blocat, se poate bloca sau poate lovi ușa. De asemenea, clasificarea greșită a unei încăperi ocupate ca fiind liberă poate determina robotul să încerce o sarcină într-un moment nepotrivit. Erorile celor două ieșiri trebuie evaluate separat.

**3.3. Tipul datelor și o familie posibilă de rețea.**

Datele sunt imagini, iar o familie posibilă este o rețea neuronală convoluțională (CNN) sau un model pre-antrenat adaptat clasificării imaginilor. O soluție simplă ar putea folosi un model pre-antrenat și două ieșiri de clasificare, una pentru starea ușii și una pentru starea încăperii. Alegerea concretă depinde de dimensiunea și varietatea pilotului și de resursele de calcul disponibile. Nu pot confirma încă dacă datele vor fi suficiente; dacă sunt prea greu de obținut, voi discuta cu îndrumătorul restrângerea scenariilor, păstrând decizia utilă pentru robot.

## 4. Următorul pas

| | Răspuns |
|---|---|
| Ce fac în prima săptămână | Clarific cu îndrumătorul ce spații și echipamente pot folosi, ce reguli se aplică imaginilor cu persoane și cum pot obține primele cadre din perspectiva camerei robotului. Apoi voi colecta și inspecta un lot inițial de imagini reale și voi nota sursa, sesiunea, momentul și etichetele fiecărui exemplu. |
| Ce îmi lipsește sau ce mă blochează (acces, permisiuni, echipament) | Accesul la un robot mobil sau la o cameră care poate reproduce perspectiva acestuia, permisiunea de a înregistra într-o încăpere și clarificarea condițiilor permise pentru imaginile în care pot apărea persoane. |
| De ce ajutor am nevoie de la îndrumător | Confirmarea unui mod permis de colectare a datelor, a regulilor de etichetare pentru `ocupată` / `liberă` și a unei alternative dacă nu pot obține acces la camera unui robot. |

---

*Notă pentru Sprintul 1: secțiunile despre acces și exemplul real sunt marcate transparent ca neverificate. Înainte de Sprintul 2 trebuie examinat un exemplu real și pilotul trebuie să conțină doar date efectiv colectate și permise.*
