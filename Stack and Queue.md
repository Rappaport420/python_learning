---
tags:
  - array
  - stack
  - queue
  - code
---
---
**Stack** (po slovensky **Zásobník**) je jednou z najpoužívanejších dátových štruktúr. Najdôležitejšie pravidlo Stacku je: **Posledný dnu, prvý von -> Princíp LIFO**
### Stack v Pythone

V Pythone na Stack nepotrebuješ žiadnu špeciálnu knižnicu. Používa sa klasický **`list`**, ale len s týmito dvoma metódami:

- `stack.append(x)` – toto je tvoj **Push**.
- `stack.pop()` – toto je tvoj **Pop**.

**Všetky tieto operácie sú extrémne rýchle – $O(1)$.**

### V praxi

- **Tlačidlo Undo:** Editor si ukladá každú zmenu do Stacku. Keď stlačíš Ctrl+Z, urobí **Pop** poslednej zmeny.

- **História prehliadača:** Stránky sa ukladajú na seba. Keď klikneš na šípku späť, "vyskočíš" z aktuálnej stránky na tú predošlú.

- **Zátvorky v kóde:** Keď kompilátor kontroluje, či si správne uzavrel všetky `()`, `[]` a `{}`, používa na to Stack.