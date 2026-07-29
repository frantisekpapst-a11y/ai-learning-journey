# Prompt 003 — Excel KPI Dashboard Designer

## Zadání

Společnost provozuje síť maloobchodních prodejen.

K dispozici jsou data o prodejích za poslední dva roky.

Dataset obsahuje následující informace:

- Datum prodeje
- Prodejna
- Region
- Produkt
- Kategorie produktu
- Obchodník
- Prodáno kusů
- Tržby
- Náklady
- Marže
- Sleva
- Zákazník

Cílovou skupinou dashboardu je obchodní ředitel.

Potřebuje každý den sledovat výkonnost prodeje jednotlivých regionů, obchodníků a produktových kategorií, porovnávat aktuální výsledky s minulým obdobím a rychle identifikovat problémové oblasti.

Navrhni profesionální KPI dashboard v Microsoft Excel určený pro pravidelné manažerské porady. Zaměř se na návrh KPI, vizualizací, rozložení dashboardu a uživatelských interakcí. Nepopisuj technickou implementaci ani konkrétní excelové vzorce.

---

# Návrh

## 1. Shrnutí návrhu dashboardu

Dashboard poskytne obchodnímu řediteli každodenní manažerský přehled o výsledcích celé společnosti a umožní porovnání podle regionů, prodejen, obchodníků a produktových kategorií.

Hlavní pozornost bude věnována:

- tržbám a marži,
- porovnání s předchozím obdobím,
- vývoji prodeje v čase,
- výkonnosti regionů, prodejen a obchodníků,
- identifikaci slabých kategorií a produktů,
- vztahu mezi slevami, tržbami a marží.

Dashboard bude založen především na kontingenčních tabulkách a kontingenčních grafech, které umožní společné filtrování a rychlou aktualizaci při pravidelných manažerských poradách.

Minimální doporučená verze je Excel 2016. Pro komfortnější práci a dlouhodobou podporu je vhodný Microsoft 365.

## 2. Předpoklady

- Každý řádek datasetu představuje jednu prodejní položku nebo transakci.
- Sloupce Tržby, Náklady a Marže obsahují peněžní hodnoty.
- Marže představuje absolutní částku, nikoliv procento.
- Sleva má jednotný význam a formát v celém datasetu.
- Datum prodeje je uložené jako skutečné datum a umožňuje porovnání období.
- Data za poslední dva roky jsou dostatečně kompletní pro meziroční porovnání.
- Dataset neobsahuje plánované hodnoty, proto nelze vyhodnocovat plnění obchodního plánu.
- Dataset neobsahuje jednoznačný identifikátor objednávky, proto nelze spolehlivě určit počet samostatných nákupů ani průměrnou hodnotu objednávky.

## 3. Klíčové KPI

| KPI | Význam a business přínos |
|---|---|
| Celkové tržby | Zobrazuje celkový obchodní výkon za zvolené období. |
| Absolutní marže | Ukazuje finanční přínos prodeje po zohlednění nákladů. |
| Maržovost | Vyjadřuje podíl marže na tržbách a pomáhá odhalit růst založený na nízké ziskovosti. |
| Prodané kusy | Poskytuje přehled o objemu prodeje a pomáhá odlišit cenový a množstevní vývoj. |
| Meziroční změna tržeb | Ukazuje, zda se obchodní výkon proti srovnatelnému období zlepšuje, nebo zhoršuje. |
| Meziroční změna marže | Ověřuje, zda se růst tržeb promítá také do finančního výsledku. |
| Průměrná sleva | Umožňuje sledovat intenzitu cenové podpory prodeje. |
| Počet zákazníků | Orientačně ukazuje velikost aktivní zákaznické základny, pokud lze zákazníky jednoznačně rozlišit. |

KPI karty by měly zobrazovat aktuální hodnotu, změnu oproti předchozímu srovnatelnému období a jednoduchý barevný indikátor vývoje.

## 4. Doporučené vizualizace

| Vizualizace | Obsah | Business přínos |
|---|---|---|
| KPI karty | Tržby, marže, maržovost, prodané kusy a meziroční změny | Poskytují okamžitý přehled o celkové výkonnosti. |
| Spojnicový graf | Vývoj tržeb a marže podle měsíců | Odhalí trend, sezónnost a mimořádné výkyvy. |
| Skupinový sloupcový graf | Tržby a marže podle regionů | Umožní rychle porovnat regionální výkonnost. |
| Pruhový graf | Výkon obchodníků podle tržeb nebo marže | Identifikuje nejlepší a nejslabší obchodníky. |
| Kombinovaný graf | Tržby a maržovost podle produktových kategorií | Ukáže kategorie s vysokými tržbami, ale nízkou ziskovostí. |
| Bodový graf | Sleva ve vztahu k maržovosti nebo tržbám | Pomůže posoudit, zda vyšší slevy podporují výnosný prodej. |
| Manažerská tabulka | Prodejny nebo produkty s největším poklesem tržeb či marže | Upozorní na problémové oblasti vyžadující zásah. |

### Doporučené kontingenční tabulky

- Tržby, marže a prodané kusy podle období.
- Tržby a maržovost podle regionu a prodejny.
- Výkonnost podle obchodníka.
- Výkonnost podle kategorie a produktu.
- Sleva, tržby a marže podle kategorie nebo produktu.
- Přehled nejsilnějších a nejslabších prodejen, obchodníků a produktů.

Kontingenční tabulky mohou sloužit jako zdroj vizualizací a současně jako detailní analytický přehled mimo hlavní plochu dashboardu.

## 5. Doporučené filtry, slicery a časové osy

### Hlavní ovládací prvky

- časová osa podle data prodeje,
- region,
- prodejna,
- kategorie produktu,
- obchodník.

### Doplňkové slicery

- produkt,
- zákazník.

Doplňkové slicery je vhodné použít pouze tehdy, pokud jejich počet hodnot nezhorší přehlednost. Produkt a zákazník mohou být praktičtější v detailní analytické části než na hlavním manažerském dashboardu.

Časová osa by měla umožnit výběr měsíců, čtvrtletí a let. Všechny hlavní slicery musí být napojené na související kontingenční tabulky a grafy.

## 6. Doporučené interakce dashboardu

- Výběr období na časové ose aktualizuje všechny KPI, grafy i manažerskou tabulku.
- Výběr regionu omezí výsledky na příslušné prodejny, obchodníky, produkty a kategorie.
- Výběr prodejny zpřesní analýzu na její obchodní výkon a produktovou strukturu.
- Výběr kategorie aktualizuje přehled produktů, slev, tržeb a marže.
- Výběr obchodníka zobrazí jeho výsledky podle období, prodejny a produktových kategorií.
- Grafy mají zobrazovat hodnoty za aktuální výběr a tam, kde je to vhodné, také srovnání s minulým obdobím.
- Manažerská tabulka má reagovat na stejné filtry a automaticky zobrazovat nejslabší oblasti v aktuálním výběru.
- Dashboard má obsahovat jednoznačnou možnost zrušit aktivní filtry a vrátit se k celkovému pohledu.

## 7. Návrh rozložení dashboardu (ASCII wireframe)

```text
+--------------------------------------------------------------------------+
| KPI DASHBOARD PRODEJE                       Období: [časová osa]          |
+--------------------------------------------------------------------------+
| [Region] [Prodejna] [Kategorie] [Obchodník]          [Zrušit filtry]     |
+--------------------------------------------------------------------------+
|  Tržby       |  Marže       |  Maržovost   |  Prodané kusy |  Meziročně |
|  aktuální    |  aktuální    |  aktuální    |  aktuální     |  tržby/marže|
+--------------------------------------------------------------------------+
|                                                                          |
|       Vývoj tržeb a marže v čase       |  Výkon podle regionů            |
|                                         |                                 |
+-----------------------------------------+--------------------------------+
|                                         |                                 |
|  Výkon produktových kategorií           |  Výkonnost obchodníků           |
|  Tržby + maržovost                      |  Tržby nebo marže                |
|                                         |                                 |
+-----------------------------------------+--------------------------------+
|  Sleva versus maržovost                 |  Problémové prodejny / produkty |
|  Bodový graf                            |  Manažerská tabulka              |
+--------------------------------------------------------------------------+
```

Rozložení postupuje od celkového výsledku přes hlavní příčiny výkonu až k problémovým oblastem, které mohou vyžadovat rozhodnutí obchodního ředitele.

## 8. Doporučení pro další sběr dat

Pro kvalitnější reporting je vhodné doplnit:

- jednoznačný identifikátor objednávky pro výpočet počtu nákupů a průměrné hodnoty objednávky,
- plánované tržby a marži pro sledování plnění obchodního plánu,
- typ zákazníka nebo zákaznický segment,
- prodejní kanál,
- údaje o vráceném nebo stornovaném zboží,
- důvod a typ poskytnuté slevy,
- skladovou dostupnost a výpadky zásob,
- údaje o marketingových kampaních a promoakcích,
- cíle jednotlivých regionů, prodejen a obchodníků.

Tato data by umožnila rozšířit dashboard o plnění plánu, kvalitu tržeb, zákaznickou strukturu, efektivitu slev a vliv dostupnosti zboží na obchodní výsledky.
