# Prompt — Power BI 01 - Power Query Transformation Assistant

# Prompt

Jsi senior datový analytik a expert na Microsoft Power Query.

Cílem je navrhnout nejvhodnější transformace dat v Power Query pro řešení úkolu definovaného v zadání.

Na základě dostupných informací navrhni:

- doporučené transformace dat,
- doporučené pořadí transformací, pokud je důležité,
- vhodné datové typy,
- případné odvozené sloupce,
- doporučení pro zvýšení kvality dat.

Pokud některé informace chybí, nejprve uveď předpoklady.

Předpoklady formuluj pouze tehdy, pokud jsou nezbytné pro navržené řešení.

Předpoklady jasně označ a nepovažuj je za skutečnosti vyplývající ze zadání.

Do části **Předpoklady** uváděj pouze informace, které nejsou přímo uvedeny v zadání.

Neuváděj zde skutečnosti, které již vyplývají ze vstupních dat nebo ze známých problémů.

Pokud nejsou pro návrh řešení nutné žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

Nevymýšlej si data, názvy tabulek, sloupců ani strukturu dat, které nejsou uvedeny v zadání.

Pokud zadání výslovně nepožaduje implementaci, zaměř se pouze na návrh transformací.

Nevytvářej M kód ani podrobný implementační návod.

Nepopisuj konkrétní postup implementace transformací, pokud není nezbytný pro pochopení navrženého řešení.

Upřednostňuj jednoduché, přehledné a snadno udržovatelné transformační postupy.

Navrhuj pouze transformace, které přímo vyplývají z poskytnutého zadání.

Nevytvářej konkrétní implementační rozhodnutí, například konkrétní náhradní hodnoty, pokud nejsou výslovně požadována nebo jednoznačně nevyplývají ze zadání.

Na závěr doporuč případné úpravy zdrojových dat, které mohou omezit vznik obdobných problémů v budoucnu.

---

# Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Dodrž následující strukturu:

1. Shrnutí řešení
2. Předpoklady
3. Návrh transformací
4. Doporučené pořadí transformací
5. Doporučené datové typy
6. Doporučené odvozené sloupce
7. Doporučení pro zvýšení kvality dat
8. Doporučení pro úpravu zdrojových dat

Pro návrh transformací použij tabulku:

| Transformace | Důvod |
|--------------|-------|

Pro doporučené datové typy použij tabulku:

| Sloupec | Datový typ | Poznámka |
|---------|-------------|----------|

Pro odvozené sloupce použij tabulku:

| Odvozený sloupec | Účel |
|------------------|------|

Dodrž následující pravidla:

- piš stručně a věcně,
- navrhuj pouze transformace vyplývající ze zadání,
- nevysvětluj obecné principy práce s Power Query,
- nevytvářej M kód,
- nevytvářej implementační manuál,
- nevymýšlej strukturu dat ani business pravidla,
- jasně odděluj fakta od předpokladů,
- neopakuj stejné informace ve více částech.

V části **Návrh transformací** u každé transformace stručně vysvětli její účel.

V části **Doporučené pořadí transformací** uveď pořadí pouze tehdy, pokud má vliv na správnost, kvalitu nebo efektivitu navrženého řešení.

V části **Doporučené datové typy** uváděj pouze datové typy, které lze jednoznačně doporučit na základě zadání.

Pokud některý datový typ nelze jednoznačně určit, uveď tuto skutečnost.

V části **Doporučené odvozené sloupce** navrhuj pouze sloupce, jejichž přínos přímo vyplývá ze zadání.

Pokud nejsou žádné odvozené sloupce potřeba, uveď:

> Nebyly identifikovány žádné nezbytné odvozené sloupce.

V části **Doporučení pro zvýšení kvality dat** uváděj pouze doporučení přímo související se zjištěnými problémy.

V části **Doporučení pro úpravu zdrojových dat** navrhuj pouze změny, které mohou omezit opakování zjištěných problémů v budoucnu.

Výstup by měl odpovídat přibližně rozsahu 1–2 stran textu.

---

# Zadání

Společnost každý měsíc exportuje prodejní data z ERP systému. Data jsou určena pro následný reporting v Power BI, ale export obsahuje nekonzistentní hodnoty a vyžaduje pravidelnou přípravu.

Export obsahuje následující sloupce:

- Datum objednávky
- Číslo objednávky
- Produkt
- Kategorie
- Zákazník
- Region
- Obchodník
- Množství
- Jednotková cena
- Sleva
- Tržby

Známé problémy:

- Chybějící hodnoty ve sloupci **Region**.
- Nekonzistentní názvy kategorií, například „Notebook“, „Notebooky“ a „NTB“.
- Datum je u části záznamů ve formátu **DD.MM.RRRR** a u části ve formátu **YYYY-MM-DD**.
- Ve sloupci **Tržby** jsou některé záporné hodnoty z důvodu dobropisů.
- Některé objednávky jsou v exportu duplicitně.
- Sloupec **Jednotková cena** obsahuje u části záznamů textové hodnoty místo čísel.
- Export obsahuje několik prázdných řádků.

Navrhni nejvhodnější transformace v Power Query, které připraví data pro následné použití v Power BI.

---

# Návrh řešení

## 1. Shrnutí řešení

Doporučené řešení zahrnuje odstranění prázdných řádků, sjednocení dat objednávek, standardizaci názvů kategorií, ošetření chybějících regionů, převod datových typů, kontrolu duplicit a zachování záporných tržeb představujících dobropisy.

Před odstraněním duplicit a nahrazením chybějících či neplatných hodnot je nutné stanovit odpovídající business pravidla. Záporné hodnoty ve sloupci **Tržby** nemají být automaticky opraveny ani odstraněny, protože podle zadání představují platné dobropisy.

## 2. Předpoklady

> Nebyly nutné žádné dodatečné předpoklady.

Zadání však neurčuje:

- podle kterých sloupců se má posuzovat duplicita objednávek,
- zda lze chybějící region odvodit z jiných údajů,
- jak se mají řešit textové hodnoty ve sloupci **Jednotková cena**,
- zda jedna objednávka může obsahovat více produktových řádků.

Tyto skutečnosti je potřeba před konečným nastavením transformací ověřit. Nejsou proto nahrazeny předpoklady.

## 3. Návrh transformací

| Transformace | Důvod |
|--------------|-------|
| Odstranění zcela prázdných řádků | Prázdné řádky nemají pro reporting žádnou informační hodnotu. |
| Sjednocení formátů ve sloupci **Datum objednávky** | Data jsou uvedena ve dvou různých formátech a musí být převedena na jednotný datový typ datum. |
| Standardizace hodnot ve sloupci **Kategorie** | Varianty označující stejnou kategorii, například „Notebook“, „Notebooky“ a „NTB“, musí být sjednoceny podle schváleného číselníku. |
| Ošetření chybějících hodnot ve sloupci **Region** | Chybějící regiony mohou způsobit neúplné regionální přehledy v Power BI. Způsob doplnění musí odpovídat business pravidlu nebo referenčnímu zdroji. |
| Vyčištění sloupce **Jednotková cena** | Textové hodnoty je nutné identifikovat a podle jejich obsahu převést na čísla, opravit ve zdroji nebo označit jako datové chyby. |
| Nastavení datových typů | Správné typy jsou nutné pro výpočty, agregace, filtrování a tvorbu datového modelu. |
| Identifikace a odstranění skutečných duplicit | Duplicity by mohly nadhodnocovat množství a tržby. Odstranění musí vycházet z jednoznačně stanoveného klíče nebo pravidla duplicity. |
| Zachování záporných hodnot ve sloupci **Tržby** | Záporné hodnoty představují dobropisy, a proto jsou platnou součástí prodejních dat. |
| Kontrola chyb po převodu datových typů | Umožní zachytit neplatná data, která nebylo možné převést na požadovaný typ. |

## 4. Doporučené pořadí transformací

1. Odstranit zcela prázdné řádky.
2. Provést základní vyčištění textových hodnot relevantních pro následné transformace.
3. Sjednotit názvy kategorií podle schváleného číselníku.
4. Sjednotit formáty ve sloupci **Datum objednávky**.
5. Vyčistit hodnoty ve sloupci **Jednotková cena**.
6. Nastavit datové typy.
7. Ošetřit chyby vzniklé při převodu datových typů.
8. Vyřešit chybějící hodnoty ve sloupci **Region** podle schváleného pravidla.
9. Identifikovat a odstranit skutečné duplicity podle stanoveného klíče.
10. Provést závěrečnou kontrolu počtu řádků, chybějících hodnot, duplicit a souhrnných tržeb.

Odstranění duplicit je vhodné provést až po standardizaci relevantních hodnot. Formátové rozdíly by jinak mohly zabránit rozpoznání obsahově totožných záznamů.

## 5. Doporučené datové typy

| Sloupec | Datový typ | Poznámka |
|---------|-------------|----------|
| Datum objednávky | Datum | Oba vstupní formáty je nutné převést na jednotný typ. |
| Číslo objednávky | Text | Vhodné pro identifikátor, zejména pokud může obsahovat písmena nebo počáteční nuly. Přesný typ je vhodné ověřit podle ERP. |
| Produkt | Text | Popisná hodnota. |
| Kategorie | Text | Standardizovaná hodnota podle číselníku. |
| Zákazník | Text | Popisná nebo identifikační hodnota; přesnější typ nelze ze zadání určit. |
| Region | Text | Kategorická hodnota používaná pro členění reportů. |
| Obchodník | Text | Popisná hodnota. |
| Množství | Nelze jednoznačně určit | Celé číslo je vhodné pouze tehdy, pokud se produkty neprodávají v desetinných jednotkách. |
| Jednotková cena | Desetinné číslo nebo pevné desetinné číslo | Typ je nutné nastavit až po odstranění či vyřešení textových hodnot. Pro finanční data je vhodné ověřit požadovanou přesnost. |
| Sleva | Nelze jednoznačně určit | Zadání neurčuje, zda je sleva uvedena jako procento, desetinné číslo nebo peněžní částka. |
| Tržby | Desetinné číslo nebo pevné desetinné číslo | Typ musí podporovat kladné i záporné hodnoty. Pro finanční data je vhodné ověřit požadovanou přesnost. |

## 6. Doporučené odvozené sloupce

> Nebyly identifikovány žádné nezbytné odvozené sloupce.

Pro účely kontrolního procesu lze zvážit pomocné příznaky pro chybějící region, neplatnou jednotkovou cenu nebo podezření na duplicitu. Jejich potřeba však přímo nevyplývá z požadavků na výsledný dataset a nemusejí být součástí dat předávaných do Power BI.

## 7. Doporučení pro zvýšení kvality dat

- Použít schválený číselník kategorií a ponechat dohledatelné mapování původních hodnot na standardizované názvy.
- Neodstraňovat objednávky pouze podle shodného **Čísla objednávky**, dokud nebude ověřeno, zda jedna objednávka může obsahovat více produktových řádků.
- Chybějící regiony nedoplňovat odhadem. Pokud je možné region určit podle zákazníka nebo jiného referenčního údaje, použít řízené mapování.
- Textové hodnoty v **Jednotkové ceně** nenahrazovat automaticky nulou, protože by to mohlo zkreslit výpočty.
- Ponechat záporné tržby a samostatně kontrolovat pouze hodnoty, které neodpovídají evidovaným dobropisům.
- Po každém měsíčním načtení kontrolovat počet prázdných řádků, duplicit, chybějících regionů a chyb převodu datových typů.
- Porovnat součet tržeb před transformací a po ní a vysvětlit případné rozdíly způsobené odstraněním skutečných duplicit.

## 8. Doporučení pro úpravu zdrojových dat

- Nastavit v ERP exportu jednotný formát data nezávislý na místním nastavení.
- Exportovat **Jednotkovou cenu**, **Slevu** a **Tržby** vždy jako číselné hodnoty.
- Používat jednotný číselník kategorií již v ERP systému.
- Zajistit povinné vyplnění regionu nebo jeho automatické přiřazení z kmenových dat zákazníka.
- Doplnit do exportu jednoznačný identifikátor řádku objednávky, pokud jedna objednávka může obsahovat více položek.
- Odstranit příčinu vzniku duplicit přímo při generování exportu.
- Zajistit, aby export neobsahoval zcela prázdné řádky.
- Pokud to ERP umožňuje, jednoznačně označit dobropisy typem dokladu, aby nebyly rozpoznávány pouze podle záporné hodnoty tržeb.
