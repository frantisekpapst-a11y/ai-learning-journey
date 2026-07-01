# AI Prompt Engineering Cheatsheet

> Vlastní tahák vytvořený během studia AI se zaměřením na datovou analytiku, Business Intelligence a profesionální práci s LLM.

---

# Co je Prompt Engineering?

Prompt Engineering je proces navrhování kvalitních zadání (promptů), která umožní AI vytvořit co nejpřesnější, nejrelevantnější a nejpoužitelnější výstup.

Nejde o psaní otázek.

Jde o navrhování kvalitního business zadání pro AI.

---

# Základní princip

**Čím lepší zadání, tím lepší výstup.**

Garbage In → Garbage Out

---

# Analytické workflow profesionálního promptu

| Vrstva | Otázka | Příklad |
|---------|---------|----------|
| **Role** | Kdo je AI? | Jsi senior datový analytik. |
| **Cíl** | Co má AI vytvořit? | Navrhni Power BI dashboard. |
| **Kontext** | Co AI ví o problému? | Máme data z e-shopu: datum, produkt, zákazník, region... |
| **Omezení** | Co AI nesmí nebo musí dodržet? | Nepoužívej Python. Pokud něco chybí, napiš předpoklady. |
| **Formát výstupu** | Jak má výsledek vypadat? | Markdown, tabulka, checklist, JSON... |
| **Zdůvodnění** | Má AI vysvětlit své návrhy? | Zdůvodni každý návrh. |

---

# Profesionální struktura promptu

Role
↓
Cíl
↓
Kontext
↓
Omezení
↓
Formát výstupu
↓
Zdůvodnění
↓
Iterace
---

# Role

Role určuje způsob uvažování AI.

Příklady:
- senior datový analytik
- Power BI konzultant
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
- dostupná data
- použité technologie
- business problém

---

# Omezení

Profesionální prompt vždy obsahuje omezení.

Například:
- nepoužívej Python
- pracuj pouze s Power BI
- používej pouze informace ze zadaných dat
- pokud něco chybí, napiš to
- nevymýšlej si informace

---

# Formát výstupu

AI by měla vědět, jak má odpověď vypadat.

Například:
- Markdown
- Tabulka
- JSON
- Checklist
- Seznam kroků
- Executive Summary

---

# Zdůvodnění

Nechtěj pouze výsledek.

Chtěj také vysvětlení.

Například:
- Zdůvodni každý návrh.
- Popiš výhody a nevýhody.
- Uveď alternativní řešení.

---

# Iterativní promptování

Prompt se běžně upravuje.

První odpověď nebývá finální.

Typický postup:

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
Finální výstup

---

# AI není Google

Google

Dotaz
↓
Vyhledání
↓
Výsledek

AI

Prompt
↓
Návrh
↓
Iterace
↓
Lepší návrh
↓
Kontrola
↓
Finální řešení

---

# Best Practices

## Buď konkrétní.
❌ Navrhni dashboard.

✅ Navrhni Power BI dashboard pro management e-shopu.

---

## Definuj roli.

Například:
> Jsi senior BI konzultant.

---

## Přidej kontext.

Například:
- typ firmy
- dostupná data
- business problém
- cílový uživatel

---

## Definuj omezení.

Například:
- nepředpokládej chybějící data
- nepoužívej externí zdroje
- používej pouze dostupné informace

---

## Specifikuj formát.

Například:
- Markdown
- Tabulka
- JSON
- Checklist

---

## Požaduj zdůvodnění.

Například:
> Zdůvodni každý návrh.

---

## Iteruj.

První odpověď téměř nikdy není finální.

---

## Rozděl složitý problém.

Místo jednoho obrovského promptu vytvoř více menších kroků.

Stejně jako při datové analýze.

---

## Označ předpoklady.

Například:

> Pokud některé informace chybí, nejprve vypiš předpoklady.

Výrazně tím omezíš halucinace.

---

## Nech AI klást otázky.

Například:
> Pokud nemáš dostatek informací, polož mi nejprve doplňující otázky.

---

## Vyžaduj více variant.

Například:
> Navrhni tři možná řešení a porovnej je.

---

## Nech AI kritizovat vlastní řešení.

Například:
> Jaké jsou slabiny tohoto návrhu?

---

## Nech AI hledat rizika.

Například:
> Jaká rizika vidíš?

---

## Vyžaduj business pohled.

Například:
> Jakou hodnotu to přinese managementu?

---

## Odděluj fakta od předpokladů.

Například:
> Rozděl odpověď na:
- Ověřená fakta
- Předpoklady
- Doporučení

---

## Používej Executive Summary.

Na začátek odpovědi:
- stručné shrnutí
- hlavní závěry
- doporučení

---

## Požaduj kontrolní seznam.

Například:
> Na závěr vytvoř checklist všech kroků.

---

# Prompt mindset datového analytika

AI není náhrada analytika.

AI urychluje práci.

Analytik:
- definuje problém
- ověřuje výsledky
- interpretuje data
- rozhoduje

AI:
- navrhuje řešení
- automatizuje rutinu
- připravuje podklady
- šetří čas

---

# Nejčastější chyby
- příliš obecný prompt
- chybějící kontext
- neurčený formát výstupu
- žádné omezení
- slepá důvěra AI
- neověřené informace
- neprovedení iterace

---

# Lessons Learned
- AI není vyhledávač.
- Prompt je business zadání.
- Kontext rozhoduje o kvalitě výstupu.
- Iterace je běžnou součástí práce.
- AI pomáhá přemýšlet, nerozhoduje za analytika.
- Výstupy AI je vždy potřeba kriticky ověřit.
- Kvalitní prompt šetří více času než následné opravování špatného výstupu.
