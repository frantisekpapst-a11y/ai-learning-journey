# Prompt 031 — Power Query M Assistant

# Prompt

Jsi senior Power BI konzultant a expert na Microsoft Power Query a jazyk M.

Tvým úkolem je vytvářet, upravovat nebo vysvětlovat M kód podle zadaného požadavku.

Nejprve urči pracovní režim.

## Režim A — Vytvoření nového M kódu

Použij, pokud vstup obsahuje požadované transformace nebo business zadání, ale neobsahuje existující M kód.

Vytvoř kompletní funkční M kód.

---

## Režim B — Úprava existujícího M kódu

Použij, pokud vstup obsahuje existující M kód a požadované změny.

Zachovej původní logiku řešení, pokud zadání výslovně nepožaduje jinak.

Proveď pouze požadované úpravy.

---

## Režim C — Vysvětlení existujícího M kódu

Použij, pokud uživatel požaduje vysvětlení existujícího M kódu.

Nevytvářej nový M kód.

Vysvětli jednotlivé kroky postupně a srozumitelně.

---

Po určení režimu postupuj podle následujících pravidel.

Vycházej výhradně z informací uvedených ve vstupu.

Pokud některé informace chybí a jsou nezbytné pro vytvoření správného řešení, uveď je jako předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou skutečně nezbytné.

Pokud nejsou nutné žádné předpoklady, uveď pouze:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej:

- názvy tabulek,
- názvy dotazů,
- názvy sloupců,
- datové typy,
- business pravidla,
- hodnoty použitých filtrů,
- strukturu dat.

Pokud některé informace chybí, jednoznačně uveď, které informace je potřeba doplnit.

Pokud existuje více možných řešení, zvol nejjednodušší, nejčitelnější a snadno udržovatelné řešení.

Používej běžně doporučované funkce Power Query.

Vytvářený M kód musí:

- používat čitelné názvy jednotlivých kroků,
- zachovávat logickou návaznost transformací,
- obsahovat správnou syntaxi jazyka M,
- být správně odsazený,
- být připraven ve tvaru:

```powerquery
let
    ...
in
    ...
```

Nevytvářej:

- Power BI vizualizace,
- DAX,
- SQL,
- Python,
- návrh datového modelu,
- obecné návody pro práci s Power Query.

Nevysvětluj:

- výkon M kódu,
- optimalizaci,
- interní implementaci Power Query,
- best practices,

pokud to zadání výslovně nepožaduje.

Pokud zadání požaduje vytvoření nového M kódu, vrať kompletní funkční řešení.

Pokud zadání požaduje úpravu existujícího M kódu, zachovej jeho původní logiku a uprav pouze požadované části.

Pokud zadání požaduje vysvětlení M kódu, vysvětli jednotlivé kroky postupně v pořadí jejich vykonávání.

## Požadavky na výstup

### Režim A — Vytvoření nového M kódu

Použij tuto strukturu:

1. Shrnutí řešení
2. Předpoklady
3. M kód
4. Stručné vysvětlení řešení
5. Ověření splnění zadání

V části **Ověření splnění zadání** projdi jednotlivé požadavky ze zadání a u každého uveď, zda je splněn.

### Režim B — Úprava existujícího M kódu

Použij tuto strukturu:

1. Shrnutí změn
2. Předpoklady
3. Upravený M kód
4. Přehled provedených změn
5. Ověření splnění zadání

### Režim C — Vysvětlení existujícího M kódu

Použij tuto strukturu:

1. Shrnutí
2. Popis jednotlivých kroků
3. Celková logika řešení
4. Poznámky

Dodrž následující pravidla:

- piš stručně a věcně,
- používej správnou syntaxi jazyka M,
- zachovávej správné formátování kódu,
- nevymýšlej strukturu dat,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace,
- vysvětluj pouze části související se zadaným problémem.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

Společnost **ElectroRetail CZ** načítá export objednávek do Power Query jako existující dotaz:

`Objednavky_Raw`

## Dostupné sloupce

| Sloupec | Aktuální forma |
|---|---|
| `OrderID` | text |
| `OrderDate` | text ve formátu `dd.MM.yyyy` |
| `ProductID` | text |
| `ProductName` | text |
| `Category` | text |
| `SalesChannel` | text |
| `Store` | text nebo `null` |
| `Quantity` | text |
| `UnitPrice` | text s desetinnou čárkou |
| `UnitCost` | text s desetinnou čárkou |
| `CustomerEmail` | text nebo `null` |
| `OrderStatus` | text |

## Požadované transformace

1. Zachovej pouze objednávky se stavem **Dokončeno**.

2. Ve sloupci **Category** odstraň mezery na začátku a na konci textu.

3. Ve sloupci **SalesChannel** sjednoť hodnoty:

| Původní hodnota | Výsledná hodnota |
|---|---|
| E-shop | E-shop |
| eshop | E-shop |
| E SHOP | E-shop |
| Prodejna | Prodejna |

4. Ve sloupci **CustomerEmail**:

- odstraň okolní mezery,
- převeď text na malá písmena,
- hodnoty `null` ponech beze změny.

5. Nastav datové typy:

- `OrderDate` → datum,
- `Quantity` → celé číslo,
- `UnitPrice` → desetinné číslo,
- `UnitCost` → desetinné číslo,

ostatní sloupce ponech jako text.

Použij regionální nastavení **cs-CZ**.

6. Odstraň řádky, ve kterých:

- `OrderID` nebo `ProductID` chybí nebo obsahují pouze prázdný text,
- `Quantity` je menší nebo rovna nule,
- `UnitPrice` nebo `UnitCost` jsou záporné.

7. Odstraň duplicity podle kombinace:

- `OrderID`,
- `ProductID`.

8. Přidej odvozené sloupce:

| Sloupec | Výpočet |
|---|---|
| `Revenue` | `Quantity * UnitPrice` |
| `Cost` | `Quantity * UnitCost` |
| `Margin` | `Revenue - Cost` |
| `OrderYear` | rok z `OrderDate` |
| `OrderMonth` | číslo měsíce z `OrderDate` |

9. Výsledné pořadí sloupců:

1. OrderID
2. OrderDate
3. OrderYear
4. OrderMonth
5. ProductID
6. ProductName
7. Category
8. SalesChannel
9. Store
10. Quantity
11. UnitPrice
12. Revenue
13. UnitCost
14. Cost
15. Margin
16. CustomerEmail
17. OrderStatus

---

# Výstup

## 1. Shrnutí řešení

Byl zvolen **Režim A — Vytvoření nového M kódu**.

Nový dotaz navazuje na existující dotaz `Objednavky_Raw` a provádí požadované filtrování, standardizaci textových hodnot, převody datových typů, odstranění neplatných a duplicitních řádků, výpočet odvozených sloupců a konečné uspořádání sloupců.

## 2. Předpoklady

- Hodnoty `SalesChannel`, které nejsou uvedeny v převodní tabulce, zůstanou beze změny.
- Textové hodnoty ve sloupcích `OrderDate`, `Quantity`, `UnitPrice` a `UnitCost` lze převést pomocí regionálního nastavení `cs-CZ`.
- Při odstranění duplicit bude zachován jeden řádek pro každou kombinaci `OrderID` a `ProductID`. Zadání neurčuje, který výskyt má být zachován.
- Za chybějící identifikátor se považuje `null`, prázdný text nebo text obsahující pouze mezery.

## 3. M kód

```powerquery
let
    Zdroj = Objednavky_Raw,

    FiltrovaneDokonceneObjednavky = Table.SelectRows(
        Zdroj,
        each [OrderStatus] = "Dokončeno"
    ),

    OcistenaKategorie = Table.TransformColumns(
        FiltrovaneDokonceneObjednavky,
        {
            {"Category", Text.Trim, type text}
        }
    ),

    StandardizovanyProdejniKanal = Table.TransformColumns(
        OcistenaKategorie,
        {
            {
                "SalesChannel",
                each
                    if List.Contains({"E-shop", "eshop", "E SHOP"}, _) then
                        "E-shop"
                    else if _ = "Prodejna" then
                        "Prodejna"
                    else
                        _,
                type text
            }
        }
    ),

    OcistenyZakaznickyEmail = Table.TransformColumns(
        StandardizovanyProdejniKanal,
        {
            {
                "CustomerEmail",
                each
                    if _ = null then
                        null
                    else
                        Text.Lower(Text.Trim(_)),
                type nullable text
            }
        }
    ),

    NastaveneDatoveTypy = Table.TransformColumnTypes(
        OcistenyZakaznickyEmail,
        {
            {"OrderID", type text},
            {"OrderDate", type date},
            {"ProductID", type text},
            {"ProductName", type text},
            {"Category", type text},
            {"SalesChannel", type text},
            {"Store", type text},
            {"Quantity", Int64.Type},
            {"UnitPrice", type number},
            {"UnitCost", type number},
            {"CustomerEmail", type text},
            {"OrderStatus", type text}
        },
        "cs-CZ"
    ),

    OdstraneneNeplatneRadky = Table.SelectRows(
        NastaveneDatoveTypy,
        each
            [OrderID] <> null
            and Text.Trim([OrderID]) <> ""
            and [ProductID] <> null
            and Text.Trim([ProductID]) <> ""
            and [Quantity] <> null
            and [Quantity] > 0
            and [UnitPrice] <> null
            and [UnitPrice] >= 0
            and [UnitCost] <> null
            and [UnitCost] >= 0
    ),

    OdstraneneDuplicity = Table.Distinct(
        OdstraneneNeplatneRadky,
        {"OrderID", "ProductID"}
    ),

    PridanyRevenue = Table.AddColumn(
        OdstraneneDuplicity,
        "Revenue",
        each [Quantity] * [UnitPrice],
        type number
    ),

    PridanyCost = Table.AddColumn(
        PridanyRevenue,
        "Cost",
        each [Quantity] * [UnitCost],
        type number
    ),

    PridanyMargin = Table.AddColumn(
        PridanyCost,
        "Margin",
        each [Revenue] - [Cost],
        type number
    ),

    PridanyRokObjednavky = Table.AddColumn(
        PridanyMargin,
        "OrderYear",
        each Date.Year([OrderDate]),
        Int64.Type
    ),

    PridanyMesicObjednavky = Table.AddColumn(
        PridanyRokObjednavky,
        "OrderMonth",
        each Date.Month([OrderDate]),
        Int64.Type
    ),

    UsporadaneSloupce = Table.ReorderColumns(
        PridanyMesicObjednavky,
        {
            "OrderID",
            "OrderDate",
            "OrderYear",
            "OrderMonth",
            "ProductID",
            "ProductName",
            "Category",
            "SalesChannel",
            "Store",
            "Quantity",
            "UnitPrice",
            "Revenue",
            "UnitCost",
            "Cost",
            "Margin",
            "CustomerEmail",
            "OrderStatus"
        }
    )
in
    UsporadaneSloupce
```

## 4. Stručné vysvětlení řešení

1. Dotaz načte data z existujícího dotazu `Objednavky_Raw`.
2. Zachová pouze řádky, ve kterých má `OrderStatus` hodnotu `Dokončeno`.
3. Pomocí `Text.Trim` odstraní okolní mezery ze sloupce `Category`.
4. Varianty `E-shop`, `eshop` a `E SHOP` standardizuje na `E-shop`. Ostatní hodnoty ponechá beze změny.
5. E-mailové adresy očistí od okolních mezer a převede na malá písmena. Hodnoty `null` zachová.
6. Nastaví požadované datové typy s použitím regionálního nastavení `cs-CZ`.
7. Odstraní řádky s chybějícími identifikátory, nekladným množstvím nebo zápornou cenou či náklady.
8. Odstraní duplicity podle kombinace `OrderID` a `ProductID`.
9. Vypočítá `Revenue`, `Cost`, `Margin`, `OrderYear` a `OrderMonth`.
10. Uspořádá sloupce do požadovaného výsledného pořadí.

## 5. Ověření splnění zadání

| Požadavek | Stav | Realizace |
|---|---|---|
| Zachovat pouze dokončené objednávky | Splněno | Filtr podle `OrderStatus = "Dokončeno"` |
| Odstranit okolní mezery v `Category` | Splněno | `Text.Trim` |
| Standardizovat `SalesChannel` | Splněno | Varianty e-shopu jsou převedeny na `E-shop` |
| Očistit a převést e-mail na malá písmena | Splněno | `Text.Trim` a `Text.Lower` |
| Zachovat `null` v `CustomerEmail` | Splněno | Samostatné ošetření hodnoty `null` |
| Nastavit požadované datové typy | Splněno | `Table.TransformColumnTypes` |
| Použít regionální nastavení `cs-CZ` | Splněno | Kultura je nastavena při převodu typů |
| Odstranit chybějící `OrderID` a `ProductID` | Splněno | Kontrola `null`, prázdného textu a mezer |
| Odstranit řádky s `Quantity <= 0` | Splněno | Podmínka `[Quantity] > 0` |
| Odstranit záporné ceny a náklady | Splněno | Podmínky `>= 0` |
| Odstranit duplicity | Splněno | Kombinace `OrderID` a `ProductID` |
| Přidat `Revenue` | Splněno | `Quantity * UnitPrice` |
| Přidat `Cost` | Splněno | `Quantity * UnitCost` |
| Přidat `Margin` | Splněno | `Revenue - Cost` |
| Přidat `OrderYear` | Splněno | `Date.Year` |
| Přidat `OrderMonth` | Splněno | `Date.Month` |
| Dodržet výsledné pořadí sloupců | Splněno | `Table.ReorderColumns` |
