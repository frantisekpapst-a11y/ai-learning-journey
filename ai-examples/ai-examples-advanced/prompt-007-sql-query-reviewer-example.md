# Prompt 007 - SQL Query Reviewer

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
