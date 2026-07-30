# Prompt 007 - SQL Query Reviewer

# Zadání

## Business scénář

Společnost provozuje e-commerce platformu a ukládá data o zákaznících a objednávkách do relační databáze.

Vývojář vytvořil SQL dotaz pro obchodní oddělení.

Tvým úkolem je provést odbornou revizi existujícího SQL dotazu.

Nevytvářej nový ani opravený SQL dotaz.

---

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

~~~sql
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
~~~

---

# Odborná revize SQL dotazu

## 1. Shrnutí hodnocení

SQL dotaz je syntakticky i logicky správný pro Microsoft SQL Server a splňuje všechny uvedené business požadavky.

Dotaz správně:

- propojuje zákazníky s jejich objednávkami,
- vytváří souhrn za jednotlivé zákazníky,
- počítá objednávky,
- sčítá jejich celkovou hodnotu,
- určuje datum poslední objednávky,
- aplikuje obě požadované podmínky,
- řadí výsledek podle celkové hodnoty objednávek sestupně.

Nebyly nalezeny chyby ani nedostatky, které by vyžadovaly úpravu SQL dotazu.

## 2. Předpoklady

Pro provedení revize nejsou nutné žádné dodatečné předpoklady.

Posouzení vychází výhradně z uvedeného databázového systému, datového modelu, vazby mezi tabulkami a business požadavku.

## 3. Silné stránky

- Použití `INNER JOIN` odpovídá požadavku zahrnout pouze zákazníky, kteří uskutečnili objednávky.
- Propojení tabulek přes `Customers.CustomerID = Orders.CustomerID` odpovídá uvedené vazbě.
- Agregační funkce `COUNT`, `SUM` a `MAX` správně vytvářejí požadované zákaznické metriky.
- Podmínky nad agregovanými hodnotami jsou správně umístěny v klauzuli `HAVING`.
- Podmínka `COUNT(o.OrderID) >= 5` správně vyjadřuje alespoň pět objednávek.
- Podmínka `SUM(o.TotalAmount) > 50000` správně vyjadřuje překročení částky 50 000 Kč.
- Seskupení zahrnuje identifikátor zákazníka, takže zákazníci se stejným jménem, příjmením a městem nebudou nesprávně sloučeni.
- Alias `TotalOrderAmount` zlepšuje čitelnost výstupu a lze jej v Microsoft SQL Serveru použít v klauzuli `ORDER BY`.
- Struktura a formátování dotazu jsou přehledné a snadno udržovatelné.

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
| Zobrazit počet objednávek | Splněno | Počet objednávek počítá výraz `COUNT(o.OrderID)`. |
| Zobrazit celkovou hodnotu objednávek | Splněno | Celkovou hodnotu počítá výraz `SUM(o.TotalAmount)`. |
| Zobrazit datum poslední objednávky | Splněno | Nejnovější datum určuje výraz `MAX(o.OrderDate)`. |
| Zahrnout pouze zákazníky s alespoň pěti objednávkami | Splněno | Klauzule `HAVING` obsahuje podmínku `COUNT(o.OrderID) >= 5`. |
| Zahrnout pouze zákazníky s celkovou hodnotou objednávek přes 50 000 Kč | Splněno | Klauzule `HAVING` obsahuje podmínku `SUM(o.TotalAmount) > 50000`. |
| Seřadit výsledek podle celkové hodnoty objednávek sestupně | Splněno | Řazení zajišťuje `ORDER BY TotalOrderAmount DESC`. |

## 8. Celkové hodnocení

**Schválit bez úprav.**

SQL dotaz je pro zadaný datový model a business požadavek syntakticky správný, logicky konzistentní, čitelný a úplný.
