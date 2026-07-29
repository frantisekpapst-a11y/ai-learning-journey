# Prompt 004 — Power Query Transformation Assistant

## Zadání

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
- Nekonzistentní názvy kategorií (např. „Notebook“, „Notebooky“, „NTB“).
- Datum je u části záznamů ve formátu **DD.MM.RRRR** a u části ve formátu **YYYY-MM-DD**.
- Ve sloupci **Tržby** jsou některé záporné hodnoty z důvodu dobropisů.
- Některé objednávky jsou v exportu duplicitně.
- Sloupec **Jednotková cena** obsahuje u části záznamů textové hodnoty místo čísel.
- Export obsahuje několik prázdných řádků.

Navrhni nejvhodnější transformace v Power Query, které připraví data pro následné použití v Power BI.

Zaměř se pouze na transformace potřebné k vyřešení uvedených problémů.

Neřeš způsob implementace jednotlivých transformací ani nenavrhuj konkrétní technické řešení, pokud nevyplývá ze zadání.

Nevytvářej M kód ani detailní implementační postup.

---

# Návrh transformací prodejních dat v Power Query

## 1. Shrnutí řešení

Navržený proces odstraní prázdné řádky, sjednotí textové hodnoty a bezpečně převede datum a číselné údaje na odpovídající datové typy. Následně standardizuje názvy kategorií, ošetří chybějící regiony a odstraní pouze prokazatelné duplicity.

Záporné hodnoty ve sloupci **Tržby** zůstanou zachovány, protože představují dobropisy a mají obchodní význam. Hodnoty, které nelze spolehlivě převést nebo doplnit, budou označeny ke kontrole, aby nedošlo k neúmyslné ztrátě dat.

---

## 2. Předpoklady

- Jedno **Číslo objednávky** se může vyskytovat na více řádcích, pokud objednávka obsahuje více položek. Samotné opakování čísla proto není dostatečným důkazem duplicity.
- Za bezpečně odstranitelné duplicity se považují řádky shodné ve všech uvedených sloupcích.
- Chybějící **Region** nelze spolehlivě odvodit z ostatních dostupných sloupců bez dalšího referenčního zdroje.
- Textové hodnoty ve sloupci **Jednotková cena** mohou obsahovat rozdílné desetinné oddělovače nebo běžné formátovací znaky. Jejich přesná podoba není v zadání uvedena.

---

## 3. Návrh transformací

| Transformace | Důvod |
|---|---|
| Odstranit zcela prázdné řádky | Zabrání načítání záznamů bez obchodního významu. |
| Očistit textová pole od nadbytečných mezer a netisknutelných znaků | Omezí zdánlivé rozdíly mezi jinak shodnými hodnotami. |
| Sjednotit zápis prázdných textových hodnot | Zajistí jednotné rozpoznání chybějících údajů. |
| Převést hodnoty ve sloupci **Datum objednávky** na jednotný datový typ datum | Sjednotí oba uvedené formáty a umožní správné časové vyhodnocování. |
| Převést textové hodnoty ve sloupci **Jednotková cena** na čísla | Umožní použití ceny ve výpočtech a agregacích. |
| Označit neúspěšné převody data a jednotkové ceny | Zabrání skrytému nahrazení chybných hodnot nebo ztrátě záznamů. |
| Standardizovat varianty názvů ve sloupci **Kategorie** | Sloučí například hodnoty „Notebook“, „Notebooky“ a „NTB“ pod jeden schválený název. |
| Ošetřit chybějící hodnoty ve sloupci **Region** jednotným označením | Umožní chybějící regiony zahrnout do reportingu a současně je rozpoznat. |
| Odstranit pouze řádky shodné ve všech uvedených sloupcích | Omezí dvojí započítání prodeje bez odstranění oprávněně opakovaných položek objednávek. |
| Zachovat záporné hodnoty ve sloupci **Tržby** | Dobropisy jsou platné obchodní transakce a nesmějí být automaticky odstraněny ani převedeny na kladné hodnoty. |
| Nastavit konečné datové typy všech sloupců | Zajistí konzistentní načtení dat do Power BI. |

---

## 4. Doporučené pořadí transformací

1. Odstranění zcela prázdných řádků.
2. Očištění textových hodnot a sjednocení zápisu chybějících údajů.
3. Převod sloupce **Datum objednávky** na datum.
4. Převod sloupců **Množství**, **Jednotková cena**, **Sleva** a **Tržby** na odpovídající číselné typy.
5. Označení hodnot, které nebylo možné převést.
6. Standardizace názvů ve sloupci **Kategorie**.
7. Ošetření chybějících hodnot ve sloupci **Region**.
8. Odstranění prokazatelně duplicitních řádků.
9. Kontrola konečných datových typů a kvality výsledných dat.

Pořadí je důležité zejména proto, že očištění textu musí předcházet standardizaci kategorií a bezpečnému převodu textových čísel. Duplicity je vhodné vyhodnotit až po sjednocení hodnot, protože mezery, rozdílné formáty data nebo datové typy mohou bránit rozpoznání jinak totožných řádků.

---

## 5. Doporučené datové typy

| Sloupec | Datový typ | Poznámka |
|---|---|---|
| Datum objednávky | Datum | Oba zdrojové formáty musí být převedeny na jednotnou hodnotu data. |
| Číslo objednávky | Text | Zachová případné počáteční nuly a nečíselné znaky identifikátoru. |
| Produkt | Text | Popisná hodnota. |
| Kategorie | Text | Po standardizaci názvů kategorií. |
| Zákazník | Text | Zachová identifikátor nebo název bez číselné interpretace. |
| Region | Text | Chybějící hodnoty budou jednotně označeny. |
| Obchodník | Text | Popisná hodnota. |
| Množství | Celé číslo | Vhodné, pokud se prodávají pouze celé jednotky; při dílčím množství je vhodné desetinné číslo. |
| Jednotková cena | Pevné desetinné číslo | Vhodné pro peněžní hodnoty a přesné finanční výpočty. |
| Sleva | Desetinné číslo nebo pevné desetinné číslo | Desetinné číslo je vhodné pro sazbu, pevné desetinné číslo pro peněžní částku; význam sloupce není upřesněn. |
| Tržby | Pevné desetinné číslo | Záporné hodnoty zůstanou povoleny kvůli dobropisům. |

---

## 6. Doporučené odvozené sloupce

| Odvozený sloupec | Účel |
|---|---|
| Stav kvality záznamu | Označí řádky s neplatným datem, nepřeveditelnou jednotkovou cenou nebo chybějícím regionem pro následnou kontrolu. |

Další odvozené sloupce nejsou pro řešení uvedených problémů nezbytné. Standardizovaná kategorie a ošetřený region mohou nahradit původní nekonzistentní hodnoty, pokud není nutné uchovávat jejich zdrojovou podobu pro audit.

---

## 7. Doporučení pro zvýšení kvality dat

- Používat schválený seznam kategorií a všechny ostatní varianty označit ke kontrole.
- Chybějící regiony nespojovat automaticky s konkrétním regionem bez důvěryhodného referenčního zdroje.
- Neúspěšné převody data a jednotkové ceny ponechat dohledatelné a zahrnout je do kontroly kvality.
- Před odstraněním duplicit ověřovat shodu celých řádků, nikoliv pouze shodu **Čísla objednávky**.
- Kontrolovat počet odstraněných prázdných a duplicitních řádků a počet chybných převodů při každém měsíčním načtení.
- Záporné **Tržby** nevnímat automaticky jako chybu; kontrolovat pouze neobvyklé hodnoty, které neodpovídají dobropisům.

---

## 8. Doporučení pro úpravu zdrojových dat

- Exportovat **Datum objednávky** vždy v jednom jednoznačném formátu.
- Exportovat **Jednotkovou cenu**, **Slevu**, **Množství** a **Tržby** jako číselné hodnoty bez textových znaků.
- Omezit hodnoty **Kategorie** na jednotný číselník spravovaný v ERP.
- Nastavit **Region** jako povinnou hodnotu nebo jej doplňovat z jednotného číselníku zákazníků.
- Zabránit vzniku zcela prázdných řádků v exportu.
- Doplnit jednoznačný identifikátor položky objednávky, aby bylo možné spolehlivě rozlišit legitimní opakování čísla objednávky od skutečné duplicity.
- Pokud je to možné, doplnit označení typu transakce, například prodej nebo dobropis, aby byly záporné tržby jednoznačně interpretovatelné.
