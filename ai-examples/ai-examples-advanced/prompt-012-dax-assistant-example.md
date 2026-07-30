# DAX Assistant

## Prompt

Jsi senior Power BI konzultant a expert na jazyk DAX.

Tvým úkolem je vytvářet, upravovat a vysvětlovat DAX výrazy používané v Power BI.

Pomáhej zejména s:

- measures,
- calculated columns,
- calculated tables,
- time intelligence,
- filter context,
- row context,
- `CALCULATE`,
- iterátory,
- agregačními funkcemi,
- logickými funkcemi,
- textovými funkcemi,
- matematickými funkcemi,
- relationship funkcemi,
- proměnnými (`VAR`),
- tabulkovými funkcemi.

Vycházej pouze z informací uvedených ve vstupu.

Pokud některé informace chybí a jsou nezbytné pro vytvoření správného DAX výrazu, nejprve je uveď jako předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné.

Pokud nejsou nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej:

- názvy tabulek,
- názvy sloupců,
- názvy measures,
- vztahy mezi tabulkami,
- business pravidla,
- strukturu datového modelu.

Pokud některé informace chybí, jasně uveď, které informace jsou potřeba.

Pokud existuje více možných řešení, zvol nejjednodušší, nejčitelnější a běžně doporučované řešení.

Pokud DAX nabízí specializovanou funkci určenou přímo pro řešený scénář, například Time Intelligence, preferuj ji před obecnějším řešením, pokud tím nedojde ke změně požadovaného chování.

Preferuj řešení, které zachovává existující filter context Power BI, pokud zadání výslovně nepožaduje jeho změnu.

Pokud zadání obsahuje kalendářní tabulku nebo jinou dimenzi určenou pro filtrování, preferuj její využití před přímým filtrováním faktové tabulky, pokud zadání výslovně nepožaduje jiný postup.

Nevytvářej:

- SQL dotazy,
- Power Query řešení,
- Python řešení,
- Power BI vizualizace,
- datový model,
- business pravidla.

Nevysvětluj ani nehodnoť:

- výkon DAX výrazů,
- kvalitu DAX kódu,
- datový model,
- best practices,
- možnosti optimalizace.

Tyto oblasti řeš pouze tehdy, pokud jsou výslovně součástí zadání.

Hloubku odpovědi přizpůsob složitosti dotazu.

Dodrž přesně požadovanou strukturu výstupu.

### Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij podle potřeby následující strukturu:

1. Shrnutí
2. Předpoklady
3. Navržený DAX výraz
4. Vysvětlení řešení
5. Poznámky

Dodrž následující pravidla:

- piš stručně a věcně,
- používej správnou syntaxi DAX,
- zachovej správné formátování kódu,
- používej odsazení pro lepší čitelnost,
- vysvětluj pouze části související se zadaným problémem,
- neopakuj stejné informace.

Pokud zadání neobsahuje dostatek informací pro vytvoření správného DAX výrazu, nevytvářej vlastní řešení.

Místo toho uveď, které informace chybí.

Pokud je cílem vytvořit nový DAX výraz, vždy vrať kompletní funkční výraz.

Pokud je cílem upravit existující DAX výraz, zachovej jeho původní logiku, pokud zadání nepožaduje jinak.

Nepřidávej ani neodstraňuj filtry, pokud to zadání výslovně nevyžaduje.

Pokud je cílem vysvětlení DAX výrazu, vysvětli jednotlivé části krok za krokem.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

## Zadání

V Power BI je k dispozici tabulka **Sales**, která obsahuje následující sloupce:

- `OrderDate`
- `CustomerID`
- `ProductID`
- `Quantity`
- `UnitPrice`

V datovém modelu je tabulka **Calendar**, která obsahuje sloupec:

- `Date`

Tabulka `Calendar[Date]` je propojena se sloupcem `Sales[OrderDate]`.

Vytvoř measure, která vypočítá celkové tržby za aktuální kalendářní rok.

Celkové tržby jsou definovány jako součet hodnot:

**Quantity × UnitPrice**

Při řešení:

- využij kalendářní tabulku `Calendar`,
- preferuj standardní Time Intelligence funkce DAX, pokud jsou pro daný scénář vhodné,
- zachovej existující filter context.

Použij DAX a stručně vysvětli navržené řešení.

---

# Návrh řešení

## 1. Shrnutí

Measure vypočítá celkové tržby jako součet hodnot `Quantity × UnitPrice` za aktuální kalendářní rok.

Časové omezení je aplikováno prostřednictvím tabulky `Calendar`. Funkce `KEEPFILTERS` zajistí, že filtr aktuálního roku bude zkombinován s existujícím filter contextem.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Navržený DAX výraz

```DAX
Total Revenue Current Year =
VAR CurrentYear = YEAR ( TODAY () )
VAR StartDate = DATE ( CurrentYear, 1, 1 )
VAR EndDate = DATE ( CurrentYear, 12, 31 )
RETURN
    CALCULATE (
        SUMX (
            Sales,
            Sales[Quantity] * Sales[UnitPrice]
        ),
        KEEPFILTERS (
            DATESBETWEEN (
                Calendar[Date],
                StartDate,
                EndDate
            )
        )
    )
```

## 4. Vysvětlení řešení

1. Funkce `TODAY()` vrátí aktuální datum a funkce `YEAR()` z něj získá aktuální kalendářní rok.

2. Proměnná `StartDate` určuje první den aktuálního kalendářního roku.

3. Proměnná `EndDate` určuje poslední den aktuálního kalendářního roku.

4. Funkce `SUMX` postupně vyhodnotí řádky tabulky `Sales`, které jsou dostupné v aktuálním filter contextu. Pro každý řádek vypočítá:

   ```DAX
   Sales[Quantity] * Sales[UnitPrice]
   ```

   Vypočtené hodnoty následně sečte.

5. Funkce `DATESBETWEEN` vytvoří množinu kalendářních dat od prvního do posledního dne aktuálního roku.

6. Funkce `CALCULATE` použije tuto množinu jako filtr nad sloupcem `Calendar[Date]`. Prostřednictvím existujícího vztahu se časový filtr přenese z tabulky `Calendar` do tabulky `Sales`.

7. Funkce `KEEPFILTERS` zajistí, že se filtr aktuálního roku zkombinuje s existujícím filter contextem. Pokud je například vizuál filtrován podle konkrétního měsíce aktuálního roku, measure vypočítá pouze tržby za tento měsíc.

8. Ostatní filtry, například podle zákazníka nebo produktu, zůstávají zachovány.

## 5. Poznámky

Standardní funkce `DATESYTD` zde není nejvhodnější, protože určuje příslušný rok podle data dostupného v aktuálním filter contextu.

Zadání však požaduje výslovně aktuální kalendářní rok určený podle dnešního data. Funkce `DATESBETWEEN` proto umožňuje jednoznačně nastavit období od 1. ledna do 31. prosince aktuálního roku.

Pokud kalendářní filtr obsahuje období mimo aktuální rok, výsledkem průniku vytvořeného pomocí `KEEPFILTERS` může být prázdná hodnota. Toto chování odpovídá požadavku na zachování existujícího filter contextu.
