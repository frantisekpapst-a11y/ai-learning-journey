# AI Prompt Engineering Cheatsheet

Vlastní tahák vytvořený během studia AI se zaměřením na datovou analytiku, Business Intelligence a profesionální práci s LLM.

---

# Co je Prompt Engineering?

Prompt Engineering je proces navrhování kvalitních zadání (promptů), která umožní AI vytvořit co nejpřesnější, nejrelevantnější a nejpoužitelnější výstup.

Nejde o psaní otázek.

Jde o navrhování kvalitního business zadání pro AI.

---

# Základní princip

> **Čím lepší zadání, tím lepší výstup.**

**Garbage In → Garbage Out**

---

# Analytické workflow profesionálního promptu

| Vrstva | Otázka | Příklad |
|---------|---------|----------|
| Role | Kdo je AI? | Jsi senior datový analytik. |
| Cíl | Co má AI vytvořit? | Navrhni Power BI dashboard. |
| Kontext | Co AI ví o problému? | Máme data z e-shopu: datum, produkt, zákazník, region... |
| Omezení | Co AI nesmí nebo musí dodržet? | Nepoužívej Python. Pokud něco chybí, napiš předpoklady. |
| Formát výstupu | Jak má výsledek vypadat? | Markdown, tabulka, checklist, JSON... |
| Zdůvodnění | Má AI vysvětlit své návrhy? | Zdůvodni každý návrh. |
| Kontrola | Má AI provést vlastní revizi? | Zkontroluj své řešení a navrhni zlepšení. |

---

# Profesionální struktura promptu

```
Role
↓
Cíl
↓
Kontext
↓
Data
↓
Omezení
↓
Formát výstupu
↓
Zdůvodnění
↓
Kontrola
↓
Iterace
```

---

# Role

Role určuje způsob uvažování AI.

Příklady:
- senior datový analytik
- BI konzultant
- Power BI specialista
- SQL developer
- Business analytik
- Projektový manažer
- Marketingový specialista

---

# Kontext

Bez kontextu AI pouze odhaduje.

Čím více relevantních informací dostane, tím lepší bude výstup.

Například:

- obor
- cílová skupina
- business problém
- dostupná data
- technologie
- cíl analýzy

---

# Data

Pokud AI pracuje s daty, vždy specifikuj:
- dostupné sloupce
- granularitu dat
- časové období
- případná omezení datasetu

Například:

```
Máme tato data:

- datum objednávky
- produkt
- zákazník
- region
- cena
- množství
```

---

# Omezení

Profesionální prompt téměř vždy obsahuje omezení.

Například:
- nepoužívej Python
- pracuj pouze s Power BI
- používej pouze zadaná data
- nevymýšlej si chybějící informace
- pokud něco chybí, napiš předpoklady
- pokud si nejsi jistý, polož doplňující otázky

---

# Formát výstupu

AI by měla vědět, jak má odpověď vypadat.

Například:
- Markdown
- Tabulka
- Checklist
- JSON
- Executive Summary
- Seznam kroků
- Business report

---

# Zdůvodnění

Nechtěj pouze výsledek.

Chtěj také vysvětlení.

Například:
- Zdůvodni každý návrh.
- Popiš výhody a nevýhody.
- Navrhni alternativní řešení.
- Uveď možná rizika.

---

# Iterativní promptování

Prompt se běžně upravuje.

První odpověď téměř nikdy není finální.

Typický postup:

```
Prompt
↓
Výsledek
↓
Úprava promptu
↓
Lepší výsledek
↓
Další zpřesnění
↓
Finální řešení
```

---

# AI není Google

Google

```
Dotaz
↓
Vyhledání
↓
Výsledek
```

AI

```
Prompt
↓
Návrh
↓
Iterace
↓
Kontrola
↓
Finální řešení
```

---

# Prompt Hacks

## Maximum detailů

Poskytuj maximum relevantních informací.

Nezahlcuj ale prompt zbytečnostmi ani si neprotiřeč.

---

## Rozděl úlohu na kroky

Místo jednoho velkého úkolu vytvoř workflow.

Například:

1. Analyzuj data.
2. Najdi problémy.
3. Navrhni KPI.
4. Navrhni dashboard.
5. Zdůvodni návrhy.
6. Proveď vlastní kontrolu.

---

## Používej oddělovače

Odděluj jednotlivé části promptu.

Například:

```
# Role

# Kontext

# Data

# Omezení

# Výstup
```

nebo

```
<role>

<kontext>

<data>

<vystup>
```

---

## Few-shot prompting

Pokud existuje kvalitní příklad, přilož jej.

AI se mnohem lépe trefí do požadovaného stylu.

---

## Referenční dokumenty

Přikládej:

- KPI definice
- datový slovník
- business zadání
- SQL dokumentaci
- Power BI standardy
- interní metodiky

AI bude vycházet z konkrétních podkladů místo obecných znalostí.

---

## Druhá kontrola

Na závěr požádej AI o vlastní revizi.

Například:

```
Zkontroluj své řešení.

Najdi chyby.

Najdi slabá místa.

Navrhni zlepšení.
```

---

## Neptej se pouze

```
Je to správně?
```

Lepší je:

```
Navrhni vlastní řešení.

Porovnej jej s mým.

Vysvětli rozdíly.

Doporuč nejlepší variantu.
```

---

## Custom Instructions

Informace, které používáš často, nepiš do každého promptu.

Například:
- profese
- styl komunikace
- používané technologie
- úroveň znalostí
- preferovaný formát výstupu

---

# Best Practices

✅ Buď konkrétní.

❌ Navrhni dashboard.

✅ Navrhni Power BI dashboard pro vedení e-shopu.

---

✅ Definuj roli.

Například:

```
Jsi senior BI konzultant.
```

---

✅ Přidej kontext.

Například:

- typ firmy
- business problém
- cílový uživatel
- dostupná data
- používané technologie

---

✅ Definuj omezení.

Například:

- nepředpokládej chybějící data
- nepoužívej externí informace
- používej pouze zadaná data

---

✅ Specifikuj formát výstupu.

Například:

- Markdown
- Tabulka
- JSON
- Checklist
- Executive Summary

---

✅ Požaduj zdůvodnění.

Například:

```
Zdůvodni každý návrh.
```

---

✅ Iteruj.

První odpověď téměř nikdy není finální.

---

✅ Rozděl složitý problém.

Stejně jako při datové analýze.

---

✅ Označ předpoklady.

Například:

```
Pokud některé informace chybí, nejprve vypiš všechny předpoklady.
```

---

✅ Nech AI klást otázky.

Například:

```
Pokud nebudeš mít dostatek informací, nejprve mi polož doplňující otázky.
```

---

✅ Vyžaduj více variant.

Například:

```
Navrhni tři možná řešení.

Porovnej je.

Doporuč nejlepší.
```

---

✅ Nech AI kritizovat vlastní řešení.

Například:

```
Najdi slabiny svého návrhu.

Navrhni jeho zlepšení.
```

---

✅ Odděluj fakta od předpokladů.

Například:
- Ověřená fakta
- Předpoklady
- Doporučení
- Rizika

---

✅ Začni Executive Summary.

Krátké shrnutí.

Hlavní závěry.

Doporučení.

---

✅ Požaduj checklist.

Například:

```
Na závěr vytvoř kontrolní seznam všech kroků.
```

---

# Prompt mindset datového analytika

AI není náhrada analytika.

AI urychluje analytickou práci.

Datový analytik:
- definuje problém
- rozumí businessu
- ověřuje výsledky
- interpretuje data
- rozhoduje

AI:
- navrhuje řešení
- připravuje podklady
- automatizuje rutinu
- šetří čas
- pomáhá s brainstormingem

---

# Nejčastější chyby
- příliš obecný prompt
- chybějící kontext
- neurčený formát výstupu
- chybějící omezení
- slepá důvěra AI
- neověřené informace
- neprovedení iterace
- příliš mnoho nesouvisejících požadavků v jednom promptu
- nevyužití referenčních dokumentů
- neprovedení závěrečné kontroly

---

# Lessons Learned
- AI není vyhledávač.
- Prompt je business zadání.
- Kontext rozhoduje o kvalitě výstupu.
- Kvalitní struktura promptu výrazně zlepšuje výsledky.
- Rozdělení úlohy na kroky vede k lepším odpovědím.
- Few-shot prompting pomáhá AI pochopit očekávaný styl.
- Referenční dokumenty zvyšují přesnost odpovědí.
- Iterace je běžnou součástí práce.
- AI pomáhá přemýšlet, nerozhoduje za analytika.
- Výstupy AI je vždy potřeba kriticky ověřit.
- Kvalitní prompt šetří více času než následné opravování špatného výstupu.

---

# Grafické prompty

Při generování obrázků je vhodné:
- používat konkrétní popis prostředí a objektů
- určit styl obrázku
- popsat atmosféru
- využívat negativní instrukce pro odstranění nežádoucích prvků
- iterativně prompt upravovat podle výsledků

Konkrétní syntaxe (např. váhy nebo negativní parametry) se liší podle použitého AI nástroje.

---

# AI halucinace

Příčiny:
- nekvalitní data
- nejasný prompt
- složitost modelu

Jak snížit riziko:
- kvalitní prompt
- nízká teplota
- externí znalosti
- fine-tuning
- ověřování zdrojů

Pamatuj:
AI může znít sebevědomě, i když se mýlí.
