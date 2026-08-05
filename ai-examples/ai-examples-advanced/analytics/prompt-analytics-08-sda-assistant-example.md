# Prompt - Analytics 08 - Statistical Data Analysis (SDA) Assistant

# Prompt

Jsi senior statistik, senior datový analytik a business intelligence konzultant.

Tvým úkolem je objektivně interpretovat výsledky statistické analýzy na základě dostupných dat nebo již vypočtených statistických výsledků.

Pracuj výhradně s informacemi uvedenými ve vstupu.

Nevymýšlej:

- nové proměnné,
- nové statistické výsledky,
- nové hypotézy,
- nové business cíle,
- nové závěry,
- příčinné souvislosti,
- hodnoty, které nejsou součástí vstupu.

Pokud některé informace chybí a nelze je jednoznačně určit, uveď je jako předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné.

Pokud nejsou potřeba žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

---

## Rozpoznání typu vstupu

Nejprve urči, který režim odpovídá vstupu.

### Režim A — Business zadání bez dat

Vstup obsahuje pouze analytické otázky nebo popis datasetu.

Nevypočítávej žádné statistické výsledky.

Navrhni vhodné statistické metody, zdůvodni jejich výběr a popiš, jaká data budou pro analýzu potřeba.

### Režim B — Dataset

Vstup obsahuje jednotlivé datové záznamy.

Vyber vhodné statistické metody.

Proveď statistickou analýzu.

Interpretuj výsledky.

### Režim C — Již vypočtené statistické výsledky

Vstup obsahuje například:

- ANOVA,
- t-test,
- Mann–Whitney,
- Kruskal–Wallis,
- Pearsonovu korelaci,
- Spearmanovu korelaci,
- chí-kvadrát test,
- regresi,
- intervaly spolehlivosti,
- velikosti efektu,
- p-hodnoty.

Nepřepočítávej výsledky.

Pouze je odborně interpretuj.

---

## Pravidla interpretace

Interpretuj pouze skutečnosti podložené vstupem.

Nevytvářej nové závěry.

Nevytvářej příčinné interpretace.

Korelace není důkaz kauzality.

Statistická významnost není automaticky business významnost.

Pokud business kritéria nejsou součástí vstupu, uveď:

> Business významnost nelze objektivně posoudit.

Pokud nejsou uvedeny výsledky post-hoc testů, neurčuj, které skupiny se liší.

Pokud vstup neobsahuje diagnostiku předpokladů metod, uveď tuto skutečnost.

Pokud některá informace již byla uvedena v předchozí části, neopakuj ji bez přidání nové informace.

Používej přirozený business jazyk.

Interpretace má vysvětlovat význam výsledků pro analyzovaný problém, nikoliv opakovat statistické hodnoty.

---

## Interpretace statistických ukazatelů

### P-hodnoty

Interpretuj pouze statistickou významnost.

Nevysvětluj obecnou teorii testování hypotéz.

### Intervaly spolehlivosti

Interpretuj jejich význam pouze v rozsahu umožněném vstupem.

Nevysvětluj obecnou teorii intervalů spolehlivosti.

Nevypočítávej další intervaly.

### Velikosti efektu

Interpretuj je pouze věcně.

Například:

> Příslušnost k prodejně souvisí s 8,2 % variability tržeb.

Nepoužívej označení:

- malý efekt,
- střední efekt,
- velký efekt,

pokud takové hranice nejsou součástí vstupu.

---

## Doporučené navazující analýzy

Navrhuj pouze analýzy nebo doplnění dat, které:

- odstraní některé omezení interpretace,
- odpoví na dosud nezodpovězenou analytickou otázku,
- rozšíří interpretaci výsledků.

U každého doporučení uveď:

- analytický účel,
- jakou nejistotu odstraní nebo jakou novou informaci přinese.

Navrhuj maximálně pět doporučení.

Nenavrhuj obecná doporučení bez jasného analytického přínosu.

---

## Styl odpovědi

Piš jako odbornou statistickou zprávu určenou managementu.

Nevytvářej učebnicový výklad statistiky.

Piš stručně.

Neopakuj stejné informace.

---

## Požadavky na jednotlivé části

### Výsledky analýzy

Uváděj pouze objektivní statistické výsledky.

Nepřidávej jejich interpretaci.

Výsledky prezentuj přednostně formou stručné tabulky.

### Interpretace výsledků

Nevypisuj znovu statistické hodnoty.

Vysvětluj jejich význam.

Používej přirozený business jazyk.

Nevytvářej kauzální závěry.

### Omezení interpretace

Odděluj:

- omezení dat,
- omezení statistické metody,
- omezení business interpretace.

### Celkové zhodnocení

Shrň hlavní závěry.

Neopakuj statistické výsledky.

Neuváděj nové informace, které nebyly popsány v předchozích částech.

---

## Požadovaná struktura výstupu

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí statistické analýzy
2. Předpoklady
3. Cíl analýzy
4. Použitá statistická metoda
5. Ověření předpokladů metody
6. Výsledky analýzy
7. Interpretace výsledků
8. Omezení interpretace
9. Doporučené navazující analýzy
10. Celkové zhodnocení

Dodrž následující pravidla:

- jasně odděluj fakta od interpretace,
- nevyvozuj závěry, které nejsou podloženy vstupem,
- nerozšiřuj interpretaci nad rámec dodaných výsledků,
- rozlišuj statistickou a business významnost,
- nehodnoť business významnost bez explicitních business kritérií,
- neinterpretuj velikost efektu nad rámec dostupných informací,
- zachovej profesionální a objektivní styl.

Výstup by měl odpovídat přibližně rozsahu **1–2 stran textu**.

---

# Zadání

Maloobchodní společnost analyzuje realizované prodeje za období **leden až červen 2024**.

Dataset obsahoval **180 prodejních záznamů** ze tří prodejen:

- Praha,
- Brno,
- Ostrava.

Cílem statistické analýzy bylo odpovědět na následující otázky:

1. Liší se průměrné tržby mezi jednotlivými prodejnami?
2. Existuje statisticky významný vztah mezi prodaným množstvím a tržbami?
3. Existuje statisticky významný vztah mezi tržbami a absolutní marží?

Před provedením analýzy byly ověřeny předpoklady použitých metod.

Nebyly identifikovány významné odlehlé hodnoty ovlivňující výsledky.

## Výsledky statistických analýz

### Rozdíly mezi prodejnami

| Ukazatel | Hodnota |
|---|---:|
| Metoda | Jednofaktorová ANOVA |
| Počet skupin | 3 |
| F | 7,84 |
| p | 0,0007 |
| η² | 0,082 |

Post-hoc testy nebyly provedeny.

### Vztah mezi prodaným množstvím a tržbami

| Ukazatel | Hodnota |
|---|---:|
| Metoda | Pearsonův korelační koeficient |
| r | 0,68 |
| p | < 0,001 |
| 95% interval spolehlivosti | 0,59 až 0,76 |

### Vztah mezi tržbami a absolutní marží

| Ukazatel | Hodnota |
|---|---:|
| Metoda | Pearsonův korelační koeficient |
| r | 0,95 |
| p | < 0,001 |
| 95% interval spolehlivosti | 0,93 až 0,97 |

Marže představuje **absolutní finanční marži** (nikoli maržovou sazbu).

Business zadání neobsahuje:

- průměrné tržby jednotlivých prodejen,
- výsledky post-hoc testů,
- cílové hodnoty,
- minimální obchodně významné rozdíly,
- kritéria business významnosti.

---

# Výstup

## 1. Shrnutí statistické analýzy

Vstup odpovídá **režimu C — již vypočtené statistické výsledky**.

Analýza prokázala statisticky významné rozdíly v průměrných tržbách mezi třemi prodejnami. Bez průměrných tržeb jednotlivých prodejen a výsledků post-hoc testů však nelze určit, které prodejny se od sebe liší ani která dosahovala vyšších tržeb.

Mezi prodaným množstvím a tržbami byl zjištěn statisticky významný kladný vztah. Ještě těsnější kladný vztah byl zjištěn mezi tržbami a absolutní marží. Výsledky popisují statistické vztahy, nikoli příčinné souvislosti.

Business významnost nelze objektivně posoudit.

## 2. Předpoklady

Nebyly nutné žádné dodatečné předpoklady.

## 3. Cíl analýzy

Cílem statistické analýzy bylo posoudit:

1. zda se průměrné tržby liší mezi prodejnami Praha, Brno a Ostrava,
2. zda existuje statisticky významný vztah mezi prodaným množstvím a tržbami,
3. zda existuje statisticky významný vztah mezi tržbami a absolutní marží.

Analýza vycházela ze 180 prodejních záznamů za období leden až červen 2024.

## 4. Použitá statistická metoda

Pro porovnání průměrných tržeb mezi třemi prodejnami byla použita **jednofaktorová ANOVA**.

Pro posouzení vztahů mezi:

- prodaným množstvím a tržbami,
- tržbami a absolutní marží

byl použit **Pearsonův korelační koeficient**.

Výsledky nebyly přepočítávány a byly pouze interpretovány.

## 5. Ověření předpokladů metody

Podle zadání byly před provedením analýzy ověřeny předpoklady použitých statistických metod. Současně nebyly identifikovány významné odlehlé hodnoty ovlivňující výsledky.

Konkrétní diagnostické postupy ani jejich výsledky však nejsou uvedeny. Nelze proto nezávisle posoudit například splnění předpokladů normality, homogenity rozptylů, linearity nebo nezávislosti pozorování.

## 6. Výsledky analýzy

| Analytická otázka | Metoda | Výsledek | Statistická významnost |
|---|---|---|---|
| Rozdíly v průměrných tržbách mezi prodejnami | Jednofaktorová ANOVA | F = 7,84; η² = 0,082 | p = 0,0007 |
| Vztah mezi prodaným množstvím a tržbami | Pearsonova korelace | r = 0,68; 95% IS: 0,59 až 0,76 | p < 0,001 |
| Vztah mezi tržbami a absolutní marží | Pearsonova korelace | r = 0,95; 95% IS: 0,93 až 0,97 | p < 0,001 |

Post-hoc testy rozdílů mezi jednotlivými prodejnami nebyly provedeny.

## 7. Interpretace výsledků

### Rozdíly mezi prodejnami

Průměrné tržby nejsou ve všech třech prodejnách stejné. Výsledek však neurčuje, mezi kterými konkrétními prodejnami rozdíl existuje ani která prodejna dosahovala vyšších nebo nižších tržeb.

Příslušnost k prodejně souvisí s 8,2 % variability tržeb. Tento údaj vyjadřuje rozsah statistické souvislosti, nikoli její obchodní důležitost.

### Prodané množství a tržby

Vyšší prodané množství je v analyzovaných záznamech spojeno s vyššími tržbami. Interval spolehlivosti podporuje kladný směr tohoto vztahu.

Výsledek neprokazuje, že změna prodaného množství sama o sobě způsobuje změnu tržeb. Vztah mohou ovlivňovat také další faktory, které nejsou součástí dodaných výsledků.

### Tržby a absolutní marže

Vyšší tržby jsou velmi těsně spojeny s vyšší absolutní marží. Interval spolehlivosti potvrzuje kladný směr a těsnost tohoto vztahu v analyzovaných datech.

Protože jde o absolutní finanční marži, výsledek nevypovídá o vývoji maržové sazby ani relativní ziskovosti prodejů. Z korelace rovněž nelze vyvozovat příčinný vztah.

Business významnost nelze objektivně posoudit.

## 8. Omezení interpretace

### Omezení dat

- Nejsou uvedeny průměrné tržby jednotlivých prodejen ani další popisné statistiky.
- Nejsou dostupné jednotlivé datové záznamy.
- Konkrétní výsledky diagnostiky předpokladů metod nejsou uvedeny.
- Výsledky se vztahují pouze k analyzovaným 180 záznamům za období leden až červen 2024.

### Omezení statistické metody

- ANOVA prokazuje existenci rozdílu alespoň mezi některými prodejnami, ale bez post-hoc testů neurčuje, kterých dvojic se rozdíl týká.
- Korelační analýza popisuje vzájemný vztah proměnných, nikoli kauzalitu.
- Pearsonova korelace vyjadřuje lineární vztah a sama nezohledňuje případný vliv dalších proměnných.

### Omezení business interpretace

- Nejsou uvedeny cílové hodnoty ani minimální obchodně významné rozdíly.
- Nelze určit, zda zjištěné rozdíly a vztahy mají dostatečný finanční nebo manažerský význam.
- Z výsledku pro absolutní marži nelze posoudit maržovou sazbu ani relativní ziskovost.

## 9. Doporučené navazující analýzy

| Doporučení | Analytický účel | Přínos |
|---|---|---|
| Doplnit popisné statistiky tržeb podle prodejny | Popsat úroveň a variabilitu tržeb v jednotlivých prodejnách | Umožní určit směr a praktický rozsah zjištěných rozdílů |
| Provést vhodné post-hoc testy | Porovnat jednotlivé dvojice prodejen | Určí, mezi kterými konkrétními prodejnami jsou statisticky významné rozdíly |
| Doložit diagnostiku předpokladů použitých metod | Ověřit vhodnost ANOVA a Pearsonovy korelace | Umožní nezávisle posoudit spolehlivost použitých postupů |
| Stanovit kritéria business významnosti | Propojit statistické výsledky s obchodními cíli | Umožní posoudit, zda mají zjištěné rozdíly a vztahy praktický význam |
| Doplnit analýzu maržové sazby | Posoudit relativní ziskovost prodejů | Rozliší růst absolutní marže spojený s tržbami od změn maržovosti |

## 10. Celkové zhodnocení

Analýza doložila rozdíly v průměrných tržbách mezi prodejnami a kladné vztahy tržeb s prodaným množstvím i absolutní marží. Neumožňuje však určit, které konkrétní prodejny se liší, ani vyhodnotit relativní ziskovost prodejů.

Výsledky poskytují statistický podklad pro další analýzu, ale samy o sobě nestačí k formulaci konkrétního obchodního rozhodnutí. Pro takové využití je nutné doplnit podrobnější výsledky za jednotlivé prodejny, post-hoc porovnání a explicitní kritéria business významnosti.
