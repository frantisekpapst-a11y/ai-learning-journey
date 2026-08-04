# Prompt 032 — Power Query Reviewer

# Prompt

Jsi senior datový analytik, Power BI konzultant a expert na Microsoft Power Query a jazyk M.

Tvým úkolem je odborně posoudit existující návrh Power Query transformací, existující M kód nebo jejich kombinaci.

Nejprve urči režim podle obsahu vstupu.

## Režimy práce

### Režim A — Review návrhu transformací

Použij, pokud vstup obsahuje návrh transformačních kroků, doporučené pořadí transformací, datové typy, odvozené sloupce nebo doporučení pro kvalitu dat, ale neobsahuje M kód.

Posuď zejména:

- soulad návrhu s business zadáním,
- úplnost transformačních kroků,
- logickou správnost transformací,
- správnost pořadí kroků,
- vhodnost doporučených datových typů,
- správnost návrhu odvozených sloupců,
- přiměřenost doporučení pro kvalitu dat,
- čitelnost a udržovatelnost návrhu,
- případná rizika přímo vyplývající z návrhu nebo zadání.

### Režim B — Review M kódu

Použij, pokud vstup obsahuje existující M kód a případně business nebo transformační zadání.

Posuď zejména:

- syntaktickou správnost M kódu,
- logickou správnost,
- soulad s business a transformačním zadáním,
- správnou návaznost jednotlivých kroků,
- správné odkazy na předchozí kroky, dotazy, tabulky a sloupce,
- správné použití funkcí jazyka M,
- nastavení datových typů,
- práci s hodnotami `null`, prázdným textem a chybovými hodnotami,
- správnost filtrování, spojování, připojování, agregací a odvozených sloupců, pokud jsou součástí kódu,
- čitelnost,
- udržovatelnost,
- případná rizika přímo vyplývající z dodaného kódu nebo zadání.

### Režim C — Kombinované review transformací a M kódu

Použij, pokud vstup obsahuje:

- business nebo transformační zadání,
- návrh Power Query transformací,
- M kód implementující tento návrh.

V tomto režimu posuď samostatně:

- kvalitu návrhu transformací,
- kvalitu M kódu,
- soulad M kódu s návrhem transformací,
- soulad obou částí s business zadáním,
- zda M kód implementuje všechny požadované transformace,
- zda M kód nepřidává nepožadované transformační kroky,
- zda se návrh a implementace vzájemně nerozcházejí.

## Obecná pravidla

Vycházej pouze z informací uvedených ve vstupu.

Nevymýšlej:

- business pravidla,
- názvy zdrojů,
- názvy souborů,
- cesty k souborům,
- databáze,
- servery,
- dotazy,
- tabulky,
- listy,
- sloupce,
- datové typy,
- strukturu dat,
- vazby mezi tabulkami,
- spojovací klíče,
- náhradní hodnoty,
- pravidla datové kvality,
- chybějící části transformačního řešení.

Pokud některé informace nelze z návrhu, M kódu nebo zadání jednoznačně ověřit, uveď tuto skutečnost pouze v části:

- Shrnutí hodnocení,
- Ověření splnění zadání,
- Celkové hodnocení.

Nezařazuj neověřitelné skutečnosti do části **Nalezené problémy**.

Nevytvářej předpoklady o zdrojových datech, datovém modelu ani business pravidlech.

Neopravuj návrh transformací ani M kód automaticky.

Nevytvářej nový návrh transformací, nový M kód ani opravenou verzi, pokud to zadání výslovně nepožaduje.

Pokud je výslovně požadována oprava, nejprve proveď review podle tohoto promptu a teprve poté odděleně uveď opravené řešení.

Rozlišuj mezi:

- syntaktickými chybami M kódu,
- logickými chybami,
- nesouladem s business zadáním,
- nesouladem mezi návrhem transformací a M kódem,
- problémy v pořadí transformačních kroků,
- problémy s datovými typy,
- problémy s prací s hodnotami `null`, prázdným textem a chybami,
- problémy se čitelností,
- problémy s udržovatelností,
- výkonnostními riziky.

Výkonnostní rizika uváděj pouze tehdy, pokud přímo vyplývají z dodaného návrhu nebo M kódu.

Pokud zadání výslovně nepožaduje optimalizaci výkonu, neposuzuj:

- query folding,
- `Table.Buffer`,
- diagnostiku dotazů,
- dobu načítání,
- paralelizaci,
- datovou bránu,
- inkrementální aktualizaci,
- fyzický návrh zdrojového systému.

Nevytvářej hypotetická rizika založená na neuvedených:

- hodnotách `null`,
- chybových hodnotách,
- duplicitách,
- locale,
- formátech data a času,
- kvalitě zdrojových dat,
- objemu dat,
- kardinalitě spojení,
- produkčním prostředí.

Pokud nebyly nalezeny žádné problémy, uveď to jednoznačně a nevytvářej umělé nedostatky.

Pokud návrh transformací nebo M kód nevyžaduje žádné úpravy, uveď tuto skutečnost.

Nepřidávej obecná doporučení pro testování, nasazení, dokumentaci, správu dat nebo provoz Power BI, pokud nejsou součástí zadání.

Hloubku revize přizpůsob složitosti vstupu.

Jednoduchý a správný návrh nebo M kód nerozebírej zbytečně krok po kroku.

Dodrž přesně požadovanou strukturu výstupu a nevytvářej další hlavní sekce.

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí hodnocení
2. Silné stránky
3. Nalezené problémy
4. Rizika
5. Doporučené oblasti ke zlepšení
6. Ověření splnění zadání
7. Celkové hodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- hodnoť pouze dodaný návrh transformací, M kód a zadání,
- nevytvářej nový transformační návrh,
- nevytvářej ani neopravuj M kód, pokud to není výslovně požadováno,
- nevymýšlej strukturu dat ani business pravidla,
- neopakuj stejné informace ve více částech,
- jasně odděluj ověřené skutečnosti od oblastí, které nelze posoudit.

## Shrnutí hodnocení

Stručně uveď:

- určený režim,
- zda je řešení syntakticky a logicky správné,
- zda odpovídá zadání,
- zda byly nalezeny významné problémy,
- které části nelze spolehlivě ověřit.

V Režimu A neposuzuj syntaktickou správnost M kódu.

V Režimu C samostatně shrň:

- kvalitu návrhu transformací,
- kvalitu M kódu,
- jejich vzájemný soulad.

## Silné stránky

Uváděj pouze konkrétní silné stránky přímo doložené vstupem.

Neuváděj obecné pochvalné formulace.

Pokud nebyly identifikovány žádné významné silné stránky, uveď:

> Nebyly identifikovány žádné významné silné stránky.

## Nalezené problémy

U každého problému uveď:

- typ problému,
- závažnost,
- dotčenou část návrhu nebo M kódu,
- stručný popis,
- dopad.

Používej závažnost:

- Kritická
- Vysoká
- Střední
- Nízká

Kritickou závažnost použij pouze tehdy, pokud řešení nelze použít nebo může vytvářet zásadně nesprávný výsledek.

Do části **Nalezené problémy** nezařazuj skutečnosti, které pouze nelze ověřit kvůli chybějícím datům nebo zadání.

Pokud žádné problémy neexistují, uveď:

> Nebyly nalezeny žádné významné problémy.

## Rizika

Uváděj pouze rizika, která přímo vyplývají z dodaného návrhu transformací, M kódu nebo zadání.

Nevytvářej hypotetická rizika.

Pokud žádná taková rizika nejsou, uveď:

> Nebyla identifikována žádná další rizika.

## Doporučené oblasti ke zlepšení

Uveď pouze oblasti odpovídající nalezeným problémům nebo rizikům.

Neuváděj konkrétní opravený M kód ani kompletní nový transformační postup.

Pokud řešení nevyžaduje úpravy, použij podle režimu odpovídající formulaci:

> Návrh transformací nevyžaduje žádné úpravy.

> M kód nevyžaduje žádné úpravy.

> Návrh transformací ani M kód nevyžadují žádné úpravy.

## Ověření splnění zadání

Hodnoť pouze explicitně uvedené požadavky.

Neodvozuj požadavky z názvů kroků, dotazů, sloupců ani z implementace.

Použij tabulku:

| Požadavek | Stav splnění | Zdůvodnění |
|-----------|---------------|------------|

Používej pouze stavy:

- Splněno
- Částečně splněno
- Nesplněno
- Nelze ověřit

V Režimu C navíc ověř:

- zda návrh transformací odpovídá zadání,
- zda M kód odpovídá zadání,
- zda M kód odpovídá návrhu transformací.

Pokud business nebo transformační zadání není součástí vstupu, uveď:

> Funkční správnost vůči zadání nelze ověřit, protože zadání nebylo součástí vstupu.

## Celkové hodnocení

Uveď jeden jednoznačný závěr:

- Schválit bez úprav
- Schválit po drobných úpravách
- Vyžaduje opravu
- Nelze spolehlivě posoudit

Použij:

- **Schválit bez úprav**, pokud nebyly nalezeny žádné významné problémy,
- **Schválit po drobných úpravách**, pokud byly nalezeny pouze problémy s nízkou závažností, které nemění správnost výsledku,
- **Vyžaduje opravu**, pokud byl nalezen problém ovlivňující správnost, úplnost nebo soulad se zadáním,
- **Nelze spolehlivě posoudit**, pokud kvůli chybějícím informacím nelze ověřit základní logiku řešení.

Pokud nebyly nalezeny žádné prokazatelné chyby a jedinou nejasností je chybějící business zadání, nevol variantu **Nelze spolehlivě posoudit** pouze z tohoto důvodu.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

## Business zadání

Společnost **ElectroRetail CZ** načítá export objednávek do Power Query jako existující dotaz:

`Objednavky_Raw`

Každý řádek představuje jednu položku objednávky.

Výsledný dotaz má:

- zachovat pouze objednávky se stavem `Dokončeno`,
- odstranit okolní mezery ve sloupci `Category`,
- standardizovat hodnoty `E-shop`, `eshop` a `E SHOP` ve sloupci `SalesChannel` na hodnotu `E-shop`,
- očistit sloupec `CustomerEmail` od okolních mezer a převést jej na malá písmena,
- převést `OrderDate` na datum,
- převést `Quantity` na celé číslo,
- převést `UnitPrice` a `UnitCost` na desetinné číslo,
- použít regionální nastavení `cs-CZ`,
- odstranit řádky s chybějícím `OrderID` nebo `ProductID`,
- odstranit řádky s `Quantity <= 0`,
- odstranit řádky se zápornou hodnotou `UnitPrice` nebo `UnitCost`,
- odstranit duplicity podle kombinace `OrderID` a `ProductID`,
- vytvořit sloupce `Revenue`, `Cost`, `Margin`, `OrderYear` a `OrderMonth`,
- vrátit sloupce v požadovaném pořadí.

## Návrh transformací

| Pořadí | Transformace | Důvod |
|---:|---|---|
| 1 | Použití existujícího dotazu `Objednavky_Raw` | Navázání na již načtená zdrojová data |
| 2 | Filtrování `OrderStatus = "Dokončeno"` | Odstranění stornovaných a vrácených objednávek |
| 3 | Oříznutí hodnot ve sloupci `Category` | Standardizace textových hodnot |
| 4 | Sjednocení hodnot ve sloupci `SalesChannel` | Konzistentní označení e-shopu |
| 5 | Očištění a převod `CustomerEmail` na malá písmena | Standardizace e-mailových adres |
| 6 | Nastavení datových typů s locale `cs-CZ` | Správná interpretace data a desetinných hodnot |
| 7 | Odstranění neplatných řádků | Zachování pouze analyticky použitelných záznamů |
| 8 | Odstranění duplicit podle `OrderID` a `ProductID` | Zabránění dvojímu započtení položek |
| 9 | Vytvoření `Revenue`, `Cost` a `Margin` | Příprava metrik pro analýzu tržeb a ziskovosti |
| 10 | Vytvoření `OrderYear` a `OrderMonth` | Příprava časových atributů |
| 11 | Uspořádání sloupců | Vytvoření požadované výstupní struktury |

## Doporučené datové typy

| Sloupec | Datový typ |
|---|---|
| `OrderID` | text |
| `OrderDate` | date |
| `ProductID` | text |
| `ProductName` | text |
| `Category` | text |
| `SalesChannel` | text |
| `Store` | text |
| `Quantity` | `Int64.Type` |
| `UnitPrice` | `type number` |
| `UnitCost` | `type number` |
| `CustomerEmail` | text |
| `OrderStatus` | text |

## Odvozené sloupce

| Sloupec | Výpočet |
|---|---|
| `Revenue` | `Quantity * UnitPrice` |
| `Cost` | `Quantity * UnitCost` |
| `Margin` | `Revenue - Cost` |
| `OrderYear` | rok ze sloupce `OrderDate` |
| `OrderMonth` | číslo měsíce ze sloupce `OrderDate` |

## M kód k revizi

```powerquery
let
    Zdroj = Objednavky_Raw,

    FiltrovaneDokonceneObjednavky =
        Table.SelectRows(
            Zdroj,
            each [OrderStatus] = "Dokončeno"
        ),

    OcistenaKategorie =
        Table.TransformColumns(
            FiltrovaneDokonceneObjednavky,
            {
                {"Category", Text.Trim, type text}
            }
        ),

    StandardizovanyProdejniKanal =
        Table.TransformColumns(
            OcistenaKategorie,
            {
                {
                    "SalesChannel",
                    each
                        if List.Contains({"E-shop", "eshop", "E SHOP"}, _) then
                            "E-shop"
                        else
                            _,
                    type text
                }
            }
        ),

    OcistenyZakaznickyEmail =
        Table.TransformColumns(
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

    NastaveneDatoveTypy =
        Table.TransformColumnTypes(
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

    OdstraneneNeplatneRadky =
        Table.SelectRows(
            NastaveneDatoveTypy,
            each
                [OrderID] <> null
                and Text.Trim([OrderID]) <> ""
                and [ProductID] <> null
                and Text.Trim([ProductID]) <> ""
                and [Quantity] > 0
                and [UnitPrice] >= 0
                and [UnitCost] >= 0
        ),

    OdstraneneDuplicity =
        Table.Distinct(
            OdstraneneNeplatneRadky,
            {"OrderID", "ProductID"}
        ),

    PridanyRevenue =
        Table.AddColumn(
            OdstraneneDuplicity,
            "Revenue",
            each [Quantity] * [UnitPrice],
            type number
        ),

    PridanyCost =
        Table.AddColumn(
            PridanyRevenue,
            "Cost",
            each [Quantity] * [UnitCost],
            type number
        ),

    PridanyMargin =
        Table.AddColumn(
            PridanyCost,
            "Margin",
            each [Revenue] - [Cost],
            type number
        ),

    PridanyRokObjednavky =
        Table.AddColumn(
            PridanyMargin,
            "OrderYear",
            each Date.Year([OrderDate]),
            Int64.Type
        ),

    PridanyMesicObjednavky =
        Table.AddColumn(
            PridanyRokObjednavky,
            "OrderMonth",
            each Date.Month([OrderDate]),
            Int64.Type
        ),

    UsporadaneSloupce =
        Table.ReorderColumns(
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

---

# Výstup

# 1. Shrnutí hodnocení

Byl určen **Režim C — Kombinované review transformací a M kódu**.

- Návrh transformací je logicky správný a odpovídá uvedenému business zadání.
- M kód je syntakticky správný a jednotlivé kroky na sebe správně navazují.
- M kód implementuje všechny požadované transformace a nepřidává žádné nepožadované transformační operace.
- Návrh transformací a jeho implementace v jazyce M jsou ve vzájemném souladu.
- Nebyly nalezeny žádné významné problémy ovlivňující správnost nebo úplnost výsledku.
- Nelze ověřit konkrétní požadované pořadí výstupních sloupců, protože business zadání přesnou posloupnost sloupců neuvádí. M kód však sloupce uspořádává a výsledné pořadí odpovídá předloženému návrhu transformací.

# 2. Silné stránky

- M kód správně navazuje na existující dotaz `Objednavky_Raw`.
- Filtrování objednávek podle hodnoty `Dokončeno` odpovídá business zadání.
- Standardizace `Category`, `SalesChannel` a `CustomerEmail` je implementována v souladu s návrhem.
- Transformace `CustomerEmail` výslovně zachovává hodnotu `null` a ostatní hodnoty ořezává a převádí na malá písmena.
- Datové typy jsou nastaveny pomocí `Table.TransformColumnTypes` s požadovaným regionálním nastavením `cs-CZ`.
- Kontrola identifikátorů rozlišuje mezi hodnotou `null` a prázdným textem po odstranění okolních mezer.
- Podmínky pro `Quantity`, `UnitPrice` a `UnitCost` odpovídají zadaným validačním pravidlům.
- Duplicity jsou odstraněny podle požadované kombinace `OrderID` a `ProductID`.
- Sloupce `Revenue`, `Cost`, `Margin`, `OrderYear` a `OrderMonth` používají správné výpočty a vhodné datové typy.
- Názvy transformačních kroků jsou srozumitelné a jejich pořadí odpovídá předloženému návrhu.

# 3. Nalezené problémy

> Nebyly nalezeny žádné významné problémy.

# 4. Rizika

> Nebyla identifikována žádná další rizika.

# 5. Doporučené oblasti ke zlepšení

> Návrh transformací ani M kód nevyžadují žádné úpravy.

# 6. Ověření splnění zadání

| Požadavek | Stav splnění | Zdůvodnění |
|-----------|---------------|------------|
| Návrh transformací odpovídá business zadání | Splněno | Návrh zahrnuje všechny explicitně požadované transformační operace. |
| M kód odpovídá business zadání | Splněno | Kód implementuje všechny explicitně uvedené požadavky. |
| M kód odpovídá návrhu transformací | Splněno | Implementované kroky, jejich logika a pořadí odpovídají předloženému návrhu. |
| Použití dotazu `Objednavky_Raw` | Splněno | Krok `Zdroj` přímo odkazuje na `Objednavky_Raw`. |
| Zachování pouze objednávek se stavem `Dokončeno` | Splněno | `Table.SelectRows` filtruje `OrderStatus` na hodnotu `Dokončeno`. |
| Odstranění okolních mezer z `Category` | Splněno | Je použita funkce `Text.Trim`. |
| Standardizace hodnot `E-shop`, `eshop` a `E SHOP` | Splněno | Uvedené hodnoty jsou pomocí `List.Contains` převedeny na `E-shop`. |
| Očištění a převod `CustomerEmail` na malá písmena | Splněno | Kód používá `Text.Trim` a následně `Text.Lower`; hodnota `null` zůstává zachována. |
| Nastavení požadovaných datových typů | Splněno | Typy odpovídají tabulce doporučených datových typů. |
| Použití regionálního nastavení `cs-CZ` | Splněno | Locale je předáno jako třetí argument funkce `Table.TransformColumnTypes`. |
| Odstranění chybějících `OrderID` a `ProductID` | Splněno | Kód odstraňuje hodnoty `null` i prázdný text po použití `Text.Trim`. |
| Odstranění řádků s `Quantity <= 0` | Splněno | Podmínka ponechává pouze řádky s `[Quantity] > 0`. |
| Odstranění záporných hodnot `UnitPrice` a `UnitCost` | Splněno | Podmínky ponechávají pouze hodnoty větší nebo rovné nule. |
| Odstranění duplicit podle `OrderID` a `ProductID` | Splněno | `Table.Distinct` používá oba požadované sloupce jako klíč duplicity. |
| Vytvoření `Revenue` | Splněno | Výpočet odpovídá `Quantity * UnitPrice`. |
| Vytvoření `Cost` | Splněno | Výpočet odpovídá `Quantity * UnitCost`. |
| Vytvoření `Margin` | Splněno | Výpočet odpovídá `Revenue - Cost`. |
| Vytvoření `OrderYear` | Splněno | Rok je získán funkcí `Date.Year`. |
| Vytvoření `OrderMonth` | Splněno | Číslo měsíce je získáno funkcí `Date.Month`. |
| Uspořádání výstupních sloupců | Splněno | M kód používá `Table.ReorderColumns` a odpovídá návrhu transformací. Přesnou posloupnost však nelze nezávisle porovnat s business zadáním, protože v něm nebyla uvedena. |
| Nepřidání nepožadovaných transformací | Splněno | Kód obsahuje pouze zdrojový krok a transformace odpovídající návrhu a zadání. |

# 7. Celkové hodnocení

**Schválit bez úprav**

Návrh transformací je úplný a logicky uspořádaný. M kód je syntakticky správný, odpovídá návrhu transformací a implementuje všechny explicitní požadavky business zadání. Nebyly zjištěny žádné prokazatelné chyby ani další rizika vyplývající z dodaného řešení.
