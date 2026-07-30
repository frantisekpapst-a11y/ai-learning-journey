# Prompt 003 — Excel KPI Dashboard Designer

# Prompt

Jsi senior datový analytik a expert na Microsoft Excel.

Cílem je navrhnout profesionální KPI dashboard v Microsoft Excel pro cílovou skupinu definovanou v zadání.

Na základě dostupných dat navrhni:

- klíčové KPI,
- vhodné excelové vizualizace,
- doporučené kontingenční tabulky, pokud jsou vhodné,
- filtry, průřezy (Slicery) a časové osy,
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

Pokud zadání výslovně nepožaduje implementaci, zaměř se pouze na návrh dashboardu.

Nevytvářej kompletní excelový soubor ani podrobný implementační návod.

Nepopisuj konkrétní excelové vzorce ani technickou implementaci dashboardu, pokud nejsou nezbytné pro pochopení navrženého řešení.

Upřednostňuj KPI, která podporují rozhodování managementu před provozními metrikami.

Navrhuj pouze KPI a vizualizace, které přímo vyplývají z poskytnutých dat.

Pokud některý KPI nelze jednoznačně definovat na základě zadání, tuto skutečnost uveď místo vytváření vlastních předpokladů.

Pokud řešení závisí na konkrétní verzi Excelu, uveď minimální podporovanou verzi.

Rozložení dashboardu znázorni pomocí jednoduchého ASCII wireframu zobrazujícího rozmístění jednotlivých vizualizací.

Na závěr doporuč další data, která by bylo vhodné sbírat pro kvalitnější reporting.

---

## Požadavky na výstup

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
- neopakuj stejné informace ve více částech.

V části **Doporučené klíčové KPI** u každého KPI uveď:

- název,
- způsob zobrazení,
- business přínos.

Pokud některý KPI nelze jednoznačně definovat na základě dostupných dat, uveď tuto skutečnost.

V části **Doporučené vizualizace** navrhuj pouze vizualizace odpovídající dostupným datům a potřebám cílové skupiny.

U každé vizualizace stručně vysvětli její business přínos.

V části **Doporučené kontingenční tabulky** doporuč jejich použití pouze tehdy, pokud přinášejí přidanou hodnotu oproti běžným tabulkám.

V části **Filtry, průřezy a časová osa** navrhuj pouze ovládací prvky podporující efektivní práci cílového uživatele.

V části **Doporučené interakce** popisuj pouze chování dashboardu z pohledu uživatele.

Nepopisuj technickou implementaci.

V části **Logické rozložení dashboardu** zobraz rozmístění prvků pomocí jednoduchého ASCII wireframu.

V části **Minimální podporovaná verze Excelu** uveď pouze tehdy, pokud navržené řešení využívá funkce závislé na konkrétní verzi.

Jinak uveď:

> Návrh dashboardu nevyžaduje konkrétní minimální verzi Microsoft Excelu.

V části **Doporučená další data** navrhuj pouze údaje, které mohou významně zvýšit vypovídací hodnotu dashboardu.

Výstup by měl odpovídat přibližně rozsahu 2–3 stran textu.

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

Potřebuje každý den sledovat výkonnost prodeje jednotlivých regionů, obchodníků a produktových kategorií, porovnávat aktuální výsledky s minulým obdobím a rychle identifikovat problémové oblasti.

Navrhni profesionální KPI dashboard v Microsoft Excel určený pro pravidelné manažerské porady.

---

# Návrh KPI dashboardu v Microsoft Excel

## 1. Shrnutí návrhu

Dashboard bude sloužit obchodnímu řediteli ke každodennímu sledování obchodní výkonnosti a jako podklad pro pravidelné manažerské porady.

Návrh se zaměřuje na:

- vývoj tržeb, marže, nákladů a prodaného množství,
- porovnání výsledků s předchozím srovnatelným obdobím,
- výkonnost regionů, obchodníků a produktových kategorií,
- rychlou identifikaci poklesů a problémových oblastí,
- možnost přecházet od celkového výsledku k podrobnějšímu pohledu.

Dashboard bude tvořit jedna hlavní manažerská obrazovka s KPI kartami, trendovými grafy, výkonnostním porovnáním a společnými ovládacími prvky.

---

## 2. Předpoklady

- Marže představuje hodnotu marže v peněžních jednotkách, nikoliv procentní marži.
- Jednotlivé záznamy lze jednoznačně přiřadit ke konkrétnímu datu prodeje.
- Dostupná historie za dva roky umožňuje porovnat zvolené období s bezprostředně předcházejícím obdobím nebo se stejným obdobím předchozího roku.
- Sleva je v datasetu vedena ve formě, která umožňuje její agregaci nebo porovnání mezi jednotlivými částmi prodeje.

Konkrétní význam a způsob evidence zákazníka nejsou uvedeny. Zákaznické KPI proto nelze bez dalšího popisu dat jednoznačně definovat.

---

## 3. Doporučené klíčové KPI

| KPI | Způsob zobrazení | Business přínos |
|---|---|---|
| Tržby | KPI karta s hodnotou a procentní změnou proti srovnatelnému období | Poskytuje okamžitý přehled o celkovém obchodním výkonu. |
| Marže | KPI karta s hodnotou a procentní změnou | Ukazuje, zda prodej vytváří odpovídající ekonomický přínos, nejen objem tržeb. |
| Maržovost | KPI karta v procentech | Umožňuje posoudit kvalitu tržeb a odhalit růst založený na nízké marži. Maržovost lze určit jako poměr marže k tržbám, pokud význam sloupce Marže odpovídá uvedenému předpokladu. |
| Prodáno kusů | KPI karta s hodnotou a procentní změnou | Odlišuje změnu prodejního objemu od změny hodnoty tržeb. |
| Náklady | KPI karta s hodnotou a procentní změnou | Umožňuje sledovat, zda vývoj nákladů odpovídá vývoji prodeje a marže. |
| Sleva | KPI karta s hodnotou nebo průměrnou úrovní slevy | Pomáhá posoudit, zda je obchodní výkon podporován zvýšeným poskytováním slev. Přesná definice závisí na formátu sloupce Sleva. |
| Počet zákazníků | Nezařazovat bez ověření významu sloupce Zákazník | Bez informace, zda zákazník představuje jednoznačný identifikátor, nelze spolehlivě stanovit počet unikátních zákazníků. |

Na hlavní obrazovce je vhodné upřednostnit čtyři KPI: **Tržby, Marže, Maržovost a Prodáno kusů**. Náklady a sleva mohou tvořit doplňkovou druhou řadu, pokud zůstane dashboard přehledný.

Porovnání musí vždy uvádět, vůči kterému období je změna vypočtena. Samotná procentní změna bez označení srovnávací základny by mohla být při poradě nesprávně interpretována.

---

## 4. Doporučené vizualizace

### Vývoj tržeb a marže v čase

**Typ:** Spojnicový graf se dvěma datovými řadami.

Graf zobrazí vývoj tržeb a marže podle data prodeje. Časová podrobnost se bude řídit vybraným obdobím, například po dnech nebo měsících.

**Business přínos:** Umožní rychle rozpoznat trend, sezónní vývoj, výkyvy a období, kdy růst tržeb nebyl doprovázen odpovídajícím růstem marže.

### Tržby a maržovost podle regionu

**Typ:** Kombinovaný graf – sloupce pro tržby a značka nebo spojnice pro maržovost.

**Business přínos:** Umožní porovnat velikost obchodního výkonu regionů s jeho kvalitou. Region s vysokými tržbami, ale nízkou maržovostí může vyžadovat větší pozornost než region s mírně nižšími tržbami a zdravou marží.

### Výkonnost obchodníků

**Typ:** Seřazený vodorovný pruhový graf podle tržeb nebo marže.

**Business přínos:** Zpřehlední rozdíly mezi obchodníky a umožní identifikovat nejlepší výsledky i významné propady. Zvolený ukazatel musí být v názvu grafu vždy jednoznačně uveden.

### Výkonnost produktových kategorií

**Typ:** Seřazený vodorovný pruhový graf zobrazující tržby a porovnání s minulým obdobím.

**Business přínos:** Ukáže, které kategorie nejvíce přispívají k výsledku a u kterých dochází k poklesu. To podporuje rozhodování o prioritách produktového portfolia.

### Nejvýznamnější problémové oblasti

**Typ:** Zvýrazněná manažerská tabulka.

Doporučené sloupce:

- oblast,
- aktuální tržby,
- změna tržeb proti srovnatelnému období,
- aktuální marže nebo maržovost,
- změna marže proti srovnatelnému období.

Oblastí může být podle zvoleného pohledu region, obchodník nebo produktová kategorie.

**Business přínos:** Soustředí pozornost na položky s největším poklesem a umožní rychle určit témata vyžadující projednání.

Samostatné koláčové grafy nejsou doporučeny. Pro porovnávání většího počtu regionů, obchodníků nebo kategorií jsou seřazené pruhové grafy přehlednější.

---

## 5. Doporučené kontingenční tabulky

Kontingenční tabulky mají přidanou hodnotu zejména jako podklad pro interaktivní porovnávání více dimenzí a období.

| Kontingenční tabulka | Obsah | Přidaná hodnota |
|---|---|---|
| Regionální výkonnost | Region; tržby, náklady, marže a prodané kusy | Umožní rychle porovnat všechny regiony podle stejné sady ukazatelů. |
| Výkonnost obchodníků | Region a obchodník; tržby, marže a prodané kusy | Umožní analyzovat obchodníky v kontextu jejich regionu. |
| Produktové portfolio | Kategorie produktu a produkt; tržby, marže a prodané kusy | Podporuje přechod od kategorie ke konkrétním produktům. |
| Časové porovnání | Datum prodeje seskupené podle vhodné časové úrovně; hlavní KPI | Umožní porovnávat vývoj výsledků mezi obdobími. |

Kontingenční tabulky nemusí být všechny umístěny na hlavním dashboardu. Na hlavní obrazovce je vhodné zobrazit pouze jejich manažersky významné výstupy.

---

## 6. Filtry, průřezy a časová osa

Doporučené ovládací prvky:

- **Časová osa podle data prodeje** – hlavní nástroj pro volbu analyzovaného období.
- **Region** – umožní přejít z celofiremního pohledu na konkrétní region.
- **Prodejna** – umožní dohledat, které prodejny ovlivňují regionální výsledek.
- **Obchodník** – podpoří hodnocení individuální obchodní výkonnosti.
- **Kategorie produktu** – umožní analyzovat části produktového portfolia.
- **Produkt** – použít jako podrobnější filtr pro následnou analýzu, nikoliv jako dominantní prvek hlavní obrazovky.

Filtr zákazníka není pro hlavní manažerský dashboard doporučen. Pravděpodobně by obsahoval velké množství hodnot a bez dalšího popisu zákaznických dat není zřejmé, jaký manažerský přínos by měl.

---

## 7. Doporučené interakce

- Změna období aktualizuje všechny KPI, grafy a přehled problémových oblastí.
- Výběr regionu omezí výsledky obchodníků, prodejen, kategorií a produktů na zvolený region.
- Výběr produktové kategorie aktualizuje celkové KPI a umožní posoudit její dopad na obchodní výsledek.
- Výběr obchodníka zobrazí jeho výsledky v čase a strukturu prodeje podle produktových kategorií.
- Výběr více hodnot umožní porovnat například několik regionů nebo kategorií.
- Zrušení všech filtrů vrátí dashboard do celofiremního pohledu.
- Aktivní výběry budou na dashboardu viditelně uvedeny, aby bylo vždy zřejmé, k jakému výřezu dat se výsledky vztahují.
- Problémová tabulka bude seřazena podle největšího negativního rozdílu proti srovnatelnému období.

---

## 8. Logické rozložení dashboardu

~~~text
+--------------------------------------------------------------------------------+
| OBCHODNÍ KPI DASHBOARD                     Vybrané období: [.................] |
| Filtry: [Region] [Prodejna] [Obchodník] [Kategorie] [Produkt] [Zrušit výběr] |
+--------------------------------------------------------------------------------+
|     TRŽBY          MARŽE          MARŽOVOST       PRODÁNO KUSŮ                |
|  aktuální stav  aktuální stav    aktuální stav     aktuální stav               |
|  změna období   změna období     změna období      změna období                |
+--------------------------------------------------------------------------------+
|                         VÝVOJ TRŽEB A MARŽE V ČASE                             |
|                                                                                |
+---------------------------------------+----------------------------------------+
| TRŽBY A MARŽOVOST PODLE REGIONU       | VÝKONNOST PRODUKTOVÝCH KATEGORIÍ      |
|                                       |                                        |
+---------------------------------------+----------------------------------------+
| VÝKONNOST OBCHODNÍKŮ                  | NEJVÝZNAMNĚJŠÍ PROBLÉMOVÉ OBLASTI     |
|                                       | oblast | výsledek | změna | marže      |
+---------------------------------------+----------------------------------------+
| Doplňkové ukazatele: Náklady | Sleva | Označení srovnávacího období           |
+--------------------------------------------------------------------------------+
~~~

Horní část obsahuje celkový stav a filtry, střední část vysvětluje časový vývoj a spodní část pomáhá určit, které regiony, kategorie nebo osoby stojí za dosaženým výsledkem.

---

## 9. Doporučení pro manažerské porady

Dashboard je vhodné při poradě používat v tomto pořadí:

1. Posoudit celkové tržby, marži, maržovost a prodané množství.
2. Porovnat aktuální výsledky s jasně označeným minulým obdobím.
3. Prověřit časový trend a určit okamžik vzniku významné změny.
4. Porovnat regiony a identifikovat největší pozitivní a negativní odchylky.
5. Prověřit, kteří obchodníci a produktové kategorie ovlivnili zjištěný vývoj.
6. Zaměřit diskuzi na omezený počet nejvýznamnějších problémových oblastí.

Pro každodenní použití by měl dashboard zachovat jednotný výchozí pohled. Na manažerské poradě se tak nebude měnit význam ukazatelů ani způsob jejich interpretace.

---

## 10. Minimální podporovaná verze Excelu

Pro navržené řešení s časovou osou a průřezy připojenými k více kontingenčním tabulkám je doporučen minimálně **Microsoft Excel 2013 pro Windows**.

Pro pravidelné firemní používání a průběžnou podporu je vhodnější aktuální desktopová verze **Microsoft Excel pro Microsoft 365**.

---

## 11. Doporučená další data

Pro zvýšení vypovídací hodnoty dashboardu je vhodné zvážit sběr následujících údajů:

- **Plánované tržby a plánovaná marže** podle období, regionu nebo prodejny – umožní hodnotit plnění obchodního plánu, nejen vývoj proti minulosti.
- **Identifikátor prodejní transakce** – umožní určit počet nákupů a průměrnou hodnotu nákupu.
- **Jednoznačný identifikátor zákazníka** – umožní spolehlivě sledovat počet zákazníků a rozlišovat nové a vracející se zákazníky.
- **Důvod a typ slevy** – pomůže rozlišit plánované obchodní akce od individuálně poskytnutých slev.
- **Prodejní kanál** – umožní porovnat výsledky kamenných prodejen s případnými dalšími prodejními kanály.
- **Skladová dostupnost nebo počet dní bez zásoby** – pomůže určit, zda pokles prodeje způsobil nižší zájem, nebo nedostupnost produktu.
- **Vratky a storna** – umožní hodnotit čistý obchodní výsledek a kvalitu dosažených tržeb.
