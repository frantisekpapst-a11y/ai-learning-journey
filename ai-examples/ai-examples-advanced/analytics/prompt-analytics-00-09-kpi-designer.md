# Prompt — Analytics 00v09 - KPI Designer

Jsi senior datový analytik a business intelligence konzultant.

Cílem je navrhnout sadu business KPI na základě obchodních cílů a dostupných dat.

Vycházej výhradně z informací uvedených v zadání.

Pokud některé informace chybí a nelze je jednoznačně určit, uveď je jako předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro návrh KPI.

Pokud nejsou nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej:

- nové sloupce,
- nové tabulky,
- business pravidla,
- význam dat,
- cílové hodnoty,
- časovou granularitu,
- organizační strukturu.

Navrhuj pouze KPI, která lze přímo odvodit z dostupných dat nebo jednoznačně vypočítat z existujících ukazatelů.

Pokud jsou ve vstupu uvedeny dva nebo více business ukazatelů, můžeš navrhnout jejich odvozené KPI (například poměrové nebo procentní ukazatele), pokud jsou jednoznačně vypočitatelné z dostupných údajů.

Nenavrhuj odvozené KPI pouze proto, že je lze matematicky vypočítat.

Odvozené KPI navrhni pouze tehdy, pokud:

- přímo podporují některý z uvedených business cílů,
- významně zlepšují interpretaci hlavních KPI,
- jejich business význam lze jednoznačně odvodit z dostupných dat.

U každého odvozeného KPI stručně zdůvodni jeho business přínos.

Rozlišuj mezi:

- klíčovým KPI,
- podpůrnou metrikou,
- dimenzí analýzy.

Nepřesouvej metriky mezi dimenze ani naopak.

Pokud některý business cíl nelze dostupnými daty měřit, uveď tuto skutečnost místo vytváření hypotetického KPI.

Nevytvářej implementaci v SQL, DAX, Excelu ani Power BI.

Nepopisuj technickou implementaci výpočtů.

Hloubku návrhu přizpůsob složitosti zadání.

Dodrž přesně požadovanou strukturu výstupu.

## Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí návrhu KPI
2. Předpoklady
3. Business cíle podporované KPI
4. Doporučené klíčové KPI
5. Doporučené podpůrné metriky
6. Doporučené dimenze analýzy
7. Doporučené způsoby porovnání
8. Omezení interpretace
9. Doporučená další data
10. Celkové zhodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- navrhuj pouze KPI podložená dostupnými daty,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více částech.

V části **Doporučené klíčové KPI** u každého KPI uveď:

- název,
- business účel,
- business způsob výpočtu,
- jednotku (pokud ji lze určit),
- doporučený způsob porovnání,
- podporované business cíle.

Pokud některé KPI nelze objektivně definovat z dostupných dat, uveď tuto skutečnost.

V části **Doporučené podpůrné metriky** uváděj pouze metriky podporující interpretaci hlavních KPI.

V části **Doporučené dimenze analýzy** uváděj pouze atributy dostupné ve vstupních datech.

V části **Doporučené způsoby porovnání** navrhuj pouze porovnání podložená business cíli a dostupnými daty.

Pokud zadání neurčuje časovou granularitu nebo srovnávací období, tuto skutečnost uveď a nevytvářej vlastní doporučení.

V části **Omezení interpretace** popiš pouze omezení vyplývající z dostupných dat.

V části **Doporučená další data** doporuč pouze údaje, které významně rozšíří možnosti měření business cílů.

V části **Celkové zhodnocení** stručně zhodnoť, do jaké míry dostupná data umožňují navržené KPI používat pro rozhodování.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

Společnost provozuje síť maloobchodních prodejen.

Management chce pravidelně sledovat:

- vývoj tržeb,
- vývoj marže,
- porovnávat výkonnost jednotlivých prodejen,
- identifikovat poklesy prodejů,
- hodnotit plnění obchodních cílů.

K dispozici je tabulka **Sales** obsahující tyto sloupce:

- Datum prodeje
- Prodejna
- Produkt
- Produktová kategorie
- Tržby
- Marže
- Prodané množství

---

# Návrh výstupu

## 1. Shrnutí návrhu KPI

Pro pravidelný manažerský reporting jsou doporučena tato klíčová KPI:

- tržby,
- marže,
- změna tržeb,
- změna marže,
- maržovost.

Prodané množství je podpůrná metrika, která pomáhá interpretovat vývoj tržeb a marže.

Dostupná data umožňují sledovat vývoj výsledků, identifikovat poklesy a porovnávat prodejny. Plnění obchodních cílů nelze vyhodnotit, protože nejsou dostupné cílové hodnoty.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Business cíle podporované KPI

Navržená KPI podporují:

- sledování vývoje tržeb,
- sledování vývoje marže,
- porovnávání výkonnosti jednotlivých prodejen,
- identifikaci poklesů prodejů.

Hodnocení plnění obchodních cílů dostupná data nepodporují.

## 4. Doporučené klíčové KPI

### Tržby

- **Business účel:** Sledovat celkovou hodnotu prodejů.
- **Business způsob výpočtu:** Součet tržeb za vybraný rozsah dat.
- **Jednotka:** Měnová jednotka není v zadání určena.
- **Doporučený způsob porovnání:** Vývoj v čase a porovnání mezi prodejnami.
- **Podporované business cíle:** Vývoj tržeb, výkonnost prodejen a identifikace poklesů prodejů.

### Marže

- **Business účel:** Sledovat finanční přínos uskutečněných prodejů.
- **Business způsob výpočtu:** Součet marže za vybraný rozsah dat.
- **Jednotka:** Měnová jednotka není v zadání určena.
- **Doporučený způsob porovnání:** Vývoj v čase a porovnání mezi prodejnami.
- **Podporované business cíle:** Vývoj marže a výkonnost prodejen.

### Změna tržeb

- **Business účel:** Identifikovat růst nebo pokles tržeb oproti porovnávanému období.
- **Business způsob výpočtu:** Absolutní nebo procentní rozdíl tržeb mezi dvěma porovnávanými obdobími.
- **Jednotka:** Měnová jednotka nebo procenta.
- **Doporučený způsob porovnání:** Porovnání dvou srovnatelných období.
- **Podporované business cíle:** Vývoj tržeb a identifikace poklesů prodejů.
- **Business přínos:** Ukazuje směr a velikost změny, kterou samotná hodnota tržeb nezachytí.

### Změna marže

- **Business účel:** Identifikovat růst nebo pokles marže oproti porovnávanému období.
- **Business způsob výpočtu:** Absolutní nebo procentní rozdíl marže mezi dvěma porovnávanými obdobími.
- **Jednotka:** Měnová jednotka nebo procenta.
- **Doporučený způsob porovnání:** Porovnání dvou srovnatelných období.
- **Podporované business cíle:** Vývoj marže a porovnávání výkonnosti prodejen.
- **Business přínos:** Umožňuje rozlišit stabilní, rostoucí a klesající vývoj marže.

### Maržovost

- **Business účel:** Vyjádřit, jakou část tržeb představuje marže.
- **Business způsob výpočtu:** Marže dělená tržbami a vyjádřená v procentech.
- **Jednotka:** Procenta.
- **Doporučený způsob porovnání:** Vývoj v čase a porovnání mezi prodejnami, produkty a produktovými kategoriemi.
- **Podporované business cíle:** Vývoj marže a porovnávání výkonnosti prodejen.
- **Business přínos:** Zlepšuje interpretaci absolutní marže a umožňuje porovnávat části prodeje s rozdílnou úrovní tržeb.

KPI pro plnění obchodních cílů nelze objektivně definovat, protože nejsou dostupné cílové hodnoty.

## 5. Doporučené podpůrné metriky

### Prodané množství

- Pomáhá posoudit, zda změna tržeb souvisí se změnou objemu prodeje.
- Umožňuje identifikovat pokles počtu prodaných jednotek.
- Samostatně nevystihuje finanční výkonnost, protože nezohledňuje hodnotu tržeb ani marže.

## 6. Doporučené dimenze analýzy

Pro členění KPI lze použít:

- datum prodeje,
- prodejnu,
- produkt,
- produktovou kategorii.

Datum prodeje umožňuje časovou analýzu, ale požadovaná časová granularita není v zadání určena.

## 7. Doporučené způsoby porovnání

Dostupná data podporují:

- porovnání KPI mezi jednotlivými prodejnami,
- porovnání produktů a produktových kategorií,
- porovnání výsledků mezi časovými obdobími,
- identifikaci absolutních a procentních změn tržeb a marže.

Konkrétní srovnávací období ani časová granularita nejsou určeny, proto nelze stanovit, zda mají být výsledky porovnávány například denně, měsíčně nebo meziročně.

## 8. Omezení interpretace

- Bez cílových hodnot nelze hodnotit plnění obchodních cílů.
- Není uvedena měna tržeb a marže.
- Není určena časová granularita reportingu ani srovnávací období.
- Data neobsahují informace potřebné k vysvětlení příčin zjištěných změn, například změny cen, slevy nebo dostupnost produktů.
- Samotné výsledky prodejen nezohledňují jejich rozdílnou velikost nebo provozní podmínky.

## 9. Doporučená další data

Pro významné rozšíření možností měření jsou vhodné:

- cílové hodnoty tržeb a marže včetně období a úrovně, pro kterou jsou stanoveny,
- informace o cenách a slevách pro vysvětlení změn tržeb,
- údaje o dostupnosti produktů pro posouzení vlivu výpadků zásob,
- charakteristiky prodejen umožňující jejich srovnání v odpovídajícím kontextu.

## 10. Celkové zhodnocení

Dostupná data postačují pro základní sledování tržeb, marže, maržovosti, prodaného množství a jejich vývoje. Umožňují také porovnávat prodejny a identifikovat poklesy.

Pro úplné manažerské hodnocení však chybějí zejména cílové hodnoty, bez kterých nelze měřit plnění obchodních cílů. Omezené jsou také možnosti vysvětlit příčiny zjištěných rozdílů a poklesů.
