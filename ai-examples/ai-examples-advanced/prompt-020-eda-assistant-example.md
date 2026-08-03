# Prompt 020 — Exploratory Data Analysis Assistant

# Prompt

```text
Jsi senior datový analytik specializovaný na Exploratory Data Analysis (EDA).

Tvým úkolem je provést objektivní průzkumnou analýzu datasetu.

Nejprve urči režim analýzy:

- Režim A — pokud vstup obsahuje pouze popis struktury datasetu.
- Režim B — pokud vstup obsahuje skutečná data nebo jejich vypočtené souhrny.

Vycházej výhradně z informací uvedených ve vstupu.

Pokud některé informace chybí a nelze je objektivně určit, uveď je jako předpoklady pouze tehdy, jsou-li nezbytné.

Pokud nejsou nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej:

- hodnoty dat,
- statistiky,
- trendy,
- korelace,
- odlehlé hodnoty,
- anomálie,
- business pravidla,
- příčiny pozorovaných jevů.

Pokud jsou k dispozici pouze metadata nebo struktura datasetu:

- popiš analytický význam jednotlivých proměnných,
- identifikuj jejich předpokládané role,
- navrhni oblasti, které bude možné po dodání dat analyzovat,
- neprováděj statistické výpočty.

Pokud jsou k dispozici skutečná data:

- vypočítej pouze charakteristiky podložené vstupem,
- popiš rozdělení proměnných,
- identifikuj objektivně doložené vzory,
- popiš vztahy mezi proměnnými pouze tehdy, pokud přímo vyplývají z dat.

Za odlehlou hodnotu označ pozorování pouze tehdy, pokud bylo použito explicitní statistické nebo věcné kritérium.

Samotná minimální nebo maximální hodnota není automaticky odlehlou hodnotou.

Pokud kritérium odlehlosti není součástí zadání ani analýzy, uveď tuto skutečnost.

Nevysvětluj příčiny zjištěných rozdílů, pokud je nelze doložit dostupnými daty.

Nepřecházej do diagnostické ani kauzální analýzy.

Nenavrhuj KPI, dashboardy ani technická řešení.

Hloubku analýzy přizpůsob rozsahu dostupných dat.

Dodrž přesně požadovanou strukturu výstupu.

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí průzkumné analýzy
2. Předpoklady
3. Přehled datasetu
4. Základní charakteristiky dat
5. Rozdělení proměnných
6. Identifikované vzory a zajímavá zjištění
7. Vztahy mezi proměnnými
8. Odlehlé hodnoty a anomálie
9. Omezení interpretace
10. Doporučené další analýzy
11. Celkové zhodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- jasně odděluj fakta od předpokladů,
- nevytvářej hypotetické závěry,
- neopakuj stejné informace,
- neprováděj kauzální interpretaci,
- nehodnoť obchodní výkonnost nad rámec dostupných dat.

Pokud vstup obsahuje pouze strukturu datasetu:

- popiš analytický potenciál proměnných,
- neuváděj vypočtené statistiky,
- neidentifikuj vzory ani odlehlé hodnoty.

Pokud vstup obsahuje skutečná data:

- u numerických proměnných vypočítej vhodné popisné statistiky,
- u kategoriálních proměnných popiš četnosti,
- popiš vztahy mezi proměnnými pouze tehdy, pokud přímo vyplývají z dat.

V části Odlehlé hodnoty a anomálie:

- uveď použité kritérium identifikace odlehlých hodnot,
- pokud žádné kritérium použito nebylo, neoznačuj žádné pozorování za odlehlou hodnotu pouze na základě jeho velikosti.

V části Doporučené další analýzy navrhuj pouze analýzy logicky navazující na zjištěné výsledky nebo dostupnou strukturu dat.

Výstup by měl odpovídat přibližně rozsahu 1–3 stran textu.
```

# 1. Zadání bez konkrétních dat

K dispozici je tabulka **Sales** obsahující údaje o prodejích za jedno účetní období.

Tabulka obsahuje následující sloupce:

- SaleID
- Datum prodeje
- Prodejna
- Produkt
- Produktová kategorie
- Prodané množství
- Tržby
- Marže

Business cílem je získat základní přehled o analytickém potenciálu dostupných dat před provedením podrobné analýzy a návrhem manažerského reportingu.

---

# 2. Výstup k zadání bez konkrétních dat

### 1. Shrnutí datového průzkumu

Vstup obsahuje pouze popis struktury tabulky **Sales**, nikoliv konkrétní datové záznamy nebo vypočtené souhrny. Byl proto použit **Režim A — Data Discovery**.

Dostupná struktura umožňuje po dodání dat zkoumat prodeje z časového, produktového a prodejního hlediska a analyzovat prodané množství, tržby a marži. Skutečné výsledky, trendy, rozdíly, vztahy a neobvyklé hodnoty nelze bez konkrétních dat posoudit.

### 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

### 3. Přehled dostupné struktury

Dataset je tvořen jednou tabulkou **Sales**, která obsahuje osm proměnných vztahujících se k prodejům za jedno účetní období.

Struktura zahrnuje:

- identifikátor prodeje,
- datum prodeje,
- prodejnu,
- produkt a produktovou kategorii,
- prodané množství,
- tržby,
- marži.

Konkrétní počet záznamů, granularita jednotlivých řádků ani technické datové typy nebyly uvedeny.

### 4. Přehled proměnných

| Proměnná | Předpokládaný analytický typ | Role v analýze | Poznámka |
|----------|------------------------------|-----------------|----------|
| SaleID | Identifikační | Identifikátor | Pravděpodobně označuje prodejní záznam; technický datový typ ani unikátnost nejsou ověřeny. |
| Datum prodeje | Časová | Časová dimenze | Umožňuje časové členění analýzy; technický formát ani úroveň podrobnosti nejsou uvedeny. |
| Prodejna | Kategoriální | Kategoriální dimenze | Umožňuje porovnání výsledků mezi prodejnami. |
| Produkt | Kategoriální | Kategoriální dimenze | Umožňuje analýzu výsledků podle produktů. |
| Produktová kategorie | Kategoriální | Kategoriální dimenze | Umožňuje seskupení produktů podle dostupných kategorií. |
| Prodané množství | Numerická | Numerická metrika | Umožňuje analyzovat objem prodeje; jednotka není uvedena. |
| Tržby | Numerická | Numerická metrika | Umožňuje analyzovat hodnotu prodeje; měna ani způsob výpočtu nejsou uvedeny. |
| Marže | Numerická | Numerická metrika | Význam a způsob vyjádření marže nejsou definovány. |

Uvedené analytické typy jsou odvozeny z předpokládaného využití proměnných v analýze. Nejde o ověřené technické datové typy.

### 5. Analytický potenciál datasetu

| Oblast analýzy | Stav | Potřebné proměnné | Omezení |
|----------------|------|--------------------|---------|
| Vývoj prodejů v čase | Lze analyzovat po dodání dat | Datum prodeje, Prodané množství, Tržby, Marže | Rozsah a granularita časových údajů nejsou uvedeny. |
| Výkonnost prodejen | Lze analyzovat po dodání dat | Prodejna, Prodané množství, Tržby, Marže | Nejsou dostupné charakteristiky prodejen ani jejich cíle. |
| Výkonnost produktů | Lze analyzovat po dodání dat | Produkt, Prodané množství, Tržby, Marže | Nejsou uvedeny ceny, náklady ani další vlastnosti produktů. |
| Výkonnost produktových kategorií | Lze analyzovat po dodání dat | Produktová kategorie, Prodané množství, Tržby, Marže | Definice a struktura kategorií nejsou uvedeny. |
| Vztahy mezi prodejními metrikami | Lze analyzovat po dodání dat | Prodané množství, Tržby, Marže | Význam a způsob výpočtu marže nejsou definovány. |
| Zákaznická analýza | Nelze analyzovat | Zákaznické proměnné | Tabulka neobsahuje informace o zákaznících. |
| Analýza marketingových aktivit | Nelze analyzovat | Údaje o kampaních a marketingových nákladech | Marketingové proměnné nejsou součástí dostupné struktury. |
| Porovnání se stanovenými cíli | Nelze analyzovat | Plánované nebo cílové hodnoty | Dataset podle popisu obsahuje pouze údaje o realizovaných prodejích. |

### 6. Business otázky podporované daty

Po dodání konkrétních dat lze zkoumat například:

- Jak se vyvíjely prodané množství, tržby a marže během účetního období?
- Jaké byly výsledky jednotlivých prodejen?
- Které produkty a produktové kategorie dosahovaly nejvyšších a nejnižších hodnot sledovaných metrik?
- Jak se struktura prodejů lišila mezi prodejnami?
- Jaký podíl na celkových tržbách a marži připadal na jednotlivé produkty a produktové kategorie?
- Jak se ve sledovaných skupinách lišily tržby a marže vzhledem k prodanému množství?

### 7. Omezení dostupné struktury

- Bez konkrétních hodnot nelze vypočítat statistické charakteristiky ani posoudit rozdělení proměnných.
- Nelze identifikovat časové trendy, rozdíly mezi skupinami, vztahy mezi metrikami, odlehlé hodnoty ani anomálie.
- Není uveden počet záznamů ani přesná granularita jednoho řádku.
- Nejsou dostupné ověřené technické datové typy.
- Není definována měna tržeb ani význam a způsob vyjádření marže.
- Jedno účetní období nemusí umožňovat meziroční srovnání.
- Struktura nepodporuje analýzu zákazníků, marketingových aktivit ani plnění plánovaných cílů.

### 8. Doporučený plán EDA

1. Popsat rozsah datasetu, počet záznamů, časové pokrytí a granularitu řádků.
2. Získat základní charakteristiky proměnných Prodané množství, Tržby a Marže.
3. Prozkoumat četnosti prodejen, produktů a produktových kategorií.
4. Analyzovat rozdělení numerických metrik.
5. Vyhodnotit časový vývoj prodaného množství, tržeb a marže.
6. Porovnat sledované metriky mezi prodejnami, produkty a produktovými kategoriemi.
7. Prozkoumat vztahy mezi prodaným množstvím, tržbami a marží.
8. Prověřit neobvyklé nebo odlehlé hodnoty bez automatického označení za chyby.
9. Shrnout objektivní zjištění využitelná jako podklad pro následný návrh manažerského reportingu.

### 9. Celkové zhodnocení

Tabulka **Sales** poskytuje základní strukturu vhodnou pro průzkumnou analýzu prodejních výsledků podle času, prodejen, produktů a produktových kategorií. Obsahuje také tři numerické metriky umožňující hodnotit objem a hodnotu prodejů.

Analytický potenciál je pro základní prodejní EDA dostatečný, jeho skutečné využití však závisí na dodání konkrétních dat a upřesnění významu některých proměnných, zejména marže. Dostupná struktura sama o sobě neumožňuje formulovat závěry o skutečné výkonnosti ani navrhovat konkrétní manažerská opatření.

# 3. Zadání s konkrétními daty

Byla poskytnuta tabulka **Sales** obsahující prodejní data za jedno účetní období.

Sloupce tabulky:

- SaleID
- Datum prodeje
- Prodejna
- Produkt
- Produktová kategorie
- Prodané množství
- Tržby
- Marže

Data:

| SaleID | Datum prodeje | Prodejna | Produkt | Produktová kategorie | Prodané množství | Tržby | Marže |
|--------:|---------------|----------|---------|----------------------|-----------------:|------:|------:|
| 1001 | 2024-01-02 | Praha | Notebook A | Notebooky | 3 | 90000 | 18000 |
| 1002 | 2024-01-02 | Brno | Myš X | Příslušenství | 25 | 12500 | 4200 |
| 1003 | 2024-01-03 | Praha | Monitor M | Monitory | 6 | 48000 | 9600 |
| 1004 | 2024-01-03 | Ostrava | Notebook A | Notebooky | 2 | 60000 | 12000 |
| 1005 | 2024-01-04 | Brno | Klávesnice K | Příslušenství | 18 | 18000 | 5400 |
| 1006 | 2024-01-04 | Praha | Notebook B | Notebooky | 1 | 42000 | 8400 |
| 1007 | 2024-01-05 | Ostrava | Monitor M | Monitory | 4 | 32000 | 6400 |
| 1008 | 2024-01-05 | Praha | Myš X | Příslušenství | 40 | 20000 | 7000 |
| 1009 | 2024-01-06 | Brno | Notebook B | Notebooky | 2 | 84000 | 16800 |
| 1010 | 2024-01-06 | Ostrava | Klávesnice K | Příslušenství | 15 | 15000 | 4500 |
| 1011 | 2024-01-07 | Praha | Monitor M | Monitory | 5 | 40000 | 8000 |
| 1012 | 2024-01-07 | Brno | Notebook A | Notebooky | 1 | 30000 | 6000 |
| 1013 | 2024-01-08 | Ostrava | Myš X | Příslušenství | 35 | 17500 | 6100 |
| 1014 | 2024-01-08 | Praha | Notebook B | Notebooky | 3 | 126000 | 25200 |
| 1015 | 2024-01-09 | Brno | Monitor M | Monitory | 7 | 56000 | 11200 |
| 1016 | 2024-01-09 | Ostrava | Notebook A | Notebooky | 2 | 60000 | 12000 |
| 1017 | 2024-01-10 | Praha | Klávesnice K | Příslušenství | 22 | 22000 | 6600 |
| 1018 | 2024-01-10 | Brno | Myš X | Příslušenství | 30 | 15000 | 5100 |
| 1019 | 2024-01-11 | Ostrava | Notebook B | Notebooky | 1 | 42000 | 8400 |
| 1020 | 2024-01-11 | Praha | Notebook A | Notebooky | 4 | 120000 | 24000 |

---

## 4. Výstup k zadání s konkrétními daty

### 1. Shrnutí průzkumné analýzy

Tabulka **Sales** obsahuje 20 prodejních záznamů z období 2.–11. ledna 2024. Celkem bylo prodáno 226 kusů zboží, dosaženo tržeb 950 000 a marže 204 900.

Nejvyšších souhrnných tržeb dosáhla Praha. Kategorie Notebooky vytvořila většinu celkových tržeb a marže, zatímco Příslušenství představovalo většinu prodaného množství. Rozdíl souvisí s odlišnými hodnotami tržeb na jeden prodaný kus mezi produkty.

### 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

### 3. Přehled datasetu

| Charakteristika | Hodnota |
|---|---:|
| Počet záznamů | 20 |
| Počet proměnných | 8 |
| Časové období | 2.–11. 1. 2024 |
| Počet prodejen | 3 |
| Počet produktů | 5 |
| Počet produktových kategorií | 3 |
| Celkové prodané množství | 226 |
| Celkové tržby | 950 000 |
| Celková marže | 204 900 |

Každý identifikátor `SaleID` se ve vstupu vyskytuje právě jednou. Záznamy zahrnují prodejny Praha, Brno a Ostrava.

### 4. Základní charakteristiky dat

| Metrika | Minimum | Medián | Průměr | Maximum | Součet |
|---|---:|---:|---:|---:|---:|
| Prodané množství | 1 | 4,5 | 11,3 | 40 | 226 |
| Tržby | 12 500 | 41 000 | 47 500 | 126 000 | 950 000 |
| Marže | 4 200 | 8 200 | 10 245 | 25 200 | 204 900 |

Celková marže odpovídá přibližně 21,6 % celkových tržeb. Vstup však neobsahuje definici marže, proto tento výsledek představuje pouze poměr uvedených hodnot.

### 5. Rozdělení proměnných

#### Prodejny

| Prodejna | Počet záznamů | Prodané množství | Tržby | Marže |
|---|---:|---:|---:|---:|
| Praha | 8 | 84 | 508 000 | 106 800 |
| Ostrava | 6 | 59 | 226 500 | 49 400 |
| Brno | 6 | 83 | 215 500 | 48 700 |

Praha vytvořila přibližně 53,5 % celkových tržeb a 52,1 % celkové marže. Brno a Ostrava měly stejný počet záznamů. Brno vykázalo vyšší prodané množství, zatímco Ostrava dosáhla vyšších tržeb a marže.

#### Produktové kategorie

| Produktová kategorie | Počet záznamů | Prodané množství | Tržby | Marže |
|---|---:|---:|---:|---:|
| Notebooky | 9 | 19 | 654 000 | 130 800 |
| Příslušenství | 7 | 185 | 120 000 | 38 900 |
| Monitory | 4 | 22 | 176 000 | 35 200 |

Notebooky představovaly přibližně 68,8 % celkových tržeb při podílu 8,4 % na prodaném množství. Příslušenství tvořilo přibližně 81,9 % prodaného množství, ale pouze 12,6 % tržeb.

### 6. Identifikované vzory a zajímavá zjištění

| Produkt | Počet záznamů | Prodané množství | Tržby | Marže |
|---|---:|---:|---:|---:|
| Notebook A | 5 | 12 | 360 000 | 72 000 |
| Notebook B | 4 | 7 | 294 000 | 58 800 |
| Monitor M | 4 | 22 | 176 000 | 35 200 |
| Myš X | 4 | 130 | 65 000 | 22 400 |
| Klávesnice K | 3 | 55 | 55 000 | 16 500 |

- Notebook A dosáhl nejvyšších souhrnných tržeb i marže.
- Myš X měla nejvyšší prodané množství, ale nižší souhrnné tržby než oba notebooky a Monitor M.
- Nejvyšší denní tržby byly zaznamenány 11. ledna: 162 000 při prodeji pěti kusů.
- Nejvyšší denní prodané množství bylo zaznamenáno 10. ledna: 52 kusů při tržbách 37 000.
- Desetidenní časové období neposkytuje dostatečný podklad pro závěr o dlouhodobém trendu.

### 7. Vztahy mezi proměnnými

V rámci jednotlivých produktů jsou tržby přímo úměrné prodanému množství:

| Produkt | Tržby na jeden prodaný kus |
|---|---:|
| Notebook B | 42 000 |
| Notebook A | 30 000 |
| Monitor M | 8 000 |
| Klávesnice K | 1 000 |
| Myš X | 500 |

Rozdílná produktová skladba souvisí s rozdíly mezi prodaným množstvím a tržbami. Vyšší počet prodaných kusů proto napříč různými produkty automaticky neodpovídá vyšším tržbám.

U produktů Notebook A, Notebook B a Monitor M odpovídá marže ve všech záznamech 20 % tržeb. U Klávesnice K odpovídá 30 %. U produktu Myš X se poměr marže k tržbám mezi jednotlivými záznamy mírně liší.

### 8. Odlehlé hodnoty a anomálie

Pro označení odlehlých hodnot nebylo použito žádné explicitní statistické ani věcné kritérium. Z dostupných údajů proto nelze žádný záznam jednoznačně označit za odlehlou hodnotu.

Pozorovaná maxima a minima jsou:

| Metrika | Minimum | Maximum |
|---|---:|---:|
| Prodané množství | 1 | 40 |
| Tržby | 12 500 | 126 000 |
| Marže | 4 200 | 25 200 |

Maximální tržby 126 000 a maximální marže 25 200 se vztahují k prodeji tří kusů produktu Notebook B v Praze dne 8. ledna. Maximální prodané množství 40 kusů se vztahuje k produktu Myš X v Praze dne 5. ledna.

Tyto hodnoty představují maxima v dostupném datasetu, nikoliv automaticky odlehlé hodnoty nebo chyby. Rozdíly odpovídají mimo jiné odlišným hodnotám tržeb na jeden kus u jednotlivých produktů.

Jako neobvyklé pozorování lze popsat mírně proměnlivý poměr marže k tržbám u produktu Myš X, zatímco u ostatních produktů je tento poměr v dostupných záznamech konstantní. Bez definice marže nelze určit význam tohoto rozdílu ani jej označit za anomálii.

### 9. Omezení interpretace

- Data pokrývají pouze deset dnů, přestože jsou popsána jako údaje za jedno účetní období.
- Není uvedena měna tržeb a marže.
- Není definováno, zda je marže uvedena jako absolutní částka ani jak byla vypočtena.
- Dataset neobsahuje náklady, slevy, vratky ani plánované hodnoty.
- Výsledky prodejen mohou souviset s jejich produktovou skladbou; samotné souhrnné hodnoty proto neposkytují úplné hodnocení jejich výkonnosti.
- Bez explicitního kritéria nelze určit, zda některá pozorování představují odlehlé hodnoty.
- Z dostupných dat nelze vysvětlit příčiny zjištěných rozdílů.

### 10. Doporučené další analýzy

- Porovnat prodejny samostatně podle jednotlivých produktů a produktových kategorií, aby byl zohledněn vliv produktové skladby.
- Podrobněji analyzovat rozdíly v poměru marže k tržbám u produktu Myš X.
- Po získání dat za delší období analyzovat časový vývoj a případné opakující se časové vzory.
- Porovnat výsledky s dalšími účetními obdobími, pokud budou odpovídající data dostupná.
- Pokud bude potřeba systematicky vyhledávat odlehlé hodnoty, předem stanovit vhodné kritérium s ohledem na jednotlivé produkty a jejich rozdílné hodnotové úrovně.

### 11. Celkové zhodnocení

Dataset umožňuje základní EDA podle času, prodejen, produktů a produktových kategorií. Nejvýraznějším zjištěním je rozdíl mezi strukturou prodaného množství a strukturou tržeb: Příslušenství dominuje počtem kusů, zatímco Notebooky vytvářejí většinu tržeb a marže.

Výsledky poskytují základní popis sledovaných prodejů, ale krátké časové pokrytí a chybějící definice marže omezují jejich interpretaci. Žádná hodnota nebyla označena za odlehlou, protože nebylo použito explicitní kritérium pro posouzení odlehlosti.
