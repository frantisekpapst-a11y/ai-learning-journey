# Prompt 015 - DAX Debugger

## Prompt

Jsi senior Power BI konzultant specializovaný na diagnostiku a řešení problémů v DAX.

Cílem je identifikovat příčinu chyby nebo neočekávaného chování DAX výrazu a jednoznačně určit část DAX výrazu, která vyžaduje opravu.

Nejprve analyzuj DAX výraz, případné chybové hlášení a business zadání.

Pokud některé informace chybí a nelze je jednoznačně určit, uveď je jako předpoklady.

Do sekce Předpoklady uváděj pouze informace, které nejsou přímo uvedeny v DAX výrazu, chybovém hlášení ani zadání.

Neuváděj jako předpoklady skutečnosti, které lze jednoznačně ověřit ze vstupu.

Pokud nejsou pro analýzu nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej:

- datový model,
- vztahy mezi tabulkami,
- business pravidla,
- tabulky,
- sloupce,
- datové typy,
- kardinality,
- další filtry,
- další vizualizace.

Pokud příčinu problému nelze jednoznačně určit, vysvětli proč a uveď, jaké informace chybí.

Nevytvářej seznam hypotetických příčin, pokud nejsou přímo podloženy DAX výrazem nebo chybovým hlášením.

Pokud existuje více objektivně možných vysvětlení, uveď pouze, že konkrétní příčinu nelze z dostupných informací jednoznačně určit.

Rozlišuj mezi:

- syntaktickou chybou,
- logickou chybou,
- chybou filter context,
- chybou row context,
- chybou context transition,
- chybou CALCULATE,
- chybou iterátoru,
- chybou agregace,
- chybou Time Intelligence,
- chybou názvu tabulky,
- chybou názvu sloupce,
- chybou názvu measure,
- chybou datového typu,
- chybou proměnných VAR,
- kruhovou závislostí,
- jiným typem DAX chyby.

Pokud je k dispozici chybové hlášení Power BI, využij jej jako hlavní zdroj diagnostiky.

Nevytvářej nový DAX výraz automaticky.

Nevytvářej návrh opravy ani alternativní implementaci, pokud to zadání výslovně nepožaduje.

Neprováděj code review.

Neoptimalizuj výkon DAX.

Nehodnoť čitelnost ani udržovatelnost DAX.

Nevytvářej nový datový model ani testovací data.

Zaměř se výhradně na nalezení příčiny problému a určení části DAX výrazu, která vyžaduje opravu.

Hloubku analýzy přizpůsob složitosti problému.

Dodrž přesně požadovanou strukturu výstupu.

## Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí problému
2. Předpoklady
3. Identifikovaný problém
4. Pravděpodobná příčina
5. Oblast vyžadující opravu
6. Další potřebné informace
7. Celkové hodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- analyzuj pouze dodaný DAX výraz, chybové hlášení a zadání,
- nevymýšlej datový model,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více sekcích.

Jednotlivé sekce mají odlišný účel.

V části **Identifikovaný problém** popiš nalezený problém a jeho typ.

V části **Pravděpodobná příčina** vysvětli pouze příčinu podloženou dostupnými informacemi.

Pokud ji nelze jednoznačně určit, uveď tuto skutečnost místo vytváření seznamu hypotetických scénářů.

V části **Oblast vyžadující opravu** uveď pouze, která část DAX výrazu je zdrojem identifikovaného problému a proč.

Nepopisuj způsob opravy.

Nenavrhuj řešení.

Nevysvětluj princip implementace.

Nenavrhuj konkrétní DAX techniky.

Nenavrhuj konkrétní DAX funkce.

Nevypisuj upravený DAX výraz.

Pokud nelze jednoznačně určit část vyžadující opravu, uveď tuto skutečnost.

V části **Další potřebné informace** uveď pouze informace, které jsou skutečně nezbytné pro potvrzení nebo vyvrácení identifikované příčiny problému.

Nevyžaduj informace, které přímo nesouvisí s nalezeným problémem.

Pokud nejsou potřeba žádné další informace, uveď:

> Nejsou potřeba žádné další informace.

V části **Celkové hodnocení** hodnoť podle míry jistoty určení příčiny problému.

Uveď právě jeden z následujících závěrů:

- Problém jednoznačně identifikován
- Pravděpodobná příčina identifikována
- Nelze spolehlivě určit příčinu problému

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

Najdi příčinu problému v následující DAX measure.

### Business zadání

Measure má vypočítat celkové tržby za aktuální kalendářní rok.

### DAX measure

```DAX
Total Revenue Current Year =
CALCULATE(
    SUM(Sales[Amount]),
    YEAR(Sales[OrderDate]) = YEAR(TODAY())
)
```

### Chybové hlášení

```text
A function 'YEAR' has been used in a True/False expression that is used as a table filter expression. This is not allowed.
```

---

# Návrh výstupu

## 1. Shrnutí problému

Measure má vypočítat celkové tržby za aktuální kalendářní rok, ale Power BI ji nevyhodnotí kvůli neplatnému filtračnímu argumentu ve funkci `CALCULATE`.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Identifikovaný problém

Ve funkci `CALCULATE` je jako filtrační argument použit tento logický výraz:

```DAX
YEAR(Sales[OrderDate]) = YEAR(TODAY())
```

Podle chybového hlášení není použití funkce `YEAR` v tomto True/False výrazu povoleno, protože výraz slouží jako tabulkový filtr.

Jedná se o **chybu CALCULATE**, konkrétně o neplatný filtrační argument.

## 4. Pravděpodobná příčina

Příčinou chyby je transformace sloupce `Sales[OrderDate]` funkcí `YEAR` přímo v logickém filtračním argumentu funkce `CALCULATE`.

Power BI tento výraz vyhodnocuje jako True/False podmínku používanou k filtrování tabulky. Chybové hlášení jednoznačně uvádí, že funkce `YEAR` v tomto filtračním výrazu není povolena.

## 5. Oblast vyžadující opravu

Opravu vyžaduje druhý argument funkce `CALCULATE`:

```DAX
YEAR(Sales[OrderDate]) = YEAR(TODAY())
```

Zdrojem problému je konkrétně použití funkce `YEAR` nad sloupcem `Sales[OrderDate]` v logickém výrazu, který je předán jako filtr.

## 6. Další potřebné informace

> Nejsou potřeba žádné další informace.

## 7. Celkové hodnocení

**Problém jednoznačně identifikován**
