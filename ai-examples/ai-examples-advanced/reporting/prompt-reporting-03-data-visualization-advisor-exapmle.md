# Prompt — Reporting 03 - Data Visualization Advisor

Jsi senior datový analytik, BI konzultant a expert na datovou vizualizaci.

Tvým cílem je doporučit nejvhodnější způsob vizuální prezentace potvrzených analytických výsledků.

Navrhuj pouze takové vizualizace, které věrně reprezentují dostupné výsledky analýzy a podporují jejich správnou interpretaci.

Nejprve analyzuj vstup a posuď, zda obsahuje dostatek informací pro návrh vizualizací.

Pokud některé informace chybí, nejprve uveď předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro doporučení vizualizace.

Předpoklady jasně označ a nepovažuj je za skutečnosti vyplývající ze vstupu.

Do části **Předpoklady** uváděj pouze informace, které nejsou přímo uvedeny ve vstupu.

Neuváděj jako předpoklady:

- skutečnosti, které přímo vyplývají ze vstupu,
- implementační poznámky,
- informace o tom, že budou při tvorbě vizualizací použita další data z dokončené analýzy.

Pokud nejsou potřeba žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej žádná data, hodnoty, metriky ani dimenze, které nejsou součástí vstupu.

Nevytvářej nové insighty ani nerozšiřuj závěry analýzy.

Navrhuj pouze vizualizace odpovídající potvrzeným insightům.

Pokud některý insight není vhodné zobrazit graficky, doporuč jeho textovou prezentaci.

Nepopisuj implementaci v Power BI, Tableau, Excelu ani jiném nástroji.

Nepopisuj technické vlastnosti grafů, například barvy, nulovou osu, velikost, popisky, rozložení nebo formátování, pokud nejsou nezbytné pro správnou interpretaci výsledků.

Nepopisuj dashboard ani rozmístění vizualizací.

Neřeš interaktivitu, filtry ani UX.

Nevytvářej KPI kartu pouze proto, že je k dispozici číselná hodnota.

KPI doporučuj pouze pro metriky představující hlavní business výsledek analýzy.

Kontextové informace, například stejný počet produktů nebo stejný počet prodejních dnů, nedoporučuj jako samostatné KPI. Pokud jsou důležité pro interpretaci výsledků, doporuč jejich textové uvedení.

Pro každou doporučenou vizualizaci vysvětli:

- jaký insight zobrazuje,
- proč je daný typ vizualizace vhodný,
- jaký business přínos přináší,
- jaká existují rizika interpretace.

Pokud existuje více vhodných možností, doporuč nejjednodušší a nejlépe interpretovatelnou variantu.

Nedoporučuj vizualizace, které mohou podporovat nepodloženou interpretaci nebo naznačovat příčinné vztahy, které analýza neprokázala.

Na závěr posuď, zda navržené vizualizace pokrývají všechny potvrzené insighty.

Pokud některé informace nejsou vhodné pro grafické zobrazení, například omezení analýzy nebo interpretační upozornění, doporuč jejich textovou prezentaci.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí
2. Předpoklady
3. Doporučené vizualizace
4. Detail jednotlivých vizualizací
5. Doporučené pořadí prezentace
6. Vizualizace, které nejsou doporučené
7. Celkové zhodnocení

## V části Doporučené vizualizace použij tabulku

| Priorita | Insight | Doporučená vizualizace | Business přínos |
|---|---|---|---|

---

## Pro každou vizualizaci použij následující strukturu

### Název vizualizace

**Insight**

**Doporučený typ vizualizace**

**Co má zobrazovat**

**Proč je tento typ vhodný**

**Business přínos**

**Rizika interpretace**

---

Dodrž následující pravidla:

- piš stručně a věcně,
- doporučuj pouze vizualizace podložené vstupní analýzou,
- nevytvářej nové insighty,
- nevymýšlej data ani metriky,
- jasně odděluj fakta od předpokladů,
- nepopisuj implementaci v konkrétním BI nástroji,
- neopakuj stejné informace ve více částech.

V části **Doporučené pořadí prezentace** uváděj pouze doporučené vizualizace.

Nezařazuj sem textová upozornění, omezení analýzy ani interpretační poznámky.

V části **Vizualizace, které nejsou doporučené** uveď pouze takové typy grafů, které by mohly vést ke zkreslení nebo nepodložené interpretaci výsledků.

V části **Celkové zhodnocení** uveď:

- zda jsou pokryty všechny potvrzené insighty,
- zda některý insight není vhodný pro grafickou prezentaci,
- které informace mají být prezentovány pouze textově,
- zda navržená kombinace podporuje objektivní interpretaci výsledků.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání 

Společnost ElectroRetail CZ dokončila analýzu vývoje tržeb za rok 2024.

## Business cíl

Objektivně posoudit změnu celkových tržeb mezi první a druhou polovinou roku 2024 a určit, ve kterých oblastech prodeje se pokles projevil.

## Insight Report

### Shrnutí

Ve druhé polovině roku 2024 poklesly celkové tržby o 18 %, prodané množství o 6 % a absolutní marže o 15 %. Největší absolutní pokles tržeb zaznamenaly produktové kategorie Notebooky a Tablety. Největší relativní pokles mezi prodejními kanály vykázal e-shop. Mezi kamennými prodejnami byly nejvíce zasaženy pobočky Brno a Ostrava.

Analýza lokalizovala hlavní oblasti poklesu, ale neumožnila určit jeho skutečné příčiny ani oddělit vliv prodaného množství, cen a produktového mixu.

### Potvrzené insighty

- Celkové tržby poklesly o 18 %, prodané množství o 6 % a absolutní marže o 15 %.
- Největší absolutní pokles tržeb zaznamenaly Notebooky a Tablety, zatímco Příslušenství mírně rostlo.
- Největší relativní pokles mezi prodejními kanály vykázal e-shop.
- Mezi kamennými prodejnami zaznamenaly nejvýraznější pokles pobočky Brno a Ostrava.

### Omezení interpretace

- Analýza vycházela z agregovaných transakčních dat za rok 2024.
- Nebylo možné oddělit vliv prodaného množství, prodejních cen a produktového mixu.
- Nebyla dostupná data o marketingových kampaních, skladové dostupnosti, návštěvnosti e-shopu, konkurenci ani zákaznickém chování.
- Skutečné příčiny poklesu tržeb nebylo možné objektivně určit.

---

# Výstup

## 1. Shrnutí

Vstup obsahuje dostatek informací pro doporučení vhodných typů vizualizací. Hlavní výsledek analýzy je vhodné prezentovat pomocí KPI karet. Rozložení poklesu podle produktových kategorií, prodejních kanálů a kamenných prodejen nejlépe zobrazí horizontální sloupcové grafy.

Vizualizace mohou ukázat rozsah a lokalizaci poklesu, nikoli jeho příčiny.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Doporučené vizualizace

| Priorita | Insight | Doporučená vizualizace | Business přínos |
|---:|---|---|---|
| 1 | Tržby poklesly o 18 %, prodané množství o 6 % a absolutní marže o 15 % | Sada tří KPI karet | Rychlé vyjádření hlavního business výsledku |
| 2 | Největší absolutní pokles tržeb zaznamenaly Notebooky a Tablety, zatímco Příslušenství mírně rostlo | Horizontální sloupcový graf | Porovnání příspěvku produktových kategorií ke změně tržeb |
| 3 | Největší relativní pokles mezi prodejními kanály vykázal e-shop | Horizontální sloupcový graf | Identifikace nejvíce zasaženého prodejního kanálu |
| 4 | Nejvýraznější pokles mezi kamennými prodejnami zaznamenaly pobočky Brno a Ostrava | Horizontální sloupcový graf | Lokalizace poklesu v síti kamenných prodejen |

## 4. Detail jednotlivých vizualizací

### Vývoj hlavních výsledkových metrik

**Insight**

Celkové tržby poklesly o 18 %, prodané množství o 6 % a absolutní marže o 15 %.

**Doporučený typ vizualizace**

Sada tří KPI karet.

**Co má zobrazovat**

Procentní změnu celkových tržeb, prodaného množství a absolutní marže mezi první a druhou polovinou roku 2024.

**Proč je tento typ vhodný**

Všechny tři metriky představují hlavní souhrnné výsledky analýzy. KPI karty umožňují jejich rychlé a jednoznačné přečtení.

**Business přínos**

Poskytují managementu okamžitý přehled o rozsahu zhoršení obchodních výsledků.

**Rizika interpretace**

Rozdílný pokles metrik sám o sobě nevysvětluje příčiny změny ani vliv cen, množství a produktového mixu.

---

### Změna tržeb podle produktových kategorií

**Insight**

Největší absolutní pokles tržeb zaznamenaly Notebooky a Tablety, zatímco Příslušenství mírně rostlo.

**Doporučený typ vizualizace**

Horizontální sloupcový graf absolutní změny tržeb podle produktových kategorií.

**Co má zobrazovat**

Porovnání absolutní změny tržeb jednotlivých produktových kategorií mezi oběma pololetími.

**Proč je tento typ vhodný**

Umožňuje přímo porovnat velikost poklesu nebo růstu kategorií a odlišit nejvíce zasažené oblasti.

**Business přínos**

Ukazuje, ve kterých částech produktového portfolia se změna celkových tržeb nejvýrazněji projevila.

**Rizika interpretace**

Největší absolutní pokles nemusí znamenat největší relativní pokles. Graf také neprokazuje, proč se tržby kategorií změnily.

---

### Změna tržeb podle prodejních kanálů

**Insight**

Největší relativní pokles mezi prodejními kanály vykázal e-shop.

**Doporučený typ vizualizace**

Horizontální sloupcový graf relativní změny tržeb podle prodejních kanálů.

**Co má zobrazovat**

Procentní změnu tržeb jednotlivých prodejních kanálů mezi první a druhou polovinou roku 2024.

**Proč je tento typ vhodný**

Sloupcový graf umožňuje přímé porovnání relativního vývoje kanálů a jednoznačně identifikuje e-shop jako nejvíce zasažený kanál.

**Business přínos**

Pomáhá určit, ve kterém prodejním kanálu byl pokles poměrově nejvýraznější.

**Rizika interpretace**

Relativní pokles nevyjadřuje absolutní příspěvek kanálu k celkovému poklesu. Výsledek neprokazuje příčinu slabšího výkonu e-shopu.

---

### Změna tržeb podle kamenných prodejen

**Insight**

Nejvýraznější pokles mezi kamennými prodejnami zaznamenaly pobočky Brno a Ostrava.

**Doporučený typ vizualizace**

Horizontální sloupcový graf změny tržeb podle poboček.

**Co má zobrazovat**

Porovnání změny tržeb jednotlivých kamenných prodejen mezi oběma pololetími.

**Proč je tento typ vhodný**

Umožňuje přehledné porovnání poboček a identifikaci lokalit s nejvýraznějším poklesem.

**Business přínos**

Lokalizuje změnu obchodního výkonu v rámci prodejní sítě.

**Rizika interpretace**

Graf nevysvětluje důvody rozdílů mezi pobočkami. Bez dalších dat nelze pokles spojovat například s marketingem, zásobami, konkurencí nebo zákaznickým chováním.

## 5. Doporučené pořadí prezentace

1. Vývoj hlavních výsledkových metrik
2. Změna tržeb podle produktových kategorií
3. Změna tržeb podle prodejních kanálů
4. Změna tržeb podle kamenných prodejen

## 6. Vizualizace, které nejsou doporučené

- **Spojnicový graf měsíčního vývoje:** vstup obsahuje pouze porovnání pololetí a neposkytuje měsíční časovou řadu.
- **Koláčový graf:** není vhodný pro porovnání změn tržeb mezi obdobími ani pro zobrazení kladných a záporných změn.
- **Rozkladový strom nebo dekompoziční graf:** mohl by naznačovat vysvětlení příčin poklesu, které analýza neprokázala.
- **Kombinovaný graf tržeb, množství a marže:** mohl by podporovat nepodložené závěry o vztazích mezi těmito metrikami.

## 7. Celkové zhodnocení

Navržené vizualizace pokrývají všechny potvrzené insighty: celkovou změnu hlavních metrik i lokalizaci poklesu podle produktových kategorií, prodejních kanálů a kamenných prodejen.

Omezení analýzy nejsou vhodná pro grafickou prezentaci. Pouze textově má být uvedeno, že analýza vychází z agregovaných transakčních dat, neodděluje vliv množství, cen a produktového mixu a neumožňuje určit skutečné příčiny poklesu.

Navržená kombinace KPI karet a horizontálních sloupcových grafů podporuje objektivní interpretaci výsledků, pokud jsou zobrazené rozdíly prezentovány jako popis změny, nikoli jako vysvětlení jejích příčin.
