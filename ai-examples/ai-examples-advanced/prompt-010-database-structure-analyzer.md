# Prompt 010 - Database Structure Analyzer

# Zadání

## Business scénář

Byl ti předán návrh databázového modelu připravované aplikace pro správu objednávek.

Tvým úkolem je provést technickou analýzu databázové struktury.

Analyzuj výhradně informace uvedené ve vstupu.

Nevymýšlej chybějící tabulky, sloupce, datové typy, klíče, vztahy ani business pravidla.

Nevytvářej SQL dotazy.

Nevytvářej DDL skripty.

Nenavrhuj novou databázovou strukturu.

Neoptimalizuj databázi ani SQL.

Neposuzuj business význam jednotlivých atributů ani pravidla jejich používání.

Nevyvozuj závěry o způsobu používání databáze v aplikaci.

Posuzuj pouze technickou kvalitu databázového modelu.

Při analýze se zaměř zejména na:

- organizaci databázové struktury,
- datové typy,
- primární klíče,
- cizí klíče,
- vztahy mezi tabulkami,
- konzistenci pojmenování,
- redundanci,
- normalizaci,
- technické předpoklady databázového modelu pro analytické využití,
- udržovatelnost databázového modelu.

Nevyvozuj závěry o kvalitě reportingu ani business intelligence.

Posuzuj pouze technické vlastnosti databázové struktury, které lze objektivně ověřit ze vstupu.

Pokud některou oblast nelze objektivně posoudit, uveď proč.

---

## Databázová struktura

### Customers

| Sloupec | Datový typ | Klíč |
|---|---|---|
| CustomerID | INT | PK |
| FirstName | VARCHAR(50) | |
| LastName | VARCHAR(50) | |
| Email | VARCHAR(100) | |

### Orders

| Sloupec | Datový typ | Klíč |
|---|---|---|
| OrderID | INT | PK |
| CustomerID | INT | FK → Customers.CustomerID |
| OrderDate | DATE | |
| TotalAmount | DECIMAL(10,2) | |

### OrderItems

| Sloupec | Datový typ | Klíč |
|---|---|---|
| OrderItemID | INT | PK |
| OrderID | INT | FK → Orders.OrderID |
| ProductID | INT | |
| Quantity | INT | |
| UnitPrice | DECIMAL(10,2) | |

### Products

| Sloupec | Datový typ | Klíč |
|---|---|---|
| ProductID | INT | PK |
| ProductName | VARCHAR(100) | |
| Category | VARCHAR(50) | |
| Price | DECIMAL(10,2) | |

---

## Dostupné informace

K dispozici je pouze výše uvedená databázová struktura.

Nejsou dostupné:

- business požadavky,
- popis aplikace,
- pravidla validace dat,
- pravidla ukládání dat,
- význam jednotlivých atributů,
- funkční závislosti,
- databázová omezení nad rámec uvedených klíčů,
- hodnoty NULL,
- UNIQUE omezení,
- CHECK omezení,
- DEFAULT hodnoty,
- indexy,
- pohledy (Views),
- uložené procedury,
- triggery,
- databázový server,
- výkonové požadavky,
- vzorová data,
- dokumentace datového modelu.

Veškeré závěry musí vycházet výhradně z poskytnuté databázové struktury.

Pokud některou oblast nelze objektivně posoudit, výslovně to uveď a nevytvářej domněnky.

---

# 1. Shrnutí analýzy

Databázová struktura obsahuje čtyři přehledně oddělené tabulky pro zákazníky, objednávky, položky objednávek a produkty. Každá tabulka má definovaný jednoduchý primární klíč typu `INT`. U uvedených vazeb jsou datové typy primárních a cizích klíčů konzistentní.

Objektivně zjištěným nedostatkem je chybějící cizí klíč u sloupce `OrderItems.ProductID`, přestože tabulka `Products` obsahuje odpovídající primární klíč `ProductID`. Databázový model proto nevynucuje referenční integritu mezi položkami objednávek a produkty.

Kvůli omezenému rozsahu vstupu nelze úplně posoudit normalizaci, redundanci, pravidla přípustnosti hodnot ani integritu neklíčových atributů.

# 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

# 3. Silné stránky databázové struktury

- Datové entity jsou rozděleny do samostatných a srozumitelně pojmenovaných tabulek.
- Každá tabulka má jednoznačně definovaný primární klíč.
- Primární klíče používají jednotný datový typ `INT`.
- Existují explicitně definované vazby:
  - `Orders.CustomerID` → `Customers.CustomerID`,
  - `OrderItems.OrderID` → `Orders.OrderID`.
- Datové typy na obou stranách uvedených vazeb jsou shodné.
- Pojmenování tabulek, identifikátorů a ostatních sloupců je v rámci poskytnuté struktury převážně konzistentní a technicky srozumitelné.
- Peněžní hodnoty používají datový typ `DECIMAL(10,2)`, který umožňuje ukládat hodnoty s pevně stanoveným počtem desetinných míst.
- Datum objednávky používá samostatný datový typ `DATE`.

# 4. Nalezené problémy

Sloupec `OrderItems.ProductID` je definován jako `INT`, ale není u něj uveden cizí klíč odkazující na `Products.ProductID`.

Struktura tak obsahuje technicky odpovídající identifikátory produktu v obou tabulkách, jejich vztah však není na úrovni poskytnutého modelu explicitně definován ani vynucován.

Další problémy nelze z dostupných informací objektivně potvrdit.

# 5. Rizika

Chybějící cizí klíč u `OrderItems.ProductID` umožňuje z hlediska uvedené struktury vznik položek objednávek, jejichž hodnota `ProductID` nemá odpovídající záznam v tabulce `Products`.

To představuje riziko narušení referenční integrity mezi položkami objednávek a produkty. Při spojování těchto tabulek mohou záznamy bez odpovídajícího produktu vést k neúplným výsledkům analytického zpracování.

# 6. Doporučené oblasti ke zlepšení

Doporučuje se doplnit do databázového modelu explicitní vazbu mezi `OrderItems.ProductID` a `Products.ProductID` prostřednictvím cizího klíče.

Tím bude technicky vynucena referenční integrita mezi položkami objednávek a existujícími produkty a současně bude vztah jednoznačně zachycen v databázové struktuře.

Další doporučení nelze formulovat bez vytváření domněnek nad rámec poskytnutých informací.

# 7. Připravenost pro analytické využití

Databázový model obsahuje základní technické předpoklady pro analytické využití:

- data jsou rozdělena do samostatných entit,
- většina potřebných vztahů je explicitně definována,
- primární a uvedené cizí klíče používají konzistentní datové typy,
- názvy tabulek a sloupců jsou srozumitelné,
- struktura umožňuje technicky propojit zákazníky, objednávky, položky objednávek a produkty.

Připravenost však snižuje chybějící cizí klíč mezi `OrderItems` a `Products`, protože model nezajišťuje úplnou referenční integritu v celém řetězci vztahů.

Úplnou normalizaci a případnou redundanci nelze ověřit bez funkčních závislostí, pravidel ukládání dat a významu jednotlivých atributů.

Konzistenci pravidel pro hodnoty `NULL`, jedinečnost neklíčových atributů a přípustnost ukládaných hodnot nelze ověřit z poskytnutých informací.

# 8. Celkové hodnocení

**Doporučeny drobné úpravy.**
