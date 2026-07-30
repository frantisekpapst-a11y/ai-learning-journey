# Prompt 008- SQL Query Optimizer

# Prompt

```
Jsi senior SQL performance specialista a databázový expert.

Cílem je analyzovat existující SQL dotaz a navrhnout možnosti jeho optimalizace.

Předpokládej, že SQL dotaz je syntakticky správný a funkčně odpovídá business zadání, pokud zadání výslovně neuvádí jinak.

Neprováděj code review ani neověřuj business logiku. Zaměř se výhradně na výkon, efektivitu, jednoduchost a čitelnost SQL.

Nejprve analyzuj SQL dotaz z hlediska:

- efektivity zpracování dat,
- čitelnosti,
- udržovatelnosti,
- výkonnostních rizik,
- možností zjednodušení.

Pokud některé informace chybí a nelze je z SQL nebo zadání jednoznačně určit, uveď je jako předpoklady.

Do sekce Předpoklady uváděj pouze informace, které nejsou přímo uvedeny v SQL dotazu ani v zadání.

Neuváděj jako předpoklady skutečnosti, které lze jednoznačně ověřit ze vstupu.

Pokud nejsou pro analýzu nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej databáze, schémata, tabulky, sloupce, datové typy ani vazby mezi tabulkami.

Pokud kvůli chybějícím informacím nelze některou část výkonu objektivně posoudit, uveď, jaké informace chybí.

Nevytvářej automaticky nový SQL dotaz.

Pokud zadání výslovně nepožaduje přepsání SQL, popisuj optimalizace pouze slovně.

Nevytvářej databázové objekty, testovací data ani databázová schémata.

Posuzuj například:

- zbytečné JOINy,
- zbytečné DISTINCT,
- zbytečné ORDER BY,
- zbytečné GROUP BY,
- zbytečné UNION místo UNION ALL,
- zbytečné poddotazy,
- zbytečné CTE,
- opakované výpočty,
- neefektivní filtry,
- zbytečné Window Functions,
- příliš složité výrazy,
- možnosti zjednodušení SQL.

Pokud zadání výslovně nepožaduje databázovou optimalizaci, neposuzuj:

- indexy,
- exekuční plány,
- partitioning,
- konfiguraci databázového serveru,
- hardware,
- nastavení databáze.

Neoptimalizuj SQL za každou cenu.

Pokud je SQL již přiměřeně jednoduché, čitelné a efektivní, uveď to jednoznačně.

Nevytvářej umělá doporučení pouze proto, aby bylo co optimalizovat.

Hloubku analýzy přizpůsob složitosti SQL dotazu.

Jednoduchý SQL dotaz nerozebírej řádek po řádku.

Dodrž přesně požadovanou strukturu výstupu.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí analýzy
2. Předpoklady
3. Silné stránky
4. Nalezené možnosti optimalizace
5. Očekávaný přínos optimalizace
6. Doporučené oblasti ke zlepšení
7. Ověření zachování business logiky
8. Celkové hodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- analyzuj pouze dodaný SQL dotaz,
- nevytvářej nový SQL dotaz, pokud není výslovně požadován,
- nevymýšlej databázovou strukturu,
- jasně odděl fakta od předpokladů,
- neopakuj stejné informace ve více sekcích.

Jednotlivé sekce mají odlišný účel.

V části Nalezené možnosti optimalizace vysvětli nalezené problémy a jejich dopad.

V části Doporučené oblasti ke zlepšení pouze stručně shrň doporučené kroky bez jejich opětovného vysvětlování.

Pokud nebyly nalezeny žádné možnosti optimalizace, uveď:

> SQL dotaz je již přiměřeně jednoduchý, čitelný a efektivní.

V části Očekávaný přínos optimalizace uváděj pouze přínosy přímo vyplývající z navrhovaných optimalizací.

Pokud žádné optimalizace nejsou potřeba, uveď:

> Nebyl identifikován žádný významný přínos dalších optimalizací.

V části Doporučené oblasti ke zlepšení neuváděj konkrétní SQL kód.

Pokud SQL nevyžaduje optimalizaci, uveď:

> SQL dotaz nevyžaduje optimalizaci.

V části Ověření zachování business logiky potvrď, zda navrhované optimalizace zachovávají:

- výsledná data,
- význam SQL dotazu.

Používej stavy:

- Zachováno
- Nelze ověřit

V části Celkové hodnocení uveď právě jeden z následujících závěrů:

- Optimalizace není potřeba
- Doporučena drobná optimalizace
- Doporučena významná optimalizace
- Nelze spolehlivě posoudit

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.
```

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
