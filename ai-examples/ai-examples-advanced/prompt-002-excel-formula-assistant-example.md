# Prompt 002 — Excel Formula Assistant

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

Pro automatické doplnění názvu oddělení podle hodnoty **Osobní číslo** je nejvhodnější funkce `XVYHLEDAT`.

Funkce vyhledá osobní číslo zaměstnance na listu **Oddělení** a vrátí odpovídající hodnotu ze sloupce **Oddělení**. Pokud osobní číslo nenajde, může místo chyby zobrazit zvolený text.

## 2. Předpoklady

- Osobní čísla mají na obou listech stejný datový typ.
- Každému osobnímu číslu odpovídá na listu **Oddělení** nejvýše jeden záznam.
- Skutečné rozsahy dat ani názvy excelových tabulek nejsou uvedeny.
- Používá se česká verze Excelu se středníkem jako oddělovačem argumentů.
- Funkce `XVYHLEDAT` je dostupná v Excelu pro Microsoft 365 a Excelu 2021 nebo novějším.

## 3. Proč právě toto řešení

Funkce `XVYHLEDAT` je pro tento úkol vhodná, protože:

- standardně vyhledává přesnou shodu;
- nevyžaduje zadání pořadového čísla návratového sloupce;
- vyhledávací a návratový rozsah jsou definovány samostatně;
- umožňuje přímo určit výsledek pro nenalezenou hodnotu;
- je čitelnější a lépe udržovatelná než starší funkce `SVYHLEDAT`.

## 4. Doporučený vzorec

Obecný zápis:

```excel
=XVYHLEDAT(osobní_číslo;rozsah_osobních_čísel_na_listu_Oddělení;rozsah_oddělení_na_listu_Oddělení;"Nenalezeno")
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

Pomocná funkce není potřebná, protože obsluhu nenalezené hodnoty zajišťuje přímo čtvrtý argument funkce `XVYHLEDAT`.

## 6. Alternativní řešení

### Starší verze Excelu

Pro verze bez funkce `XVYHLEDAT` lze použít kombinaci `INDEX` a `POZVYHLEDAT`:

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
- Pokud se stejné osobní číslo na listu **Oddělení** vyskytuje vícekrát, `XVYHLEDAT` standardně vrátí první nalezenou shodu.
- Text `Nenalezeno` lze nahradit prázdným řetězcem `""`, pokud má při neúspěšném vyhledání zůstat buňka vizuálně prázdná.
