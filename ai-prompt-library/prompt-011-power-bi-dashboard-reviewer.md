# Prompt 011 — Power BI Dashboard Reviewer

Analyzuje existující Power BI dashboard a hodnotí jeho kvalitu z pohledu business intelligence, použitelnosti a podpory rozhodování bez hodnocení DAX, datového modelu, výkonu nebo technické implementace.

---

# Účel

Prompt slouží k odborné revizi existujícího Power BI dashboardu.

Je určen pro analýzu návrhu dashboardů, jejich struktury, použitých KPI, vizualizací, rozložení a celkové použitelnosti.

Prompt se zaměřuje výhradně na objektivně posouditelné vlastnosti dashboardu z pohledu cílového uživatele a business intelligence.

---

# Vhodné použití

### Oblast

- Power BI
- Business Intelligence
- Dashboard Design
- Data Visualization
- Datová analýza

### Typ úlohy

Odborná revize existujícího Power BI dashboardu.

### Business scénáře

- Revize návrhu Power BI dashboardu
- Kontrola dashboardu před nasazením
- Odborné hodnocení dashboardu pro zákazníka
- Posouzení použitelnosti dashboardu
- Ověření souladu s BI best practices

### Typické úlohy

- analýza struktury dashboardu
- hodnocení KPI
- hodnocení použitých vizualizací
- posouzení použitelnosti dashboardu
- kontrola informační hierarchie
- analýza rozložení dashboardu
- identifikace objektivně doložených problémů
- hodnocení podpory manažerského rozhodování
- doporučení oblastí ke zlepšení

---

# Prompt

```text
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

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

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
- neopakuj stejné informace ve více sekcích.

Jednotlivé sekce mají odlišný účel.

V části Silné stránky uváděj pouze skutečnosti podložené zadáním.

Pokud nelze žádnou silnou stránku jednoznačně doložit, tuto část nevyplňuj.

V části Identifikované problémy uváděj pouze skutečně doložené problémy dashboardu.

Nevytvářej hypotetické problémy.

Neuváděj jako problém skutečnost, že některé informace nejsou součástí vstupu.

Pokud některou oblast nelze objektivně posoudit z důvodu chybějících informací, uveď tuto skutečnost pouze jako omezení hodnocení.

V části Hodnocení KPI posuzuj zejména:

- relevanci,
- srozumitelnost,
- podporu business rozhodování.

V části Hodnocení vizualizací posuzuj zejména:

- vhodnost typu vizualizace,
- čitelnost,
- přehlednost,
- schopnost podporovat interpretaci dat.

V části Hodnocení použitelnosti posuzuj zejména:

- orientaci uživatele,
- filtrování,
- konzistenci ovládání,
- snadnost práce s dashboardem.

V části Hodnocení rozložení dashboardu posuzuj zejména:

- logické rozmístění prvků,
- informační hierarchii,
- vizuální rovnováhu,
- přehlednost.

V části Doporučení ke zlepšení uváděj pouze doporučení vycházející z objektivně zjištěných problémů dashboardu.

Nenavrhuj nové KPI, nové vizualizace ani novou funkcionalitu dashboardu, pokud jejich potřeba přímo nevyplývá ze zadání nebo z identifikovaných problémů.

Pokud nebyly identifikovány žádné objektivně doložené problémy, uveď:

> Nebyly identifikovány žádné objektivně doložené problémy dashboardu.

Každé doporučení stručně zdůvodni.

Pokud některou oblast nelze objektivně posoudit, uveď:

> Nelze ověřit z poskytnutých informací.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.
```

---

# Požadavky na výstup

Výstup obsahuje:

- stručné celkové hodnocení dashboardu,
- případné předpoklady,
- silné stránky dashboardu,
- identifikované objektivně doložené problémy,
- hodnocení KPI,
- hodnocení použitých vizualizací,
- hodnocení použitelnosti,
- hodnocení rozložení dashboardu,
- doporučené oblasti ke zlepšení,
- jednoznačné celkové zhodnocení.

---

# Co tento prompt řeší

- analyzuje existující Power BI dashboard,
- hodnotí kvalitu návrhu dashboardu,
- posuzuje vhodnost KPI,
- hodnotí použité vizualizace,
- kontroluje informační hierarchii a rozložení dashboardu,
- posuzuje použitelnost z pohledu cílového uživatele,
- identifikuje objektivně doložené problémy,
- navrhuje doporučení podložená zjištěnými nedostatky,
- nevymýšlí KPI, vizualizace ani funkcionalitu,
- nehodnotí DAX, datový model ani výkon, pokud nejsou součástí zadání,
- jasně rozlišuje mezi skutečným problémem a omezením způsobeným chybějícími informacemi.
