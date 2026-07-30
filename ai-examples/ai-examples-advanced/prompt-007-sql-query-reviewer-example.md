# Prompt 007 - SQL Query Reviewer

# Prompt

Jsi senior SQL developer, code reviewer a datový analytik.

Cílem je provést odbornou revizi existujícího SQL dotazu.

Nejprve analyzuj SQL dotaz a posuď jeho:

- syntaktickou správnost,
- logickou správnost,
- soulad s business zadáním,
- čitelnost,
- udržovatelnost,
- případná rizika, která přímo vyplývají z dodaného SQL, datového modelu nebo zadání.

Pokud je součástí vstupu business požadavek, ověř, zda SQL dotaz splňuje všechny jeho části.

Pokud některé informace chybí a nelze je z SQL nebo zadání jednoznačně určit, uveď je jako předpoklady.

Předpoklady jasně označ a nepovažuj je za skutečnosti.

Nevymýšlej databáze, schémata, tabulky, sloupce, datové typy, vazby ani business pravidla, která nejsou uvedena ve vstupu.

Pokud kvůli chybějícím informacím nelze některou část SQL spolehlivě posoudit, uveď, co není možné ověřit a jaké informace chybí.

Neopravuj SQL dotaz automaticky.

Nevytvářej nový SQL dotaz ani opravenou verzi, pokud to zadání výslovně nepožaduje.

Nevytvářej databázové objekty, testovací data ani ukázková schémata.

Rozlišuj mezi:

- syntaktickými chybami,
- logickými chybami,
- nesouladem s business požadavky,
- problémy se čitelností,
- problémy s udržovatelností,
- výkonnostními riziky.

Výkonnostní rizika uváděj pouze tehdy, pokud přímo vyplývají z dodaného SQL.

Pokud zadání výslovně nepožaduje optimalizaci výkonu, neposuzuj:

- indexy,
- exekuční plány,
- fyzický návrh databáze,
- partitioning,
- konfiguraci databáze.

Uváděj pouze rizika, která přímo vyplývají z dodaného SQL, datového modelu nebo business zadání.

Nevytvářej hypotetická rizika založená na neuvedených:

- hodnotách NULL,
- stavech záznamů,
- měnách,
- pravidlech datové kvality,
- dodatečných sloupcích,
- procesech produkčního nasazení.

Pokud nebyly nalezeny žádné problémy, uveď to jednoznačně a nevytvářej umělé nedostatky.

Pokud nejsou potřebná žádná zlepšení, uveď, že SQL dotaz nevyžaduje úpravy.

Nepřidávej obecná doporučení pro produkční nasazení, testování nebo business ověření, pokud nejsou součástí zadání.

Hloubku revize přizpůsob složitosti SQL dotazu.

Jednoduchý a správný SQL dotaz nerozebírej řádek po řádku.

Dodrž přesně požadovanou strukturu výstupu a nevytvářej další hlavní sekce.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí hodnocení
2. Předpoklady
3. Silné stránky
4. Nalezené problémy
5. Rizika
6. Doporučené oblasti ke zlepšení
7. Ověření splnění zadání
8. Celkové hodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- hodnot pouze dodaný SQL dotaz, datový model a business zadání,
- nevytvářej nový SQL dotaz,
- neopravuj SQL, pokud to není výslovně požadováno,
- nevymýšlej databázovou strukturu ani business pravidla,
- jasně odděl předpoklady od faktů,
- rozlišuj závažnost nalezených problémů,
- nevytvářej další hlavní sekce,
- neopakuj stejné zjištění ve více částech.

V části **Nalezené problémy** u každého problému uveď:

- typ problému,
- závažnost,
- stručný popis,
- dopad.

Používej závažnost:

- Kritická
- Vysoká
- Střední
- Nízká

Pokud žádné problémy neexistují, uveď:

> Nebyly nalezeny žádné významné problémy.

V části **Rizika** uváděj pouze rizika, která přímo vyplývají z dodaného SQL nebo zadání.

Pokud žádná taková rizika nejsou, uveď:

> Nebyla identifikována žádná další rizika.

V části **Doporučené oblasti ke zlepšení** neuváděj konkrétní opravený SQL kód.

Pokud SQL dotaz nevyžaduje úpravy, uveď:

> SQL dotaz nevyžaduje žádné úpravy.

V části **Ověření splnění zadání** projdi jednotlivé business požadavky a u každého uveď:

- požadavek,
- stav splnění,
- stručné zdůvodnění.

Používej stavy:

- Splněno
- Částečně splněno
- Nesplněno
- Nelze ověřit

Pokud business zadání není součástí vstupu, uveď, že funkční správnost vůči business požadavkům nelze ověřit.

V části **Celkové hodnocení** uveď jednoznačný závěr:

- Schválit bez úprav
- Schválit po drobných úpravách
- Vyžaduje opravu
- Nelze spolehlivě posoudit

Výstup by měl odpovídat přibližně 1–2 stranám textu.

# Zadání

## Business scénář

Společnost provozuje e-commerce platformu a ukládá data o zákaznících a objednávkách do relační databáze.

Vývojář vytvořil SQL dotaz pro obchodní oddělení.

## Databázový systém

Microsoft SQL Server

---

## Datový model

### Customers

| Sloupec | Popis |
|---|---|
| `CustomerID` | Jedinečný identifikátor zákazníka |
| `FirstName` | Jméno zákazníka |
| `LastName` | Příjmení zákazníka |
| `City` | Město zákazníka |
| `Country` | Země zákazníka |

### Orders

| Sloupec | Popis |
|---|---|
| `OrderID` | Jedinečný identifikátor objednávky |
| `CustomerID` | Identifikátor zákazníka |
| `OrderDate` | Datum objednávky |
| `TotalAmount` | Celková hodnota objednávky |

---

## Vazby

- `Customers.CustomerID = Orders.CustomerID`

---

## Business požadavek

SQL dotaz má zobrazit:

- jméno zákazníka,
- příjmení zákazníka,
- město,
- počet objednávek,
- celkovou hodnotu objednávek,
- datum poslední objednávky.

Do výsledku mají být zahrnuti pouze zákazníci:

- kteří uskutečnili alespoň 5 objednávek,
- jejichž celková hodnota objednávek přesahuje 50 000 Kč.

Výsledek má být seřazen podle celkové hodnoty objednávek sestupně.

---

## SQL dotaz k revizi

```sql
SELECT
    c.FirstName,
    c.LastName,
    c.City,
    COUNT(o.OrderID) AS OrderCount,
    SUM(o.TotalAmount) AS TotalOrderAmount,
    MAX(o.OrderDate) AS LastOrderDate
FROM Customers AS c
INNER JOIN Orders AS o
    ON c.CustomerID = o.CustomerID
GROUP BY
    c.CustomerID,
    c.FirstName,
    c.LastName,
    c.City
HAVING
    COUNT(o.OrderID) >= 5
    AND SUM(o.TotalAmount) > 50000
ORDER BY
    TotalOrderAmount DESC;
```

---

# Návrh odborné revize

## 1. Shrnutí hodnocení

SQL dotaz je pro Microsoft SQL Server syntakticky správný, logicky konzistentní a splňuje všechny uvedené business požadavky.

Správně propojuje zákazníky s objednávkami, agreguje údaje na úroveň zákazníka, filtruje výsledné skupiny pomocí `HAVING` a řadí výsledek podle celkové hodnoty objednávek sestupně. Dotaz je přehledný a nevyžaduje úpravy.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Silné stránky

- `INNER JOIN` odpovídá požadavku zahrnout pouze zákazníky, kteří mají objednávky.
- Propojení tabulek používá vazbu uvedenou v datovém modelu.
- `COUNT(o.OrderID)` správně zjišťuje počet objednávek zákazníka.
- `SUM(o.TotalAmount)` vypočítává celkovou hodnotu objednávek.
- `MAX(o.OrderDate)` určuje datum poslední objednávky.
- `GROUP BY` vytváří samostatnou skupinu pro každého zákazníka prostřednictvím `CustomerID`.
- Agregační podmínky jsou správně umístěny v klauzuli `HAVING`.
- Podmínky přesně rozlišují „alespoň 5“ pomocí `>= 5` a „přesahuje 50 000“ pomocí `> 50000`.
- Výsledek je správně seřazen sestupně podle aliasu `TotalOrderAmount`.
- Názvy aliasů jsou srozumitelné a dotaz je dobře čitelný.

## 4. Nalezené problémy

> Nebyly nalezeny žádné významné problémy.

## 5. Rizika

> Nebyla identifikována žádná další rizika.

## 6. Doporučené oblasti ke zlepšení

> SQL dotaz nevyžaduje žádné úpravy.

## 7. Ověření splnění zadání

| Požadavek | Stav splnění | Stručné zdůvodnění |
|---|---|---|
| Zobrazit jméno zákazníka | Splněno | Dotaz vybírá `c.FirstName`. |
| Zobrazit příjmení zákazníka | Splněno | Dotaz vybírá `c.LastName`. |
| Zobrazit město zákazníka | Splněno | Dotaz vybírá `c.City`. |
| Zobrazit počet objednávek | Splněno | Počet je vypočítán pomocí `COUNT(o.OrderID)`. |
| Zobrazit celkovou hodnotu objednávek | Splněno | Celková hodnota je vypočítána pomocí `SUM(o.TotalAmount)`. |
| Zobrazit datum poslední objednávky | Splněno | Poslední datum je určeno pomocí `MAX(o.OrderDate)`. |
| Zahrnout pouze zákazníky s alespoň 5 objednávkami | Splněno | Podmínka `COUNT(o.OrderID) >= 5` odpovídá požadavku. |
| Zahrnout pouze zákazníky s celkovou hodnotou objednávek přesahující 50 000 Kč | Splněno | Podmínka `SUM(o.TotalAmount) > 50000` odpovídá požadavku. |
| Seřadit výsledek podle celkové hodnoty objednávek sestupně | Splněno | Použito je `ORDER BY TotalOrderAmount DESC`. |

## 8. Celkové hodnocení

**Schválit bez úprav.**
