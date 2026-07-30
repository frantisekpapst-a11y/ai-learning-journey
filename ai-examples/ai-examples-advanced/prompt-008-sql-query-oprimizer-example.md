# Prompt 008- SQL Query Optimizer

# Zadání

## Business scénář

Vývojový tým vytvořil SQL dotaz pro interní reporting.

Dotaz již prošel code review a byl schválen jako funkčně správný.

## Databázový systém

Microsoft SQL Server

## SQL dotaz

```sql
SELECT DISTINCT
    c.CustomerID,
    c.FirstName,
    c.LastName,
    SUM(o.TotalAmount) AS TotalSales
FROM Customers c
INNER JOIN Orders o
    ON c.CustomerID = o.CustomerID
WHERE c.CustomerID IN (
    SELECT CustomerID
    FROM Orders
)
GROUP BY
    c.CustomerID,
    c.FirstName,
    c.LastName
ORDER BY
    TotalSales DESC;
```

---

# Návrh řešení

## 1. Shrnutí analýzy

SQL dotaz obsahuje dvě nadbytečné části:

- `DISTINCT`, protože jedinečnost výsledných řádků již zajišťuje `GROUP BY`,
- podmínku `WHERE c.CustomerID IN (...)`, protože zákazníci bez odpovídající objednávky jsou již vyloučeni pomocí `INNER JOIN`.

Jejich odstranění může dotaz zjednodušit a omezit zbytečné operace při jeho zpracování. Zbývající části dotazu jsou pro požadovanou agregaci přiměřeně jednoduché a čitelné.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Silné stránky

- Dotaz používá explicitní `INNER JOIN` s jasně definovanou podmínkou spojení.
- Agregace `SUM(o.TotalAmount)` je přehledná a srozumitelně pojmenovaná aliasem `TotalSales`.
- Sloupce mimo agregační funkci jsou uvedeny v `GROUP BY`.
- Řazení podle aliasu agregovaného sloupce zvyšuje čitelnost dotazu.
- Struktura dotazu je i přes nadbytečné části snadno pochopitelná a udržovatelná.

## 4. Nalezené možnosti optimalizace

### Nadbytečné použití `DISTINCT`

Klauzule `GROUP BY` již vytváří jeden výsledný řádek pro každou jedinečnou kombinaci následujících hodnot:

- `CustomerID`,
- `FirstName`,
- `LastName`.

Použití `DISTINCT` nad takto agregovaným výsledkem proto nemůže odstranit žádné další duplicity. V závislosti na zvoleném exekučním plánu může představovat zbytečnou operaci pro kontrolu nebo odstranění duplicit.

### Nadbytečný filtr s poddotazem

Podmínka:

```sql
WHERE c.CustomerID IN (
    SELECT CustomerID
    FROM Orders
)
```

ověřuje, zda má zákazník alespoň jeden odpovídající záznam v tabulce `Orders`.

Stejnou podmínku již fakticky zajišťuje použitý `INNER JOIN`. Zákazník bez odpovídající objednávky se do výsledku spojení nedostane, a proto je dodatečný filtr redundantní.

Poddotaz zbytečně komplikuje zápis a může vést k dodatečnému zpracování tabulky `Orders`, přestože Microsoft SQL Server může tuto redundanci při optimalizaci exekučního plánu rozpoznat.

### `ORDER BY` je opodstatněné

Řazení podle `TotalSales DESC` odpovídá požadavku na seřazení výsledků podle celkových tržeb od nejvyšší hodnoty. Ze zadání nevyplývá, že by bylo možné řazení odstranit, a proto není považováno za možnost optimalizace.

## 5. Očekávaný přínos optimalizace

- Jednodušší SQL dotaz s menším množstvím redundantní logiky.
- Lepší čitelnost a snadnější budoucí údržba.
- Potenciální omezení zbytečného vyhodnocování existence objednávek.
- Potenciální odstranění nadbytečné operace související s `DISTINCT`.
- Jednoznačnější vyjádření skutečnosti, že výběr zákazníků s objednávkami již zajišťuje `INNER JOIN`.

Konkrétní výkonnostní přínos nelze bez exekučního plánu a informací o objemu dat objektivně určit. Exekuční plán však podle zadání není předmětem této analýzy.

## 6. Doporučené oblasti ke zlepšení

- Odstranit nadbytečné `DISTINCT`.
- Odstranit redundantní filtr s poddotazem nad tabulkou `Orders`.
- Zachovat `INNER JOIN`, agregaci, seskupení a požadované řazení výsledků.

## 7. Ověření zachování business logiky

| Ověřovaná oblast | Stav |
|---|---|
| Výsledná data | Zachováno |
| Význam SQL dotazu | Zachováno |

Odstranění `DISTINCT` nezmění výsledná data, protože jejich granularitu již určuje `GROUP BY`.

Odstranění podmínky `WHERE ... IN (...)` rovněž nezmění výsledná data, protože existenci odpovídající objednávky již vyžaduje `INNER JOIN`.

## 8. Celkové hodnocení

**Doporučena drobná optimalizace**
