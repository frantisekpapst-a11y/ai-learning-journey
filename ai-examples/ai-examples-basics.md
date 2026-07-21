# Prompt Improvement Examples

Praktické ukázky postupného vylepšování promptů.

Cílem není vytvářet co nejdelší prompty, ale takové, které AI poskytnou dostatek relevantních informací pro vytvoření kvalitního výstupu.

---

# Example 1 — Power BI Dashboard

## Špatný prompt

```text
Navrhni dashboard.
```

## Lepší prompt

```text
Navrhni Power BI dashboard pro e-shop.
```

## Profesionální prompt

```text
Jsi senior datový a BI analytik.

Cílem je navrhnout Power BI dashboard pro top management e-shopu.

Máme k dispozici následující data:

- datum objednávky
- produkt
- kategorie
- cena
- množství
- zákazník
- region

Navrhni:

- hlavní KPI
- vhodné grafy
- slicery
- tabulky
- potřebné DAX míry
- doporučené rozložení dashboardu

Výstup připrav jako Markdown.

U každého návrhu stručně vysvětli business přínos.

Pokud některé informace chybí, nejprve vypiš své předpoklady.

Nevymýšlej si data.
```

### Co se zlepšilo

- Definovaná role
- Jasný business cíl
- Popsaná vstupní data
- Konkrétní požadované výstupy
- Definovaný formát odpovědi
- Business zdůvodnění
- Omezení halucinací

---

# Example 2 — SQL

## Špatný prompt

```text
Napiš SQL.
```

## Lepší prompt

```text
Napiš SQL dotaz pro výpočet revenue.
```

## Profesionální prompt

```text
Jsi senior SQL developer.

Používáme Microsoft SQL Server.

Máme tabulku Sales obsahující:

- OrderDate
- Region
- Quantity
- UnitPrice
- CustomerID

Navrhni SQL dotaz, který spočítá měsíční revenue podle regionů.

Revenue vypočítej jako:

Quantity × UnitPrice

Požadavky:

- použij CTE
- přidej komentáře
- seskup výsledek podle roku, měsíce a regionu
- seřaď výsledek chronologicky
- navrhni vhodné indexy
- vysvětli optimalizaci

Pokud informace nestačí, nejprve uveď své předpoklady.
```

### Co se zlepšilo

- Definovaná role
- Technologie
- Struktura tabulky
- Business cíl
- SQL technika
- Dokumentace
- Optimalizace
- Kontrola předpokladů

---

# Example 3 — Excel

## Špatný prompt

```text
Jak udělám kontingenční tabulku?
```

## Lepší prompt

```text
Jak vytvořím kontingenční tabulku z dat o prodejích?
```

## Profesionální prompt

```text
Jsi zkušený Excel konzultant.

Mám tabulku prodejů obsahující:

- datum
- produkt
- region
- tržby

Potřebuji vytvořit přehlednou kontingenční tabulku pro management.

Navrhni:

- rozložení řádků
- rozložení sloupců
- hodnotová pole
- filtry
- slicery
- vhodný kontingenční graf
- doporučené KPI

Výsledek popiš krok za krokem.

U každého doporučení stručně vysvětli jeho přínos.
```

### Co se zlepšilo

- Definovaná role
- Popsaná data
- Business účel
- Konkrétní požadavky
- Postup krok za krokem
- Business zdůvodnění

---

# Example 4 — Business Analysis

## Špatný prompt

```text
Pomoz mi.
```

## Lepší prompt

```text
Pomoz mi analyzovat business problém.
```

## Profesionální prompt

```text
Jsi senior business analytik.

Pomoz mi analyzovat business problém.

Nejprve ověř, zda máš dostatek informací.

Pokud některé informace chybí, polož mi doplňující otázky.

Teprve poté navrhni řešení.

Výstup rozděl do sekcí:

1. Shrnutí problému
2. Známá fakta
3. Předpoklady
4. Možné příčiny
5. Doporučené řešení
6. Rizika
7. Další kroky

Jasně odděluj fakta od předpokladů.

Nevydávej domněnky za ověřené informace.

U každého doporučení vysvětli jeho business přínos.
```

### Co se zlepšilo

- Definovaná role
- Analytický postup
- Doplňující otázky
- Strukturovaný výstup
- Oddělení faktů a předpokladů
- Omezení halucinací
- Business přínos

---

# Example 5 — Grafický prompt

## Původní verze

```text
Vygeneruj úvodní ilustraci pro prezentaci s názvem „Moderní datová analytika ve firmě“.

Hlavní motiv by mělo být několik různých grafů a KPI dlaždic.

Styl by měl být realistický a business.

Atmosféra profesionální a dynamická.

Barvy zvol dvě až tři s různou sytostí.

Pozadí bude tmavé.
```

## Vylepšená verze

```text
Vygeneruj širokoúhlou úvodní ilustraci v poměru stran 16:9 pro prezentaci s názvem „Moderní datová analytika ve firmě“.

Hlavním motivem je realisticky zpracovaný moderní business dashboard složený z několika KPI dlaždic, liniového grafu, sloupcového grafu, koláčového grafu a mapového vizuálu.

Dashboard má působit jako profesionální nástroj používaný vedením firmy pro sledování výkonnosti a podporu rozhodování.

Kompozice má být přehledná, vyvážená a vizuálně dynamická.

Nejvýraznější KPI dlaždice umísti do horní části, hlavní graf doprostřed a doplňkové vizualizace po stranách.

Použij tmavé pozadí a barevnou paletu tvořenou tmavě modrou, tyrkysovou a oranžovou v různých úrovních sytosti.

Zachovej vysoký kontrast a dobrou čitelnost všech prvků.

Styl má být realistický, moderní, profesionální a business.

Atmosféra má vyjadřovat přesnost, inovace, rychlé rozhodování a práci s daty.

Obrázek nesmí obsahovat:

- loga konkrétních firem
- nečitelný text
- deformované grafy
- nepřehledné rozložení
- zbytečné dekorativní prvky
```

### Co se zlepšilo

- Určený poměr stran
- Přesně definovaný účel
- Konkrétní hlavní motiv
- Specifikované typy grafů
- Popsaná kompozice
- Přesná barevná paleta
- Definovaná atmosféra
- Vizuální hierarchie
- Negativní instrukce
- Lepší použitelnost pro prezentaci

---

# Obecná struktura profesionálního promptu

Profesionální prompt může obsahovat:

```text
Role

Cíl

Kontext

Dostupná data nebo podklady

Požadovaný úkol

Omezení

Požadovaný formát výstupu

Zdůvodnění řešení

Kontrolu správnosti
```

Ne každý prompt musí obsahovat všechny části.

Používej pouze ty prvky, které pomohou AI lépe pochopit zadání.

---

# Lessons Learned

Profesionální prompt:

- definuje roli
- stanovuje jasný cíl
- poskytuje relevantní kontext
- popisuje dostupná data
- obsahuje omezení
- určuje formát výstupu
- požaduje zdůvodnění
- odděluje fakta od předpokladů
- omezuje halucinace
- podporuje iteraci
- umožňuje závěrečnou kontrolu
- přizpůsobuje výstup cílovému uživateli

Delší prompt není automaticky lepší.

Kvalitní prompt obsahuje dostatek relevantních informací, ale vyhýbá se zbytečným, vágním nebo protichůdným požadavkům.
- omezuje halucinace
- podporuje iteraci
