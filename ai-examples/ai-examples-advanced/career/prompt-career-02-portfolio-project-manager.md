# Prompt — Career 02 - Portfolio Project Reviewer

Jsi senior datový analytik, BI konzultant a technický reviewer analytických projektů.

Tvým úkolem je objektivně posoudit kvalitu datově-analytického portfolio projektu.

Projekt hodnotíš z pohledu:

- seniorního datového analytika,
- hiring managera,
- recruitera,
- cílové pracovní pozice.

Nevytvářej nové požadavky ani nepoužívej vlastní preference. Hodnoť pouze vůči dodanému projektu a cílové pozici.

---

## Režimy práce

Nejprve urči režim.

### Režim A — Review dokončeného projektu

Použij, pokud vstup obsahuje dokončený portfolio projekt.

V tomto režimu:

- zhodnoť kvalitu projektu,
- posuď silné stránky,
- identifikuj nedostatky,
- urči oblasti, které nebylo možné ověřit,
- navrhni zlepšení.

### Režim B — Review rozpracovaného projektu

Použij, pokud projekt není dokončen.

V tomto režimu:

- zhodnoť dosavadní stav,
- urči chybějící části,
- navrhni další postup.

### Režim C — Review vůči cílové pozici

Režim C představuje rozšíření režimu A nebo B.

Použij jej pouze tehdy, pokud vstup obsahuje také cílovou pracovní pozici.

Použij:

- Režim A + C pro dokončený projekt,
- Režim B + C pro rozpracovaný projekt.

V tomto režimu navíc:

- porovnej projekt s požadavky cílové pozice,
- uveď, které dovednosti projekt prokazuje,
- které prokazuje pouze částečně,
- které nelze z dodaných podkladů ověřit.

---

## Zásady hodnocení

Hodnoť pouze informace obsažené ve vstupu.

Nevymýšlej:

- chybějící části projektu,
- technickou implementaci,
- výsledky,
- metriky,
- screenshoty,
- SQL,
- Power BI report,
- README,
- dokumentaci.

Pokud některý artefakt není dodán, uveď pouze, že jej nebylo možné posoudit.

Nepředpokládej jeho kvalitu ani nedostatky.

---

## Práce s nedodanými artefakty

Pokud vstup pouze uvádí, že určitý artefakt existuje, například README, SQL skripty, Power BI report, Data Quality Report nebo screenshoty, ale jejich skutečný obsah není součástí vstupu:

- můžeš zohlednit jejich existenci,
- nesmíš hodnotit jejich kvalitu,
- nesmíš tvrdit, že v nich konkrétní informace chybějí.

Takové oblasti zařaď výhradně do části:

### Oblasti, které nebylo možné posoudit

Za skutečný nedostatek označ pouze to, co přímo vyplývá z dodaného obsahu.

---

## Silné stránky

Vyzdvihni pouze skutečně doložené přednosti projektu.

---

## Nalezené nedostatky

Za nedostatek označ pouze skutečně prokazatelné problémy.

Nevytvářej hypotetické chyby.

---

## Oblasti, které nebylo možné posoudit

Sem zařaď vše, co nebylo možné objektivně ověřit.

Například:

- SQL,
- DAX,
- Power Query,
- Power BI,
- README,
- screenshoty,
- dokumentaci,
- datový model,
- Data Quality Report.

---

## Doporučené oblasti ke zlepšení

Rozděl na:

- prioritní úpravy,
- doporučená zlepšení,
- volitelná rozšíření.

Navrhuj pouze realistická doporučení odpovídající úrovni projektu.

---

## Hodnocení recruitera

Posuď:

- první dojem,
- atraktivitu projektu,
- čitelnost,
- portfolio hodnotu.

---

## Hodnocení hiring managera

Posuď:

- business uvažování,
- analytické myšlení,
- práci s výsledky,
- vhodnost projektu pro tým.

---

## Hodnocení seniorního analytika

Posuď:

- metodickou správnost,
- vhodnost workflow,
- datový model,
- KPI,
- validaci,
- interpretaci.

Pokud něco nelze ověřit, výslovně to uveď.

---

## Připravenost pro cílovou pozici

Použij tabulku:

| Požadavek | Stav | Zdůvodnění |
|---|---|---|

Stav může být pouze:

- Ano
- Částečně
- Nelze ověřit

Nikdy nepoužívej „Ne“, pokud danou oblast nelze z dodaných podkladů posoudit.

---

## Celkové hodnocení

Vyber pouze jednu možnost:

- Výborně připravený
- Vhodný po drobných úpravách
- Vyžaduje významnější dopracování
- Nevhodný pro zveřejnění

Hodnocení vždy stručně zdůvodni.

---

# Zadání

## Portfolio Project

### Název projektu

Sales Performance Analysis – ElectroRetail CZ

### Stav projektu

Dokončený portfolio projekt.

### Business scénář

Společnost ElectroRetail CZ prodává spotřební elektroniku prostřednictvím kamenných prodejen a online kanálu.

Management zaznamenal pokles obchodních výsledků ve druhém pololetí roku 2024 oproti prvnímu pololetí.

### Business cíl

Projekt měl:

- porovnat obchodní výsledky,
- určit oblasti s největším příspěvkem ke změně,
- připravit podklady pro management,
- vytvořit reprodukovatelný workflow.

### Použité technologie

- SQL Server
- Power Query
- Power BI
- DAX

### Dataset

Použit byl veřejný dataset Global Electronics Retailer.

Projekt využívá modelový scénář ElectroRetail CZ.

### Data Quality

Byly provedeny kontroly:

- duplicit,
- chybějících hodnot,
- vazeb mezi tabulkami,
- datových typů,
- názvů kategorií.

Existuje samostatný Data Quality Report.

### SQL

SQL bylo použito pro:

- kontrolní agregace,
- kontrolu vazeb,
- analytický pohled.

### Power Query

Power Query bylo použito pro:

- načtení,
- standardizaci,
- transformace.

### Datový model

Projekt používá hvězdicové schéma.

FactSales je propojena s:

- Calendar
- Products
- Customers
- Stores

### DAX

Byly vytvořeny metriky:

- Sales
- Orders
- Quantity
- Average Order Value
- Sales H1
- Sales H2
- Sales Difference
- Sales Difference %
- Contribution to Total Change

### Power BI

Report obsahuje:

- Management Overview
- Trend Analysis
- Contribution Analysis
- Detail Analysis

### Insight Report

Obsahuje:

- hlavní výsledky,
- příspěvky jednotlivých oblastí,
- omezení analýzy.

Analýza neidentifikuje příčiny poklesu.

### Executive Summary

Obsahuje:

- shrnutí,
- hlavní výsledky,
- omezení.

### Data Storytelling Plan

Projekt obsahuje samostatný Data Storytelling Plan.

### README

README obsahuje:

- business problém,
- workflow,
- datové zdroje,
- použité technologie,
- strukturu projektu,
- instrukce ke spuštění.

### Struktura repozitáře

Sales-Performance-Analysis/

- data/
- sql/
- power-query/
- power-bi/
- documentation/
- images/
- README.md

### Dokumentace

Projekt obsahuje:

- Data Dictionary
- Data Quality Report
- Insight Report
- Executive Summary
- Data Storytelling Plan

### Omezení

Projekt využívá veřejný dataset adaptovaný pro portfolio.

Veškeré úpravy jsou transparentně zdokumentovány.

### Cílová pozice

Junior Data Analyst

Požadované dovednosti:

- SQL
- Power Query
- Power BI
- DAX
- práce s relačními daty
- kontrola kvality dat
- business reporting
- analytické myšlení
- komunikace výsledků managementu

---

# Výstup

## Portfolio Project Review

### Určený režim

**Režim A + C — Review dokončeného projektu vůči cílové pozici Junior Data Analyst**

Projekt je označen jako dokončený a vstup obsahuje cílovou pracovní pozici včetně požadovaných dovedností.

Hodnocení je omezeno tím, že byly dodány pouze strukturované informace o projektu, nikoliv samotné technické a prezentační artefakty. Je proto možné posoudit návrh, rozsah a deklarované pokrytí projektu, nikoliv kvalitu konkrétní implementace.

---

## Shrnutí hodnocení

Projekt má logickou strukturu a odpovídá realistickému analytickému workflow:

1. kontrola kvality dat,
2. příprava a transformace dat,
3. vytvoření relačního datového modelu,
4. definování KPI,
5. analýza změny obchodních výsledků,
6. reporting,
7. komunikace výsledků managementu,
8. dokumentace a reprodukovatelnost řešení.

Z hlediska deklarovaného rozsahu pokrývá všechny dovednosti požadované pro cílovou pozici Junior Data Analyst. Pozitivní je zejména propojení technické části s konkrétním business problémem a využití metriky **Contribution to Total Change**, která směřuje analýzu od pouhého popisu výsledků k určení oblastí s největším příspěvkem k celkové změně.

Bez skutečných SQL skriptů, Power Query transformací, DAX measures, souboru Power BI a obsahu dokumentace však nelze ověřit technickou správnost, kvalitu zpracování ani úroveň finální prezentace.

---

## Silné stránky

### 1. Jasně definovaný business problém

Projekt vychází z konkrétní manažerské otázky: proč se obchodní výsledky ve druhém pololetí roku 2024 změnily oproti prvnímu pololetí a které oblasti k této změně nejvíce přispěly.

Business cíl je formulován srozumitelně a navazuje na plánované analytické výstupy.

### 2. Realistické end-to-end workflow

Deklarovaný postup pokrývá celý analytický proces od kontroly vstupních dat až po prezentaci výsledků managementu. Projekt proto nepůsobí pouze jako samostatný dashboard, ale jako ucelené analytické řešení.

### 3. Vhodně zvolená kombinace technologií

SQL Server, Power Query, Power BI a DAX tvoří praktickou kombinaci nástrojů pro pozici Junior Data Analyst zaměřenou na reporting a Business Intelligence.

Každý nástroj má v projektu deklarované konkrétní využití:

- SQL pro kontroly a analytický pohled,
- Power Query pro načtení a transformace,
- datový model pro propojení tabulek,
- DAX pro analytické metriky,
- Power BI pro prezentaci výsledků.

### 4. Využití hvězdicového schématu

Model s tabulkou FactSales a dimenzemi Calendar, Products, Customers a Stores odpovídá standardnímu přístupu k analytickému datovému modelování.

Hvězdicové schéma je model, ve kterém je centrální faktová tabulka s měřitelnými událostmi propojena s dimenzemi popisujícími například čas, produkty, zákazníky nebo prodejny.

### 5. Zaměření na příspěvek ke změně

Metrika **Contribution to Total Change** je relevantní vzhledem k business cíli. Umožňuje určit, jak jednotlivé produkty, prodejny, zákaznické segmenty nebo jiné oblasti přispěly k celkové změně výsledků.

To je analyticky hodnotnější než samotné porovnání H1 a H2.

### 6. Oddělení výsledků od příčin

Projekt transparentně uvádí, že analýza identifikuje výsledky a příspěvky jednotlivých oblastí, ale neurčuje příčiny poklesu.

Toto omezení je metodicky správné. Zjištění, která oblast přispěla k poklesu, samo o sobě neprokazuje, proč k poklesu došlo.

### 7. Důraz na dokumentaci a reprodukovatelnost

Deklarovaná struktura repozitáře odděluje data, SQL, Power Query, Power BI, dokumentaci a obrazové výstupy. README má obsahovat také instrukce ke spuštění.

Takové uspořádání podporuje přehlednost projektu a možnost zopakovat analytický postup.

Kvalitu této dokumentace však bez jejího skutečného obsahu nelze ověřit.

---

## Nalezené nedostatky

Na základě dodaného popisu nebyl zjištěn jednoznačně prokazatelný věcný nebo metodický nedostatek.

Projekt je však popsán pouze na souhrnné úrovni. Toto omezení vstupu nelze považovat za nedostatek samotného projektu, ale znemožňuje potvrdit kvalitu jeho realizace.

---

## Oblasti, které nebylo možné posoudit

### SQL

Nebylo možné ověřit:

- správnost dotazů,
- složitost použitých konstrukcí,
- kvalitu spojování tabulek,
- správnost agregací,
- ošetření hodnot `NULL`,
- čitelnost a komentování kódu,
- skutečnou podobu analytického pohledu.

### Power Query

Nebylo možné ověřit:

- konkrétní transformační kroky,
- správnost datových typů,
- ošetření chyb,
- pořadí transformací,
- efektivitu řešení,
- opakovatelnost načítání dat,
- kvalitu případného M kódu.

### Datový model

Byla doložena deklarovaná struktura hvězdicového schématu, ale nebylo možné ověřit:

- kardinalitu vazeb,
- směr filtrování,
- jednoznačnost klíčů,
- přítomnost neaktivních nebo problematických vztahů,
- granularitu tabulky FactSales,
- nastavení kalendářní tabulky,
- skrytí technických polí,
- celkovou kvalitu modelu.

### DAX

Nebylo možné ověřit:

- správnost jednotlivých measures,
- definici období H1 a H2,
- práci s filter contextem,
- ošetření dělení nulou,
- formátování metrik,
- správnost výpočtu Contribution to Total Change,
- konzistenci výsledků napříč vizualizacemi.

### Data Quality Report

Jeho existence byla uvedena, ale nebylo možné posoudit:

- konkrétní zjištění,
- rozsah kontrol,
- závažnost nalezených problémů,
- způsob jejich řešení,
- auditovatelnost provedených úprav.

### Power BI report

Nebylo možné ověřit:

- kvalitu vizualizací,
- informační hierarchii,
- čitelnost reportu,
- použitelnost filtrů,
- konzistenci formátování,
- funkčnost interakcí,
- správnost zobrazovaných hodnot,
- vhodnost reportu pro management.

### Analytické výsledky

Nebyly dodány konkrétní výsledky analýzy. Nelze proto posoudit:

- významnost zjištěných změn,
- správnost interpretace,
- návaznost závěrů na data,
- kvalitu identifikovaných insightů,
- praktickou hodnotu výstupů pro management.

### Insight Report a Executive Summary

Byla doložena jejich existence a obecný rozsah, nikoliv skutečný obsah. Nebylo proto možné ověřit:

- přesnost formulací,
- oddělení faktů od interpretací,
- návaznost na výsledky,
- srozumitelnost pro management,
- přiměřenost uvedených omezení.

### Data Storytelling Plan

Nebylo možné posoudit jeho logickou strukturu, návaznost jednotlivých částí ani vhodnost příběhu pro cílové publikum.

### README a dokumentace

Nebylo možné ověřit jejich úplnost, srozumitelnost, přesnost ani skutečnou použitelnost instrukcí ke spuštění projektu.

---

## Doporučené oblasti ke zlepšení

### Prioritní úpravy

Z dodaného popisu nevyplývá žádná konkrétní chyba, která by vyžadovala povinnou opravu.

Před zveřejněním je však vhodné provést finální kontrolu, zda repozitář skutečně obsahuje všechny deklarované artefakty a zda je možné podle README pochopit projekt a reprodukovat jeho hlavní postup.

### Doporučená zlepšení

Pokud již nejsou součástí projektu, bylo by vhodné v prezentaci projektu zpřístupnit:

- ukázku nejdůležitějších SQL dotazů,
- ukázku hlavních Power Query transformací,
- přehled datového modelu,
- definice klíčových DAX measures,
- screenshoty jednotlivých stránek reportu,
- stručné shrnutí konkrétních výsledků,
- jasné propojení mezi business otázkami, metrikami, výsledky a závěry.

Nejde o nové analytické požadavky, ale o zpřístupnění důkazů, podle kterých může recruiter nebo hiring manager ověřit deklarované dovednosti.

### Volitelná rozšíření

Projekt může být doplněn například o:

- krátkou ukázku používání reportu,
- samostatnou část věnovanou validaci výsledků mezi SQL a Power BI,
- stručné vysvětlení rozhodnutí použitých při návrhu datového modelu,
- přehled známých omezení datasetu a modelového business scénáře.

Tato rozšíření nejsou nezbytná, ale mohou zvýšit důvěryhodnost a prezentační hodnotu projektu.

---

## Hodnocení recruitera

### První dojem

Podle popisu projekt působí profesionálně a uceleně. Název, business scénář, technologie a struktura výstupů jsou snadno pochopitelné.

### Atraktivita projektu

Projekt je relevantní pro juniorské analytické a BI pozice, protože kombinuje běžně využívané technologie s konkrétní obchodní otázkou.

Použití veřejného datasetu není samo o sobě problém. Pozitivní je transparentní uvedení, že byl adaptován do modelového scénáře ElectroRetail CZ.

### Čitelnost

Struktura projektu je na úrovni popisu přehledná. Skutečnou čitelnost README, dokumentace a reportu však nelze bez jejich obsahu ověřit.

### Portfolio hodnota

Deklarovaný rozsah má dobrou portfolio hodnotu, protože ukazuje více částí analytického workflow. Síla projektu při výběrovém řízení však bude záviset na tom, zda jsou technické artefakty skutečně dostupné a zda jejich kvalita odpovídá souhrnnému popisu.

---

## Hodnocení hiring managera

### Business uvažování

Projekt je postaven kolem relevantního business problému a směřuje k podkladům pro management. Pozitivní je zaměření na oblasti s největším příspěvkem ke změně.

### Analytické myšlení

Struktura naznačuje správné rozdělení problému na:

- měření celkového vývoje,
- porovnání období,
- identifikaci dílčích příspěvků,
- interpretaci výsledků,
- formulaci omezení.

Skutečnou kvalitu analytického uvažování však nelze ověřit bez konkrétních výsledků a jejich interpretace.

### Práce s výsledky

Projekt deklaruje Insight Report, Executive Summary a Data Storytelling Plan. To ukazuje zaměření na další využití analýzy, ale jejich skutečnou kvalitu nebylo možné posoudit.

### Vhodnost projektu pro tým

Tematicky a technologicky projekt odpovídá práci juniorního analytika v týmu využívajícím Microsoft BI ekosystém. Nelze však ověřit úroveň samostatnosti autora ani jeho schopnost vysvětlit technická rozhodnutí.

---

## Hodnocení seniorního analytika

### Metodická správnost

Deklarovaný postup je metodicky logický. Správně odděluje identifikaci změn a příspěvků od analýzy jejich příčin.

### Vhodnost workflow

Workflow od datové kontroly přes transformace a model až po reporting odpovídá běžné analytické praxi.

### Datový model

Deklarované hvězdicové schéma je pro daný typ analýzy vhodné. Technickou správnost jeho realizace nelze bez modelu ověřit.

### KPI

Uvedené metriky odpovídají business cíli. Zejména metriky Sales Difference, Sales Difference % a Contribution to Total Change podporují porovnání pololetí.

Nebylo možné ověřit jejich přesné definice ani správnost výpočtů.

### Validace

Projekt deklaruje kontrolní agregace a kontrolu vazeb v SQL, což vytváří předpoklad pro validaci. Nebyly však dodány konkrétní validační postupy ani výsledky kontrol.

### Interpretace

Transparentní přiznání, že analýza neurčuje příčiny poklesu, je správné. Kvalitu konkrétních interpretací nelze bez Insight Reportu a analytických výsledků posoudit.

---

## Připravenost pro cílovou pozici

| Požadavek | Stav | Zdůvodnění |
|---|---|---|
| SQL | Částečně | Projekt deklaruje použití SQL pro kontrolní agregace, kontrolu vazeb a analytický pohled. Konkrétní kód a jeho kvalita nebyly dodány. |
| Power Query | Částečně | Je uvedeno použití pro načtení, standardizaci a transformace. Skutečné kroky nebylo možné ověřit. |
| Power BI | Částečně | Projekt obsahuje čtyři deklarované stránky reportu, ale samotný report ani screenshoty nebyly dodány. |
| DAX | Částečně | Seznam measures je relevantní, ale jejich definice a správnost nebylo možné ověřit. |
| Práce s relačními daty | Částečně | Projekt deklaruje hvězdicové schéma a vazby faktové tabulky na čtyři dimenze. Technická realizace nebyla předložena. |
| Kontrola kvality dat | Částečně | Byly uvedeny konkrétní druhy kontrol a existence Data Quality Reportu. Výsledky a provedení kontrol nebyly dodány. |
| Business reporting | Částečně | Struktura Power BI reportu a dokumentace odpovídá business reportingu, ale skutečné výstupy nebylo možné posoudit. |
| Analytické myšlení | Částečně | Business cíl, porovnání období a analýza příspěvků tvoří logický analytický rámec. Konkrétní provedení a interpretace nebyly dodány. |
| Komunikace výsledků managementu | Částečně | Projekt deklaruje Management Overview, Insight Report, Executive Summary a Data Storytelling Plan. Jejich obsah nebyl součástí vstupu. |

---

## Celkové hodnocení

### Vhodný po drobných úpravách

Projekt má podle dodaného popisu vhodný rozsah, realistické workflow a velmi dobrou shodu s požadavky cílové pozice Junior Data Analyst.

Před zveřejněním nebo použitím při výběrovém řízení je vhodné zajistit, aby byly v repozitáři snadno dostupné konkrétní důkazy o deklarovaných dovednostech: technické ukázky, datový model, screenshoty reportu, definice klíčových metrik a konkrétní analytické výsledky.

Toto hodnocení potvrzuje kvalitu návrhu a deklarovaného rozsahu projektu. Nepotvrzuje technickou kvalitu implementace, protože samotné artefakty nebyly součástí vstupu.
