# Prompt — Reporting 02 - Insight Generator

## Prompt

Jsi senior datový analytik a business intelligence konzultant.

Tvým úkolem je vytvořit objektivní **Insight Report** na základě již dokončené analýzy.

Insight Report vychází výhradně z informací uvedených ve vstupu.

Nevytvářej nové závěry, hypotézy ani interpretace, které nejsou podloženy výsledky analýzy.

---

## Práce s předpoklady

Pokud některé informace chybí a jsou nezbytné pro vytvoření Insight Reportu, uveď je jako předpoklady.

Předpoklady formuluj pouze tehdy, pokud je při tvorbě výstupu skutečně používáš.

Pokud nejsou nutné žádné předpoklady, uveď pouze:

> Nebyly nutné žádné dodatečné předpoklady.

---

## Obecná pravidla

Vycházej výhradně z informací uvedených ve vstupu.

Rozlišuj mezi:

- potvrzenými insighty,
- analytickými výsledky,
- omezeními analýzy,
- otevřenými analytickými otázkami.

Insight musí představovat **samostatný business poznatek**, nikoli pouze přepis jedné metriky nebo KPI.

Pokud více analytických výsledků popisuje stejný business jev, spoj je do jednoho insightu.

Obvykle vytvářej **3 až 5 insightů**.

Vyšší počet použij pouze tehdy, pokud jednotlivé insighty představují skutečně odlišné business skutečnosti.

Nevytvářej insight pouze proto, že je některá metrika nebo dimenze dostupná.

Název insightu formuluj co nejblíže skutečnostem uvedeným ve vstupu.

Nevytvářej nové souhrnné pojmy (například „obchodní výsledky“, „výkonnost společnosti“, „vývoj byznysu“), pokud nejsou explicitně podloženy vstupní analýzou.

Insight nesmí obsahovat:

- domněnky,
- kauzální tvrzení,
- doporučená opatření,
- technické informace,
- metodiku analýzy.

Pokud analýza pouze lokalizuje problém, neoznačuj tuto lokalizaci za jeho příčinu.

Pokud některou skutečnost nelze z dostupných dat objektivně určit, tuto nejistotu explicitně uveď.

---

## Shrnutí

Shrnutí představuje stručný manažerský přehled celé analýzy.

Nemá opakovat jednotlivé insighty ani vyjmenovávat všechny konkrétní výsledky.

Stručně popiš:

- hlavní závěr analýzy,
- celkový význam výsledků,
- nejdůležitější omezení interpretace.

Rozsah shrnutí by měl být přibližně **2 až 3 věty**.

---

## Potvrzené insighty

Každý insight musí obsahovat:

- název,
- stručný popis,
- business význam (Vysoký / Střední / Nízký),
- zdůvodnění business významu,
- podložení výsledky analýzy.

Business význam určuj podle toho, jak významně insight podporuje rozhodování managementu a naplnění business cíle.

---

## Priorita insightů

Seřaď insighty podle jejich významu pro management.

Priorita představuje doporučené pořadí, ve kterém by měl management jednotlivé insighty vyhodnocovat.

Použij číslovaný seznam obsahující pouze názvy insightů.

---

## Omezení interpretace

Uváděj pouze omezení vyplývající z:

- dostupných dat,
- rozsahu analýzy,
- agregace dat,
- chybějících informací,
- nemožnosti potvrdit příčinné vztahy.

Neopakuj omezení již uvedená v jednotlivých insightích.

---

## Otevřené analytické otázky

Formuluj pouze otázky, které přímo vyplývají z omezení analýzy.

Nevytvářej samostatnou otázku pro každý insight.

Slučuj související témata do obecnějších analytických oblastí.

Formuluj otázky na úrovni analytických témat, nikoli jednotlivých produktů, poboček nebo jiných konkrétních entit, pokud to není výslovně podloženo vstupní analýzou.

Neformuluj otázky, které lze již zodpovědět na základě dostupných výsledků.

---

## Celkové zhodnocení

Stručně uveď:

- co bylo objektivně prokázáno,
- co zůstává nejisté,
- jaké jsou hlavní limity interpretace výsledků.

Nevytvářej nové insighty ani doporučení.

Neopakuj podrobně jednotlivé insighty; pouze shrň celkový přínos analýzy.

---

## Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně tuto strukturu:

# Insight Report

## 1. Shrnutí

## 2. Předpoklady

## 3. Potvrzené insighty

## 4. Priorita insightů

## 5. Omezení interpretace

## 6. Otevřené analytické otázky

## 7. Celkové zhodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- nevytvářej nové závěry,
- neopakuj stejné informace ve více částech,
- jasně odděluj fakta od předpokladů,
- zachovávej objektivní analytický jazyk,
- nepřidávej doporučení ani návrhy řešení.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

Společnost ElectroRetail CZ dokončila analýzu vývoje tržeb za rok 2024.

## Business cíl

Objektivně posoudit změnu celkových tržeb mezi první a druhou polovinou roku 2024 a určit, ve kterých oblastech prodeje se pokles projevil.

## Výsledky dokončené analýzy

- Celkové tržby ve druhé polovině roku 2024 poklesly o 18 % oproti první polovině roku.
- Celkové prodané množství pokleslo o 6 %.
- Absolutní marže poklesla o 15 %.
- Největší absolutní pokles tržeb byl zaznamenán v kategorii Notebooky.
- Druhý největší pokles zaznamenala kategorie Tablety.
- Kategorie Příslušenství zaznamenala mírný růst tržeb.
- Největší relativní pokles mezi prodejními kanály vykázal e-shop.
- Tržby kamenných prodejen poklesly méně než tržby e-shopu.
- Mezi kamennými prodejnami zaznamenaly nejvýraznější pokles pobočky Brno a Ostrava.
- Ostatní pobočky vykázaly pouze mírné změny.
- Počet aktivních produktů se mezi oběma obdobími nezměnil.
- Počet prodejních dnů byl v obou pololetích stejný.
- Analýza byla provedena nad agregovanými transakčními daty za rok 2024.
- Nebyla dostupná data o marketingových kampaních, skladové dostupnosti, změnách cen, návštěvnosti e-shopu, konkurenci ani zákaznickém chování.
- Analýza neumožnila oddělit vliv prodaného množství, prodejních cen a změny produktového mixu.
- Skutečné příčiny poklesu tržeb nebylo možné z dostupných dat objektivně určit.

---

# Výstup

# Insight Report

## 1. Shrnutí

Analýza prokázala výrazný pokles tržeb ve druhé polovině roku 2024 a lokalizovala jeho hlavní projevy podle produktových kategorií, prodejních kanálů a poboček. Výsledky poskytují podklad pro určení oblastí s nejvýraznější změnou, ale kvůli agregaci dat a chybějícím informacím neumožňují určit příčiny poklesu.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Potvrzené insighty

### 3.1 Pokles tržeb byl výraznější než pokles prodaného množství

**Stručný popis:** Ve druhé polovině roku poklesly celkové tržby výrazněji než prodané množství a současně se snížila absolutní marže.

**Business význam:** Vysoký

**Zdůvodnění business významu:** Insight zachycuje rozsah změny hlavních sledovaných ukazatelů a ukazuje, že vývoj tržeb nelze popsat pouze změnou celkového prodaného množství.

**Podložení výsledky analýzy:**

- celkové tržby poklesly o 18 %,
- celkové prodané množství pokleslo o 6 %,
- absolutní marže poklesla o 15 %,
- počet aktivních produktů se mezi pololetími nezměnil,
- počet prodejních dnů byl v obou pololetích stejný.

### 3.2 Největší absolutní pokles tržeb se projevil v kategoriích Notebooky a Tablety

**Stručný popis:** Kategorie Notebooky zaznamenala největší absolutní pokles tržeb a kategorie Tablety druhý největší. Kategorie Příslušenství se od tohoto vývoje odlišovala mírným růstem.

**Business význam:** Vysoký

**Zdůvodnění business významu:** Insight určuje produktové kategorie, ve kterých se pokles tržeb projevil nejvýrazněji, a přímo tak podporuje lokalizaci změny podle business cíle.

**Podložení výsledky analýzy:**

- největší absolutní pokles tržeb byl zaznamenán v kategorii Notebooky,
- druhý největší pokles zaznamenala kategorie Tablety,
- kategorie Příslušenství zaznamenala mírný růst tržeb.

### 3.3 E-shop vykázal výraznější pokles tržeb než kamenné prodejny

**Stručný popis:** Z prodejních kanálů zaznamenal největší relativní pokles e-shop. Tržby kamenných prodejen poklesly méně, přičemž mezi pobočkami byl pokles nejvýraznější v Brně a Ostravě.

**Business význam:** Vysoký

**Zdůvodnění business významu:** Insight lokalizuje pokles podle prodejního kanálu a v rámci kamenných prodejen také podle poboček, což přímo přispívá k naplnění business cíle.

**Podložení výsledky analýzy:**

- největší relativní pokles mezi prodejními kanály vykázal e-shop,
- tržby kamenných prodejen poklesly méně než tržby e-shopu,
- nejvýraznější pokles mezi kamennými prodejnami zaznamenaly pobočky Brno a Ostrava,
- ostatní pobočky vykázaly pouze mírné změny.

## 4. Priorita insightů

1. Pokles tržeb byl výraznější než pokles prodaného množství
2. Největší absolutní pokles tržeb se projevil v kategoriích Notebooky a Tablety
3. E-shop vykázal výraznější pokles tržeb než kamenné prodejny

## 5. Omezení interpretace

- Analýza vycházela z agregovaných transakčních dat za rok 2024.
- Nebyla dostupná data o marketingových kampaních, skladové dostupnosti, změnách cen, návštěvnosti e-shopu, konkurenci ani zákaznickém chování.
- Analýza neumožnila oddělit vliv prodaného množství, prodejních cen a změny produktového mixu.
- Z dostupných výsledků nelze potvrdit příčinné vztahy ani objektivně určit skutečné příčiny poklesu tržeb.

## 6. Otevřené analytické otázky

- Jaký podíl na poklesu tržeb měly změny prodaného množství, prodejních cen a produktového mixu?
- Jak pokles tržeb souvisel se skladovou dostupností, marketingovými aktivitami, návštěvností e-shopu, konkurenčním prostředím a zákaznickým chováním?
- Jaké okolnosti souvisejí s rozdílným vývojem tržeb mezi produktovými kategoriemi, prodejními kanály a kamennými prodejnami?

## 7. Celkové zhodnocení

Analýza objektivně prokázala pokles celkových tržeb, prodaného množství a absolutní marže a určila oblasti, ve kterých se pokles projevil nejvýrazněji. Skutečné příčiny vývoje ani samostatný vliv množství, cen a produktového mixu prokázány nebyly. Interpretaci omezuje agregovaná úroveň transakčních dat a nedostupnost dalších obchodních, marketingových, provozních a zákaznických informací.
