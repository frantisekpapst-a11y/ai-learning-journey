# AI Prompt Library

Kurátorovaná knihovna znovupoužitelných AI promptů pro datovou analytiku, Business Intelligence a produktivitu.

---

# O knihovně

Tento repozitář obsahuje postupně rozšiřovanou knihovnu znovupoužitelných AI promptů zaměřených na datovou analytiku, Business Intelligence a každodenní práci analytika.

Nejde o sbírku jednorázových dotazů, ale o promyšlené pracovní postupy (workflows), které lze opakovaně používat, přizpůsobovat konkrétním projektům a průběžně vylepšovat na základě praktických zkušeností.

Každý prompt je navržen tak, aby byl:

- znovupoužitelný,
- snadno přizpůsobitelný,
- prakticky využitelný v reálných projektech,
- ověřený na realistických zadáních.

Součástí repozitáře jsou také **[Examples](ai-examples/ai-examples-advanced/)**, které obsahují ukázky použití jednotlivých promptů na realistických business scénářích.

---

# Struktura promptů

Každý prompt používá jednotnou strukturu:

- Účel
- Vhodné použití
- Prompt
- Co tento prompt řeší
- Další možnosti použití
- Lessons Learned

Každý příklad (Example) obsahuje:

- Zadání
- Výstup

---

# Aktuální prompty

## Business Intelligence

| ID | Prompt |
|----|--------|
| 001 | Power BI Executive Dashboard Designer |

---

# Připravované prompty

## Excel

- Excel Formula Assistant
- Excel KPI Dashboard Designer
- Power Query Transformation Assistant
- Excel Workbook Reviewer

## SQL

- SQL Query Generator
- SQL Query Reviewer
- SQL Query Optimizer
- SQL Debugger
- Database Schema Analyzer

## Power BI

- Power BI Dashboard Reviewer
- DAX Assistant
- Power BI Data Model Reviewer
- Power BI Performance Reviewer

## Datová analytika

- Data Cleaning Assistant
- Exploratory Data Analysis Assistant
- KPI Designer
- Root Cause Analysis Assistant
- Trend Analysis Assistant
- Customer Segmentation Assistant
- Data Validation Assistant

## Business analýza

- Business Requirements Analyzer
- Executive Summary Generator
- Business Question Refinement Assistant
- Requirements-to-KPI Assistant

## AI Quality

- Prompt Reviewer & Optimizer
- AI Output Reviewer

---

# Principy návrhu promptů

Každý prompt je navržen tak, aby:

- definoval jasnou roli AI,
- v návaznosti na konkrétní zadání řešil konkrétní analytický úkol,
- byl obecný a znovupoužitelný pro různé projekty,
- jasně určoval, jaké informace má obsahovat konkrétní zadání,
- obsahoval pouze nezbytná pravidla a omezení,
- definoval očekávaný rozsah a podobu výstupu,
- minimalizoval riziko halucinací,
- podporoval konzistentní a opakovatelné výsledky.

Konkrétní business kontext, dostupná data, cílová skupina a požadovaný výsledek jsou doplněny až v zadání připojeném k promptu.

Prompt představuje obecnou a znovupoužitelnou instrukci. Zadání následně doplňuje konkrétní situaci, data a business potřebu.

Prompty nejsou pevné šablony dokumentů. Jejich cílem je vést AI k vytvoření kvalitního řešení, nikoli vynutit jediný správný formát nebo totožnou odpověď napříč různými AI modely.

---

# Lessons Learned

- Prompt není pouze otázka, ale strukturované zadání, které AI jednoznačně definuje očekávaný úkol.
- Jasně definovaná role AI významně zvyšuje kvalitu, konzistenci a relevanci výsledků.
- Obecný a znovupoužitelný prompt doplněný konkrétním zadáním je efektivnější než vytváření nového promptu pro každý scénář.
- Prompt by měl AI vést k požadovanému výsledku, nikoli ji svazovat zbytečnými pravidly nebo implementačními detaily.
- Omezení domýšlení dat, datových struktur nebo dalších chybějících informací pomáhá výrazně snižovat riziko halucinací.
- Každý prompt v této knihovně řeší jeden konkrétní typ úlohy a je navržen tak, aby se nepřekrýval s ostatními prompty.
- Všechny prompty jsou průběžně testovány na realistických business scénářích a iterativně vylepšovány na základě získaných zkušeností.

---

# Status

| Položka | Hodnota |
|----------|---------|
| Projekt | AI Prompt Library |
| Verze | 1.0 |
| Stav | In Development |
| Autor | František Papst |
| Licence | MIT License |
