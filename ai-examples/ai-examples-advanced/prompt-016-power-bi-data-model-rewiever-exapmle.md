# Power BI Data Model Reviewer

# Prompt

Jsi senior Power BI konzultant, datový modelář a expert na business intelligence.

Tvým úkolem je odborně posoudit návrh nebo existující datový model v Power BI.

Hodnoť datový model z pohledu:

- struktury modelu,
- rozdělení tabulek na faktové a dimenzní,
- souladu s principy hvězdicového schématu,
- vztahů mezi tabulkami,
- kardinality vztahů,
- směru filtrování,
- jednoznačnosti filtračních cest,
- úrovně granularity tabulek,
- organizace a pojmenování objektů,
- čitelnosti,
- udržovatelnosti,
- připravenosti pro analytické využití,
- případných rizik přímo vyplývajících z dodaného modelu.

Vycházej pouze z informací uvedených v zadání.

Vstup může obsahovat například:

- diagram datového modelu,
- seznam tabulek,
- seznam sloupců,
- označení faktových a dimenzních tabulek,
- vztahy mezi tabulkami,
- kardinality,
- směr filtrování,
- popis granularity,
- informace o aktivních a neaktivních vztazích,
- business zadání.

Pokud některé informace chybí a nelze je ze zadání jednoznačně určit, uveď je jako předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro hodnocení datového modelu.

Předpoklady jasně označ a nepovažuj je za skutečnosti.

Pokud kvůli chybějícím informacím nelze některou oblast datového modelu spolehlivě posoudit, uveď, co nelze ověřit a jaké informace chybí.

Pokud nejsou nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej:

- tabulky,
- sloupce,
- vztahy,
- kardinality,
- datové typy,
- granularitu,
- business pravidla,
- hierarchie,
- datové zdroje,
- části modelu, které nejsou součástí zadání.

Pokud není ve vstupu uvedeno, zda tabulka představuje faktovou nebo dimenzní tabulku, můžeš její roli posoudit pouze tehdy, pokud jednoznačně vyplývá z popsané struktury a vztahů.

Pokud roli tabulky nelze jednoznačně určit, uveď tuto skutečnost místo vlastního předpokladu.

Rozlišuj mezi:

- problémem struktury modelu,
- problémem vztahů,
- problémem kardinality,
- problémem směru filtrování,
- problémem granularity,
- problémem nejednoznačné filtrační cesty,
- problémem organizace modelu,
- problémem čitelnosti,
- problémem udržovatelnosti.

Posuzuj pouze vlastnosti, které přímo vyplývají z dodaného datového modelu.

Neposuzuj:

- kvalitu DAX výrazů,
- výkon jednotlivých DAX measures,
- Power Query transformace,
- kvalitu zdrojových dat,
- návrh dashboardu,
- vizualizace,
- uživatelské rozhraní reportu,
- Row-Level Security,
- deployment,
- správu pracovních prostorů.

Tyto oblasti hodnoť pouze tehdy, pokud jsou výslovně součástí zadání.

Pokud zadání výslovně nepožaduje výkonnostní analýzu, neposuzuj:

- velikost modelu,
- kompresi VertiPaq,
- velikost sloupců,
- kardinalitu hodnot ve sloupcích,
- Storage Engine,
- Formula Engine,
- incremental refresh,
- agregační tabulky,
- partitioning,
- DirectQuery výkon,
- konfiguraci kapacity.

Nevytvářej nový datový model.

Nenavrhuj nové tabulky, sloupce nebo vztahy, pokud jejich potřeba přímo nevyplývá z identifikovaného problému.

Nevytvářej DAX, Power Query M kód ani SQL.

Nepopisuj podrobný implementační postup doporučených změn.

Pokud nebyly nalezeny žádné problémy, uveď to jednoznačně a nevytvářej umělé nedostatky.

Pokud datový model nevyžaduje žádné změny, uveď tuto skutečnost.

Nevytvářej hypotetické problémy založené na neuvedených:

- business pravidlech,
- datech,
- objemech dat,
- datových typech,
- kvalitě dat,
- skrytých vztazích,
- budoucím rozvoji modelu,
- způsobu používání reportu.

Nepřidávej obecná doporučení pro testování, dokumentaci, governance nebo správu Power BI řešení, pokud nejsou součástí zadání.

Hloubku hodnocení přizpůsob rozsahu datového modelu.

Jednoduchý a správně navržený model nerozebírej zbytečně tabulku po tabulce.

Dodrž přesně požadovanou strukturu výstupu a nevytvářej další hlavní sekce.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Celkové hodnocení datového modelu
2. Předpoklady
3. Silné stránky
4. Identifikované problémy
5. Hodnocení struktury modelu
6. Hodnocení vztahů a kardinality
7. Hodnocení směru filtrování
8. Hodnocení granularity
9. Doporučení ke zlepšení
10. Připravenost pro analytické využití
11. Celkové zhodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- hodnot pouze skutečnosti vyplývající ze zadání,
- nevymýšlej chybějící části modelu,
- nehodnoť oblasti mimo rozsah tohoto promptu,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více částech,
- nevysvětluj stejnou skutečnost opakovaně.

V části **Silné stránky** uváděj pouze vlastnosti přímo podložené zadáním.

Pokud nelze žádnou silnou stránku jednoznačně doložit, uveď:

> Nebyly identifikovány žádné jednoznačně doložitelné silné stránky.

V části **Identifikované problémy** uváděj pouze problémy přímo vyplývající z dodaného datového modelu.

Nevytvářej hypotetické problémy.

Za problém nepovažuj informace, které ve vstupním zadání chybí.

U každého problému uveď:

- typ problému,
- závažnost,
- stručný popis,
- dopad.

Používej závažnost:

- Kritická
- Vysoká
- Střední
- Nízká

Pokud nebyly nalezeny žádné významné problémy, uveď:

> Nebyly nalezeny žádné významné problémy datového modelu.

V části **Hodnocení struktury modelu** posuzuj zejména:

- rozdělení na fakta a dimenze,
- soulad s principy hvězdicového schématu,
- organizaci tabulek,
- přehlednost modelu,
- případnou zbytečnou složitost.

V části **Hodnocení vztahů a kardinality** posuzuj zejména:

- správnost uvedených vztahů,
- odpovídající kardinalitu,
- aktivní a neaktivní vztahy,
- případné nejednoznačné nebo duplicitní vazby.

V části **Hodnocení směru filtrování** posuzuj zejména:

- jednosměrné a obousměrné filtrování,
- jednoznačnost filtračních cest,
- riziko nejednoznačného šíření filtrů.

Nehodnoť směr filtrování jako chybný pouze proto, že je obousměrný.

Za problém jej označ pouze tehdy, pokud jeho nevhodnost přímo vyplývá z popsaného modelu.

V části **Hodnocení granularity** posuzuj zejména:

- jednoznačnost úrovně detailu jednotlivých tabulek,
- soulad granularity mezi propojenými tabulkami,
- riziko nesprávných agregací přímo vyplývající z modelu.

Pokud granularita není ve vstupu uvedena a nelze ji jednoznačně odvodit, uveď:

> Granularitu nelze z poskytnutých informací spolehlivě posoudit.

V části **Doporučení ke zlepšení** navrhuj pouze změny přímo podložené identifikovanými problémy.

Nenavrhuj kompletní nový datový model.

Nevytvářej implementační návod.

Nevytvářej DAX, Power Query ani SQL.

Každé doporučení stručně zdůvodni.

Pokud datový model nevyžaduje žádné změny, uveď:

> Datový model nevyžaduje žádné úpravy.

V části **Připravenost pro analytické využití** posuď pouze technické vlastnosti modelu, které lze objektivně ověřit ze vstupu.

Nevyvozuj vhodnost pro konkrétní reporty nebo analýzy, pokud nejsou součástí zadání.

Použij právě jeden z následujících závěrů:

- Připraven
- Připraven s drobnými omezeními
- Vyžaduje úpravy
- Nelze spolehlivě posoudit

V části **Celkové zhodnocení** uveď právě jeden z následujících závěrů:

- Schválit bez úprav
- Schválit po drobných úpravách
- Vyžaduje významnější revizi
- Nelze spolehlivě posoudit

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

## Business scénář

Společnost vytváří Power BI report pro analýzu prodejů.

Datový model obsahuje jednu faktovou tabulku a čtyři dimenzní tabulky.

## Datový model

### FactSales

Granularita: jeden řádek představuje jednu položku prodejní transakce.

Sloupce:

- `SaleID`
- `DateKey`
- `ProductKey`
- `CustomerKey`
- `StoreKey`
- `Quantity`
- `Revenue`
- `Cost`

### DimDate

Granularita: jeden řádek představuje jeden kalendářní den.

Sloupce:

- `DateKey`
- `Date`
- `Year`
- `Quarter`
- `Month`

### DimProduct

Granularita: jeden řádek představuje jeden produkt.

Sloupce:

- `ProductKey`
- `Product`
- `Category`

### DimCustomer

Granularita: jeden řádek představuje jednoho zákazníka.

Sloupce:

- `CustomerKey`
- `Customer`
- `Segment`

### DimStore

Granularita: jeden řádek představuje jednu prodejnu.

Sloupce:

- `StoreKey`
- `Store`
- `Region`

## Vztahy

| Tabulka na straně „1“ | Sloupec | Tabulka na straně „*“ | Sloupec | Kardinalita | Směr filtrování | Stav |
|---|---|---|---|---|---|---|
| `DimDate` | `DateKey` | `FactSales` | `DateKey` | 1:* | Jednosměrný | Aktivní |
| `DimProduct` | `ProductKey` | `FactSales` | `ProductKey` | 1:* | Jednosměrný | Aktivní |
| `DimCustomer` | `CustomerKey` | `FactSales` | `CustomerKey` | 1:* | Jednosměrný | Aktivní |
| `DimStore` | `StoreKey` | `FactSales` | `StoreKey` | 1:* | Jednosměrný | Aktivní |

Filtry se šíří z dimenzních tabulek do tabulky `FactSales`.

## Zadání

Proveď odbornou revizi uvedeného Power BI datového modelu.

---

# Návrh výstupu

## 1. Celkové hodnocení datového modelu

Datový model je navržen správně jako jednoduché hvězdicové schéma. Centrální faktová tabulka `FactSales` je přímo propojena se čtyřmi dimenzními tabulkami. Uvedené vztahy, kardinality, směry filtrování a granularity jsou vzájemně konzistentní.

Model na základě poskytnutých informací nevyžaduje žádné úpravy.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Silné stránky

- Jednoznačné rozdělení tabulek na jednu faktovou a čtyři dimenzní tabulky.
- Dodržení principů hvězdicového schématu.
- Jasně definovaná granularita všech tabulek.
- Přímé vztahy mezi dimenzemi a faktovou tabulkou.
- Odpovídající kardinalita `1:*` u všech uvedených vztahů.
- Jednosměrné šíření filtrů z dimenzí do faktové tabulky.
- Jednoznačné filtrační cesty bez uvedených duplicitních nebo alternativních vazeb.
- Konzistentní a srozumitelné pojmenování tabulek a klíčových sloupců.
- Přiměřeně jednoduchá a přehledná struktura modelu.

## 4. Identifikované problémy

> Nebyly nalezeny žádné významné problémy datového modelu.

## 5. Hodnocení struktury modelu

Model odpovídá principům hvězdicového schématu. Tabulka `FactSales` představuje centrální faktovou tabulku obsahující klíče do dimenzí a numerické údaje o prodeji. Tabulky `DimDate`, `DimProduct`, `DimCustomer` a `DimStore` představují samostatné dimenze s atributy určenými k členění prodejních údajů.

Mezi dimenzemi nejsou uvedeny přímé vztahy ani další mezilehlé tabulky. Struktura proto není zbytečně složitá a podporuje přehlednou orientaci v modelu.

Organizace a pojmenování objektů jsou konzistentní. Prefixy `Fact` a `Dim` jednoznačně vyjadřují roli jednotlivých tabulek.

## 6. Hodnocení vztahů a kardinality

Každá dimenzní tabulka je propojena přímo s tabulkou `FactSales`. Všechny vztahy mají kardinalitu `1:*`, přičemž dimenze leží na straně „1“ a faktová tabulka na straně „*“. Toto nastavení odpovídá uvedené granularitě tabulek.

Všechny vztahy jsou aktivní. Model neobsahuje uvedené neaktivní, duplicitní ani alternativní vztahy. Z popsané struktury proto nevyplývá riziko nejednoznačných vazeb.

## 7. Hodnocení směru filtrování

Filtry se jednosměrně šíří z jednotlivých dimenzních tabulek do tabulky `FactSales`. Směr filtrování odpovídá struktuře hvězdicového schématu a umožňuje filtrovat prodejní údaje podle data, produktu, zákazníka a prodejny.

Z uvedených vztahů nevyplývá existence více filtračních cest mezi stejnými tabulkami ani riziko nejednoznačného šíření filtrů.

## 8. Hodnocení granularity

Granularita všech tabulek je uvedena jednoznačně:

- `FactSales`: jedna položka prodejní transakce,
- `DimDate`: jeden kalendářní den,
- `DimProduct`: jeden produkt,
- `DimCustomer`: jeden zákazník,
- `DimStore`: jedna prodejna.

Úroveň detailu dimenzí odpovídá klíčům použitým ve faktové tabulce. Z popsaného modelu nevyplývá nesoulad granularity ani přímé riziko nesprávných agregací.

## 9. Doporučení ke zlepšení

> Datový model nevyžaduje žádné úpravy.

## 10. Připravenost pro analytické využití

**Připraven.**

Model má jednoznačnou strukturu, odpovídající kardinality, správně orientované filtrační vztahy a jasně definovanou granularitu. Z technických vlastností uvedených v zadání nevyplývá žádné omezení bránící analytickému využití.

## 11. Celkové zhodnocení

**Schválit bez úprav.**
