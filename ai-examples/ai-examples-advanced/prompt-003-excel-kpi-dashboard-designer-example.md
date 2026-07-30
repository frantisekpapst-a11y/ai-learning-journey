# Prompt 003 — Excel KPI Dashboard Designer

# Prompt

Jsi senior datový analytik a expert na Microsoft Excel.

Cílem je navrhnout profesionální KPI dashboard v Microsoft Excel pro cílovou skupinu definovanou v zadání.

Na základě dostupných dat navrhni:

- klíčové KPI,
- vhodné excelové vizualizace,
- doporučené kontingenční tabulky, pokud jsou vhodné,
- filtry, průřezy a časové osy,
- logické rozložení dashboardu,
- doporučené interakce mezi jednotlivými částmi dashboardu.

U každého návrhu stručně vysvětli jeho business přínos.

Pokud některé informace chybí, nejprve uveď předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro návrh dashboardu.

Předpoklady jasně označ a nepovažuj je za skutečnosti vyplývající ze zadání.

Do části **Předpoklady** uváděj pouze informace nezbytné pro návrh dashboardu.

Neuváděj zde návrhová rozhodnutí ani doporučené výchozí nastavení dashboardu.

Pokud nejsou pro návrh dashboardu nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej si data, sloupce, názvy listů, tabulek ani strukturu dat, které nejsou uvedeny v zadání.

Nevytvářej doporučení, která vyžadují předpoklady o struktuře nebo významu dat, pokud nejsou výslovně uvedeny v zadání.

Pokud zadání výslovně nepožaduje implementaci, zaměř se pouze na návrh dashboardu.

Nevytvářej kompletní excelový soubor ani podrobný implementační návod.

Nepopisuj konkrétní excelové vzorce ani technickou implementaci dashboardu, pokud nejsou nezbytné pro pochopení navrženého řešení.

Upřednostňuj KPI, která podporují rozhodování managementu před provozními metrikami.

Navrhuj pouze KPI a vizualizace, které přímo vyplývají z poskytnutých dat a potřeb cílové skupiny.

Pokud některý KPI nelze jednoznačně definovat na základě zadání, tuto skutečnost uveď místo vytváření vlastních předpokladů.

Pokud řešení závisí na konkrétní verzi Excelu, uveď minimální podporovanou verzi.

Rozložení dashboardu znázorni pomocí jednoduchého ASCII wireframu zobrazujícího rozmístění jednotlivých prvků.

Na závěr doporuč další data, která by bylo vhodné sbírat pro kvalitnější reporting.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Dodrž následující strukturu:

1. Shrnutí návrhu
2. Předpoklady
3. Doporučené klíčové KPI
4. Doporučené vizualizace
5. Doporučené kontingenční tabulky
6. Filtry, průřezy a časová osa
7. Doporučené interakce
8. Logické rozložení dashboardu
9. Doporučení pro manažerské porady
10. Minimální podporovaná verze Excelu
11. Doporučená další data

Dodrž následující pravidla:

- piš stručně a věcně,
- navrhuj pouze KPI a vizualizace vyplývající ze zadání,
- nevysvětluj obecné principy práce s Excelem,
- nevytvářej implementační manuál,
- nepopisuj technickou realizaci dashboardu,
- nevymýšlej strukturu dat ani business pravidla,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více částech,
- nevysvětluj stejnou skutečnost opakovaně; pokud již byla uvedena, pouze na ni stručně navazuj.

V části **Doporučené klíčové KPI** u každého KPI uveď:

- název,
- způsob zobrazení,
- business přínos.

Pokud některý KPI nelze jednoznačně definovat na základě dostupných dat, uveď tuto skutečnost.

V části **Doporučené vizualizace** u každé vizualizace uveď:

- doporučený typ,
- zobrazovaný obsah,
- business přínos.

Navrhuj pouze vizualizace odpovídající dostupným datům a potřebám cílové skupiny.

V části **Doporučené kontingenční tabulky** doporuč jejich použití pouze tehdy, pokud přinášejí přidanou hodnotu oproti běžným tabulkám.

U každé doporučené kontingenční tabulky stručně uveď:

- analyzovanou oblast,
- použité dimenze,
- hlavní hodnoty,
- přidanou hodnotu.

V části **Filtry, průřezy a časová osa** navrhuj pouze ovládací prvky podporující efektivní práci cílového uživatele.

V části **Doporučené interakce** popisuj pouze chování dashboardu z pohledu uživatele.

Nepopisuj technickou implementaci.

V části **Logické rozložení dashboardu** zobraz rozmístění prvků pomocí jednoduchého ASCII wireframu.

Wireframe musí obsahovat alespoň:

- hlavní ovládací prvky,
- KPI karty,
- klíčové grafy,
- přehled problémových oblastí.

V části **Doporučení pro manažerské porady** navrhni stručnou posloupnost, ve které by měl cílový uživatel dashboard při poradě vyhodnocovat.

V části **Minimální podporovaná verze Excelu** uveď konkrétní verzi pouze tehdy, pokud navržené řešení jednoznačně vyžaduje funkce dostupné až od určité verze Microsoft Excelu.

Jinak uveď:

> Návrh dashboardu nevyžaduje konkrétní minimální verzi Microsoft Excelu.

V části **Doporučená další data** navrhuj pouze údaje, které mohou významně zvýšit vypovídací hodnotu dashboardu.

U každého doporučeného údaje stručně vysvětli jeho očekávaný business přínos.

Výstup by měl odpovídat přibližně rozsahu **1–2 stran textu**.

Upřednostňuj stručnost. Rozšiřuj jednotlivé části pouze tehdy, pokud je to nezbytné pro správné zdůvodnění návrhu.

---

# Zadání

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

Potřebuje každý den:

- sledovat výkonnost regionů, obchodníků a produktových kategorií,
- vyhodnocovat vývoj hlavních obchodních KPI,
- porovnávat aktuální výsledky s minulým obdobím,
- rychle identifikovat problémové oblasti vyžadující manažerské rozhodnutí.

Navrhni profesionální KPI dashboard v Microsoft Excel určený pro pravidelné manažerské porady.

---

# Návrh řešení

## 1. Shrnutí návrhu

Dashboard bude sloužit obchodnímu řediteli ke každodennímu sledování obchodních výsledků a jako podklad pro pravidelné manažerské porady.

Zaměří se na:

- vývoj tržeb, marže, nákladů a prodaného množství,
- porovnání aktuálního a předchozího srovnatelného období,
- výkonnost regionů, obchodníků a produktových kategorií,
- rychlou identifikaci poklesů a problémových oblastí,
- přechod od celkového výsledku k detailu prodejny, produktu nebo obchodníka.

Hlavní obrazovka bude obsahovat společné ovládací prvky, KPI karty, trendové grafy, výkonnostní porovnání a přehled problémových oblastí.

## 2. Předpoklady

- Aktuální a minulé období představují dvě stejně dlouhá, bezprostředně navazující období vybraná uživatelem.
- Hodnota **Marže** vyjadřuje absolutní částku. Pokud představuje procento, musí být definice příslušného KPI upravena.
- Hodnota **Sleva** má v celém datasetu jednotný význam a měrnou jednotku.
- Pole **Zákazník** umožňuje jednoznačně rozlišit jednotlivé zákazníky.

## 3. Doporučené klíčové KPI

| KPI | Způsob zobrazení | Business přínos |
|---|---|---|
| Tržby | KPI karta: aktuální hodnota a změna proti minulému období | Základní ukazatel obchodní výkonnosti. |
| Marže | KPI karta: aktuální hodnota a změna proti minulému období | Ukazuje ekonomický přínos realizovaných prodejů. |
| Maržovost | KPI karta: podíl marže na tržbách a změna v procentních bodech | Odhaluje, zda růst tržeb není vykoupen poklesem ziskovosti. |
| Náklady | KPI karta: aktuální hodnota a změna proti minulému období | Umožňuje sledovat nákladový vývoj ve vztahu k prodejům. |
| Prodané kusy | KPI karta: aktuální hodnota a procentní změna | Rozlišuje změny objemu prodeje od změn jeho hodnoty. |
| Tržby na zákazníka | KPI karta: tržby připadající na jednoznačně rozlišeného zákazníka | Pomáhá posoudit hodnotu zákaznických nákupů. |
| Sleva | KPI karta podle jednotky uložené v datech | Upozorňuje na možnou souvislost mezi podporou prodeje a marží. |

Maržovost lze jednoznačně definovat pouze tehdy, pokud pole **Marže** obsahuje absolutní částku. Interpretace KPI **Sleva** závisí na tom, zda jde o částku, procento nebo jinou metriku.

## 4. Doporučené vizualizace

| Doporučený typ | Zobrazovaný obsah | Business přínos |
|---|---|---|
| Spojnicový graf | Vývoj tržeb a marže v čase za aktuální a minulé období | Rychle ukáže trend, obraty ve vývoji a odchylky mezi obdobími. |
| Horizontální pruhový graf | Tržby a změna proti minulému období podle regionu | Umožní porovnat regiony a okamžitě rozpoznat poklesy. |
| Horizontální pruhový graf | Výkonnost obchodníků podle tržeb nebo marže | Identifikuje nejsilnější a nejslabší obchodníky. |
| Kombinovaný graf | Tržby a maržovost podle produktové kategorie | Odliší kategorie s vysokými tržbami od skutečně ziskových kategorií. |
| Zvýrazněná přehledová tabulka | Regiony, prodejny, obchodníci nebo kategorie s největším poklesem tržeb či marže | Soustředí pozornost na oblasti vyžadující manažerské rozhodnutí. |

Samostatný graf podle zákazníků není pro hlavní manažerskou obrazovku vhodný, protože množství zákazníků může omezit přehlednost. Zákazník bude využit především jako detailní filtr.

## 5. Doporučené kontingenční tabulky

| Analyzovaná oblast | Dimenze | Hlavní hodnoty | Přidaná hodnota |
|---|---|---|---|
| Regionální výkonnost | Region → Prodejna | Tržby, marže, náklady, prodané kusy | Umožní přejít od výsledku regionu k jednotlivým prodejnám. |
| Výkonnost sortimentu | Kategorie produktu → Produkt | Tržby, marže, prodané kusy, sleva | Odhalí produkty podporující nebo oslabující výsledek kategorie. |
| Výkonnost obchodníků | Region → Obchodník | Tržby, marže, prodané kusy | Umožní srovnat obchodníky v odpovídajícím regionálním kontextu. |

Kontingenční tabulky přinášejí přidanou hodnotu zejména možností rychlého rozbalení výsledků do podrobnější úrovně.

## 6. Filtry, průřezy a časová osa

Doporučené společné ovládací prvky:

- časová osa podle data prodeje,
- průřez **Region**,
- průřez **Prodejna**,
- průřez **Kategorie produktu**,
- průřez **Obchodník**,
- volitelný detailní filtr **Produkt** a **Zákazník**.

Průřezy by měly ovládat všechny související KPI, grafy a přehledové tabulky. Po výběru regionu se mají dostupné prodejny a obchodníci omezit na odpovídající hodnoty.

## 7. Doporučené interakce

- Změna období aktualizuje celý dashboard a porovnání s předchozím stejně dlouhým obdobím.
- Výběr regionu zpřesní výsledky na příslušné prodejny, obchodníky, produkty a kategorie.
- Výběr kategorie umožní vyhodnotit její trend a přejít k jednotlivým produktům.
- Výběr obchodníka zobrazí jeho výsledky v kontextu zvoleného období a regionu.
- Zrušení filtrů vrátí celkový pohled za celou maloobchodní síť.
- Problémové oblasti budou vizuálně zvýrazněny podle velikosti poklesu proti minulému období.

## 8. Logické rozložení dashboardu

```text
+--------------------------------------------------------------------------+
| OBCHODNÍ KPI DASHBOARD                        Datum aktualizace / období |
+--------------------------------------------------------------------------+
| Časová osa | Region | Prodejna | Kategorie | Obchodník | Zrušit filtry |
+--------------------------------------------------------------------------+
|   Tržby    |   Marže   | Maržovost | Náklady | Prodané kusy | Tržby/zák.|
| hodnota Δ  | hodnota Δ | hodnota Δ | hodnota Δ|  hodnota Δ   | hodnota Δ |
+--------------------------------------------------------------------------+
| Vývoj tržeb a marže: aktuální vs. minulé období                         |
+------------------------------------+-------------------------------------+
| Výkonnost regionů                  | Kategorie: tržby a maržovost        |
| tržby a změna proti období         |                                     |
+------------------------------------+-------------------------------------+
| Výkonnost obchodníků               | Problémové oblasti                  |
| tržby nebo marže                   | největší poklesy a nízká maržovost  |
+------------------------------------+-------------------------------------+
| Detail: Region → Prodejna / Kategorie → Produkt / Region → Obchodník     |
+--------------------------------------------------------------------------+
```

## 9. Doporučení pro manažerské porady

Dashboard doporučuji vyhodnocovat v následujícím pořadí:

1. Zkontrolovat celkové KPI a jejich změnu proti minulému období.
2. Posoudit trend tržeb a marže v čase.
3. Porovnat výkonnost regionů.
4. Prověřit obchodníky a produktové kategorie s největšími odchylkami.
5. Zaměřit se na přehled problémových oblastí.
6. Přejít do detailu konkrétní prodejny, produktu nebo obchodníka.
7. Formulovat potřebná manažerská opatření a určit oblasti pro další analýzu.

## 10. Minimální podporovaná verze Excelu

> Návrh dashboardu nevyžaduje konkrétní minimální verzi Microsoft Excelu.

Dostupnost a podoba některých interaktivních prvků se však může mezi jednotlivými podporovanými verzemi Excelu lišit.

## 11. Doporučená další data

| Doporučený údaj | Očekávaný business přínos |
|---|---|
| Obchodní plán nebo cílové hodnoty | Umožní porovnávat skutečnost nejen s minulostí, ale také s plánem. |
| Skladové zásoby a nedostupnost produktů | Pomohou rozlišit slabou poptávku od ztracených prodejů způsobených nedostupností zboží. |
| Počet transakcí | Umožní vypočítat průměrnou hodnotu nákupu a oddělit vliv návštěvnosti od velikosti nákupu. |
| Vrácené zboží a storna | Zpřesní pohled na čisté tržby, prodané množství a skutečnou výkonnost. |
| Prodejní kanál | Umožní porovnat výsledky jednotlivých způsobů prodeje, pokud společnost využívá více kanálů. |
| Důvod a typ slevy | Pomůže vyhodnotit účinnost slevových akcí a jejich dopad na marži. |
