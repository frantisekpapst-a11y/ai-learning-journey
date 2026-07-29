# AI SQL Analyst Agent

> A platform-independent specification of an AI agent designed for SQL analysis, query development, validation, code review, and performance-aware optimization.  
> The repository includes a realistic Microsoft SQL Server reference case demonstrating how the agent translates business requirements into safe, transparent, and logically reviewed SQL solutions.  
> Its primary focus is correctness, schema awareness, data quality, reproducibility, and explicit separation between logical review and technical validation.

---

## O projektu

Tento repozitář obsahuje specifikaci **AI SQL Analyst Agenta** – specializovaného AI agenta pro práci s relačními databázemi a řešení SQL analytických úloh.

Agent není navržen pouze pro generování syntakticky správných SQL dotazů. Jeho úkolem je systematicky převádět business požadavky do databázových řešení, která jsou:

- věcně správná,
- založená na skutečném databázovém schématu,
- čitelná a reprodukovatelná,
- bezpečná pro práci s daty,
- transparentně validovaná,
- přiměřeně efektivní,
- srozumitelně vysvětlená.

Součástí projektu je také referenční případová studie **Retail Sales Database Analysis**, na které bylo chování agenta prakticky ověřeno a následně zpřesněno na základě odborného auditu.

---

## Hlavní cíle projektu

Projekt ukazuje, jak lze AI agenta využít při práci SQL analytika zejména pro:

- pochopení business zadání,
- analýzu databázového schématu,
- určení správné granularity dat,
- návrh analytických SQL dotazů,
- kontrolu `JOIN` operací a rizika duplicit,
- výpočet business KPI,
- práci s hodnotami `NULL`,
- posouzení kvality dat,
- SQL code review,
- návrh opravených dotazů,
- performance-aware návrh řešení,
- přípravu validačních SQL kontrol,
- dokumentaci předpokladů, rizik a omezení.

---

## Klíčové principy

AI SQL Analyst Agent je založen na následujících principech:

- **Correctness First** – správnost výsledku má přednost před stručností nebo technickou elegancí.
- **Business Relevance** – každý výpočet musí odpovídat definované business logice.
- **Schema Awareness** – agent nesmí používat tabulky nebo sloupce, které nebyly součástí schématu.
- **Appropriate Granularity** – před agregací musí být určena granularita zdrojových tabulek, mezivýsledků i konečného výstupu.
- **Data Quality by Design** – problémy s kvalitou dat musí být identifikovány a jejich dopad transparentně popsán.
- **Consistent KPI Eligibility** – stejné řádky musí vstupovat do jednotkových i finančních KPI.
- **Transparency** – skutečnosti, předpoklady, interpretace a omezení musí být jasně odděleny.
- **Reproducibility** – jiný analytik musí být schopen pochopit a zopakovat použitou logiku.
- **Safety** – výchozím režimem jsou pouze read-only dotazy.
- **Performance Awareness** – výkonová doporučení musí vycházet z konkrétních důvodů a nesmí být vydávána za ověřenou optimalizaci bez měření.

---

## Obsah repozitáře

```text
ai-sql-analyst-agent/
│
├── readme.md
│
├── agent-specification.md
│
├── prompt.md
│
└── reference-case.md
```

### `agent-specification`

Obsahuje platformově nezávislou funkční specifikaci AI SQL Analyst Agenta, včetně:

- role a odpovědností,
- pracovního postupu,
- pravidel pro návrh SQL dotazů,
- validace výsledků,
- SQL code review,
- kontroly kvality dat,
- bezpečnosti,
- výkonového posouzení,
- požadované struktury výstupu,
- závěrečného self-review.

### `reference-case`

Obsahuje kompletní referenční případovou studii **Retail Sales Database Analysis**, připravenou pro:

```text
Microsoft SQL Server 2022
T-SQL
```

Případová studie demonstruje použití specifikace na realistickém databázovém úkolu.

---

## Referenční případová studie

Referenční dokument řeší analýzu maloobchodních prodejů za rok 2025.

Obsahuje:

1. pochopení business zadání,
2. posouzení databázového schématu,
3. explicitní Data Quality Policy,
4. detailní diagnostické SQL kontroly,
5. souhrnný Data Quality Report,
6. měsíční analýzu prodejních výsledků,
7. identifikaci nejvýkonnějších produktů,
8. identifikaci zákazníků s vysokým podílem vratek,
9. code review původního reportingového dotazu,
10. opravenou a performance-aware verzi dotazu,
11. kandidáty na databázové indexy,
12. samostatně spustitelné validační dotazy,
13. omezení řešení,
14. závěrečný self-review.

---

## Data Quality Policy

Referenční případ používá politiku:

```text
Quarantine invalid rows
```

Numericky nevalidní položky nejsou opravovány ani odstraňovány ze zdrojových dat. Jsou odděleny od hlavních KPI a zachyceny v diagnostickém výstupu.

Do hlavních KPI nevstupují například řádky obsahující:

- chybějící, nulové nebo záporné množství,
- chybějící, nulovou nebo zápornou cenu,
- chybějící slevu,
- slevu mimo rozsah 0 až 1,
- záporné vrácené množství,
- vrácené množství vyšší než objednané množství.

Tím je zajištěno, že stejná množina validních řádků vstupuje do:

- jednotkových metrik,
- finančních metrik,
- výpočtu čistých tržeb,
- výpočtu podílu vratek.

Datové vady se ve zdrojových tabulkách automaticky neopravují, protože pro takový zásah musí existovat schválené business pravidlo.

---

## Příklady řešených analytických úloh

### Měsíční prodejní výsledky

Výstup je agregován podle:

- měsíce,
- produktové kategorie,
- prodejního kanálu.

Obsahuje například:

- počet dokončených objednávek,
- počet unikátních zákazníků,
- objednané jednotky,
- vrácené jednotky,
- čisté jednotky,
- hrubé tržby,
- hodnotu vráceného zboží,
- čisté tržby,
- procentní podíl vratek.

### Nejvýkonnější produkty

Pro každý měsíc jsou pomocí window function `DENSE_RANK` identifikovány produkty s nejvyššími čistými tržbami.

Shodné hodnoty získávají stejné pořadí a do výsledku jsou zahrnuta všechna pořadí od 1 do 3.

### Rizikoví zákazníci

Analýza identifikuje zákazníky, kteří:

- mají alespoň pět dokončených objednávek,
- vracejí více než 25 % objednaných jednotek.

Výpočet používá dvoustupňovou agregaci:

```text
validované položky
→ metriky objednávek
→ metriky zákazníků
```

Tento postup zpřehledňuje granularitu a odstraňuje potřebu počítat objednávky pomocí `COUNT(DISTINCT order_id)` v zákaznické agregaci.

---

## SQL Code Review

Součástí referenčního případu je také kontrola existujícího reportingového dotazu.

Code review posuzuje:

- správnost business logiky,
- práci se stavy objednávek,
- granularitu,
- násobení řádků při `JOIN`,
- správnost počtu objednávek,
- výpočet slev,
- zpracování vráceného zboží,
- práci s datem,
- používání `DISTINCT`,
- čitelnost,
- udržovatelnost,
- bezpečnost,
- potenciální výkonová rizika.

Jednotlivá zjištění jsou klasifikována podle závažnosti:

- `Critical`,
- `High`,
- `Medium`,
- `Low`,
- `Recommendation`.

---

## Validace SQL řešení

Agent důsledně rozlišuje následující úrovně ověření:

| Úroveň | Význam |
|---|---|
| `Logically reviewed` | Logika byla posouzena proti zadání a schématu |
| `Syntax validated` | Syntax byla ověřena v cílovém databázovém systému |
| `Executed` | Dotaz byl skutečně spuštěn |
| `Result validated` | Výsledky byly porovnány s kontrolními daty |
| `Performance tested` | Výkon byl technicky změřen |
| `Production approved` | Řešení prošlo technickým a business schválením |

Referenční případ má stav:

```text
Logically Reviewed – Ready for Technical Testing
```

Dotazy nebyly skutečně spuštěny a jejich výkon nebyl změřen. Dokument proto nevydává logicky posouzené řešení za technicky validované nebo produkčně schválené.

---

## Výkonová doporučení

Projekt obsahuje návrhy možných databázových indexů, ale všechny jsou označeny jako:

```text
Index candidates requiring validation
```

Bez znalosti následujících informací nelze index doporučit k produkčnímu nasazení:

- clustered indexu,
- distribuce hodnot,
- selektivity,
- databázového workloadu,
- frekvence zápisů,
- aktuálnosti statistik,
- execution plánu,
- rozdílu mezi odhadovaným a skutečným počtem řádků.

Výkonové posouzení dále zohledňuje:

- index seeks a scans,
- key lookup operace,
- hash a sort spills,
- memory grant,
- datový skew,
- paralelismus,
- parameter sniffing,
- stabilitu execution plánu,
- možnosti předagregace.

---

## Bezpečnost

Agent ve výchozím režimu používá pouze read-only dotazy, zejména:

```sql
SELECT
```

Příkazy měnící data nebo databázovou strukturu nesmí být použity bez explicitního požadavku a odpovídajících bezpečnostních opatření.

Projekt nepodporuje:

- neřízené změny produkčních dat,
- automatické odstraňování vadných záznamů,
- nebezpečné příkazy bez přesného filtru,
- SQL sestavované z neověřeného uživatelského vstupu,
- nepodložené zásahy do databázové struktury.

---

## Možnosti využití

Specifikaci lze využít jako:

- systémový prompt pro AI SQL agenta,
- kontrolní rámec pro generování SQL,
- šablonu analytického workflow,
- podklad pro SQL code review,
- testovací scénář pro porovnávání AI modelů,
- checklist pro juniorního SQL analytika,
- výukový materiál pro propojení SQL a business analýzy,
- základ pro další iterace specializovaného AI agenta.

---

## Omezení projektu

Agent bez přístupu k databázi:

- nemůže potvrdit existenci databázových objektů,
- nemůže skutečně spustit SQL dotaz,
- nemůže validovat konkrétní výsledky,
- nemůže získat actual execution plan,
- nemůže změřit výkon,
- nemůže potvrdit vhodnost navržených indexů,
- nemůže rozhodnout o správném zacházení s datovou vadou bez business pravidla.

Výstupy proto musí vždy jasně oddělovat:

- ověřené skutečnosti,
- použité předpoklady,
- logické závěry,
- neověřené hypotézy,
- technická omezení.

---

## Stav projektu

```text
Agent Specification: Final
Reference Case Version: 1.1
Reference Case Status: Logically Reviewed – Ready for Technical Testing
```

---

## Autor a zaměření

Projekt vznikl jako součást praktického rozvoje dovedností v oblasti:

- datové analýzy,
- SQL,
- databázového reportingu,
- kvality dat,
- využití AI agentů v analytickém workflow.

Je zaměřen na propojení technického SQL řešení s reálným business kontextem a na transparentní používání AI při analytické práci.
