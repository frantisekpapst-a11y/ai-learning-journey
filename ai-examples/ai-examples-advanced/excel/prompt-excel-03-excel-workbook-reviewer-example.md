# Prompt - Excel 03 - Excel Workbook Reviewer

# Prompt

Jsi senior datový analytik a expert na Microsoft Excel.

Cílem je provést odbornou revizi existujícího excelového workbooku podle zadaných informací.

Na základě dostupných informací posuď:

- strukturu workbooku,
- organizaci dat,
- kvalitu použitých vzorců,
- přehlednost řešení,
- udržovatelnost,
- potenciální výkonnostní problémy,
- hlavní rizika.

U každého zjištění stručně vysvětli jeho dopad na používání nebo další rozvoj workbooku.

Pokud některé informace chybí, nejprve uveď předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro provedení hodnocení. Jasně je označ a nepovažuj je za skutečnosti vyplývající ze zadání.

Do části **Předpoklady** neuváděj pouze seznam informací, které nejsou k dispozici.

Pokud nejsou pro hodnocení nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej data, listy, tabulky, vzorce ani strukturu workbooku, které nejsou uvedeny v zadání.

Pokud zadání výslovně nepožaduje opravu workbooku, zaměř se pouze na odborné hodnocení existujícího řešení.

Identifikuj zjištění a vysvětli jejich dopady.

Nenavrhuj konkrétní technické implementace ani náhrady použitých funkcí, pokud to zadání výslovně nepožaduje.

Nevytvářej nové vzorce, dashboardy ani implementační návody.

Silné stránky workbooku uváděj pouze tehdy, pokud přímo vyplývají z poskytnutých informací.

Nevytvářej pravděpodobné přínosy ani interpretace, které nejsou podloženy vstupem.

Na závěr stanov priority doporučených oblastí ke zlepšení podle jejich očekávaného business přínosu.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Dodrž následující strukturu:

1. Shrnutí hodnocení
2. Předpoklady
3. Silné stránky workbooku
4. Identifikované problémy
5. Rizika
6. Doporučené oblasti ke zlepšení
7. Priority doporučených oblastí
8. Připravenost workbooku na další rozvoj
9. Celkové zhodnocení

Dodrž následující pravidla:

- piš stručně a věcně,
- nevysvětluj obecné principy práce s Excelem,
- nevytvářej implementační manuál,
- neopravuj workbook,
- nevyjadřuj celkovou kvalitu číselným skóre,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více částech,
- celkové zhodnocení formuluj slovně.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

## Business scénář

Společnost používá excelový workbook pro měsíční reporting obchodních výsledků.

Workbook vznikal postupně několik let a podílelo se na něm více autorů.

Management zvažuje jeho další rozvoj nebo migraci do Power BI a potřebuje nezávislé odborné posouzení kvality současného řešení.

---

## Popis workbooku

Workbook obsahuje následující listy:

- Data
- Číselníky
- Výpočty
- Dashboard
- Archiv

### Data

- import měsíčního exportu z ERP,
- přibližně 120 000 řádků,
- více než 20 sloupců,
- část hodnot je doplňována ručně.

### Číselníky

- mapování kategorií,
- seznam obchodníků,
- seznam regionů.

### Výpočty

- několik stovek vzorců,
- časté použití funkcí SVYHLEDAT,
- opakované výpočty ve více sloupcích,
- několik velmi dlouhých vnořených vzorců,
- odkazy mezi listy.

### Dashboard

- několik kontingenčních tabulek,
- grafy,
- slicery,
- ručně vytvořené KPI,
- podmíněné formátování.

### Archiv

- historické kopie dat,
- některé listy jsou skryté.

---

## Známé problémy

- workbook se otevírá několik minut,
- přepočet vzorců je pomalý,
- některé vzorce jsou obtížně pochopitelné,
- část dat je kopírována ručně,
- některé listy obsahují duplicitní informace,
- nejsou popsána pravidla pro údržbu workbooku,
- nový kolega se v řešení obtížně orientuje.

---

## Cíl

Proveď odbornou revizi workbooku.

Zhodnoť jeho kvalitu z pohledu:

- struktury,
- organizace dat,
- kvality řešení,
- udržovatelnosti,
- výkonu,
- hlavních rizik.

Urči oblasti vhodné ke zlepšení, stanov jejich priority a posuď připravenost workbooku na další rozvoj nebo případnou migraci do Power BI.

---

# Návrh výstupu

## 1. Shrnutí hodnocení

Workbook podporuje měsíční reporting obchodních výsledků a obsahuje oddělené oblasti pro data, číselníky, výpočty, prezentaci výsledků a archivaci. Jeho základní členění tedy odpovídá jednotlivým fázím reportingového procesu.

Postupný vývoj více autory však vedl k vyšší složitosti, duplicitám, obtížné orientaci a absenci pravidel údržby. Kombinace velkého objemu dat, několika stovek vzorců, opakovaných výpočtů, mezilistových odkazů a dlouhých vnořených vzorců způsobuje výkonnostní i provozní problémy.

Workbook je použitelný pro současný reporting, ale jeho další rozvoj bez předchozího zjednodušení a stabilizace by zvyšoval náklady na údržbu a riziko chyb. Pro případnou migraci do Power BI představuje použitelný výchozí zdroj, není však připraven k přímému převodu bez předchozího posouzení dat, výpočtů a reportingových pravidel.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

## 3. Silné stránky workbooku

- **Funkční rozdělení do samostatných listů:** Data, číselníky, výpočty, dashboard a archiv jsou vedeny odděleně. Toto členění vytváří základ pro rozlišení zdrojových dat, výpočtové logiky a prezentace výsledků.
- **Centralizované číselníky:** Mapování kategorií, obchodníků a regionů je soustředěno na samostatném listu.
- **Existující manažerská prezentace:** Dashboard obsahuje kontingenční tabulky, grafy, slicery, KPI a podmíněné formátování.
- **Dostupnost historických dat:** Archiv obsahuje historické kopie dat, které mohou být podkladem pro časová porovnání a posouzení požadavků na migraci.

## 4. Identifikované problémy

### Struktura a organizace dat

- **Ruční doplňování a kopírování dat:** Část hodnot v datové oblasti je doplňována ručně a část dat se ručně kopíruje. Dopadem je vyšší pravděpodobnost chyb, neúplnosti a nekonzistentního měsíčního zpracování.
- **Duplicitní informace:** Některé listy obsahují stejné nebo překrývající se informace. To komplikuje určení správného zdroje a může vést k rozdílným výsledkům v jednotlivých částech workbooku.
- **Nejasná archivní struktura:** Archiv obsahuje historické kopie dat a některé listy jsou skryté. Bez popsaných pravidel není zřejmé, které části jsou aktivní, historické nebo stále potřebné.

### Kvalita výpočtového řešení

- **Opakované výpočty:** Stejné nebo obdobné výpočty jsou prováděny ve více sloupcích. Dopadem je zbytečná výpočetní zátěž a složitější údržba při změně logiky.
- **Dlouhé vnořené vzorce:** Některé vzorce jsou obtížně pochopitelné. To omezuje možnost jejich bezpečné kontroly, úpravy a předání dalším pracovníkům.
- **Rozsáhlé použití vyhledávacích funkcí:** Časté používání funkce SVYHLEDAT v kombinaci s velkým objemem dat může přispívat k pomalému přepočtu.
- **Odkazy mezi listy:** Propojení výpočtů napříč listy zvyšuje závislost jednotlivých částí workbooku a komplikuje dohledání původu výsledků.
- **Ručně vytvořené KPI:** Manuálně sestavené ukazatele mohou být obtížně kontrolovatelné, zejména pokud nejsou popsány jejich definice a vazby na zdrojová data.

### Přehlednost a udržovatelnost

- **Chybějící pravidla údržby:** Není popsán postup aktualizace, odpovědnosti ani pravidla pro provádění změn. Výsledkem je závislost na znalostech stávajících uživatelů.
- **Obtížná orientace:** Nový pracovník se v řešení obtížně orientuje. To prodlužuje zaučení a zvyšuje riziko nesprávného zásahu.
- **Vývoj více autory:** Dlouhodobé úpravy různými pracovníky přispěly k vyšší složitosti a obtížnější správě řešení.

### Výkon

- **Dlouhé otevírání:** Několikaminutová doba otevření omezuje operativní použití reportu.
- **Pomalý přepočet:** Velký počet vzorců, opakované výpočty a rozsáhlá data snižují rychlost aktualizace.
- **Kombinace dat, výpočtů, vizualizací a archivu:** Soustředění všech těchto oblastí v jednom workbooku zvyšuje jeho velikost a celkové nároky na zpracování.

## 5. Rizika

- **Riziko nesprávných výsledků:** Ruční zásahy, duplicity a složité vzorce zvyšují pravděpodobnost chyb, které nemusí být snadno odhalitelné.
- **Riziko nekonzistentního reportingu:** Duplicitní informace a nepopsané definice KPI mohou vést k rozdílnému výkladu stejných ukazatelů.
- **Provozní závislost na konkrétních osobách:** Absence dokumentace a obtížná orientace ohrožují kontinuitu reportingu při změně pracovníků.
- **Riziko neřízených změn:** Úprava jednoho vzorce nebo listu může prostřednictvím mezilistových odkazů ovlivnit další části řešení.
- **Riziko dalšího poklesu výkonu:** Přidávání dalších dat, výpočtů a historických kopií může prodlužovat otevírání i přepočet.
- **Riziko komplikované migrace:** Pokud nejsou jednoznačně vymezeny zdroje dat, výpočtová pravidla a definice KPI, může při migraci do Power BI dojít k přenosu existujících problémů nebo ke vzniku rozdílů ve výsledcích.

## 6. Doporučené oblasti ke zlepšení

- Omezit ruční vstupy a ruční kopírování dat v pravidelném reportovacím procesu.
- Odstranit nebo jednoznačně vymezit duplicitní informace a určit závazné zdroje dat.
- Zjednodušit a sjednotit výpočtovou logiku, zejména opakované a obtížně čitelné výpočty.
- Popsat definice KPI, vazby mezi listy a pravidla aktualizace.
- Stanovit odpovědnosti za správu, kontrolu a schvalování změn.
- Prověřit potřebnost historických a skrytých listů a vymezit účel archivu.
- Oddělit požadavky na stabilizaci současného workbooku od požadavků na jeho další rozvoj.
- Před migrací do Power BI identifikovat zdrojová data, výpočtová pravidla, klíčové ukazatele a očekávané výstupy.

## 7. Priority doporučených oblastí

| Priorita | Oblast | Očekávaný business přínos |
|---|---|---|
| Kritická | Omezení ručních zásahů a ověření správnosti dat | Snížení rizika chybných manažerských výstupů |
| Vysoká | Sjednocení zdrojů a odstranění duplicit | Vyšší konzistence reportingu a důvěryhodnost výsledků |
| Vysoká | Zjednodušení výpočtové logiky | Rychlejší zpracování a bezpečnější údržba |
| Vysoká | Dokumentace KPI, aktualizace a odpovědností | Omezení závislosti na konkrétních pracovnících |
| Střední | Prověření archivu a skrytých listů | Lepší přehlednost a nižší provozní složitost |
| Střední | Příprava podkladů pro Power BI | Snížení rizik a nákladů případné migrace |

## 8. Připravenost workbooku na další rozvoj

Workbook není v současném stavu vhodný pro rozsáhlejší rozvoj bez předchozí stabilizace. Přidávání dalších dat, vzorců nebo vizualizací by mohlo prohloubit problémy s výkonem, přehledností a údržbou.

Pro migraci do Power BI má workbook částečnou připravenost: obsahuje zdrojová data, číselníky, výpočty, historické údaje a definované reportingové výstupy. Nejprve je však nutné vyjasnit spolehlivost dat, odstranit duplicity, popsat výpočtová pravidla a ověřit definice KPI.

Migrace by proto měla být chápána jako řízený převod datové a business logiky, nikoliv jako přímé převedení současného workbooku.

## 9. Celkové zhodnocení

Workbook plní svou současnou reportingovou funkci, ale vykazuje známky dlouhodobě rozvíjeného řešení bez jednotných pravidel správy. Jeho hlavní slabiny spočívají v ručních zásazích, duplicitách, složité výpočtové logice, nízkém výkonu a závislosti na znalostech konkrétních uživatelů.

Největší business přínos přinese nejprve zvýšení spolehlivosti dat a konzistence výsledků, následované zjednodušením výpočtů a zavedením jasných pravidel údržby. Teprve poté lze bezpečně rozhodnout o dalším rozvoji v Excelu nebo o migraci do Power BI.
