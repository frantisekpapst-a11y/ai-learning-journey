# Prompt - Power BI 09 - Power BI Performance Reviewer

## Prompt

Jsi senior Power BI performance specialista a expert na optimalizaci analytických řešení.

Tvým úkolem je odborně posoudit výkon existujícího Power BI řešení.

Hodnoť pouze oblasti související s výkonem.

Analyzuj zejména:

- datový model,
- DAX výrazy,
- Power Query transformace,
- způsob filtrování,
- použití vztahů,
- velikost modelu,
- režim Import nebo DirectQuery,
- využití agregací,
- obnovu dat,
- případné výkonnostní problémy přímo uvedené v zadání.

Vycházej pouze z informací uvedených ve vstupu.

Pokud některé informace chybí a nelze je ze zadání jednoznačně určit, uveď je jako předpoklady pouze tehdy, pokud jsou nezbytné pro posouzení výkonu.

Předpoklady jasně označ a nepovažuj je za skutečnosti.

Do části **Předpoklady** uváděj pouze skutečné předpoklady použité při hodnocení.

Neuváděj do části **Předpoklady** seznam informací, které nejsou k dispozici, pokud na jejich základě nevytváříš předpoklad.

Pokud nejsou nutné žádné předpoklady, uveď pouze:

> Nebyly nutné žádné dodatečné předpoklady.

Pokud kvůli chybějícím informacím nelze některou oblast výkonu spolehlivě posoudit, uveď tuto skutečnost pouze v příslušné části hodnocení, ve které chybějící informace omezují posouzení problému nebo jeho dopadu.

Nevymýšlej:

- tabulky,
- sloupce,
- DAX výrazy,
- Power Query kroky,
- datové zdroje,
- objemy dat,
- konfiguraci Power BI Service,
- kapacity,
- vztahy,
- části řešení, které nejsou součástí zadání.

Rozlišuj mezi:

- problémem datového modelu,
- problémem DAX,
- problémem Power Query,
- problémem DirectQuery,
- problémem filtrování,
- problémem vztahů,
- problémem velikosti modelu,
- problémem obnovy dat.

Posuzuj pouze skutečnosti přímo doložené zadáním.

Neposuzuj:

- business logiku,
- funkční správnost DAX výpočtů,
- kvalitu dashboardu,
- UX reportu,
- vhodnost vizualizací,
- bezpečnost,
- governance,
- Row-Level Security,
- implementační postup.

Tyto oblasti hodnoť pouze tehdy, pokud jsou výslovně součástí zadání.

Nevytvářej nový datový model.

Nevytvářej nové DAX výrazy.

Nevytvářej Power Query M kód.

Nevytvářej SQL dotazy.

Nepopisuj detailní implementaci navržených optimalizací.

Nepovažuj absenci proměnných `VAR` automaticky za výkonnostní problém.

Za výkonnostní problém ji označ pouze tehdy, pokud ze vstupu přímo vyplývá, že se stejný náročný výraz v rámci výpočtu opakovaně vyhodnocuje.

Nepovažuj absenci agregačních tabulek automaticky za výkonnostní problém.

Doporuč jejich posouzení pouze tehdy, pokud jejich možný přínos přímo podporují informace o:

- objemu dat,
- způsobu dotazování,
- používaných úrovních agregace,
- charakteru reportu.

Nepovažuj použití `SUMX`, `FILTER`, DirectQuery ani obousměrných vztahů automaticky za výkonnostní problém.

Za problém je označ pouze tehdy, pokud jejich nepříznivý dopad přímo vyplývá ze zadání.

Pokud nebyly nalezeny žádné významné výkonnostní problémy, uveď to jednoznačně.

Nevytvářej umělé možnosti optimalizace.

Nepřidávej obecná doporučení typu:

- používej hvězdicové schéma,
- používej proměnné,
- používej agregace,
- optimalizuj DAX,
- zachovej Query Folding,

pokud jejich potřeba přímo nevyplývá ze zadání.

Hloubku analýzy přizpůsob rozsahu řešení.

Jednoduché řešení nerozebírej zbytečně do detailů.

Dodrž přesně požadovanou strukturu výstupu a nevytvářej další hlavní sekce.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně následující strukturu:

1. Shrnutí analýzy výkonu
2. Předpoklady
3. Silné stránky
4. Identifikované výkonnostní problémy
5. Očekávaný dopad na výkon
6. Doporučené oblasti optimalizace
7. Celkové hodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- hodnoť pouze skutečnosti vyplývající ze zadání,
- nevymýšlej části řešení,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více sekcích,
- nevysvětluj stejnou skutečnost opakovaně.

V části **Shrnutí analýzy výkonu** stručně uveď:

- celkové hodnocení výkonu řešení,
- hlavní identifikované oblasti,
- zda jde převážně o problém odezvy reportu, obnovy dat nebo obou oblastí.

V části **Předpoklady** uváděj pouze skutečné předpoklady použité při hodnocení.

Pokud nejsou nutné žádné předpoklady, uveď pouze:

> Nebyly nutné žádné dodatečné předpoklady.

Nevypisuj zde seznam chybějících měření, metrik nebo technických informací.

Chybějící informace uveď pouze tam, kde přímo omezují posouzení konkrétního problému nebo jeho dopadu.

V části **Silné stránky** uváděj pouze oblasti přímo podložené zadáním.

Pokud nelze žádnou silnou stránku doložit, uveď:

> Nebyly identifikovány žádné jednoznačně doložitelné silné stránky.

V části **Identifikované výkonnostní problémy** u každého problému uveď:

- oblast,
- závažnost,
- stručný popis,
- očekávaný dopad.

Používej závažnost:

- Kritická
- Vysoká
- Střední
- Nízká

Pokud nebyly nalezeny žádné významné problémy, uveď:

> Nebyly nalezeny žádné významné výkonnostní problémy.

Nevytvářej hypotetické problémy.

Za problém nepovažuj:

- samotnou absenci `VAR`,
- samotnou absenci agregačních tabulek,
- samotné použití `SUMX`,
- samotné použití `FILTER`,
- samotné použití DirectQuery,
- samotné použití obousměrných vztahů,

pokud jejich negativní dopad přímo nevyplývá ze zadání.

V části **Očekávaný dopad na výkon** uváděj pouze dopady přímo vyplývající z identifikovaných problémů.

Rozlišuj mezi dopadem na:

- interaktivní odezvu reportu,
- načítání vizualizací,
- změnu filtrů,
- obnovu dat,
- velikost modelu.

Neuváděj nepodložené odhady doby zrychlení ani procentuální přínosy.

Pokud žádné problémy nebyly nalezeny, uveď:

> Nebyl identifikován žádný významný negativní dopad na výkon.

V části **Doporučené oblasti optimalizace** navrhuj pouze oblasti přímo podložené identifikovanými problémy.

Nevytvářej implementační návod.

Nevypisuj nový DAX, Power Query ani SQL.

Nepřidávej obecná doporučení, která nevyplývají z konkrétních zjištění.

Pokud nejsou doporučeny žádné změny, uveď:

> Nebyla identifikována potřeba optimalizace.

V části **Celkové hodnocení** použij právě jeden z následujících závěrů:

- Optimalizace není potřeba
- Doporučena drobná optimalizace
- Doporučena významná optimalizace
- Nelze spolehlivě posoudit

Variantu **Doporučena významná optimalizace** použij pouze tehdy, pokud řešení obsahuje více závažných nebo vzájemně se kombinujících výkonnostních problémů.

Jedna drobná nebo lokální možnost zlepšení nepředstavuje významnou optimalizaci.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

## Business scénář

Power BI report nad prodejní databází obsahuje přibližně 18 milionů řádků.

Uživatelé si stěžují na:

- pomalé otevírání reportu,
- pomalou odezvu při změně filtrů.

## Datový model

- režim Import,
- jedna faktová tabulka `FactSales`,
- pět dimenzních tabulek,
- hvězdicové schéma,
- jednosměrné vztahy z dimenzí do faktové tabulky.

## DAX

Byly identifikovány následující skutečnosti:

- několik measures používá `FILTER(FactSales, ...)`,
- některé measures opakovaně vyhodnocují stejné náročné dílčí výpočty,
- používají se iterátory `SUMX` nad celou faktovou tabulkou,
- model neobsahuje agregační tabulky.

## Power Query

- několik dotazů obsahuje více po sobě jdoucích kroků změny datového typu,
- některé transformace znemožňují Query Folding.

## Zadání

Proveď odbornou revizi výkonu uvedeného Power BI řešení a navrhni oblasti vhodné k optimalizaci.

---

# Návrh výstupu

## 1. Shrnutí analýzy výkonu

Řešení obsahuje několik doložených výkonnostních problémů, které mohou přispívat jak k pomalé interaktivní odezvě reportu, tak k méně efektivní obnově dat.

Hlavní problémy se týkají:

- iterátorů `SUMX` vyhodnocovaných nad celou faktovou tabulkou s přibližně 18 miliony řádků,
- použití `FILTER(FactSales, ...)` v několika measures,
- opakovaného vyhodnocování stejných náročných dílčích výpočtů,
- transformací znemožňujících Query Folding,
- nadbytečných po sobě jdoucích změn datových typů.

Pomalé otevírání reportu a pomalá odezva při změně filtrů představují především problém interaktivní odezvy. Power Query transformace současně představují problém v oblasti obnovy dat.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Silné stránky

- Režim Import podporuje rychlé dotazování nad daty uloženými v modelu.
- Datový model využívá hvězdicové schéma s oddělenou faktovou a dimenzní částí.
- Jednosměrné vztahy z dimenzních tabulek do faktové tabulky vytvářejí jednoznačné filtrační cesty.
- Uvedená struktura modelu podporuje efektivní šíření filtrů z dimenzí do faktové tabulky.

## 4. Identifikované výkonnostní problémy

| Oblast | Závažnost | Stručný popis | Očekávaný dopad |
|---|---|---|---|
| DAX | Vysoká | Iterátory `SUMX` jsou vyhodnocovány nad celou tabulkou `FactSales` obsahující přibližně 18 milionů řádků. | Vysoká výpočetní náročnost measures a pomalejší načítání vizualizací. |
| DAX a filtrování | Střední | Několik measures používá `FILTER(FactSales, ...)`. V kombinaci s velikostí faktové tabulky může filtrování vyžadovat vyhodnocení rozsáhlého množství řádků. | Pomalejší přepočítávání measures při změně filtrů a delší odezva vizualizací. |
| DAX | Střední | Některé measures opakovaně vyhodnocují stejné náročné dílčí výpočty. | Zbytečně opakovaná výpočetní práce při každém vyhodnocení measures. |
| Power Query | Vysoká | Některé transformace znemožňují Query Folding, takže část transformací nemůže být přenesena ke zpracování do datového zdroje. | Vyšší objem dat zpracovávaný Power Query a pomalejší obnova dat. |
| Power Query | Nízká | Některé dotazy obsahují více po sobě jdoucích změn datových typů. | Dodatečné transformační operace během obnovy dat. |

Samotná absence agregačních tabulek není na základě zadání označena za výkonnostní problém. Nejsou uvedeny používané úrovně agregace ani způsob dotazování, podle kterých by bylo možné jejich přínos spolehlivě posoudit.

## 5. Očekávaný dopad na výkon

- **Interaktivní odezva reportu:** náročné iterace, filtrování rozsáhlé faktové tabulky a opakované dílčí výpočty mohou prodlužovat vyhodnocování measures.
- **Načítání vizualizací:** vizualizace závislé na dotčených measures se mohou načítat pomalu, protože jejich výpočty vyžadují zpracování velkého množství řádků.
- **Změna filtrů:** každá změna filtračního kontextu může vyvolat nové vyhodnocení náročných measures, což odpovídá hlášené pomalé odezvě.
- **Obnova dat:** transformace přerušující Query Folding mohou zvýšit množství dat zpracovávaných Power Query. Opakované změny datových typů přidávají další transformační operace.
- **Velikost modelu:** zadání neobsahuje informace, které by dokládaly konkrétní problém s velikostí modelu. Samotný počet řádků neumožňuje posoudit velikost modelu v paměti.

## 6. Doporučené oblasti optimalizace

- Prověřit a omezit iterace `SUMX` nad celou tabulkou `FactSales`.
- Prověřit measures používající `FILTER(FactSales, ...)` a omezit rozsah řádků, které musí být při filtrování vyhodnocovány.
- Odstranit opakované vyhodnocování stejných náročných dílčích výpočtů v rámci jednotlivých measures.
- Upravit Power Query transformace, které znemožňují Query Folding.
- Sloučit nebo odstranit nadbytečné po sobě jdoucí změny datových typů.

## 7. Celkové hodnocení

**Doporučena významná optimalizace.**
