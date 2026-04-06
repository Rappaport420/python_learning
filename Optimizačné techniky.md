
## Dynamické programovanie (Dynamic Programming - DP)

Zatiaľ čo Greedy ide slepo za okamžitým ziskom, DP je o niečo inteligentnejšie. Rozloží problém na podproblémy, ich výsledky si zapamätá (**memoizácia**) a neskôr ich znova použije.

- **Kedy použiť:** Keď máš problém s "prekrývajúcimi sa podproblémami" (napr. výpočet Fibonacciho postupnosti, hľadanie najkratšej cesty v grafe, alebo problém batohu).
    
- **Kľúč k úspechu:** Ak vidíš, že počítaš tú istú vec viackrát, použi DP.
    

## 2. Rozdeľuj a panuj (Divide and Conquer)

Namiesto riešenia celku ho rozsekáš na menšie kusy, tie vyriešiš a potom výsledky spojíš.

- **Kedy použiť:** Triedenie dát (Merge Sort, Quick Sort), vyhľadávanie v usporiadaných zoznamoch (Binary Search).
    
- **Kľúč k úspechu:** Rekurzia je tvoj priateľ.
    

## 3. Backtracking (Návrat späť)

Je to v podstate inteligentné prehľadávanie všetkých možností hrubou silou. Ak zistíš, že aktuálna cesta nikam nevedie, vrátiš sa o krok späť a skúsiš inú vetvu.

- **Kedy použiť:** Riešenie puzzle (Sudoku), hľadanie ciest v bludisku, alebo pri problémoch, kde musíš splniť sadu obmedzení (Constraint Satisfaction).
    
- **Kľúč k úspechu:** Algoritmus "vyskúšaj a uvidíš".
    

## 4. Heuristické a Metaheuristické algoritmy

Niekedy je nájsť _dokonalé_ riešenie matematicky nemožné v rozumnom čase (tzv. NP-ťažké problémy). Vtedy nastupujú techniky, ktoré nájdu "dosť dobré" riešenie veľmi rýchlo.

- **Simulované žíhanie (Simulated Annealing):** Inšpirované metalurgiou, dovoľuje systému urobiť "krok späť" (horšie riešenie), aby sa nezasekol v lokálnom minime.
    
- **Genetické algoritmy:** Napodobňujú evolúciu (mutácie, kríženie, výber najsilnejších).
    
- **Kedy použiť:** Plánovanie zmien pre 500 zamestnancov, logistika kamiónov, dizajn čipov.
    

## 5. Gradientný zostup (Gradient Descent)

Absolútny kráľ moderného sveta, na ktorom stojí celé **strojové učenie a AI**.

- **Ako funguje:** Predstav si, že si v hmle na kopci a chceš ísť dole do údolia. Urobíš krok smerom, kde je najväčší sklon, a opakuješ to, kým nie si dole.
    
- **Kedy použiť:** Optimalizácia funkcií, trénovanie neurónových sietí.
    

---

### Rýchle porovnanie: Ktorý si vybrať?

|**Technika**|**Prístup**|**Hlavná výhoda**|**Hlavná nevýhoda**|
|---|---|---|---|
|**Greedy**|Berie najlepšie hneď teraz.|Super rýchly.|Často minie globálne maximum.|
|**DP**|Pamätá si minulosť.|Nájde globálne optimum.|Náročné na pamäť.|
|**Divide & Conquer**|Rozbije problém na kusy.|Efektívny pre veľké dáta.|Vyžaduje rekurziu.|
|**Backtracking**|Skúša všetky cesty.|Nájde všetko.|Môže byť extrémne pomalý.|
|**Gradient Descent**|Kráča smerom k zlepšeniu.|Zvláda milióny parametrov.|Môže sa zaseknúť v lokálnom minime.|

---

### Tip pre prax:

Ak riešiš bežný biznis problém, v 80 % prípadov ti stačí **Greedy** (pre jednoduchosť) alebo **Dynamické programovanie** (pre presnosť). Ak však robíš s dátovou vedou alebo komplexnou logistikou, tvojím denným chlebom bude **Gradient Descent** a **Heuristiky**.

Ktorá z týchto oblastí ťa zaujíma najviac? Môžem ti ukázať konkrétny kód alebo príklad.