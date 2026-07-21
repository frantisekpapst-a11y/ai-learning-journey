# AI Prompt Engineering Playbook

> Praktický workflow pro efektivní využívání AI při datové analýze, Business Intelligence a řešení business problémů.

---

# Cíl playbooku

Tento dokument popisuje osvědčený postup práce s AI od prvního zadání až po finální výstup.

AI není náhrada analytika.

AI je partner, který pomáhá s návrhy, automatizací rutinních činností a přípravou podkladů.

---

# Workflow práce s AI

Business problém

↓

Definice cíle

↓

Příprava promptu

↓

Generování návrhu

↓

Kontrola výstupu

↓

Iterace

↓

Druhá kontrola AI

↓

Business validace

↓

Finální řešení

---

# 1. Definice problému

Nejdříve si ujasním:

- Co chci vyřešit?
- Pro koho je výstup určen?
- Jaký má být výsledek?

Bez jasného cíle nevytvářím prompt.

---

# 2. Definice role AI

Určím, v jaké roli má AI vystupovat.

Například:

- senior datový analytik
- BI konzultant
- SQL developer
- Power BI specialista
- business analytik
- projektový manažer

Role ovlivňuje způsob uvažování AI.

---

# 3. Poskytnutí kontextu

AI popíšu prostředí.

Například:

- obor
- business problém
- dostupná data
- technologie
- cílový uživatel

Čím lepší kontext, tím lepší výstup.

---

# 4. Definice cíle

Přesně specifikuji, co má AI vytvořit.

Například:

- dashboard
- SQL dotaz
- dokumentaci
- business analýzu
- KPI návrh

---

# 5. Definice omezení

Určím pravidla.

Například:

- nepoužívej Python
- nevymýšlej si informace
- používej pouze dostupná data
- pokud něco chybí, napiš předpoklady
- pokud nemáš dostatek informací, polož doplňující otázky

---

# 6. Definice formátu

Specifikuji výstup.

Například:

- Markdown
- tabulka
- checklist
- JSON
- executive summary

---

# 7. Generování návrhu

Nechám AI vytvořit první návrh.

Neočekávám, že bude dokonalý.

První odpověď je návrh, nikoli finální řešení.

---

# 8. Kontrola výstupu

Kontroluji:

- správnost
- logiku
- úplnost
- business hodnotu
- případné halucinace

AI nikdy nekopíruji bez kontroly.

---

# 9. Iterace

Výstup postupně zpřesňuji.

Například:

- rozšiř
- zjednoduš
- přidej KPI
- změň strukturu
- navrhni alternativu

Iterace je běžnou součástí práce.

---

# 10. Druhá kontrola AI

Před finálním použitím požádám AI o vlastní revizi.

Například:

- Zkontroluj své řešení.
- Najdi případné chyby.
- Najdi slabá místa návrhu.
- Navrhni možná zlepšení.
- Ověř, že jsi nezapomněl na žádnou část zadání.

---

# 11. Business validace

Nakonec si položím otázky:

- Pomůže to uživateli?
- Odpovídá to business cíli?
- Je výstup realistický?
- Je něco potřeba ověřit?

---

# Workflow tvorby vlastního GPT

Pokud vytvářím specializovaný model GPT, postupuji obdobně jako při tvorbě kvalitního promptu.

Účel GPT

↓

Cílový uživatel

↓

Role a způsob komunikace

↓

Instrukce a pravidla

↓

Znalostní báze (pokud je potřeba)

↓

Testování různých scénářů

↓

Iterativní úpravy

↓

Finální GPT

Dobře navržený GPT není jednorázový projekt. Průběžně se testuje, upravuje a rozšiřuje podle zkušeností z praxe.

---

# Bezpečnost při práci s AI

Při používání veřejných AI nástrojů nikdy nevkládám:

- osobní údaje
- hesla
- API klíče
- přístupové údaje
- neveřejné firemní dokumenty
- citlivá obchodní data
- databáze obsahující osobní údaje

Pokud potřebuji pracovat s reálnými daty:

- anonymizuji data,
- používám testovací datasety,
- maskuji citlivé údaje,
- využívám pouze schválené firemní AI nástroje.

Bezpečnost dat má vždy přednost před pohodlím.

---

# Kdy AI nepoužívat

AI slouží jako pomocník, nikoliv jako jediný rozhodovací systém.

Nepoužívám ji jako jediný zdroj při:

- právních rozhodnutích,
- zdravotních doporučeních,
- práci s citlivými osobními údaji,
- rozhodování s významným finančním dopadem,
- situacích vyžadujících stoprocentně ověřené informace.

V těchto případech musí vždy následovat lidská kontrola.

---

# Prompt Hacks

## Maximum relevantních informací

Poskytuji maximum užitečných informací.

Vyhýbám se zbytečným nebo protichůdným požadavkům.

---

## Rozdělení složitých úloh

Velké problémy rozděluji na menší části.

Například:

1. analyzuj data
2. navrhni KPI
3. navrhni dashboard
4. identifikuj rizika
5. proveď kontrolu

---

## Používání oddělovačů

Větší prompty strukturuji pomocí:

- nadpisů
- číslovaných sekcí
- XML značek
- bloků textu

Prompt je přehlednější pro AI i pro mě.

---

## Few-shot Prompting

Pokud chci určitý styl výstupu, přikládám příklad.

AI lépe pochopí očekávání.

---

## Referenční dokumenty

Pokud existují:

- KPI definice
- datový slovník
- business zadání
- SQL skripty
- dokumentace
- interní metodiky

přikládám je přímo do promptu.

---

## Druhá kontrola

Na závěr větších úloh požaduji vlastní revizi AI.

Například:

> Zkontroluj své řešení a najdi případné chyby nebo opomenuté informace.

---

# Workflow datového analytika

Business požadavek

↓

AI připraví první návrh

↓

Analytik zkontroluje

↓

AI zapracuje připomínky

↓

AI provede vlastní kontrolu

↓

Analytik ověří fakta

↓

Finální dokument

---

# Kontrola halucinací

Před použitím výstupu ověřím:

- fakta
- čísla
- citace
- názvy funkcí
- SQL syntaxi
- DAX
- Power Query transformace
- úplnost odpovědi
- zda AI neopomněla důležité informace

Čím důležitější rozhodnutí, tím důkladnější kontrola.

---

# Kdy vytvořit nový prompt?

Nový prompt vytvářím pokud:

- se změnil cíl,
- řeším nový projekt,
- konverzace je nepřehledná,
- AI začíná míchat předchozí informace.

Jinak pokračuji iterací ve stejném vlákně.

---

# Best Practices

✅ Definuj roli.

✅ Popiš business problém.

✅ Přidej kontext.

✅ Definuj omezení.

✅ Urči formát výstupu.

✅ Požaduj zdůvodnění.

✅ Rozděl složité úlohy na menší části.

✅ Používej přehlednou strukturu promptu.

✅ Přikládej referenční dokumenty.

✅ Pokud je to vhodné, přidej příklad požadovaného výstupu.

✅ Iteruj.

✅ Testuj vlastní GPT na různých scénářích.

✅ Průběžně upravuj instrukce.

✅ Nech AI provést vlastní kontrolu.

✅ Ověř fakta.

✅ Chraň citlivá data.

✅ Kriticky vyhodnoť výstup.

---

# Nejčastější chyby

❌ Příliš obecný prompt.

❌ Chybějící kontext.

❌ Chybějící omezení.

❌ Nejasný formát výstupu.

❌ Příliš mnoho nesouvisejících požadavků v jednom promptu.

❌ Nepoužití referenčních dokumentů.

❌ Neprovedení iterace.

❌ Netestování vlastního GPT.

❌ Neprovedení závěrečné kontroly.

❌ Vkládání citlivých dat do veřejné AI.

❌ Neověřené informace.

❌ Slepé kopírování výstupu AI.

❌ Očekávání dokonalé první odpovědi.

---

# AI Mindset

AI není autorita.

AI není vyhledávač.

AI není náhrada analytika.

AI je inteligentní pracovní partner.

První odpověď AI je návrh, nikoli finální řešení.

Bezpečnost dat je důležitější než rychlost práce.

Konečné rozhodnutí vždy dělá člověk.

---

# Lessons Learned

- Prompt je business zadání.
- Kontext rozhoduje o kvalitě výstupu.
- Dobře strukturovaný prompt vede ke kvalitnějším odpovědím.
- Rozdělení složitého problému na menší části zlepšuje výsledky.
- Referenční dokumenty výrazně zvyšují přesnost odpovědí.
- Druhá kontrola AI často odhalí opomenuté informace.
- Iterace je přirozenou součástí práce.
- Kvalitní GPT vzniká postupným testováním a laděním.
- Citlivá data do veřejných AI nástrojů nepatří.
- Odpovědnost za výstupy AI vždy nese člověk.
- AI šetří čas, ale nenese odpovědnost.
- Výstupy AI je vždy potřeba kriticky ověřit.
- Největší hodnotu přináší kombinace odbornosti člověka a schopností AI.
