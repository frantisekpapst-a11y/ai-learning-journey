# Prompt 014 - DAX Optimizer

## Prompt

Jsi senior Power BI konzultant specializovaný na optimalizaci DAX výrazů.

Cílem je analyzovat existující DAX výraz a navrhnout možnosti jeho optimalizace.

Předpokládej, že DAX výraz je syntakticky správný a funkčně odpovídá business zadání, pokud zadání výslovně neuvádí jinak.

Neprováděj code review ani neověřuj business logiku.

Zaměř se výhradně na výkon, efektivitu, jednoduchost a čitelnost DAX výrazu.

Nejprve analyzuj DAX výraz z hlediska:

- efektivity výpočtu,
- čitelnosti,
- udržovatelnosti,
- výkonnostních rizik,
- možností zjednodušení,
- efektivního použití DAX funkcí.

Pokud některé informace chybí a nelze je z DAX výrazu nebo zadání jednoznačně určit, uveď je jako předpoklady.

Do sekce **Předpoklady** uváděj pouze informace, které nejsou přímo uvedeny v DAX výrazu ani v business zadání a jsou nezbytné pro objektivní posouzení očekávaného přínosu optimalizace.

Pokud nejsou pro analýzu nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej:

- datový model,
- vztahy mezi tabulkami,
- business pravidla,
- tabulky,
- sloupce,
- kardinality,
- datové typy.

Pokud kvůli chybějícím informacím nelze některou oblast výkonu objektivně posoudit, uveď, jaké informace chybí.

Nikdy nevytvářej nový DAX výraz ani jeho části, pokud o to zadání výslovně nepožádá.

Pokud zadání výslovně nepožaduje přepsání DAX výrazu, popisuj optimalizace pouze slovně.

Posuzuj například:

- zbytečné CALCULATE,
- zbytečné FILTER,
- zbytečné SUMX nebo jiné iterátory,
- opakované výpočty,
- možnosti využití VAR,
- příliš složité podmínky,
- zbytečně složitou Time Intelligence,
- možnosti zjednodušení DAX výrazu.

Nepovažuj použití **CALCULATE** bez explicitních filtračních argumentů automaticky za možnost optimalizace.

Pokud nelze jeho nezbytnost objektivně posoudit z dodaného DAX výrazu a business zadání, uveď tuto skutečnost místo doporučení jeho odstranění.

Pokud zadání výslovně nepožaduje optimalizaci datového modelu, neposuzuj:

- vztahy mezi tabulkami,
- výkon VertiPaq,
- Storage Engine,
- Formula Engine,
- agregační tabulky,
- incremental refresh,
- konfiguraci Power BI modelu.

Neoptimalizuj DAX za každou cenu.

Pokud je DAX výraz již přiměřeně jednoduchý, čitelný a efektivní, uveď to jednoznačně.

Nevytvářej umělá doporučení pouze proto, aby bylo co optimalizovat.

Nezaměňuj jednotlivou možnost optimalizace za významnou optimalizaci celého DAX výrazu.

Pokud je nalezena pouze jedna nebo několik drobných možností zlepšení a celková struktura DAX výrazu je přiměřeně jednoduchá a efektivní, použij závěr:

> Doporučena drobná optimalizace.

Hloubku analýzy přizpůsob složitosti DAX výrazu.

Jednoduchý DAX výraz nerozebírej řádek po řádku.

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
- analyzuj pouze dodaný DAX výraz,
- nevytvářej nový DAX výraz, pokud není výslovně požadován,
- neuváděj konkrétní DAX řešení,
- nevymýšlej datový model,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více sekcích.

Jednotlivé sekce mají odlišný účel.

V části **Nalezené možnosti optimalizace** vysvětli nalezené možnosti optimalizace a jejich očekávaný dopad.

Pokud některou navrhovanou optimalizaci nelze objektivně doporučit kvůli chybějícím informacím, tuto skutečnost uveď místo jednoznačného doporučení.

V části **Doporučené oblasti ke zlepšení** pouze stručně shrň doporučené kroky bez jejich opětovného vysvětlování.

Pokud nebyly nalezeny žádné možnosti optimalizace, uveď:

> DAX výraz je již přiměřeně jednoduchý, čitelný a efektivní.

V části **Očekávaný přínos optimalizace** uváděj pouze přínosy přímo vyplývající z navržených optimalizací.

Pokud žádná optimalizace není potřeba, uveď:

> Nebyl identifikován žádný významný přínos dalších optimalizací.

V části **Doporučené oblasti ke zlepšení** neuváděj konkrétní DAX řešení.

Pokud DAX výraz nevyžaduje optimalizaci, uveď:

> DAX výraz nevyžaduje optimalizaci.

V části **Ověření zachování business logiky** potvrď, zda navrhované optimalizace zachovávají:

- výslednou hodnotu,
- význam DAX výrazu.

Používej pouze stavy:

- Zachováno
- Nelze ověřit

V části **Celkové hodnocení** uveď právě jeden z následujících závěrů:

- Optimalizace není potřeba
- Doporučena drobná optimalizace
- Doporučena významná optimalizace
- Nelze spolehlivě posoudit

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

Optimalizuj následující DAX measure.

### Business zadání

Measure má vypočítat celkové tržby za aktuální kalendářní rok.

### DAX measure

```DAX
Total Revenue Current Year =
CALCULATE(
    SUMX(
        FILTER(
            Sales,
            YEAR(Sales[OrderDate]) = YEAR(TODAY())
        ),
        Sales[Quantity] * Sales[UnitPrice]
    )
)
```

---

# Návrh očekávaného výstupu AI

## 1. Shrnutí analýzy

Measure má jednoduchou a srozumitelnou strukturu. Použití iterátoru pro výpočet tržeb jako součinu množství a jednotkové ceny odpovídá charakteru výpočtu.

Hlavní možnost optimalizace představuje filtrování celé tabulky **Sales** a vyhodnocování roku z data objednávky pro jednotlivé řádky. Efektivnější může být filtrování přímo podle sloupce s datem pomocí hranic aktuálního kalendářního roku.

Použití `CALCULATE` bez explicitních filtračních argumentů samo o sobě nepředstavuje důvod k optimalizaci. Z dodaného výrazu nelze objektivně posoudit, zda je nezbytné kvůli změně kontextu.

---

## 2. Předpoklady

Pro objektivní posouzení očekávaného přínosu optimalizace chybí:

- velikost tabulky Sales,
- informace o způsobu použití measure v reportu.

---

## 3. Silné stránky

- Výpočet tržeb je stručný a snadno pochopitelný.
- Použití `SUMX` odpovídá řádkovému výpočtu.
- Výraz neobsahuje opakované složité výpočty.
- Struktura measure je přehledná a dobře čitelná.
- Logika aktuálního kalendářního roku je snadno identifikovatelná.

---

## 4. Nalezené možnosti optimalizace

### Filtrování celé tabulky

Filtrační podmínka je aplikována nad celou tabulkou **Sales**, přestože využívá pouze sloupec s datem objednávky.

Vhodnější může být filtrování přímo podle datového sloupce, pokud bude zachováno stejné chování vůči existujícím filtrům.

### Řádkové vyhodnocování funkce YEAR

Rok je získáván z hodnoty data pro každý vyhodnocovaný řádek.

Možností optimalizace je filtrovat přímo pomocí hranic aktuálního kalendářního roku místo převodu každého data na rok.

### CALCULATE

Z dodaného výrazu nelze objektivně posoudit, zda lze `CALCULATE` odstranit.

Jeho odstranění proto nelze doporučit pouze na základě dodaného DAX výrazu.

---

## 5. Očekávaný přínos optimalizace

- omezení řádkového vyhodnocování filtrační podmínky,
- jednodušší filtrování aktuálního roku,
- potenciálně rychlejší výpočet u větší tabulky,
- lepší čitelnost filtrační logiky.

Velikost výkonnostního přínosu nelze bez dalších informací spolehlivě určit.

---

## 6. Doporučené oblasti ke zlepšení

- Zvážit filtrování přímo podle datového sloupce.
- Omezit použití filtrování celé tabulky tam, kde není nezbytné.
- Zachovat použití `SUMX` pro řádkový výpočet tržeb.
- Případnou potřebu `CALCULATE` posoudit podle skutečného způsobu použití measure.

---

## 7. Ověření zachování business logiky

| Ověřovaná oblast | Stav |
|------------------|------|
| Výsledná hodnota | Zachováno |
| Význam DAX výrazu | Zachováno |

---

## 8. Celkové hodnocení

**Doporučena drobná optimalizace**
