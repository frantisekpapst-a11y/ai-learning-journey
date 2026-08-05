# Prompt — Power BI 07 - Power BI Executive Dashboard Designer

## Prompt

Jsi senior datový a BI analytik.

Cílem je připravit návrh profesionálního Power BI dashboardu pro cílovou skupinu definovanou v zadání.

Na základě dostupných dat navrhni:

- klíčové KPI,
- klíčové DAX míry,
- vhodné vizualizace (včetně tabulek tam, kde dávají smysl),
- filtry a slicery,
- rozložení dashboardu.

U každého návrhu stručně vysvětli jeho business přínos.

Pokud některé informace chybí, nejprve uveď předpoklady.

Nevymýšlej si data ani sloupce, které nejsou uvedeny.

Pokud zadání výslovně nepožaduje implementaci, zaměř se na návrh řešení. Nevytvářej kompletní technickou dokumentaci ani zbytečně podrobné implementační detaily.

Zaměř se na návrh dashboardu pro rozhodování managementu, nikoli na kompletní analytické řešení.

Navrhni pouze klíčové DAX míry nezbytné pro navržený dashboard.

U každé DAX míry stručně popiš její účel a uveď jednoduchý příklad implementace.

Rozložení dashboardu znázorni pomocí jednoduchého ASCII wireframu zobrazujícího rozmístění jednotlivých vizualizací.

Na závěr doporuč další data, která by bylo vhodné sbírat pro kvalitnější reporting.

## Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Dodrž následující strukturu:

1. Shrnutí návrhu dashboardu
2. Předpoklady
3. Klíčové KPI
4. Klíčové DAX míry
5. Doporučené vizualizace
6. Doporučené filtry a slicery
7. Návrh rozložení dashboardu (ASCII wireframe)
8. Doporučení pro další sběr dat

Piš stručně a věcně.

Nevysvětluj obecné principy Power BI.

Nevytvářej projektovou dokumentaci ani implementační manuál.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

## Zadání

Analyzujeme data internetového obchodu.

Cílovou skupinou dashboardu je vrcholový management společnosti.

K dispozici máme následující data:

- datum objednávky,
- produkt,
- kategorie,
- cena,
- množství,
- zákazník,
- region.

Navrhni profesionální Power BI dashboard pro vedení společnosti.

---

# Návrh

## 1. Shrnutí návrhu dashboardu

Dashboard poskytne vrcholovému managementu rychlý přehled o:

- celkových tržbách a prodaném množství,
- počtu zákazníků,
- vývoji tržeb v čase,
- výkonnosti kategorií, produktů a regionů.

Hlavní stránka bude zaměřena na vyhodnocení obchodní výkonnosti a identifikaci oblastí, které vyžadují pozornost vedení.

## 2. Předpoklady

- Každý řádek představuje jednu položku objednávky.
- Tržby se počítají jako `cena × množství`.
- Sloupec `cena` obsahuje jednotkovou prodejní cenu.
- Sloupec `zákazník` umožňuje rozlišit jednotlivé zákazníky.
- Data neobsahují jednoznačný identifikátor objednávky. Nelze proto spolehlivě určit počet objednávek ani průměrnou hodnotu objednávky.
- Nejsou dostupné informace o nákladech, slevách, vratkách ani obchodních cílech. Dashboard proto nevyhodnocuje ziskovost ani plnění plánu.
- Pro časové analýzy bude z data objednávky vytvořena standardní kalendářní tabulka.

## 3. Klíčové KPI

| KPI | Výpočet | Business přínos |
|---|---|---|
| Celkové tržby | Cena × množství | Základní ukazatel celkové obchodní výkonnosti. |
| Prodané množství | Součet množství | Ukazuje objem prodaného zboží nezávisle na jeho ceně. |
| Počet zákazníků | Počet unikátních zákazníků | Umožňuje sledovat velikost aktivní zákaznické základny. |
| Tržby na zákazníka | Celkové tržby ÷ počet zákazníků | Orientačně vyjadřují hodnotu zákazníka ve zvoleném období. |
| Meziroční změna tržeb | Porovnání s odpovídajícím obdobím minulého roku | Umožňuje rychle posoudit růst nebo pokles výkonnosti. |

## 4. Klíčové DAX míry

Příklady předpokládají tabulku `Prodeje` a kalendářní tabulku `Kalendář`.

### Celkové tržby

Vypočítá celkovou hodnotu prodaného zboží.

```DAX
Celkové tržby =
SUMX(
    Prodeje,
    Prodeje[cena] * Prodeje[množství]
)
```

### Prodané množství

Určuje celkový počet prodaných kusů.

```DAX
Prodané množství =
SUM(Prodeje[množství])
```

### Počet zákazníků

Spočítá unikátní zákazníky ve zvoleném kontextu filtrů.

```DAX
Počet zákazníků =
DISTINCTCOUNT(Prodeje[zákazník])
```

### Tržby na zákazníka

Vyjadřují průměrné tržby připadající na jednoho zákazníka.

```DAX
Tržby na zákazníka =
DIVIDE(
    [Celkové tržby],
    [Počet zákazníků]
)
```

### Tržby minulý rok

Vrací tržby za odpovídající období předchozího roku.

```DAX
Tržby minulý rok =
CALCULATE(
    [Celkové tržby],
    SAMEPERIODLASTYEAR(Kalendář[Datum])
)
```

### Meziroční změna tržeb %

Vyjadřuje procentní růst nebo pokles tržeb proti minulému roku.

```DAX
Meziroční změna tržeb % =
DIVIDE(
    [Celkové tržby] - [Tržby minulý rok],
    [Tržby minulý rok]
)
```

## 5. Doporučené vizualizace

| Vizualizace | Obsah | Business přínos |
|---|---|---|
| KPI karty | Tržby, prodané množství, počet zákazníků, tržby na zákazníka a meziroční změna | Poskytují okamžitý přehled o hlavních výsledcích. |
| Spojnicový graf | Vývoj tržeb podle data | Odhaluje trend, sezónnost a neobvyklé výkyvy. |
| Pruhový graf | Tržby podle kategorií | Umožňuje porovnat význam jednotlivých částí sortimentu. |
| Pruhový graf | Tržby podle regionů | Identifikuje nejsilnější a nejslabší trhy. |
| Tabulka produktů | Produkt, kategorie, tržby a prodané množství | Umožňuje určit nejvýkonnější i slabší produkty. |
| Tabulka regionů | Region, tržby, prodané množství a počet zákazníků | Poskytuje detailnější pohled na regionální výkonnost. |

Grafy kategorií, regionů a produktů je vhodné řadit podle tržeb sestupně. U produktové tabulky lze použít podmíněné formátování pro rychlé zvýraznění rozdílů.

## 6. Doporučené filtry a slicery

- **Období** – výběr roku, čtvrtletí, měsíce nebo vlastního časového rozsahu.
- **Kategorie** – analýza konkrétní části sortimentu.
- **Produkt** – detailní pohled na vybraný produkt.
- **Region** – porovnání obchodní výkonnosti jednotlivých oblastí.
- **Zákazník** – detailní analýza konkrétního zákazníka, spíše jako doplňkový filtr.

Na hlavní stránce je vhodné zobrazit především slicery období, kategorie a regionu. Produkt a zákazník mohou být dostupné v rozbalovacích filtrech, aby dashboard zůstal přehledný.

## 7. Návrh rozložení dashboardu (ASCII wireframe)

```text
+-----------------------------------------------------------------------+
| E-COMMERCE MANAGEMENT DASHBOARD                                       |
| Období: [________]   Kategorie: [________]   Region: [________]        |
+---------------+---------------+---------------+-----------------------+
| Celkové tržby | Prodané kusy  | Zákazníci    | Tržby/zákazník | YoY % |
+---------------+---------------+---------------+-----------------------+
|                                                                       |
|                    Vývoj tržeb v čase                                 |
|                                                                       |
+-----------------------------------+-----------------------------------+
| Tržby podle kategorií             | Tržby podle regionů               |
|                                   |                                   |
+-----------------------------------+-----------------------------------+
| Přehled produktů                                                      |
| Produkt | Kategorie | Tržby | Prodané množství                        |
+-----------------------------------------------------------------------+
| Přehled regionů                                                       |
| Region | Tržby | Prodané množství | Počet zákazníků                    |
+-----------------------------------------------------------------------+
```

## 8. Doporučení pro další sběr dat

Pro kvalitnější reporting je vhodné doplnit:

- **ID objednávky** – umožní počítat objednávky a průměrnou hodnotu objednávky.
- **Nákupní nebo pořizovací náklady** – umožní sledovat marži a ziskovost.
- **Slevy** – zpřesní výpočet skutečně dosažených tržeb.
- **Vratky a reklamace** – umožní vyhodnotit čisté tržby a kvalitu produktů.
- **Prodejní kanál** – umožní porovnat například web, mobilní aplikaci a marketplace.
- **Obchodní cíle nebo rozpočet** – umožní sledovat plnění plánu.
- **Zákaznické segmenty** – podpoří analýzu různých skupin zákazníků.
- **Stav zásob** – umožní propojit prodejní výsledky s dostupností produktů.
