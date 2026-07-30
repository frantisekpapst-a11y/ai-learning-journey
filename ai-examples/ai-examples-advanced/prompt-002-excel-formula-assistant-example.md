# Prompt 002 — Excel Formula Assistant

## Prompt

Jsi senior datový analytik a expert na Microsoft Excel.

Cílem je navrhnout nejvhodnější excelový vzorec nebo kombinaci vzorců a funkcí pro řešení úkolu definovaného v zadání.

Na základě dostupných informací navrhni:

- nejvhodnější řešení pomocí excelových funkcí,
- případné pomocné funkce, pokud jsou nezbytné,
- stručné vysvětlení, proč je navržené řešení nejvhodnější,
- alternativní řešení, pokud existuje vhodnější přístup pro jinou verzi Excelu nebo jiný způsob práce.

U každého návrhu stručně vysvětli jeho účel a výhody.

Pokud některé informace chybí, nejprve uveď předpoklady.

Nevymýšlej si názvy listů, tabulek, buněk, sloupců ani rozsahy dat, které nejsou uvedeny v zadání.

Pokud není znám skutečný rozsah dat, použij obecné odkazy nebo doporuč použití excelových tabulek se strukturovanými odkazy.

Pokud zadání neobsahuje názvy excelových tabulek nebo strukturovaných odkazů, nevytvářej zástupné názvy ve vzorcích. Místo toho použij obecný zápis nebo slovně popiš princip řešení.

Pokud není v zadání určeno umístění výsledného vzorce, neuváděj konkrétní adresy buněk nebo sloupců pro jeho vložení.

Pokud zadání výslovně nepožaduje jiné řešení, zaměř se pouze na excelové vzorce. Nenavrhuj VBA, Power Query, Power Pivot ani jiné technologie.

Upřednostňuj moderní excelové funkce (například XVYHLEDAT, FILTER, LET, LAMBDA nebo dynamická pole), pokud jsou pro daný úkol vhodnější.

Pokud řešení závisí na konkrétní verzi Excelu, uveď minimální podporovanou verzi.

Pokud je to vhodné, doporuč použití excelových tabulek a strukturovaných odkazů, ale konkrétní názvy tabulek uváděj pouze tehdy, pokud jsou součástí zadání.

Navrhuj co nejjednodušší, čitelné a snadno udržovatelné řešení.

Zaměř se na vyřešení zadaného problému. Omez doporučení pouze na ta, která mají přímý vliv na správnost, čitelnost nebo funkčnost navrženého řešení.

---

## Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Dodrž následující strukturu:

1. Shrnutí řešení
2. Předpoklady
3. Proč právě toto řešení
4. Doporučený vzorec
5. Vysvětlení vzorce
6. Alternativní řešení
7. Doporučení a omezení

Piš stručně a věcně.

Nevysvětluj obecné principy práce s Excelem.

Nevytvářej návody pro celé sešity ani rozsáhlé implementační postupy.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

## Zadání

V sešitu jsou dva listy.

### List **Zaměstnanci**

| Osobní číslo | Jméno |
|--------------:|-------|
| 1001 | Jan Novák |
| 1002 | Petra Svobodová |
| 1003 | Martin Dvořák |

### List **Oddělení**

| Osobní číslo | Oddělení |
|--------------:|----------|
| 1001 | Finance |
| 1002 | HR |
| 1003 | IT |

Potřebuji na listu **Zaměstnanci** automaticky doplnit název oddělení podle hodnoty **Osobní číslo** z listu **Oddělení**.

Navrhni nejvhodnější řešení pomocí excelových funkcí.

---

# Řešení — automatické doplnění oddělení

## 1. Shrnutí řešení

Pro automatické doplnění názvu oddělení podle hodnoty **Osobní číslo** je nejvhodnější funkce `XLOOKUP`.

Funkce vyhledá osobní číslo zaměstnance na listu **Oddělení** a vrátí odpovídající hodnotu ze sloupce **Oddělení**. Pokud osobní číslo nenajde, může místo chyby zobrazit zvolený text.

## 2. Předpoklady

- Osobní čísla mají na obou listech stejný datový typ.
- Každému osobnímu číslu odpovídá na listu **Oddělení** nejvýše jeden záznam.
- Skutečné rozsahy dat ani názvy excelových tabulek nejsou uvedeny.
- Používá se česká verze Excelu se středníkem jako oddělovačem argumentů.
- Funkce `XLOOKUP` je dostupná v Excelu pro Microsoft 365 a Excelu 2021 nebo novějším.

## 3. Proč právě toto řešení

Funkce `XLOOKUP` je pro tento úkol vhodná, protože:

- standardně vyhledává přesnou shodu;
- nevyžaduje zadání pořadového čísla návratového sloupce;
- vyhledávací a návratový rozsah jsou definovány samostatně;
- umožňuje přímo určit výsledek pro nenalezenou hodnotu;
- je čitelnější a lépe udržovatelná než starší funkce `SVYHLEDAT`.

## 4. Doporučený vzorec

Obecný zápis:

```excel
=XLOOKUP(osobní_číslo;rozsah_osobních_čísel_na_listu_Oddělení;rozsah_oddělení_na_listu_Oddělení;"Nenalezeno")
```

Význam jednotlivých obecných odkazů:

- `osobní_číslo` – osobní číslo zaměstnance v aktuálním řádku na listu **Zaměstnanci**;
- `rozsah_osobních_čísel_na_listu_Oddělení` – oblast, ve které se osobní číslo hledá;
- `rozsah_oddělení_na_listu_Oddělení` – oblast obsahující názvy oddělení, která se mají vrátit.

Konkrétní adresy buněk ani zástupné názvy tabulek nejsou uvedeny, protože skutečné rozsahy a názvy excelových tabulek nejsou součástí zadání.

## 5. Vysvětlení vzorce

Funkce postupuje následovně:

1. převezme osobní číslo z aktuálního záznamu na listu **Zaměstnanci**;
2. vyhledá jeho přesnou shodu mezi osobními čísly na listu **Oddělení**;
3. ze stejné pozice vrátí název oddělení;
4. pokud osobní číslo nenajde, zobrazí text `Nenalezeno`.

Pomocná funkce není potřebná, protože obsluhu nenalezené hodnoty zajišťuje přímo čtvrtý argument funkce `XLOOKUP`.

## 6. Alternativní řešení

### Starší verze Excelu

Pro verze bez funkce `XLOOKUP` lze použít kombinaci `INDEX` a `POZVYHLEDAT`:

```excel
=KDYŽCHYBHODN(INDEX(rozsah_oddělení_na_listu_Oddělení;POZVYHLEDAT(osobní_číslo;rozsah_osobních_čísel_na_listu_Oddělení;0));"Nenalezeno")
```

Argument `0` ve funkci `POZVYHLEDAT` vyžaduje přesnou shodu. Toto řešení je vhodné zejména pro starší verze Excelu, ale je méně čitelné než `XVYHLEDAT`.

Další možností je `SVYHLEDAT`, pokud sloupec **Osobní číslo** leží vlevo od sloupce **Oddělení**:

```excel
=KDYŽCHYBHODN(SVYHLEDAT(osobní_číslo;rozsah_obsahující_osobní_čísla_a_oddělení;2;NEPRAVDA);"Nenalezeno")
```

Tato varianta je jednodušší, ale méně odolná vůči změnám struktury zdrojových dat.

## 7. Doporučení a omezení

- Doporučeno je převést zdrojová data na excelové tabulky a použít strukturované odkazy. Vzorec se poté automaticky rozšíří na nové řádky a zůstane čitelnější.
- Vyhledávací a návratový rozsah musí mít stejný počet řádků.
- Osobní čísla musí být na obou listech uložena ve stejném formátu; například číslo `1001` se nemusí shodovat s textovou hodnotou `"1001"`.
- Pokud se stejné osobní číslo na listu **Oddělení** vyskytuje vícekrát, `XLOOKUP` standardně vrátí první nalezenou shodu.
- Text `Nenalezeno` lze nahradit prázdným řetězcem `""`, pokud má při neúspěšném vyhledání zůstat buňka vizuálně prázdná.
