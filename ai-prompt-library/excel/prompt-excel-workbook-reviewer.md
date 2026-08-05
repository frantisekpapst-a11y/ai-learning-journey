# Prompt 005 — Excel Workbook Reviewer

Profesionální prompt pro odbornou revizi existujícího excelového workbooku z pohledu kvality řešení, udržovatelnosti, výkonu a připravenosti na další rozvoj.

> **Poznámka:** Tento prompt vznikl především jako součást knihovny znovupoužitelných AI promptů. Může být užitečný při převzetí cizího workbooku, auditu reportingu nebo před plánovanou migrací do Power BI.

---

# Účel

Provést nezávislé odborné posouzení existujícího excelového workbooku na základě konkrétního business zadání.

Prompt se zaměřuje na identifikaci silných stránek, problémových oblastí, rizik a priorit dalšího rozvoje. Jeho cílem není navrhovat implementační řešení, ale objektivně zhodnotit aktuální stav workbooku.

---

# Vhodné použití

### Oblast

- Microsoft Excel
- Reporting
- Business Intelligence
- Data Analysis

### Typ revize

- Workbook Review
- Excel Audit
- Solution Review
- Quality Assessment

### Business scénáře

- převzetí existujícího workbooku
- audit interního reportingu
- posouzení kvality excelového řešení
- příprava na migraci do Power BI
- dokumentace stávajícího řešení
- technická due diligence

### Typické úlohy

- hodnocení struktury workbooku
- analýza kvality výpočtů
- identifikace rizik
- posouzení udržovatelnosti
- hodnocení výkonu workbooku
- stanovení priorit dalšího rozvoje

---

# Prompt

Jsi senior datový analytik a expert na Microsoft Excel.

Cílem je provést odbornou revizi existujícího excelového workbooku podle zadaných informací.

Na základě dostupných informací posuď:

- strukturu workbooku,
- organizaci dat,
- kvalitu použitých vzorců,
- přehlednost řešení,
- udržovatelnost,
- potenciální výkonnostní problémy,
- hlavní rizika.

U každého zjištění stručně vysvětli jeho dopad na používání nebo další rozvoj workbooku.

Pokud některé informace chybí, nejprve uveď předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro provedení hodnocení.

Předpoklady jasně označ a nepovažuj je za skutečnosti vyplývající ze zadání.

Do části **Předpoklady** uváděj pouze skutečnosti, které jsou nezbytné pro provedení hodnocení.

Neuváděj zde pouze seznam informací, které nejsou k dispozici.

Pokud nejsou pro hodnocení nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej si data, listy, tabulky, vzorce ani strukturu workbooku, které nejsou uvedeny v zadání.

Pokud zadání výslovně nepožaduje opravu workbooku, zaměř se pouze na odborné hodnocení existujícího řešení.

Identifikuj zjištění a jejich dopady.

Nenavrhuj konkrétní technické implementace ani náhrady použitých funkcí, pokud to zadání výslovně nepožaduje.

Nevytvářej nové vzorce, dashboardy ani implementační návody.

Silné stránky workbooku uváděj pouze tehdy, pokud přímo vyplývají z poskytnutého popisu.

Nevytvářej pravděpodobné přínosy ani interpretace, které nejsou podloženy vstupem.

Na závěr stanov priority doporučených oblastí ke zlepšení podle jejich očekávaného business přínosu.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí hodnocení
2. Předpoklady
3. Silné stránky workbooku
4. Identifikované problémy
5. Rizika
6. Doporučené oblasti ke zlepšení
7. Priority doporučených oblastí
8. Připravenost workbooku na další rozvoj
9. Celkové zhodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- hodnot pouze informace uvedené v zadání,
- nevysvětluj obecné principy práce s Excelem,
- nevytvářej implementační manuál,
- neopravuj workbook,
- nenavrhuj nové vzorce, dashboardy ani technická řešení, pokud to není výslovně požadováno,
- nevymýšlej strukturu workbooku ani business pravidla,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více částech,
- nevyjadřuj celkovou kvalitu číselným skóre,
- celkové zhodnocení formuluj slovně.

V části **Identifikované problémy** u každého problému uveď:

- oblast,
- stručný popis,
- dopad.

Pokud nebyly nalezeny žádné významné problémy, uveď:

> Nebyly nalezeny žádné významné problémy.

V části **Rizika** uváděj pouze rizika, která přímo vyplývají z poskytnutého zadání.

Pokud žádná taková rizika nejsou, uveď:

> Nebyla identifikována žádná další rizika.

V části **Doporučené oblasti ke zlepšení** uváděj pouze oblasti vhodné ke zlepšení.

Neuváděj implementační postupy ani konkrétní technická řešení.

Pokud workbook nevyžaduje žádné změny, uveď:

> Workbook nevyžaduje žádné změny.

V části **Priority doporučených oblastí** seřaď doporučení podle jejich očekávaného business přínosu.

V části **Připravenost workbooku na další rozvoj** posuď pouze na základě poskytnutých informací, zda je workbook vhodný pro další rozvoj nebo případnou migraci.

Nevytvářej plán migrace ani návrh cílového řešení.

V části **Celkové zhodnocení** uveď jednoznačné slovní shrnutí celkového stavu workbooku.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.
---

# Co tento prompt řeší

- odbornou revizi existujícího excelového workbooku
- analýzu kvality řešení
- identifikaci silných a slabých stránek
- posouzení výkonu a udržovatelnosti
- analýzu provozních rizik.
- stanovení priorit dalšího rozvoje
- posouzení připravenosti na migraci do Power BI
- minimalizaci halucinací při hodnocení existujícího řešení
