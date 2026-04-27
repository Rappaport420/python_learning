---
tags:
  - set
  - hashtable
  - unique_values
---
---

Sety (množiny) sú v Pythone mimoriadne efektívny nástroj. Ich hlavná sila pramení z toho, že sú postavené na **hashovacej tabuľke**, čo z nich robí bleskovo rýchleho strážcu unikátnosti.

Tu sú ich kľúčové vlastnosti a operácie, ktoré by si mal ako (budúci) Data Scientist ovládať:

### 1. Tri základné piliere Setu

- **Unikátnosť:** Set nikdy nedovolí duplicity.

- **Neusporiadanosť:** Prvky v sete nemajú poradie (index). Nemôžeš napísať `myset[0]`. Ak potrebuješ indexy, musíš použiť `list`.

- **Rýchlosť:** Kontrola prítomnosti prvku (`if x in myset`) trvá **$O(1)$**. Pri liste s miliónom prvkov by to trvalo celú večnosť ($O(n)$).


---

### 2. Matematické operácie

Sety v Pythone kopírujú matematickú teóriu množín pomocou intuitívnych operátorov:

|**Operácia**|**Operátor**|**Metóda**|**Čo to robí?**|
|---|---|---|---|
|**Prienik**|`&`|`.intersection()`|Čo majú obe množiny spoločné?|
|**Zjednotenie**|`\|`|`.union()`|Všetky prvky z oboch (bez duplicít).|
|**Rozdiel**|`-`|`.difference()`|Čo je v A, ale nie je v B.|
|**Symetrický rozdiel**|`^`|`.symmetric_difference()`|Prvky, ktoré sú len v jednej alebo len v druhej (nie v oboch).|
```
set1 = set(nums1)
set2 = set(nums2)

dif1 = set1 - set2
```
---

### 3. Modifikácia 

Na rozdiel od `tuple`, sety môžeš meniť:

- **`.add(x)`:** Pridá prvok. Ak tam už je, nič sa nestane.
    
- **`.remove(x)`:** Vymaže prvok. Ak tam nie je, Python hodí chybu (použi, keď si si istý, že tam je).
    
- **`.discard(x)`:** Vymaže prvok, ale ak tam nie je, **nehodí chybu** (bezpečnejšia voľba).
    
- **`.update([1, 2, 3])`:** Pridá viac prvkov naraz (napr. z listu).
    

---

### 4. Kedy Set v algoritmoch použiť

#### A. Rýchla deduplikácia

Najrýchlejší spôsob, ako dostať unikátne hodnoty z listu:

Python

```
unikaty = list(set(nums))
```

#### B. Kontrola "Videl som to už?"

Keď prechádzaš pole a potrebuješ si pamätať, ktoré čísla si už stretol, aby si ich nespracoval dvakrát.

Python

```
seen = set()
for n in nums:
    if n in seen:
        # už sme to riešili
    seen.add(n)
```

#### C. Membership Testing (Členstvo)

Ak máš zoznam 10 000 zakázaných ID a potrebuješ pri každom novom vstupe overiť, či je zakázané, **vždy** si tie ID premeň na `set`. Ušetríš tým kľudne 99 % času výpočtu.

---

### 5. Dôležité obmedzenie

Do setu môžeš vložiť len **nemenné (hashovateľné)** veci.

- **Môžeš:** čísla, stringy, tuple.
    
- **Nemôžeš:** listy, iné sety alebo slovníky.
    

**Pikoška:** Ak potrebuješ "set setov", existuje špeciálny typ `frozenset`, ktorý je nemenný a teda sa dá vložiť do iného setu.
