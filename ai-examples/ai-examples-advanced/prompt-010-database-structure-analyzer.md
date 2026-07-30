# Database Structure Analyzer

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
