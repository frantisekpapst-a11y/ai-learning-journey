# Prompt 030 — Data Storytelling Plan Generator

# Prompt

Jsi senior datový analytik, business intelligence konzultant a specialista na data storytelling.

Tvým úkolem je vytvořit objektivní Data Storytelling Plan na základě dokončené datové analýzy.

Data Storytelling Plan slouží jako návrh logické struktury prezentace analytických výsledků pro business publikum. Jeho cílem není interpretovat data novým způsobem ani vytvářet nové závěry, ale uspořádat již potvrzené výsledky do srozumitelného a logicky navazujícího příběhu.

## Režimy práce

Nejprve urči režim podle obsahu vstupu.

### Režim A — Business zadání

Použij, pokud vstup obsahuje pouze business problém nebo business cíl.

V tomto režimu:

- Data Storytelling Plan nevytvářej.
- Stručně uveď, že dosud nejsou k dispozici výsledky analýzy.
- Vysvětli, že datový příběh lze objektivně vytvořit až po dokončení analýzy.

---

### Režim B — Business zadání a data

Použij, pokud vstup obsahuje business zadání společně s daty nebo popisem datasetu, ale neobsahuje analytické výsledky.

V tomto režimu:

- Data Storytelling Plan nevytvářej.
- Uveď, že samotná data nepředstavují analytické závěry.
- Vysvětli, že datový příběh lze vytvořit až po dokončení analýzy.

---

### Režim C — Dokončená analýza

Použij pouze tehdy, pokud vstup obsahuje dokončenou analýzu nebo její výstupy (například Executive Summary, Insight Report, analytickou zprávu nebo obdobné podklady).

Pouze v tomto režimu vytvoř Data Storytelling Plan.

---

# Práce s předpoklady

Pokud některé informace chybí a jsou nezbytné pro vytvoření datového příběhu, uveď je jako předpoklady.

Předpoklady formuluj pouze tehdy, pokud je při tvorbě výstupu skutečně používáš.

Pokud nejsou potřeba žádné předpoklady, uveď pouze:

**Nebyly nutné žádné dodatečné předpoklady.**

---

# Obecná pravidla

Vycházej výhradně z informací uvedených ve vstupu.

Nevytvářej:

- nové insighty,
- nové interpretace,
- hypotézy,
- příčinná vysvětlení,
- business doporučení,
- nové analytické závěry.

Data Storytelling Plan má pouze:

- určit logické pořadí prezentace,
- propojit jednotlivé potvrzené výsledky,
- navrhnout vhodnou narativní strukturu,
- doporučit způsob komunikace jednotlivých částí,
- upozornit na rizika interpretace.

Pokud analýza pouze lokalizuje problém, nepředstavuj tuto lokalizaci jako jeho příčinu.

Nevysvětluj metodiku analýzy ani technickou implementaci.

Nevytvářej Power BI report.

Nevytvářej dashboard.

Nevytvářej konkrétní grafy ani návrh layoutu prezentace.

Pokud jsou ve vstupu doporučené vizualizace, využij je pouze jako podporu příběhu.

---

# Struktura příběhu

Datový příběh má vést publikum:

1. od business kontextu,
2. přes hlavní analytická zjištění,
3. ke správné interpretaci výsledků,
4. až k jasnému vymezení toho, co bylo prokázáno a co zůstává nejisté.

Každá část příběhu má navazovat na předchozí.

Přechody mezi částmi mají být logické.

Neopakuj stejné informace.

Každý insight použij pouze jednou.

---

# Vizuální podpora

Pokud jsou k dispozici doporučené vizualizace, u každé části příběhu stručně uveď:

- jaký typ vizualizace ji podporuje,
- jaký je účel této vizualizace,
- co si z ní má publikum odnést.

Nevytvářej návrh konkrétního dashboardu.

---

# Klíčové momenty příběhu

Vyber pouze několik nejdůležitějších okamžiků prezentace.

Nemají představovat nové insighty.

Mají pouze zvýraznit části, které mají největší význam pro publikum.

---

# Omezení interpretace

Shrň pouze omezení, která vyplývají z dokončené analýzy.

Nevytvářej nová omezení.

Neopakuj omezení uvedená v jednotlivých částech příběhu.

---

# Závěrečné sdělení

Jedním až dvěma odstavci shrň:

- co bylo objektivně prokázáno,
- co zůstává nejisté,
- jak má management výsledky správně interpretovat.

Nevytvářej nová doporučení.

---

# Podložené navazující kroky

Uveď pouze kroky, které přímo vyplývají z omezení nebo otevřených analytických otázek uvedených ve vstupu.

Nevytvářej nové návrhy řešení.

Nevytvářej business doporučení.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně tuto strukturu:

# Data Storytelling Plan

## Shrnutí příběhu

## Předpoklady

## Cílové publikum a komunikační cíl

## Hlavní sdělení

## Struktura datového příběhu

Tabulka:

| Část | Hlavní sdělení | Podklad ve výsledcích | Doporučená vizuální podpora a její účel | Přechod k následující části |

## Klíčové momenty příběhu

## Omezení a interpretační upozornění

## Závěrečné sdělení

## Podložené navazující kroky

---

Dodrž následující pravidla:

- piš stručně a věcně,
- zachovávej objektivní analytický jazyk,
- nevyvozuj nové závěry,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace,
- nevytvářej nové insighty,
- nepřidávej technické informace,
- nepopisuj metodiku analýzy,
- nevytvářej dashboard ani layout prezentace.

Výstup by měl odpovídat přibližně rozsahu 2–3 stran textu.

---

# Zadání

### Business zadání

Společnost **ElectroRetail CZ** zaznamenala ve druhém pololetí roku 2024 výrazný pokles tržeb oproti prvnímu pololetí.

Management požaduje připravit prezentaci výsledků analýzy, která:

- jasně vysvětlí rozsah změny obchodních výsledků,
- ukáže, ve kterých oblastech se pokles projevil nejvýrazněji,
- bude určena pro vedení společnosti,
- bude založena pouze na objektivně potvrzených výsledcích analýzy,
- nebude vytvářet nepodložené interpretace ani kauzální závěry.

---

## Executive Summary

### Shrnutí

Ve druhém pololetí roku 2024 došlo k výraznému poklesu obchodních výsledků společnosti ElectroRetail CZ. Analýza objektivně určila rozsah poklesu a identifikovala oblasti, ve kterých se projevil nejvýrazněji. Dostupná data však neumožnila určit skutečné příčiny změny.

### Business cíl

Zjistit rozsah poklesu obchodních výsledků mezi prvním a druhým pololetím roku 2024 a určit, ve kterých produktových kategoriích, prodejních kanálech a kamenných prodejnách se pokles projevil nejvýrazněji.

### Klíčová zjištění

- Celkové tržby poklesly o **18 %**.
- Prodané množství pokleslo o **6 %**.
- Absolutní marže poklesla o **15 %**.
- Počet aktivních produktů se nezměnil.
- Počet prodejních dnů se nezměnil.
- Největší absolutní pokles tržeb zaznamenaly **Notebooky** a **Tablety**.
- Kategorie **Příslušenství** jako jediná vykázala mírný růst.
- Největší relativní pokles mezi prodejními kanály zaznamenal **e-shop**.
- Mezi kamennými prodejnami vykázaly nejvýraznější pokles **Brno** a **Ostrava**.

### Omezení výsledků

Analýza vychází pouze z agregovaných transakčních dat.

Nebyla k dispozici data o:

- marketingových aktivitách,
- změnách cen,
- skladové dostupnosti,
- návštěvnosti e-shopu,
- konkurenci,
- zákaznickém chování.

Analýza neumožnila oddělit vliv:

- prodaného množství,
- prodejních cen,
- produktového mixu.

### Doporučené navazující kroky

- provést detailnější rozklad změny tržeb,
- doplnit marketingová data,
- doplnit informace o skladové dostupnosti,
- doplnit data o návštěvnosti e-shopu,
- porovnat výsledky s delší historickou řadou.

### Celkové zhodnocení

Analýza spolehlivě určila rozsah poklesu obchodních výsledků a lokalizovala oblasti s nejvýraznější změnou. Skutečné příčiny poklesu však z dostupných dat určit nelze.

---

## Insight Report

### Shrnutí

Pokles obchodních výsledků se projevil napříč společností, avšak jeho intenzita nebyla ve všech oblastech stejná. Největší změny byly zaznamenány v produktových kategoriích Notebooky a Tablety, v e-shopu a u kamenných prodejen Brno a Ostrava.

### Potvrzené insighty

#### Insight 1

Ve druhém pololetí roku 2024 poklesly:

- tržby o **18 %**,
- prodané množství o **6 %**,
- absolutní marže o **15 %**.

Business význam: **Vysoký**

---

#### Insight 2

Největší absolutní pokles tržeb zaznamenaly:

- Notebooky,
- Tablety.

Kategorie Příslušenství jako jediná vykázala mírný růst.

Business význam: **Vysoký**

---

#### Insight 3

Největší relativní pokles mezi prodejními kanály vykázal e-shop.

Business význam: **Střední**

---

#### Insight 4

Nejvýraznější pokles mezi kamennými prodejnami zaznamenaly:

- Brno,
- Ostrava.

Business význam: **Střední**

### Omezení interpretace

Analýza lokalizovala oblasti poklesu, ale neprokázala jeho skutečné příčiny.

Nebylo možné určit samostatný vliv:

- množství,
- cen,
- produktového mixu.

### Otevřené analytické otázky

- Jaký podíl na poklesu tržeb mělo prodané množství?
- Jaký podíl měly změny cen?
- Jaký vliv měl produktový mix?
- Jaký vliv měla marketingová aktivita?
- Jaký vliv měla skladová dostupnost?
- Jaký vliv měla návštěvnost e-shopu?

---

## Analytická zpráva

### Celkový vývoj

Ve druhém pololetí roku 2024:

| Metrika | Změna |
|---|---:|
| Tržby | −18 % |
| Prodané množství | −6 % |
| Absolutní marže | −15 % |
| Aktivní produkty | beze změny |
| Prodejní dny | beze změny |

### Produktové kategorie

Největší absolutní pokles tržeb:

1. Notebooky
2. Tablety

Mírný růst:

- Příslušenství

### Prodejní kanály

Největší relativní pokles:

- e-shop

### Kamenné prodejny

Nejvýraznější pokles:

- Brno
- Ostrava

### Omezení analýzy

Analýza pracovala pouze s agregovanými transakčními daty.

Nebylo možné samostatně vyhodnotit vliv:

- prodaného množství,
- prodejních cen,
- produktového mixu.

Nebyla dostupná data o:

- marketingových aktivitách,
- skladové dostupnosti,
- návštěvnosti e-shopu,
- konkurenci,
- zákaznickém chování.

Výsledky proto představují popis rozsahu a lokalizace poklesu, nikoli jeho skutečných příčin.

---

# Výstup

# Data Storytelling Plan

## Shrnutí příběhu

Příběh představí zhoršení obchodních výsledků společnosti ElectroRetail CZ ve druhém pololetí roku 2024. Nejprve vymezí celkový rozsah změny prostřednictvím vývoje tržeb, prodaného množství a absolutní marže. Následně ukáže, ve kterých produktových kategoriích, prodejních kanálech a kamenných prodejnách se pokles projevil nejvýrazněji.

 část oddělí potvrzené výsledky od oblastí, které dostupná agregovaná transakční data nedokázala vysvětlit. Management tak získá přehled o rozsahu a lokalizaci poklesu, nikoli o jeho skutečných příčinách.

## Předpoklady

**Nebyly nutné žádné dodatečné předpoklady.**

## Cílové publikum a komunikační cíl

**Cílové publikum:** vedení společnosti ElectroRetail CZ.

**Komunikační cíl:** stručně a objektivně představit:

- rozsah změny obchodních výsledků mezi prvním a druhým pololetím roku 2024,
- oblasti, ve kterých se pokles projevil nejvýrazněji,
- hranici mezi potvrzenými výsledky a dosud nezodpovězenými otázkami.

Prezentace má managementu umožnit správně interpretovat výsledky jako popis rozsahu a lokalizace poklesu, nikoli jako vysvětlení jeho příčin.

## Hlavní sdělení

Ve druhém pololetí roku 2024 došlo k výraznému zhoršení obchodních výsledků společnosti ElectroRetail CZ. Pokles se projevil v tržbách, prodaném množství i absolutní marži, ale jeho intenzita nebyla ve všech oblastech stejná.

Analýza lokalizovala nejvýraznější změny do kategorií Notebooky a Tablety, e-shopu a kamenných prodejen Brno a Ostrava. Z dostupných dat však nelze určit, proč k těmto změnám došlo ani jaký samostatný vliv měly množství, ceny a produktový mix.

## Struktura datového příběhu

| Část | Hlavní sdělení | Podklad ve výsledcích | Doporučená vizuální podpora a její účel | Přechod k následující části |
|---|---|---|---|---|
| 1. Business kontext | Analýza reaguje na výrazné zhoršení obchodních výsledků ve druhém pololetí roku 2024 a má určit jeho rozsah a lokalizaci. | Business zadání a business cíl dokončené analýzy. | Stručné textové uvedení s porovnávanými obdobími. Účelem je vymezit otázku, na kterou analýza odpovídá. Publikum si má odnést, že předmětem je porovnání prvního a druhého pololetí roku 2024. | Po vymezení business otázky následuje představení celkového rozsahu změny. |
| 2. Celkový rozsah poklesu | Obchodní výsledky se ve druhém pololetí zhoršily ve všech třech hlavních sledovaných metrikách. | Tržby poklesly o 18 %, prodané množství o 6 % a absolutní marže o 15 %. Počet aktivních produktů ani prodejních dnů se nezměnil. | Srovnávací sloupcové zobrazení změn hlavních metrik doplněné o neutrální informaci o nezměněném počtu aktivních produktů a prodejních dnů. Účelem je ukázat rozsah změny bez naznačování příčin. Publikum si má odnést, že největší relativní změna nastala u tržeb. | Celkový výsledek otevírá otázku, ve kterých částech společnosti se změna projevila nejvýrazněji. |
| 3. Produktové kategorie | Pokles tržeb nebyl mezi produktovými kategoriemi rozložen rovnoměrně. | Největší absolutní pokles tržeb zaznamenaly Notebooky a Tablety. Příslušenství jako jediná kategorie vykázalo mírný růst. | Seřazené srovnání změny tržeb podle produktových kategorií. Účelem je zvýraznit pořadí kategorií podle absolutního poklesu a odlišný vývoj Příslušenství. Publikum si má odnést, které kategorie byly z hlediska absolutní změny nejvýznamnější. | Po produktovém pohledu se příběh přesune k tomu, jak se výsledky lišily podle způsobu prodeje. |
| 4. Prodejní kanály | Mezi prodejními kanály zaznamenal největší relativní pokles e-shop. | Potvrzený insight o největším relativním poklesu e-shopu. | Srovnání relativních změn mezi prodejními kanály. Účelem je zasadit vývoj e-shopu do kontextu ostatních kanálů. Publikum si má odnést, že e-shop vykázal nejvýraznější relativní pokles, nikoliv že byl příčinou celkového výsledku. | Kanálový pohled doplní lokalizace změny v síti kamenných prodejen. |
| 5. Kamenné prodejny | Intenzita poklesu se lišila také mezi jednotlivými kamennými prodejnami. | Nejvýraznější pokles zaznamenaly prodejny Brno a Ostrava. | Seřazené srovnání výsledků kamenných prodejen. Účelem je identifikovat prodejny s nejvýraznější změnou. Publikum si má odnést, že Brno a Ostrava představují hlavní lokalizované oblasti poklesu v kamenné síti. | Po lokalizaci hlavních změn je nutné vymezit hranice jejich interpretace. |
| 6. Co analýza prokázala a co nikoli | Analýza spolehlivě popsala rozsah a lokalizaci poklesu, ale neprokázala jeho příčiny. | Nebylo možné oddělit vliv prodaného množství, cen a produktového mixu. Chyběla data o marketingu, skladové dostupnosti, návštěvnosti e-shopu, konkurenci a zákaznickém chování. | Přehledné rozdělení na „prokázáno“ a „neprokázáno“. Účelem je zabránit záměně lokalizace problému za příčinné vysvětlení. Publikum si má odnést jasnou interpretační hranici výsledků. | Vymezené nejistoty přirozeně vedou k analytickým otázkám a navazujícím krokům již uvedeným ve vstupu. |
| 7. Otevřené otázky a analytické pokračování | Další práce má objasnit dosud neoddělené vlivy a doplnit chybějící kontext. | Otevřené otázky se týkají množství, cen, produktového mixu, marketingové aktivity, skladové dostupnosti a návštěvnosti e-shopu. Doporučené kroky zahrnují detailnější rozklad tržeb, doplnění příslušných dat a porovnání s delší historií. | Stručný přehled otevřených analytických oblastí a navazujících kroků. Účelem je uzavřít příběh bez předjímání výsledků další analýzy. Publikum si má odnést, co je nutné dále ověřit. | Příběh končí potvrzeným rozsahem a lokalizací poklesu a jasně vymezenou nejistotou ohledně jeho příčin. |

## Klíčové momenty příběhu

1. **Rozsah zhoršení obchodních výsledků**  
   Tržby poklesly o 18 %, absolutní marže o 15 % a prodané množství o 6 %. Jde o hlavní moment, který stanoví význam analyzované změny.

2. **Lokalizace nejvýraznějších změn**  
   Produktový, kanálový a regionální pohled ukazuje, že intenzita poklesu nebyla ve všech částech společnosti stejná.

3. **Hranice mezi výsledkem a jeho vysvětlením**  
   Zásadním interpretačním momentem je oddělení potvrzené lokalizace poklesu od jeho neprokázaných příčin.

## Omezení a interpretační upozornění

Analýza vychází pouze z agregovaných transakčních dat. Neumožnila samostatně vyhodnotit vliv:

- prodaného množství,
- prodejních cen,
- produktového mixu.

Současně nebyla dostupná data o:

- marketingových aktivitách,
- skladové dostupnosti,
- návštěvnosti e-shopu,
- konkurenci,
- zákaznickém chování.

Výsledky proto nesmějí být prezentovány jako příčinné vysvětlení poklesu. Kategorie Notebooky a Tablety, e-shop ani prodejny Brno a Ostrava nejsou prokázanými příčinami celkového zhoršení; představují pouze oblasti, ve kterých analýza zaznamenala nejvýraznější změny.

## Závěrečné sdělení

Analýza objektivně prokázala, že ve druhém pololetí roku 2024 poklesly celkové tržby, prodané množství i absolutní marže společnosti ElectroRetail CZ. Současně určila oblasti, ve kterých se změna projevila nejvýrazněji.

Skutečné příčiny poklesu zůstávají nejisté. Management má proto výsledky interpretovat jako spolehlivé vymezení rozsahu a lokalizace problému, nikoli jako důkaz vlivu konkrétních obchodních faktorů.

## Podložené navazující kroky

- Provést detailnější rozklad změny tržeb se zaměřením na samostatný vliv prodaného množství, prodejních cen a produktového mixu.
- Doplnit data o marketingových aktivitách.
- Doplnit informace o skladové dostupnosti.
- Doplnit data o návštěvnosti e-shopu.
- Porovnat výsledky s delší historickou řadou.
