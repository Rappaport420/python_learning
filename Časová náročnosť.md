V praxi je doležite vediet ako sa počita časova naročnost algoritmu 

Big O meria, ako rýchlo rastie počet operácií so zvyšujúcim sa množstvom dát ($n$).

## Základná stupnica (Od najrýchlejšieho po najpomalšie)

#### 1. $O(1)$ – Konštantný čas (Constant Time)

- Operácia trvá rovnako dlho bez ohľadu na to, aký veľký je vstup.
- **Príklad:** Pozrieš sa na prvú stranu zoznamu. Je jedno, či má zoznam 10 strán alebo miliardu, pozrieť sa na prvú stranu je 1 úkon.
#### 2. $O(\log n)$ – Logaritmický čas (Logarithmic Time)

- S každým krokom zmenšíš problém na polovicu. Je to neskutočne rýchle.
- **Príklad:** **Binary Search**. Otvoríš zoznam v strede. Zistíš, že hľadané meno je v druhej polovici. Prvú zahodíš. Zvyšok znova poliť.

#### 3. $O(n)$ – Lineárny čas (Linear Time)

- **Čo to je:** Počet operácií rastie priamo úmerne s počtom dát.
- **Príklad:** Prelistuješ zoznam stranu po strane od začiatku až do konca.
- **V kóde:** Každý jednoduchý cyklus `for x in data:`.
    

#### 4. $O(n \log n)$ – Linearitmetický čas

- **Čo to je:** Štandard pre efektívne triedenie dát.
- **V kóde:** Pythonovský `data.sort()` (algoritmus Timsort).

#### 5. $O(n^2)$ – Kvadratický čas (Quadratic Time)

- "Zóna smrti" pre veľké dáta. Ak zdvojnásobíš dáta, čas sa štvornásobí.
- **Príklad:** Máš dva zoznamy a pre každú stranu v prvom zozname musíš prelistovať celý druhý zoznam.
- **V kóde:** Vnorené cykly `for i in data: for j in data:`.

### Ako odhadnúť zložitosť kódu (Rýchly návod)

Keď sa pozeráš na kód, drž sa týchto pravidiel:

1. **Iterácie sú násobky:** Jeden cyklus cez $n$ prvkov je $n$. Ak je v ňom ďalší cyklus cez $n$ prvkov, je to $n \times n = n^2$.
    
2. **Sčítanie nie je násobenie:** Ak máš dva cykly pod sebou (nie v sebe), je to $n + n = 2n$. V Big O konštanty (ako 2) zahadzujeme, takže je to stále len $O(n)$.
    
3. **Hľadáme "Worst Case":** Ak hľadáš v zozname a nájdeš to na prvýkrát, je to šťastie. Big O nás zaujíma pre najhorší možný prípad (prvok je na konci).
    
4. **Dominantný člen vyhráva:** Ak má tvoj algoritmus jednu časť $O(n^2)$ a druhú $O(n)$, celková zložitosť je $O(n^2)$. Tá menšia sa pri miliónoch dát stane zanedbateľnou.


> **Zlaté pravidlo Seniora:** Ak vidíš v Data Science kóde $O(n^2)$, vždy sa pýtaj: "Dá sa to nahradiť Hash Tabuľkou (Dict/Set) alebo zoradením (Sort)?" V 90 % prípadov je odpoveď **áno**.


