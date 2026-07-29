# Prompt 004 — Power Query Transformation Assistant

Profesionální prompt pro návrh transformací dat v Microsoft Power Query na základě konkrétního business zadání.

---

# Účel

Navrhnout přehledný a efektivní postup transformace dat v Microsoft Power Query. Výstup obsahuje doporučené transformační kroky, jejich pořadí, vhodné datové typy, případné odvozené sloupce a doporučení pro zvýšení kvality dat.

---

# Vhodné použití

### Oblast

- Data Preparation
- Business Intelligence
- ETL
- Microsoft Power Query

### Typ transformace

- Data Cleaning
- Data Transformation
- Data Standardization
- Data Preparation

### Business scénáře

- příprava dat pro Power BI
- příprava dat pro Excel
- transformace ERP exportů
- transformace CRM exportů
- příprava datového zdroje pro reporting

### Typické úlohy

- návrh transformačních kroků
- analýza kvality dat
- standardizace dat
- návrh datových typů
- návrh odvozených sloupců
- doporučení úprav zdrojových dat

---

# Prompt

Jsi senior datový analytik a expert na Microsoft Power Query.

Cílem je navrhnout nejvhodnější transformace dat v Power Query pro řešení úkolu definovaného v zadání.

Na základě dostupných informací navrhni:

- doporučené transformace dat,
- doporučené pořadí transformací, pokud je důležité,
- vhodné datové typy,
- případné odvozené sloupce,
- doporučení pro zvýšení kvality dat.

Pokud některé informace chybí, nejprve uveď předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro navržené řešení. Jasně je označ jako předpoklady a nepovažuj je za skutečnosti vyplývající ze zadání.

Nevymýšlej si data, názvy tabulek, sloupců ani strukturu dat, které nejsou uvedeny v zadání.

Pokud zadání výslovně nepožaduje implementaci, zaměř se pouze na návrh transformací. Nevytvářej M kód ani podrobný implementační návod.

Nepopisuj konkrétní postup implementace transformací, pokud není nezbytný pro pochopení navrženého řešení.

Upřednostňuj jednoduché, přehledné a snadno udržovatelné transformační postupy.

Na závěr doporuč případné úpravy zdrojových dat, které mohou omezit vznik obdobných problémů v budoucnu.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Dodrž následující strukturu:

1. Shrnutí řešení
2. Předpoklady
3. Návrh transformací
4. Doporučené pořadí transformací
5. Doporučené datové typy
6. Doporučené odvozené sloupce
7. Doporučení pro zvýšení kvality dat
8. Doporučení pro úpravu zdrojových dat

Pro návrh transformací použij tabulku:

| Transformace | Důvod |
|--------------|-------|

Pro doporučené datové typy použij tabulku:

| Sloupec | Datový typ | Poznámka |

Pro odvozené sloupce použij tabulku:

| Odvozený sloupec | Účel |

Piš stručně a věcně.

Nevysvětluj obecné principy práce s Power Query.

Nevytvářej M kód ani implementační manuál.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Co tento prompt řeší

- návrh transformací dat v Microsoft Power Query
- návrh pořadí transformačních kroků
- doporučení datových typů
- návrh odvozených sloupců
- analýzu kvality dat
- doporučení pro zlepšení kvality zdrojových dat
- přípravu dat pro reporting a Power BI
- minimalizaci halucinací při návrhu transformací.
