# Prompt 005- Excel Workbook Reviewer

## Zadání

### Business scénář

Společnost používá excelový sešit pro měsíční reporting obchodních výsledků. Workbook vznikal postupně několik let a podílelo se na něm více autorů. Management zvažuje jeho další rozvoj nebo migraci do Power BI a potřebuje nezávislé odborné posouzení kvality současného řešení.

### Popis workbooku

Workbook obsahuje následující listy:

- Data
- Číselníky
- Výpočty
- Dashboard
- Archiv

#### Data

- import měsíčního exportu z ERP,
- přibližně 120 000 řádků,
- více než 20 sloupců,
- část hodnot je doplňována ručně.

#### Číselníky

- mapování kategorií,
- seznam obchodníků,
- seznam regionů.

#### Výpočty

- několik stovek vzorců,
- časté použití funkcí SVYHLEDAT,
- opakované výpočty ve více sloupcích,
- několik velmi dlouhých vnořených vzorců,
- odkazy mezi listy.

#### Dashboard

- několik kontingenčních tabulek,
- grafy,
- slicery,
- ručně vytvořené KPI,
- podmíněné formátování.

#### Archiv

- historické kopie dat,
- některé listy jsou skryté.

### Známé problémy

- workbook se otevírá několik minut,
- přepočet vzorců je pomalý,
- některé vzorce jsou obtížně pochopitelné,
- část dat je kopírována ručně,
- některé listy obsahují duplicitní informace,
- nejsou popsána pravidla pro údržbu workbooku,
- nový kolega se v řešení obtížně orientuje.

### Cíl

Proveď odbornou revizi workbooku.

Zhodnoť jeho kvalitu z pohledu:

- struktury,
- organizace dat,
- kvality řešení,
- udržovatelnosti,
- výkonu,
- hlavních rizik.

Urči oblasti vhodné ke zlepšení, stanov jejich priority a posuď připravenost workbooku na další rozvoj nebo případnou migraci do Power BI.

Neopravuj workbook.

Nevytvářej nové vzorce ani implementační postupy.

---

# Výstup odborné revize

## 1. Shrnutí hodnocení

Workbook podporuje měsíční reporting obchodních výsledků a obsahuje základní oddělení dat, číselníků, výpočtů a prezentace výsledků. Jeho postupný vývoj více autory však vedl k vysoké složitosti, pomalému zpracování a obtížné údržbě.

Za nejzávažnější nedostatky lze považovat:

- pomalé otevírání a přepočítávání workbooku,
- ruční zásahy do zdrojových dat,
- opakované a obtížně čitelné vzorce,
- duplicitní informace,
- chybějící dokumentaci a pravidla údržby.

Současné řešení je použitelné pro existující reporting, ale jeho další rozšiřování bez předchozí stabilizace by zvyšovalo provozní rizika. Workbook je vhodným kandidátem na optimalizaci a následné posouzení migrace reportingu do Power BI.

## 2. Předpoklady

Pro účely hodnocení jsou použity následující předpoklady:

- měsíční export z ERP má opakující se strukturu,
- workbook je pravidelně aktualizován a používán pro manažerský reporting,
- ručně vytvořené KPI jsou alespoň částečně závislé na manuálních zásazích,
- skryté listy v archivu mohou obsahovat data nebo výpočty důležité pro fungování workbooku.

Tyto předpoklady nejsou skutečnostmi potvrzenými zadáním a před případnými změnami by měly být ověřeny.

## 3. Silné stránky workbooku

- **Základní funkční členění:** Samostatné listy pro data, číselníky, výpočty, dashboard a archiv vytvářejí základ pro logické oddělení jednotlivých částí řešení.
- **Centralizované číselníky:** Mapování kategorií, obchodníků a regionů snižuje potřebu zadávat stejné informace na více místech.
- **Existující manažerská prezentace:** Dashboard kombinuje kontingenční tabulky, grafy, slicery, KPI a podmíněné formátování, takže poskytuje uživatelům interaktivní pohled na výsledky.
- **Historická data:** Archiv umožňuje uchovávat předchozí období a podporuje dlouhodobé porovnávání výsledků.
- **Zachycení business požadavků:** Několikaletý vývoj workbooku pravděpodobně odráží významnou část současných reportingových potřeb společnosti.

## 4. Identifikované problémy

### Struktura a organizace dat

- **Ruční doplňování a kopírování dat:** Manuální zásahy narušují jednotnost datového procesu a zvyšují pravděpodobnost chyb, opomenutí nebo rozdílného postupu mezi jednotlivými obdobími.
- **Duplicitní informace:** Stejná data uložená na více místech mohou vést k rozdílným hodnotám a nejasnostem, která verze je správná.
- **Historické kopie uvnitř workbooku:** Archiv zvyšuje velikost souboru a může přispívat k dlouhému otevírání, ukládání a celkově horšímu výkonu.
- **Skryté listy:** Pokud nejsou popsány jejich účel a vazby, snižují transparentnost řešení a mohou obsahovat obtížně dohledatelné závislosti.

### Kvalita výpočtů

- **Několik stovek vzorců:** Vysoký počet vzorců zvyšuje složitost kontroly, údržby a ověřování správnosti výsledků.
- **Opakované výpočty:** Stejná nebo podobná logika ve více sloupcích vytváří duplicitu a zvyšuje výpočetní zátěž.
- **Dlouhé vnořené vzorce:** Obtížně se čtou, testují a upravují. Zvyšují riziko, že změna části logiky způsobí nečekané chyby.
- **Časté použití funkce SVYHLEDAT:** Při velkém objemu dat a vysokém počtu opakovaných vyhledávání může přispívat k pomalému přepočtu.
- **Odkazy mezi listy:** Vytvářejí závislosti, které mohou být bez dokumentace obtížně dohledatelné a kontrolovatelné.

### Přehlednost a udržovatelnost

- **Chybějící pravidla údržby:** Není jasně stanoveno, kdo workbook spravuje, jak se aktualizuje a jak se kontrolují změny.
- **Obtížná orientace nového kolegy:** Řešení je závislé na znalostech stávajících uživatelů a není dostatečně srozumitelné bez předchozího zaškolení.
- **Více autorů bez jednotného standardu:** Rozdílné způsoby práce mohly vést k nekonzistentním názvům, vzorcům a vazbám.
- **Ručně vytvářené KPI:** Pokud nejsou definice KPI popsány a jednotně spravovány, může být obtížné ověřit jejich správnost a konzistenci.

### Výkon

- **Několikaminutové otevírání:** Výrazně omezuje efektivitu pravidelného reportingu a signalizuje vysokou technickou zátěž workbooku.
- **Pomalý přepočet:** Zpomaluje aktualizace a kontrolu výsledků a zvyšuje riziko práce s neaktuálními hodnotami.
- **Kombinace velkého objemu dat, archivu a vzorců:** Přibližně 120 000 řádků, stovky vzorců, kontingenční tabulky a historické kopie společně vytvářejí významnou výkonnostní zátěž.

## 5. Rizika

- **Riziko nesprávného reportingu:** Ruční zásahy, duplicity a složité vzorce mohou způsobit chyby v údajích předkládaných managementu.
- **Provozní závislost na konkrétních osobách:** Chybějící dokumentace omezuje možnost bezpečného zastupování a předávání workbooku.
- **Riziko nekonzistentních KPI:** Nezdokumentované definice mohou vést k rozdílnému výkladu obchodních výsledků.
- **Riziko neřízených změn:** Úprava jednoho vzorce nebo listu může ovlivnit další části řešení bez okamžitého odhalení.
- **Riziko dalšího poklesu výkonu:** Přidávání dat, výpočtů a vizualizací může vést k další degradaci rychlosti a stability.
- **Riziko komplikované migrace:** Nejasné vazby, ruční procesy a skryté části workbooku mohou ztížit převod řešení do Power BI.

## 6. Doporučené oblasti ke zlepšení

- Stabilizace procesu načítání a doplňování zdrojových dat.
- Omezení ručních zásahů do dat používaných pro reporting.
- Prověření duplicitních informací a historických kopií.
- Revize výpočetní logiky, zejména opakovaných a dlouhých vnořených vzorců.
- Zmapování vazeb mezi listy, výpočty, KPI a výstupy dashboardu.
- Jednoznačné vymezení účelu skrytých listů a archivních částí.
- Zavedení dokumentace, pravidel aktualizace a odpovědnosti za údržbu.
- Sjednocení a dokumentace definic KPI.
- Samostatné posouzení, které části mají zůstat v Excelu a které jsou vhodné pro případnou migraci do Power BI.

## 7. Priority doporučených oblastí

| Priorita | Oblast | Očekávaný business přínos |
|---|---|---|
| 1 – kritická | Kvalita a způsob aktualizace dat | Omezení chyb v manažerském reportingu a zvýšení důvěryhodnosti výsledků |
| 2 – vysoká | Výkon workbooku | Zrychlení měsíčního reportingu a snížení času potřebného k aktualizaci |
| 3 – vysoká | Revize výpočtů a vazeb | Snížení rizika chybných výsledků a bezpečnější provádění změn |
| 4 – vysoká | Dokumentace a pravidla údržby | Omezení závislosti na konkrétních osobách a snazší předávání řešení |
| 5 – střední | Odstranění duplicit a prověření archivu | Zjednodušení struktury a snížení velikosti a složitosti workbooku |
| 6 – střední | Standardizace KPI | Konzistentní interpretace obchodních výsledků |
| 7 – navazující | Posouzení migrace do Power BI | Dlouhodobě udržitelnější a lépe škálovatelný reporting |

## 8. Připravenost workbooku na další rozvoj

Workbook není v současném stavu dobře připraven na další rozsáhlejší rozvoj. Přidávání dalších dat, vzorců nebo dashboardových prvků by pravděpodobně dále zhoršovalo výkon a udržovatelnost.

Pro migraci do Power BI představuje workbook užitečný zdroj business požadavků, definic reportů a historických výstupů. Není však vhodné převést jeho současnou logiku bez předchozí revize. Nejdříve je potřeba zmapovat datové zdroje, ruční zásahy, výpočty, KPI a závislosti mezi jednotlivými částmi.

## 9. Celkové zhodnocení

Workbook plní svou současnou reportingovou funkci, ale vykazuje znaky dlouhodobě rozšiřovaného řešení bez jednotné architektury a pravidel správy. Největší slabiny představují ruční práce s daty, složitá výpočetní logika, nízká transparentnost a nedostatečný výkon.

Další rozvoj v Excelu je možný až po stabilizaci a zjednodušení řešení. Migrace do Power BI může být vhodným dlouhodobým směrem, měla by však navazovat na odborné zmapování a sjednocení současného reportingového procesu.
