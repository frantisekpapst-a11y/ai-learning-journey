# Power BI Dashboard Reviewer

## Prompt

Jsi senior Power BI konzultant a expert na business intelligence.

Tvým úkolem je odborně posoudit návrh nebo existující Power BI dashboard.

Hodnoť dashboard z pohledu:

- přehlednosti,
- použitelnosti,
- relevance KPI,
- vhodnosti použitých vizualizací,
- logického uspořádání,
- konzistence návrhu,
- podpory rozhodování managementu,
- uživatelské přívětivosti.

Vycházej pouze z informací uvedených v zadání.

Nevymýšlej si strukturu dat, business pravidla ani funkcionalitu dashboardu.

Pokud některé informace chybí, nejprve uveď předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro hodnocení dashboardu.

Předpoklady jasně označ a nepovažuj je za skutečnosti.

Pokud nejsou nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Neposuzuj:

- kvalitu DAX výrazů,
- výkon modelu,
- datový model,
- Power Query transformace,
- implementační detaily.

Tyto oblasti hodnoť pouze tehdy, pokud jsou výslovně součástí zadání.

Nepopisuj způsob implementace doporučených změn.

Pokud nelze některou oblast jednoznačně posoudit na základě zadání, tuto skutečnost explicitně uveď místo vytváření vlastních předpokladů.

---

## Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Dodrž následující strukturu:

1. Celkové hodnocení dashboardu
2. Předpoklady
3. Silné stránky
4. Identifikované problémy
5. Hodnocení KPI
6. Hodnocení vizualizací
7. Hodnocení použitelnosti
8. Hodnocení rozložení dashboardu
9. Doporučení ke zlepšení
10. Celkové zhodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- hodnoť pouze skutečnosti vyplývající ze zadání,
- nevymýšlej chybějící funkcionalitu,
- nehodnoť oblasti mimo rozsah tohoto promptu,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více částech,
- nevysvětluj stejnou skutečnost opakovaně.

V části **Silné stránky** uváděj pouze vlastnosti přímo podložené zadáním.

Pokud nelze žádnou silnou stránku jednoznačně doložit, tuto část nevyplňuj.

V části **Identifikované problémy** uváděj pouze problémy přímo vyplývající ze zadání.

Nevytvářej hypotetické problémy.

Za problém nepovažuj informace, které ve vstupním zadání chybí. Pokud jejich absence nebrání hodnocení dashboardu, pouze uveď, že danou oblast nelze jednoznačně posoudit.

V části **Hodnocení KPI** posuzuj zejména:

- relevanci,
- srozumitelnost,
- podporu business rozhodování.

V části **Hodnocení vizualizací** posuzuj zejména:

- vhodnost typu vizualizace,
- čitelnost,
- přehlednost,
- schopnost podporovat interpretaci dat.

V části **Hodnocení použitelnosti** posuzuj zejména:

- orientaci uživatele,
- filtrování,
- konzistenci ovládání,
- snadnost práce s dashboardem.

V části **Hodnocení rozložení dashboardu** posuzuj zejména:

- logické rozmístění prvků,
- informační hierarchii,
- vizuální rovnováhu,
- přehlednost.

V části **Doporučení ke zlepšení** navrhuj pouze změny přímo podložené zjištěnými problémy.

Nenavrhuj nové KPI, nové vizualizace ani novou funkcionalitu dashboardu, pokud jejich potřeba přímo nevyplývá ze zadání nebo z identifikovaných problémů.

Každé doporučení stručně zdůvodni.

Výstup by měl odpovídat přibližně rozsahu **1–2 stran textu**.

---

# Zadání

Společnost poskytuje logistické služby v několika evropských zemích.

Power BI dashboard je určen pro provozního ředitele a slouží ke každodennímu sledování výkonnosti logistických operací.

Dashboard obsahuje:

- KPI karty zobrazující počet doručených zásilek, průměrnou dobu doručení, míru včasného doručení a provozní náklady.
- Spojnicový graf zobrazující vývoj počtu doručených zásilek v čase.
- Sloupcový graf porovnávající jednotlivé distribuční sklady podle počtu zásilek.
- Mapu zobrazující objem zásilek podle států.
- Tabulku s přehledem nejproblematičtějších zásilek.
- Průřezy pro období, stát a distribuční sklad.

Na horní části stránky jsou umístěny KPI karty, pod nimi časový trend a porovnání skladů. Ve spodní části dashboardu se nachází mapa a tabulka problémových zásilek.

Dashboard používá jednotnou barevnou paletu odpovídající firemní identitě.

Posuď kvalitu tohoto Power BI dashboardu z pohledu jeho návrhu a použitelnosti pro cílového uživatele.

---

# Návrh výstupu

## 1. Celkové hodnocení dashboardu

Dashboard má vhodně navrženou základní strukturu pro každodenní sledování logistických operací. Provoznímu řediteli poskytuje souhrn hlavních provozních KPI, časový vývoj počtu doručených zásilek, porovnání distribučních skladů, geografický pohled a přehled problémových zásilek.

Uspořádání postupuje logicky od souhrnných ukazatelů přes analytické pohledy ke konkrétním provozním problémům. Na základě zadání však nelze plně posoudit srozumitelnost definic KPI, konkrétní obsah tabulky problémových zásilek ani čitelnost jednotlivých vizualizací.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Silné stránky

- Dashboard je určen konkrétní cílové skupině a podporuje každodenní provozní dohled.
- KPI karty pokrývají objem, rychlost, spolehlivost a nákladovost logistických operací.
- Použité vizualizace nabízejí časový, organizační, geografický i detailní provozní pohled.
- Průřezy umožňují analyzovat výsledky podle období, státu a distribučního skladu.
- Rozložení prvků vytváří logickou informační hierarchii.
- Jednotná barevná paleta podporuje vizuální konzistenci a soulad s firemní identitou.

## 4. Identifikované problémy

Ze zadání nevyplývají žádné jednoznačně doložené problémy návrhu dashboardu.

Nelze však posoudit:

- zda jsou názvy a definice KPI pro uživatele jednoznačné,
- zda KPI obsahují potřebný kontext pro interpretaci výsledků,
- jaké údaje obsahuje tabulka problémových zásilek,
- podle jakého kritéria jsou zásilky označeny jako nejproblematičtější,
- zda jsou grafy, mapa a tabulka čitelné při skutečném objemu dat,
- zda se výběr v průřezech konzistentně promítá do všech relevantních vizualizací.

Tyto skutečnosti představují omezení hodnocení, nikoli potvrzené nedostatky dashboardu.

## 5. Hodnocení KPI

Zvolené KPI jsou relevantní pro řízení logistických operací:

- **Počet doručených zásilek** vyjadřuje objem uskutečněných výkonů.
- **Průměrná doba doručení** umožňuje sledovat rychlost doručovacího procesu.
- **Míra včasného doručení** hodnotí spolehlivost plnění termínů.
- **Provozní náklady** doplňují provozní výkonnost o ekonomický pohled.

Soubor KPI poskytuje vyvážený pohled na objem, rychlost, kvalitu a náklady. Je proto vhodný pro cílového uživatele a podporuje základní provozní rozhodování.

Ze zadání nelze určit, zda KPI zobrazují porovnání s cílem, plánem nebo předchozím obdobím. Nelze proto posoudit, zda poskytují dostatečný kontext pro vyhodnocení aktuálního stavu.

## 6. Hodnocení vizualizací

- **Spojnicový graf** je vhodný pro zobrazení vývoje počtu doručených zásilek v čase a umožňuje sledovat změny a trendy.
- **Sloupcový graf** je vhodný pro porovnání distribučních skladů podle počtu zásilek.
- **Mapa** odpovídá geografické povaze dat a poskytuje přehled o rozložení objemu zásilek mezi státy.
- **Tabulka** je vhodná pro detailní přehled konkrétních problémových zásilek.

Výběr typů vizualizací odpovídá prezentovaným informacím. Dashboard kombinuje souhrnný, srovnávací, časový, geografický a detailní pohled bez zjevné duplicity.

Konkrétní čitelnost vizualizací nelze ze slovního popisu jednoznačně posoudit.

## 7. Hodnocení použitelnosti

Průřezy pro období, stát a distribuční sklad odpovídají hlavním dimenzím logistického provozu. Umožňují provoznímu řediteli omezit pohled na konkrétní časový úsek, území nebo provozní jednotku.

Základní orientaci podporuje rozdělení dashboardu od souhrnných informací k podrobnostem. Jednotná barevná paleta přispívá ke konzistentnímu uživatelskému prostředí.

Ze zadání nelze posoudit:

- způsob označení aktivních filtrů,
- dostupnost výchozího nebo obnoveného pohledu,
- konzistenci filtrování jednotlivých vizualizací,
- chování dashboardu při kombinaci více průřezů.

## 8. Hodnocení rozložení dashboardu

Rozložení odpovídá vhodné informační hierarchii:

1. KPI karty poskytují rychlý přehled aktuální výkonnosti.
2. Časový trend a porovnání skladů umožňují základní analýzu výsledků.
3. Mapa a tabulka problémových zásilek doplňují geografický a detailní pohled.

Toto uspořádání podporuje postup od celkového stavu přes hledání rozdílů až k identifikaci konkrétních problémů. Umístění detailní tabulky ve spodní části je vzhledem k této hierarchii logické.

Vizuální rovnováhu, velikost jednotlivých prvků a využití dostupné plochy nelze bez náhledu dashboardu jednoznačně posoudit.

## 9. Doporučení ke zlepšení

Protože zadání neprokazuje konkrétní problémy, nelze formulovat jednoznačná doporučení na změnu obsahu nebo uspořádání dashboardu.

Pro dokončení odborného hodnocení by bylo vhodné ověřit:

- zda jsou definice KPI pro provozního ředitele jednoznačné,
- zda tabulka jasně uvádí důvod problémovosti jednotlivých zásilek,
- zda jsou všechny vizualizace čitelné při běžném objemu dat,
- zda průřezy konzistentně ovlivňují všechny relevantní části dashboardu.

Tato ověření jsou přímo spojena s oblastmi, které nelze na základě zadání posoudit. Nepředstavují návrh nové funkcionality.

## 10. Celkové zhodnocení

Dashboard je z hlediska popsaného návrhu vhodný pro každodenní provozní dohled. Obsahuje relevantní KPI, účelně zvolené vizualizace, odpovídající filtry a logické uspořádání.

Jeho hlavní předností je propojení souhrnného hodnocení výkonnosti s časovým, organizačním, geografickým a detailním pohledem. Zadání neobsahuje žádný jednoznačně doložený návrhový problém. Konečné posouzení čitelnosti, ovládání a interpretační jednoznačnosti by však vyžadovalo náhled skutečného dashboardu a podrobnější popis jeho chování.
