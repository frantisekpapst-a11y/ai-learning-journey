# Prompt - Reporting 01 - Executive Summary Generator

## Prompt

Jsi senior datový analytik a business intelligence konzultant.

Tvým úkolem je vytvořit stručné, objektivní a manažersky orientované Executive Summary na základě již dokončené analýzy.

Executive Summary vychází výhradně z informací uvedených ve vstupu.

Nevytvářej nové závěry, interpretace ani doporučení, které nejsou podloženy vstupní analýzou.

Pokud některé informace chybí nebo je nelze z dostupných výsledků jednoznačně určit, tuto skutečnost stručně uveď.

Rozlišuj mezi:

- potvrzenými zjištěními,
- omezeními dostupných dat nebo analýzy,
- doporučenými navazujícími kroky.

Nepřisuzuj zjištěním příčinné vztahy, pokud je analýza objektivně neprokazuje.

Pokud analýza pouze lokalizuje změnu nebo popisuje souvislosti, neoznačuj je za skutečné příčiny.

Executive Summary nesmí obsahovat:

- metodiku analýzy,
- technické detaily,
- popis použitých nástrojů,
- statistické postupy,
- implementační doporučení.

Piš jazykem určeným pro management.

Používej krátké odstavce a stručné věty.

Každou důležitou informaci uveď pouze jednou. Neopakuj stejné závěry mezi jednotlivými částmi dokumentu.

V části **Klíčová zjištění** uváděj pouze informace s přímým dopadem na business rozhodování. Neuváděj podpůrná nebo technická zjištění, pokud významně nemění interpretaci výsledků.

Klíčová zjištění řaď podle jejich business významu, nikoli podle pořadí ve vstupní analýze.

V části **Doporučené navazující kroky** používej manažerský jazyk. Pokud lze odborný analytický termín nahradit srozumitelnější formulací bez změny významu, použij jednodušší variantu.

V části **Celkové zhodnocení** vždy jednoznačně uveď:

- zda analýza odpověděla na business otázku,
- co bylo objektivně prokázáno,
- co z dostupných dat určit nelze,
- zda jsou výsledky dostatečné pro business rozhodnutí, nebo slouží pouze jako podklad pro další analýzy.

Přizpůsob rozsah Executive Summary složitosti vstupu.

---

## Požadovaná struktura výstupu

Výstup připrav jako přehledný Markdown dokument.

Použij přesně tuto strukturu:

# Executive Summary

## 1. Shrnutí

Stručně popiš nejdůležitější výsledek celé analýzy ve 2–3 větách.

## 2. Business cíl

Jednou až dvěma větami shrň business cíl analýzy.

## 3. Klíčová zjištění

Uveď pouze nejdůležitější business zjištění formou stručných odrážek.

Řaď je od nejdůležitějších po méně významná.

## 4. Omezení výsledků

Popiš pouze omezení, která mohou ovlivnit interpretaci výsledků.

Neopakuj informace již uvedené ve Shrnutí nebo Klíčových zjištěních.

## 5. Doporučené navazující kroky

Navrhni pouze kroky přímo vyplývající ze zjištěných omezení nebo výsledků.

Formuluj je jazykem srozumitelným managementu.

## 6. Celkové zhodnocení

Stručně zhodnoť:

- zda byla business otázka zodpovězena,
- co bylo objektivně prokázáno,
- co nelze z dostupných dat určit,
- zda jsou výsledky dostatečné pro business rozhodnutí nebo pouze jako podklad pro další analýzy.

Poslední věta musí jednoznačně říci, pro jaký typ rozhodování jsou výsledky použitelné.

Výstup by měl odpovídat přibližně jedné straně textu.

---

# Zadání

## Business kontext

Společnost ElectroRetail CZ analyzovala vývoj tržeb mezi první a druhou polovinou roku 2024.

Cílem analýzy bylo:

- zjistit, zda došlo ke změně celkových tržeb,
- určit, ve kterých částech prodeje se změna projevila,
- připravit podklad pro rozhodování managementu a pravidelný měsíční management reporting.

## Výsledky dokončené analýzy

- Celkové tržby ve druhé polovině roku 2024 poklesly o 18 % oproti první polovině roku.
- Největší část poklesu se koncentrovala v kategorii Notebooky.
- Nejvýraznější pokles podle prodejních kanálů nastal v online prodeji.
- Mezi kamennými prodejnami zaznamenaly největší pokles pobočky v Brně a Ostravě.
- Prodané množství pokleslo výrazně méně než celkové tržby.
- Počet aktivních produktů ani počet prodejních dnů se mezi porovnávanými obdobími nezměnil.

## Omezení analýzy

- Data jsou agregovaná.
- Nelze oddělit vliv prodaného množství, prodejních cen a produktového mixu.
- Chybí detailní propojení produktů, kategorií, prodejních kanálů a prodejen.
- Nejsou dostupná data o marketingových kampaních.
- Nejsou dostupná data o skladové dostupnosti.
- Nejsou dostupná data o návštěvnosti e-shopu.
- Nejsou dostupná data o konkurenci.
- Nejsou dostupná historická data mimo rok 2024.

## Doporučené navazující kroky

- Detailněji analyzovat vývoj tržeb podle produktů, produktových kategorií, prodejních kanálů a prodejen.
- Ověřit, jaký podíl na změně tržeb mělo prodané množství, změna cen a změna struktury prodaných produktů.
- Prověřit konzistenci údajů o průměrných prodejních cenách.
- Doplnit informace o skladové dostupnosti a marketingových aktivitách.
- Porovnat výsledky s dalšími historickými obdobími.

---

# Návrh výstupu

# Executive Summary

## 1. Shrnutí

Celkové tržby společnosti ElectroRetail CZ ve druhé polovině roku 2024 poklesly o 18 % oproti první polovině roku. Pokles se nejvíce soustředil do kategorie Notebooky, online prodeje a kamenných prodejen v Brně a Ostravě. Dostupné výsledky určují, kde se změna projevila, nikoli však její skutečné příčiny.

## 2. Business cíl

Cílem analýzy bylo posoudit změnu celkových tržeb mezi první a druhou polovinou roku 2024, určit části prodeje s nejvýraznějším poklesem a připravit podklad pro management a pravidelný měsíční reporting.

## 3. Klíčová zjištění

- Celkové tržby poklesly o 18 %.
- Největší část poklesu se koncentrovala v kategorii Notebooky.
- Z prodejních kanálů zaznamenal nejvýraznější pokles online prodej.
- Mezi kamennými prodejnami vykázaly největší pokles pobočky v Brně a Ostravě.
- Prodané množství pokleslo výrazně méně než tržby.
- Počet aktivních produktů ani počet prodejních dnů se mezi obdobími nezměnil.

## 4. Omezení výsledků

Agregovaná data neumožňují oddělit vliv prodaného množství, prodejních cen a změny struktury prodaných produktů. Chybí také detailní propojení produktů, kategorií, prodejních kanálů a jednotlivých prodejen.

Interpretaci dále omezuje absence informací o skladové dostupnosti, marketingových aktivitách, návštěvnosti e-shopu a konkurenci. Bez historických dat mimo rok 2024 nelze posoudit, zda zjištěný vývoj odpovídá sezónnosti nebo dlouhodobějšímu trendu.

## 5. Doporučené navazující kroky

- Rozšířit posouzení tržeb o detail jednotlivých produktů, kategorií, prodejních kanálů a prodejen.
- Vyčíslit, jak se na změně tržeb podílely prodané množství, prodejní ceny a struktura prodaných produktů.
- Prověřit správnost a konzistenci údajů o průměrných prodejních cenách.
- Doplnit údaje o skladové dostupnosti a marketingových aktivitách.
- Porovnat výsledky s dalšími historickými obdobími.

## 6. Celkové zhodnocení

Analýza odpověděla na otázku, zda se celkové tržby změnily, a určila části prodeje, ve kterých se pokles projevil nejvýrazněji. Objektivně prokázala pokles tržeb o 18 % a jeho koncentraci do vybraných kategorií, kanálů a prodejen.

Z dostupných dat nelze určit skutečné příčiny poklesu ani spolehlivě rozlišit vliv množství, cen a produktové struktury. Výsledky jsou použitelné pro zaměření navazujících analýz a průběžný management reporting, nikoli jako samostatný podklad pro rozhodnutí o konkrétních obchodních opatřeních.
