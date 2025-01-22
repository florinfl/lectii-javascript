20 sept

part1:

1. Instalare VS Code
2. Folosirea consolei browser-ului
3. Variabile, declarare, initializare, metode de denumire a variabilelor
4. Tipuri de date: Number, String, Boolean, undefined, null. Interactiuni folosind ferestre modale in browser: alert, prompt, confirm 
5. Conversii intre tipuri de date, conversii in String, in Number, in Boolean
6. Operatori matematici, precedenta celor mai importanti operatori. Conversia din String in numere pentru inmultire, scadere, impartire. Conversia in String pentru operatia de adunare / concatenare. Conversia automata in numere folosind operatorii unari. Operatorul virgula. Incrementare, decrementare.

part2:

7. Comparatii, comparatii intre string-uri, string-uri si numere, valori booleene si numere. Conversii automate pentru comparatii intre tipuri diferite de date
8. Instructiunea decizionala, cele doua tipuri if, if-else. Blocuri de instructiuni si greseli obisnuite de sintaxa. Conversii in boolean ale valorilor non-booleene folosite in conditii logice in instructiunea if. Inlantuiri de instructiuni if - else. Operatorul ternar
9. Expresii logice, operatori logici, utilizarile secundare ale operatorului OR atribuirea default si scurtcircuitarea. Negatia aplicata unei expresii logice complexe, analizarea efectului negatiei asupra expresiilor logice complexe
10. Operatorul "nullish coalescing", analizare situatii in care valorile "nullish" nu sunt tratate corespunzator cu operatorul OR
11. Instructiunea repetitiva, instructiunile while si for, asemanari, deosebiri, conversii. Intreruperea buclelor cu instructiunile break si continue.

part3:

12. Instructiunea switch
13. Functii: declarare, parametri. Variabile locale, externe, globale. Parametri formali, efectivi (parameters, arguments). Transfer prin valoare, referinta. Exemplu transfer referinta. Utilizare extensie AI Tabnine. Valori default. Returnarea valorilor din functii. Nume corecte pentru functii
18. Functii expresii: Lamurire privind domeniile de vizibilite. Expresii, functii expresie, cele doua faze de executie in Javascript, functii callback, functii returnate din alte functii, functii rulate "in place", IIFE, functii expresie returnate, stocate, rulate
19. Arrow functions


 part4: 
 
 20. Obiecte: doua metode de creare, obiecte de tip literal, cele doua metode de accesare proprietati - punct si paranteze patrate, computed properties, obiecte create direct cu variabile (property value shorthand), verificare apartenenta proprietate folosind operatorul "in", parcurgere obiect cu for..in, simulare vector folosind proprietati numerice, ordonarea automata a proprietatilor numerice, metoda de evitarea a ordonarii automate a proprietatilor numerice
 21. Obiecte vs primitive, accesarea obiectelor prin referinta, transfer valoare vs referinta, clonarea si combinarea obiectelor: shallow copy - copiere element cu element, operatorul spread,  Object.assign() / deep copy - JSON parse/stringify, structuredClone, functii recursive pentru copiere element cu element




!!!!!
De verificat
Valabil in toate lectiile: Cand este vorba de domenii de vizibilitate, cel mai probabil este vorba de domeniul de vizibilitate local al unei functii. Nu vom face referire direct la domeniul de vizibilitate pentru o variabila ci doar pentru functii. Mai multe lamuriri la inceputul lectiei 18.

Sectiunea 21, coloana 5 (de reluat la destructurare), shallow copy, operatorul spread: operatorul spread nu inverseaza valori, operatia de destructurare poate inversa valori: let a= 1,b =2;  [a,b] = [b,a];  sau   ({ c: b, d: a } = { c: a, d: b }); /  ({ b, a } = { b: a, a: b });  trebuie puse intre paranteze atribuirile cu obiecte pentru ca altfel le considera blocuri de instructiuni


La sectiunea 9, Conversii de tip Boolean:

Exista o exceptie pentru comparatii cu numere asa cum se vede la sectiunea 11 Comparatii (Comparatii cu valori booleene):

pentru numere  e invers, se converteste valoarea booleana in numar
