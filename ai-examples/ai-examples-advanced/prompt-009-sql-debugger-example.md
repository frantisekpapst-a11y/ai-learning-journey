# Prompt 009 - SQL Debugger

## Zadání

### Business scénář

Vývojář vytvořil SQL dotaz pro interní reporting.

Při spuštění dotazu databáze vrací chybu a dotaz nelze úspěšně provést.

Tvým úkolem je identifikovat příčinu chyby, vysvětlit její důvod a navrhnout vhodný způsob odstranění.

Neprováděj code review.

Neoptimalizuj výkon SQL dotazu.

Neposuzuj business logiku.

Pokud zadání výslovně nepožaduje opravený SQL dotaz, neposkytuj nový SQL kód.

---

### Databázový systém

Microsoft SQL Server

---

### Chybové hlášení

```text
Msg 207, Level 16, State 1

Invalid column name 'TotalPrice'.
```

---

### SQL dotaz

```sql
SELECT
    CustomerID,
    SUM(TotalPrice) AS TotalSales
FROM Orders
GROUP BY CustomerID;
```

---

## 1. Shrnutí problému

SQL Server nemůže dotaz provést, protože v tabulce `Orders` nerozpoznal sloupec `TotalPrice`, který je použit v agregační funkci `SUM`.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Identifikovaná chyba

Jedná se o **chybu názvu objektu**, konkrétně o neplatný název sloupce.

SQL Server vrací chybu `Msg 207 – Invalid column name 'TotalPrice'`, která jednoznačně uvádí, že sloupec `TotalPrice` není v kontextu dotazu dostupný.

## 4. Pravděpodobná příčina

Tabulka `Orders` neobsahuje sloupec s přesným názvem `TotalPrice`, případně dotaz pracuje s jinou tabulkou `Orders`, než vývojář očekával.

Příčinou může být například:

- nesprávně napsaný název sloupce,
- odlišný skutečný název sloupce,
- změna databázové struktury,
- spuštění dotazu v jiné databázi nebo nad jiným schématem.

Z dostupných informací nelze určit, která z těchto možností konkrétně nastala.

## 5. Doporučené řešení

Je potřeba ověřit strukturu tabulky `Orders` v databázi a zjistit skutečný název sloupce obsahujícího cenu nebo hodnotu objednávky.

Následně je nutné:

1. nahradit odkaz na `TotalPrice` správným názvem existujícího sloupce, nebo
2. ověřit, zda je dotaz spuštěn ve správné databázi a používá očekávané schéma tabulky.

Pokud sloupec skutečně neexistuje, nelze agregaci provést, dokud nebude určeno, který existující sloupec má být sčítán.

## 6. Další potřebné informace

Pro určení správné úpravy je potřeba znát:

- seznam sloupců tabulky `Orders`,
- schéma, ve kterém se tabulka nachází,
- název databáze, ve které je dotaz spuštěn,
- sloupec, který má představovat celkovou hodnotu objednávky.

## 7. Celkové hodnocení

**Chyba jednoznačně identifikována**
