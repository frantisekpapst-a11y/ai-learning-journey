# Prompt - SQL 03 - Database Structure Analyzer

# Prompt

```text
Jsi senior databázový architekt a specialista na návrh relačních databází.

Cílem je analyzovat existující strukturu databáze a posoudit její technickou kvalitu, konzistenci a připravenost pro analytické využití.

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

Absence informací ve vstupu sama o sobě nepředstavuje nalezený problém databázové struktury.

Pokud některou oblast nelze objektivně posoudit z důvodu chybějících informací, uveď tuto skutečnost pouze jako omezení analýzy.

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

Nevytvářej doporučení týkající se dokumentace databáze, procesů vývoje ani způsobu správy databáze, pokud to není výslovně součástí zadání.

Zaměř se výhradně na technickou strukturu databázového modelu.

Hloubku analýzy přizpůsob rozsahu vstupu.

Dodrž přesně požadovanou strukturu výstupu.

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

V části Nalezené problémy popiš pouze skutečně zjištěné technické nedostatky databázové struktury.

Neuváděj jako problém skutečnost, že některé informace nejsou součástí vstupu.

V části Rizika uváděj pouze rizika přímo vyplývající z poskytnuté databázové struktury.

Nevytvářej hypotetické problémy.

V části Doporučené oblasti ke zlepšení uváděj pouze doporučení vycházející z objektivně zjištěných technických nedostatků databázového modelu.

Nevytvářej doporučení založená na business pravidlech, významu atributů, dokumentaci databáze ani předpokládaném způsobu používání databáze.

Nevytvářej SQL ani DDL skripty.

Pokud nebyly nalezeny žádné významné problémy, uveď:

> Nebyly nalezeny žádné významné problémy databázové struktury.

Pokud nebyla identifikována žádná významná rizika, uveď:

> Nebyla identifikována žádná významná rizika.

V části Připravenost pro analytické využití posuď pouze technické vlastnosti databázového modelu, které lze objektivně ověřit ze vstupu.

Popisuj pouze objektivně ověřitelné technické vlastnosti databázového modelu.

Nevyvozuj závěry o vhodnosti databáze pro konkrétní typ analýz, reportingu ani business intelligence.

Pokud některou oblast nelze objektivně posoudit, uveď:

> Nelze ověřit z poskytnutých informací.

V části Celkové hodnocení uveď právě jeden z následujících závěrů:

- Struktura je dobře navržena
- Doporučeny drobné úpravy
- Doporučena významnější revize struktury
- Nelze databázovou strukturu spolehlivě posoudit

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.
```

# Zadání

## Business scénář

Byl předán návrh databázového modelu připravované aplikace pro správu objednávek.

Proveď technickou analýzu databázové struktury.

## Vstup

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

## Dostupné informace

K dispozici je pouze výše uvedená databázová struktura.

---

# Výstup

## 1. Shrnutí analýzy

Databázový model obsahuje čtyři přehledně oddělené tabulky pro zákazníky, objednávky, položky objednávek a produkty. Všechny tabulky mají definovaný primární klíč a model obsahuje dvě explicitně uvedené vazby prostřednictvím cizích klíčů.

Hlavním zjištěným nedostatkem je chybějící cizí klíč mezi `OrderItems.ProductID` a `Products.ProductID`. Databázová struktura proto nezajišťuje referenční integritu mezi položkami objednávek a produkty.

Z dostupných informací nelze posoudit zejména povinnost vyplnění sloupců, další integritní omezení ani jednoznačnost hodnot.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Silné stránky databázové struktury

- Každá tabulka má vlastní primární klíč typu `INT`.
- Vazba mezi `Orders.CustomerID` a `Customers.CustomerID` je explicitně definována cizím klíčem.
- Vazba mezi `OrderItems.OrderID` a `Orders.OrderID` je explicitně definována cizím klíčem.
- Datové typy propojených primárních a cizích klíčů jsou vzájemně konzistentní.
- Peněžní hodnoty používají pevnou desetinnou přesnost prostřednictvím typu `DECIMAL(10,2)`.
- Datum objednávky je uloženo pomocí datového typu `DATE`.
- Délky textových sloupců jsou explicitně omezeny.
- Pojmenování tabulek, identifikátorů a ostatních sloupců je konzistentní a srozumitelné.
- Oddělení zákazníků, objednávek, položek objednávek a produktů omezuje přímé opakování stejných entit v jednotlivých tabulkách.

## 4. Nalezené problémy

### Chybějící cizí klíč u produktu

Sloupec `OrderItems.ProductID` není definován jako cizí klíč odkazující na `Products.ProductID`, přestože tabulka `Products` obsahuje stejnojmenný primární klíč.

Model proto na úrovni deklarované databázové struktury nevynucuje existenci odpovídajícího produktu pro každou položku objednávky.

## 5. Rizika

Chybějící referenční integrita mezi tabulkami `OrderItems` a `Products` umožňuje vznik položek objednávek s hodnotou `ProductID`, která nemá odpovídající záznam v tabulce `Products`.

Takové záznamy mohou způsobit neúplné výsledky při propojování těchto tabulek, protože položku objednávky nebude možné přiřadit k existujícímu produktu.

## 6. Doporučené oblasti ke zlepšení

Doporučuje se doplnit referenční vazbu mezi `OrderItems.ProductID` a `Products.ProductID`.

Tím bude technicky zajištěno, že hodnota produktu uvedená v položce objednávky odpovídá existujícímu záznamu v tabulce `Products`.

Další doporučení nelze objektivně formulovat bez vytváření požadavků, které nevyplývají z poskytnuté databázové struktury.

## 7. Připravenost pro analytické využití

Model technicky umožňuje propojit:

- zákazníky s objednávkami,
- objednávky s jejich položkami.

Propojení položek objednávek s produkty lze provést podle sloupce `ProductID`, ale příslušná vazba není v databázové struktuře vynucena cizím klíčem. Konzistence tohoto propojení proto není zajištěna.

Databázový model obsahuje číselné hodnoty `TotalAmount`, `Quantity`, `UnitPrice` a `Price` a datum `OrderDate`, které mají explicitně uvedené datové typy. U peněžních hodnot je použita jednotná přesnost `DECIMAL(10,2)`.

Povinnost vyplnění sloupců, jednoznačnost hodnot a další integritní omezení:

> Nelze ověřit z poskytnutých informací.

## 8. Celkové hodnocení

**Doporučeny drobné úpravy**
