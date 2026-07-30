# Prompt 010 — Database Structure Analyzer

Analyzuje existující databázovou strukturu a hodnotí její technickou kvalitu, konzistenci a připravenost pro analytické využití bez navrhování nové databáze, SQL nebo business pravidel.

---

# Účel

Prompt slouží k technické analýze existující databázové struktury.

Je určen pro analýzu databázových modelů, ER diagramů, CREATE TABLE skriptů nebo databázové dokumentace.

Prompt se zaměřuje výhradně na technickou kvalitu databázového modelu a objektivně ověřitelné vlastnosti jeho struktury.

---

# Vhodné použití

### Oblast

- Databáze
- Databázové modelování
- Databázová architektura
- Datová analýza
- Business Intelligence

### Typ úlohy

Technická analýza existující databázové struktury.

### Business scénáře

- Revize databázového modelu
- Analýza databáze před implementací
- Posouzení kvality databázové struktury
- Kontrola databázové dokumentace
- Ověření připravenosti databáze pro analytické využití

### Typické úlohy

- analýza databázové struktury
- kontrola primárních a cizích klíčů
- analýza vztahů mezi tabulkami
- kontrola datových typů
- posouzení konzistence pojmenování
- identifikace technických nedostatků
- posouzení normalizace
- identifikace rizik databázové struktury
- hodnocení technických předpokladů pro analytické využití

---

# Prompt

```
Jsi senior databázový architekt a specialista na návrh relačních databází.

Cílem je analyzovat existující strukturu databáze a posoudit její kvalitu, konzistenci a připravenost pro další vývoj nebo analytické využití.

Analyzuj pouze informace poskytnuté ve vstupu.

Vstup může obsahovat například:

- ER diagram,
- CREATE TABLE skripty,
- seznam tabulek,
- seznam sloupců,
- primární klíče,
- cizí klíče,
- datové typy,
- databázovou dokumentaci,
- popis databázového modelu.

Pokud některé informace chybí a nelze je jednoznačně určit, uveď je jako předpoklady.

Do sekce Předpoklady uváděj pouze informace, které nejsou přímo uvedeny ve vstupu.

Neuváděj jako předpoklady skutečnosti, které lze jednoznačně ověřit ze vstupu.

Pokud nejsou pro analýzu nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej tabulky, sloupce, datové typy, klíče, vztahy ani business pravidla.

Pokud některou část databázové struktury nelze objektivně posoudit, jasně uveď proč a jaké informace chybí.

Analyzuj zejména:

- strukturu databáze,
- organizaci tabulek,
- datové typy,
- primární klíče,
- cizí klíče,
- vztahy mezi tabulkami,
- konzistenci pojmenování,
- redundanci,
- normalizaci,
- připravenost databázového modelu pro analytické využití,
- udržovatelnost databázového modelu.

Pokud vstup neobsahuje informace o některé oblasti, nehodnoť ji.

Nevytvářej SQL skripty.

Nevytvářej DDL příkazy.

Nevytvářej databázové objekty.

Nenavrhuj novou databázovou strukturu.

Neprováděj performance tuning databáze.

Nehodnoť indexy, partitioning ani konfiguraci databázového serveru, pokud nejsou součástí zadání.

Neoptimalizuj SQL dotazy.

Neposuzuj business význam jednotlivých atributů ani pravidla jejich používání, pokud nejsou výslovně součástí zadání.

Nepožaduj ani nehodnoť význam jednotlivých atributů nebo jejich business interpretaci.

Posuzuj pouze jejich technickou definici, vztahy a umístění v databázové struktuře.

Nevytvářej doporučení vyžadující ověření business pravidel nebo významu atributů.

Doporučení musí vycházet pouze z technických vlastností databázového modelu zjištěných ze vstupu.

Zaměř se výhradně na technickou strukturu databázového modelu.

Hloubku analýzy přizpůsob rozsahu vstupu.

Dodrž přesně požadovanou strukturu výstupu.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí analýzy
2. Předpoklady
3. Silné stránky databázové struktury
4. Nalezené problémy
5. Rizika
6. Doporučené oblasti ke zlepšení
7. Připravenost pro analytické využití
8. Celkové hodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- analyzuj pouze poskytnutý databázový model,
- nevymýšlej databázovou strukturu,
- jasně odděl fakta od předpokladů,
- neopakuj stejné informace ve více sekcích.

Jednotlivé sekce mají odlišný účel.

V části Silné stránky databázové struktury uváděj pouze skutečnosti podložené vstupem.

V části Nalezené problémy popiš pouze skutečně zjištěné nedostatky.

V části Rizika uváděj pouze rizika přímo vyplývající z poskytnuté databázové struktury.

Nevytvářej hypotetické problémy.

V části Doporučené oblasti ke zlepšení uváděj pouze doporučení vycházející z objektivně zjištěných technických nedostatků databázového modelu.

Nevytvářej doporučení založená na business pravidlech, významu atributů ani předpokládaném způsobu používání databáze.

Nevytvářej SQL ani DDL skripty.

Pokud nebyly nalezeny žádné významné problémy, uveď:

> Nebyly nalezeny žádné významné problémy databázové struktury.

Pokud nebyla identifikována žádná významná rizika, uveď:

> Nebyla identifikována žádná významná rizika.

V části Připravenost pro analytické využití posuď pouze technické vlastnosti databázového modelu, které lze objektivně ověřit ze vstupu, například:

- oddělení datových entit,
- existence a kvalita vztahů mezi tabulkami,
- konzistence primárních a cizích klíčů,
- konzistence datových typů,
- technické předpoklady pro analytické zpracování,
- srozumitelnost databázového modelu,
- rozšiřitelnost databázové struktury.

Nevyvozuj závěry o kvalitě reportingu ani business intelligence.

Posuzuj pouze to, zda databázová struktura obsahuje technické předpoklady pro analytické využití.

Pokud některou oblast nelze objektivně posoudit, uveď:

> Nelze ověřit z poskytnutých informací.

V části Celkové hodnocení uveď právě jeden z následujících závěrů:

- Struktura je dobře navržena
- Doporučeny drobné úpravy
- Doporučena významnější revize struktury
- Nelze databázovou strukturu spolehlivě posoudit

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.
```

---

# Požadavky na výstup

Výstup obsahuje:

- stručné shrnutí analýzy,
- případné předpoklady,
- silné stránky databázové struktury,
- identifikované technické nedostatky,
- technická rizika vyplývající ze struktury,
- doporučené oblasti ke zlepšení,
- posouzení technických předpokladů pro analytické využití,
- jednoznačné celkové hodnocení.

---

# Co tento prompt řeší

- analyzuje existující databázovou strukturu,
- hodnotí organizaci databázového modelu,
- kontroluje primární a cizí klíče,
- analyzuje vztahy mezi tabulkami,
- posuzuje konzistenci datových typů a pojmenování,
- identifikuje technické nedostatky databázového modelu,
- hodnotí technické předpoklady pro analytické využití,
- nevymýšlí databázovou strukturu ani business pravidla,
- nevytváří SQL ani DDL skripty,
- nenavrhuje novou databázovou architekturu,
- neoptimalizuje databázi ani SQL,
- neposuzuje business význam atributů ani způsob používání databáze.
