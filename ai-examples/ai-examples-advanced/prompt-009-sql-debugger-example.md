# Prompt 009 - SQL Debugger

# Zadání

## Business scénář

Vývojář vytvořil SQL dotaz pro interní reporting.

Při spuštění dotazu databáze vrací chybu a dotaz nelze úspěšně provést.

Proveď analýzu příčiny chyby.

---

## Databázový systém

Microsoft SQL Server

---

## Chybové hlášení

```text
Msg 207, Level 16, State 1

Invalid column name 'TotalPrice'.
```

---

## SQL dotaz

```sql
SELECT
    CustomerID,
    SUM(TotalPrice) AS TotalSales
FROM Orders
GROUP BY CustomerID;
```

---

## Dostupné informace

K dispozici jsou pouze chybové hlášení a SQL dotaz.

---

# Výstup

## 1. Shrnutí problému

SQL dotaz nelze v systému Microsoft SQL Server provést, protože odkazuje na neplatný název sloupce `TotalPrice`.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Identifikovaná chyba

Jedná se o **chybu názvu sloupce**.

SQL Server při zpracování výrazu `SUM(TotalPrice)` nedokázal v kontextu tabulky `Orders` rozpoznat sloupec s názvem `TotalPrice`. Tuto skutečnost přímo potvrzuje chybové hlášení:

> `Invalid column name 'TotalPrice'.`

## 4. Pravděpodobná příčina

Dotaz odkazuje na název sloupce `TotalPrice`, který SQL Server nepovažuje za platný sloupec dostupný v tabulce `Orders`.

Z poskytnutých informací nelze určit, jaký konkrétní název sloupce má být ve výrazu `SUM()` použit.

## 5. Doporučené řešení

Ověřte skutečnou strukturu tabulky `Orders` a název sloupce, který obsahuje částku určenou k agregaci.

Následně je potřeba odkaz `TotalPrice` nahradit správným existujícím názvem sloupce. Pokud měl sloupec `TotalPrice` v tabulce existovat, je nutné ověřit, zda byl dotaz spuštěn nad správnou databází, schématem a verzí tabulky.

Konkrétní opravený SQL dotaz nelze bez znalosti správného názvu sloupce spolehlivě sestavit.

## 6. Další potřebné informace

Pro určení konkrétní opravy je nutný seznam sloupců nebo definice tabulky `Orders`, zejména název sloupce obsahující hodnotu určenou k součtu.

## 7. Celkové hodnocení

**Chyba jednoznačně identifikována.**
