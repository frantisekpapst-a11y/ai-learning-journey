# Prompt 008- SQL Query Optimizer

## Zadání

### Business scénář

Vývojový tým vytvořil SQL dotaz pro interní reporting.

Dotaz již prošel code review a byl schválen jako funkčně správný.

Úkolem není kontrolovat business logiku, správnost výsledků ani syntaxi SQL.

Posuď pouze možnosti optimalizace výkonu, efektivity, jednoduchosti a čitelnosti.

Pokud navrhneš optimalizaci, nesmí změnit výsledná data ani význam SQL dotazu.

---

### Databázový systém

Microsoft SQL Server

---

### SQL dotaz

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

## 1. Shrnutí analýzy

SQL dotaz obsahuje dvě nadbytečné konstrukce:

- `DISTINCT` je zbytečný, protože jedinečnost výsledných řádků již zajišťuje `GROUP BY`.
- Podmínka `WHERE c.CustomerID IN (...)` je zbytečná, protože `INNER JOIN` již omezuje výsledek na zákazníky s odpovídající objednávkou.

Jejich odstranění zjednoduší dotaz bez změny výsledných dat nebo jeho významu. Konkrétní výkonnostní přínos nelze bez znalosti objemu dat a způsobu zpracování dotazu objektivně vyčíslit.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Silné stránky

- Dotaz používá přímé spojení tabulek pomocí `INNER JOIN`.
- Agregace je provedena jednou funkcí `SUM` a odpovídajícím `GROUP BY`.
- Aliasy tabulek a agregovaného sloupce podporují čitelnost.
- Struktura dotazu je přehledná a snadno udržovatelná.
- Řazení používá srozumitelný alias `TotalSales`.

## 4. Nalezené možnosti optimalizace

### Nadbytečný `DISTINCT`

`GROUP BY` vytváří jeden výsledný řádek pro každou jedinečnou kombinaci seskupovaných hodnot. Následný `DISTINCT` proto již nemůže odstranit další duplicity.

Jeho uvedení zbytečně komplikuje zápis a může vyvolávat dojem, že dotaz řeší samostatný problém s duplicitami.

### Nadbytečný poddotaz v podmínce `WHERE`

Podmínka:

```sql
WHERE c.CustomerID IN (
    SELECT CustomerID
    FROM Orders
)
```

ověřuje, zda zákazník existuje v tabulce `Orders`. Stejnou podmínku již zajišťuje použitý `INNER JOIN`, protože zákazník bez odpovídající objednávky nemůže být součástí výsledku.

Poddotaz proto nepřináší další filtrování. Zvyšuje složitost zápisu a představuje redundantní požadavek na zpracování, přestože jej může optimalizátor SQL Serveru automaticky odstranit nebo zjednodušit.

## 5. Očekávaný přínos optimalizace

- Jednodušší struktura SQL dotazu.
- Lepší čitelnost a snazší údržba.
- Odstranění redundantních operací z logického zápisu dotazu.
- Potenciálně jednodušší zpracování dotazu databázovým optimalizátorem.

Význam skutečného výkonnostního přínosu nelze bez informací o objemu dat a způsobu zpracování dotazu spolehlivě určit.

## 6. Doporučené oblasti ke zlepšení

- Odstranit `DISTINCT`.
- Odstranit podmínku `WHERE c.CustomerID IN (...)`.
- Zachovat stávající `INNER JOIN`, agregaci, seskupení a řazení.

## 7. Ověření zachování business logiky

| Ověřovaná oblast | Stav |
|---|---|
| Výsledná data | Zachováno |
| Význam SQL dotazu | Zachováno |

Odstranění obou redundantních konstrukcí nemění zahrnuté zákazníky, vypočtené součty ani pořadí výsledných řádků.

## 8. Celkové hodnocení

**Doporučena drobná optimalizace**
