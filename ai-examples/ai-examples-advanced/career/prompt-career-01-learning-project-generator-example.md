# Prompt — Career 01 - Learning Project Generator

## Prompt

Jsi senior datový analytik, business intelligence konzultant a mentor datové analýzy.

Tvým úkolem je vytvořit realistické zadání learning projektu určeného pro samostatné studium nebo portfolio datového analytika.

Learning Project simuluje skutečný business projekt. Má rozvíjet analytické myšlení, propojit vhodné technologie a vést uživatele analytickým procesem od business zadání až po prezentaci výsledků.

Projekt musí odpovídat úrovni, rozsahu a požadavkům uvedeným ve vstupu.

Zadání uživatele má přednost před obecnými pravidly promptu při určení:

- rozsahu projektu,
- použitých technologií,
- obtížnosti,
- business oblasti,
- požadovaných výstupů,
- časového rozsahu,
- hloubky analýzy.

Nepřidávej další části projektu pouze proto, aby projekt působil komplexněji.

---

## Režimy práce

Nejprve urči režim podle obsahu vstupu.

### Režim A — Nový projekt

Použij, pokud uživatel požaduje vytvoření nového learning projektu.

Vytvoř kompletní zadání projektu podle uvedených požadavků.

### Režim B — Rozšíření projektu

Použij, pokud vstup obsahuje existující projekt a uživatel požaduje jeho rozšíření, doplnění nebo zvýšení obtížnosti.

Rozšiř pouze existující projekt.

Nevytvářej nový projekt.

Zachovej původní business scénář, pokud uživatel výslovně nepožaduje jeho změnu.

### Režim C — Studijní cesta

Použij, pokud uživatel požaduje sérii navazujících projektů.

Navrhni logickou posloupnost projektů.

Každý další projekt musí navazovat na předchozí a rozvíjet nové dovednosti.

Nevytvářej studijní cestu, pokud uživatel požaduje pouze jeden samostatný projekt.

---

## Práce s předpoklady

Pokud některé informace chybí a jsou nezbytné pro vytvoření projektu, uveď je jako předpoklady.

Předpoklady používej pouze tehdy, pokud jsou skutečně nezbytné.

Nevydávej předpoklady za skutečnosti uvedené v zadání.

Pokud nejsou potřeba žádné předpoklady, uveď:

> Nebyly nutné žádné dodatečné předpoklady.

---

## Obecná pravidla

Projekt musí představovat realistický business scénář.

Nevytvářej:

- umělé školní příklady,
- izolovaná technická cvičení,
- úkoly bez business kontextu,
- technické úkoly bez vazby na business problém.

Business scénář má být hlavním výchozím bodem projektu.

Použité technologie představují prostředek k řešení business problému, nikoli cíl projektu.

Rozsah projektu určuj podle zadání.

Pokud business scénář vyžaduje jednodušší řešení, zachovej odpovídající rozsah.

U komplexnějšího zadání může projekt zahrnovat více:

- datových zdrojů,
- technologií,
- analytických oblastí,
- požadovaných výstupů.

Nevytvářej:

- řešení projektu,
- analytické výsledky,
- nové business závěry,
- SQL dotazy,
- M kód,
- DAX výrazy,
- Python skripty,
- hotový dashboard,
- hotový Executive Summary,
- hotový Insight Report.

Úkolem je vytvořit zadání projektu, nikoli projekt vyřešit.

---

## Obtížnost

Pokud není obtížnost zadána, použij úroveň Junior.

Podporované úrovně:

- Beginner
- Junior
- Junior+
- Mid

Obtížnost ovlivňuje zejména:

- rozsah dat,
- počet business otázek,
- počet použitých technologií,
- komplexnost business problému,
- očekávanou míru samostatnosti,
- počet požadovaných výstupů.

Pokud uživatel obtížnost uvede, respektuj ji.

---

## Typ projektu

Projekt může být zaměřen například na:

- Sales Analytics,
- Customer Analytics,
- Marketing Analytics,
- Finance Analytics,
- HR Analytics,
- Operations Analytics,
- Supply Chain Analytics,
- Product Analytics,
- Executive Reporting,
- Dashboard Project,
- End-to-End Analytics Project.

Pokud typ není zadán, zvol nejvhodnější podle business scénáře.

---

## Business scénář

Business scénář musí obsahovat:

- stručné představení společnosti nebo organizace,
- obor,
- business kontext,
- business problém,
- proč je problém důležitý,
- co management potřebuje zjistit.

Nevytvářej konkrétní příčiny problému, pokud nejsou uvedeny v zadání.

Business scénář formuluj stručně a realisticky.

---

## Business cíl

Popiš:

- hlavní cíl projektu,
- analytický přínos,
- hlavní rozhodnutí, která mají být podpořena analýzou.

Nevytvářej konkrétní analytické závěry.

---

## Doporučené datasety

Pokud existuje vhodný veřejně dostupný dataset, uveď jej v samostatné sekci **Doporučené datasety**.

U každého datasetu uveď:

- přesný název,
- poskytovatele,
- oficiální zdrojovou stránku, pokud ji lze spolehlivě ověřit,
- stručný popis,
- proč je pro projekt vhodný,
- známá omezení pro daný projekt,
- případné části zadání, které dataset nepokrývá.

Preferuj zejména důvěryhodné veřejné zdroje, například:

- Microsoft Learn,
- Maven Analytics,
- Kaggle,
- UCI Machine Learning Repository,
- Data.gov,
- data.europa.eu,
- jiné známé veřejné nebo institucionální zdroje.

Nevydávej předpokládanou strukturu datasetu za ověřenou skutečnost.

Pokud aktuální dostupnost, přesnou strukturu nebo oficiální zdrojovou stránku nelze spolehlivě ověřit, označ dataset jako:

> Kandidát k ověření.

Pokud žádný jednotlivý veřejný dataset nepokrývá celé zadání, jednoznačně uveď:

- které části projektu pokrývá,
- která data chybějí,
- zda je vhodné zúžit projekt,
- zda lze propojit více veřejných zdrojů,
- zda je potřeba vytvořit transparentně popsaný syntetický doplněk.

Nevytvářej neexistující datasety ani neověřené odkazy.

Pokud vhodný veřejný dataset nelze doporučit, uveď tuto skutečnost a navrhni pouze potřebnou strukturu dat.

---

## Popis datasetu

Pokud není dataset předem určen, navrhni realistickou datovou strukturu.

Uveď podle potřeby:

- hlavní tabulky,
- hlavní sloupce,
- vztahy mezi tabulkami,
- očekávanou velikost datasetu,
- běžné problémy kvality dat,
- možné datové zdroje.

Nevytvářej zbytečně komplikovaný datový model.

Pokud doporučuješ existující dataset, jasně rozlišuj mezi:

- skutečně ověřenou strukturou datasetu,
- předpokládanou strukturou,
- strukturou, kterou by bylo potřeba doplnit.

---

## Zadání projektu

Formuluj konkrétní analytické úkoly.

Projekt může podle zadání zahrnovat například:

- kontrolu kvality dat,
- data cleaning,
- SQL,
- Power Query,
- datový model,
- Power BI,
- DAX,
- Python,
- EDA,
- statistickou analýzu,
- vizualizaci,
- Insight Report,
- Executive Summary,
- Data Storytelling,
- dokumentaci projektu.

Používej pouze technologie a výstupy, které odpovídají business scénáři a zadání uživatele.

Nevytvářej řešení jednotlivých úkolů.

---

## Business otázky

Formuluj otázky, na které má analytik během projektu odpovědět.

Otázky musí být:

- business orientované,
- jednoznačné,
- odpovídající dostupným nebo požadovaným datům,
- přiměřené obtížnosti projektu.

Nevytvářej technické úkoly typu:

> Napiš SQL dotaz.

Technické požadavky uveď v části Zadání projektu nebo Doporučené technologie.

---

## Důležité metriky

Uveď hlavní KPI a metriky potřebné pro projekt.

Nevytvářej metriky, které nelze vypočítat z navržených nebo dostupných dat.

Pokud je výpočet metriky podmíněn dostupností konkrétního údaje, tuto podmínku uveď.

---

## Hlavní analytické dimenze

Vyjmenuj dimenze potřebné pro analýzu.

Použij pouze dimenze odpovídající business scénáři a dostupným datům.

---

## Doporučené technologie

Doporuč pouze technologie, které mají pro projekt skutečný přínos.

Ke každé stručně uveď její účel.

Nepřidávej nástroj pouze proto, aby projekt působil rozsáhleji.

Pokud uživatel požadované technologie uvede, respektuj je, pokud nejsou v přímém rozporu s business cílem.

Pokud některá požadovaná technologie nepřináší samostatnou hodnotu, tuto skutečnost stručně uveď a případně ji zařaď jako volitelné rozšíření.

---

## Požadované výstupy

Vyjmenuj artefakty, které mají být součástí dokončeného projektu.

Mohou zahrnovat například:

- dokumentované business zadání,
- Data Quality Report,
- SQL skripty,
- Power Query transformace,
- datový model,
- DAX measures,
- Python notebook,
- Power BI report,
- Insight Report,
- Executive Summary,
- Data Storytelling Plan,
- prezentaci výsledků,
- README,
- dokumentaci projektu.

Uváděj pouze relevantní výstupy.

Seřaď je podle logického workflow projektu.

---

## Hodnocené dovednosti

Vyjmenuj hlavní kompetence, které projekt rozvíjí.

Zahrň pouze dovednosti, které projekt skutečně vyžaduje.

---

## Kritéria úspěšného dokončení

Popiš, podle čeho lze poznat kvalitně dokončený projekt.

Zaměř se zejména na:

- analytickou správnost,
- business správnost,
- kvalitu dat,
- správnost výpočtů,
- konzistenci výstupů,
- interpretaci výsledků,
- dokumentaci,
- reprodukovatelnost,
- kvalitu prezentace.

Nevytvářej bodový systém ani řešení projektu.

---

## Jak by projekt hodnotil recruiter

Stručně popiš:

- co bude recruiter nebo hiring manager pravděpodobně sledovat,
- které části projektu mají největší váhu,
- jaké chyby jsou časté,
- co odlišuje průměrné zpracování od velmi kvalitního portfolia.

Nevytvářej ideální řešení projektu.

---

## Odhadovaný čas dokončení

Uveď realistický odhad času.

Rozsah určuj podle skutečné složitosti zadání.

Pokud je projekt určen pro člověka, který se technologie současně učí, můžeš uvést samostatně:

- odhad pro uživatele, který nástroje již ovládá,
- odhad pro uživatele, který se je během projektu učí.

Nevytvářej nepřiměřeně přesný odhad.

---

## Co si student odnese

Stručně popiš:

- hlavní získané zkušenosti,
- praktické dovednosti,
- business kompetence,
- přínos projektu pro portfolio.

Nehodnoť konkrétního studenta.

---

## Možná rozšíření projektu

Navrhni několik možností dalšího rozvoje projektu.

Rozšíření musí:

- přirozeně navazovat na základní zadání,
- být oddělena od povinného rozsahu,
- nezvyšovat automaticky základní obtížnost projektu,
- nepředstavovat hotové řešení.

---

## Požadavky na výstup

Výstup připrav jako přehledný Markdown dokument.

Použij přesně tuto strukturu:

# Learning Project

## Název projektu

## Obtížnost

## Typ projektu

## Předpoklady

## Business scénář

## Business cíl

## Doporučené datasety

## Popis datasetu

## Zadání projektu

## Business otázky

## Důležité metriky

## Hlavní analytické dimenze

## Doporučené technologie

## Požadované výstupy

## Hodnocené dovednosti

## Kritéria úspěšného dokončení

## Jak by projekt hodnotil recruiter

## Odhadovaný čas dokončení

## Co si student odnese

## Možná rozšíření projektu

---

Dodrž následující pravidla:

- piš stručně a věcně,
- zachovávej realistický business kontext,
- respektuj rozsah a požadavky zadání,
- nepřidávej zbytečné technologie,
- nevytvářej řešení projektu,
- nevytvářej analytické závěry,
- nevytvářej ukázkový kód,
- nevytvářej hotový dashboard,
- nepřidávej technické implementační detaily nad rámec zadání,
- jasně odděluj povinný rozsah od možných rozšíření,
- zachovávej konzistentní terminologii,
- připrav výstup jako profesionální zadání vhodné pro portfolio datového analytika.

---

# Zadání

Vytvoř nový learning projekt s následujícími parametry:

- oblast: **Sales Analytics**,
- obtížnost: **Junior+**,
- typ projektu: **End-to-End Analytics Project**,
- společnost: **ElectroRetail CZ**.

Společnost ElectroRetail CZ zaznamenala ve druhém pololetí roku 2024 pokles obchodních výsledků oproti prvnímu pololetí.

Management potřebuje:

- vyhodnotit rozsah změny,
- určit oblasti s největším příspěvkem k poklesu,
- porovnat produktové kategorie, prodejní kanály, regiony a zákaznické segmenty,
- připravit podklady pro další rozhodování.

Projekt má být vhodný jako rozsáhlejší portfolio projekt juniorního datového analytika.

Preferované technologie:

- SQL,
- Power Query,
- Power BI,
- DAX.

Python může být použit pouze tehdy, pokud přinese samostatnou analytickou hodnotu; jinak má být uveden pouze jako možné rozšíření.

Pokud existují vhodné veřejné datasety, doporuč je a uveď jejich omezení pro tento projekt.

---

# Výstup

# Learning Project

## Název projektu

**Analýza poklesu obchodních výsledků společnosti ElectroRetail CZ ve druhém pololetí roku 2024**

## Obtížnost

**Junior+**

Projekt vyžaduje propojení několika datových tabulek, kontrolu kvality dat, vytvoření jednoduchého hvězdicového datového modelu a porovnání obchodních výsledků mezi prvním a druhým pololetím.

Student má samostatně interpretovat výsledky v business kontextu. Zjištěné rozdíly však nesmí bez dalších důkazů označovat za příčiny poklesu.

## Typ projektu

**End-to-End Analytics Project — Sales Analytics**

Projekt pokrývá analytický proces od přípravy dat přes analýzu obchodních výsledků až po vytvoření reportu a podkladů pro management.

## Předpoklady

- Obchodními výsledky se rozumějí především tržby, počet prodaných kusů, počet objednávek a průměrná hodnota objednávky.
- Analýza porovnává období leden–červen 2024 a červenec–prosinec 2024.
- Jedna objednávka může obsahovat více produktových položek.
- Prodej probíhá prostřednictvím kamenných prodejen a online kanálu.
- Zákaznický segment je dostupný ve zdrojových datech nebo jej lze odvodit podle předem definovaných a dokumentovaných pravidel.
- Údaje o nákladech a marži nejsou součástí povinného rozsahu, pokud je vybraný dataset neobsahuje.
- Veřejný dataset bude použit jako základ projektu a transparentně přizpůsoben fiktivnímu scénáři ElectroRetail CZ.

## Business scénář

ElectroRetail CZ je maloobchodní společnost prodávající spotřební elektroniku prostřednictvím kamenných prodejen a online kanálu.

Ve druhém pololetí roku 2024 zaznamenala pokles obchodních výsledků oproti prvnímu pololetí. Management zatím nezná rozsah změny ani oblasti, které se na celkovém poklesu podílely nejvíce.

Pokles může mít rozdílný průběh mezi produktovými kategoriemi, prodejními kanály, regiony a zákaznickými segmenty. Tyto rozdíly je potřeba objektivně vyhodnotit před rozhodováním o dalších obchodních opatřeních.

Management potřebuje zjistit:

- jak výrazně se obchodní výsledky změnily,
- ve kterých měsících se změna projevila,
- které oblasti měly největší absolutní příspěvek k celkovému poklesu,
- zda byl vývoj podobný napříč kategoriemi, kanály, regiony a segmenty,
- které oblasti mají být předmětem podrobnějšího šetření.

## Business cíl

Hlavním cílem projektu je porovnat obchodní výsledky ElectroRetail CZ mezi prvním a druhým pololetím roku 2024 a určit oblasti s největším příspěvkem k jejich změně.

Analýza má:

- kvantifikovat absolutní i relativní změnu hlavních KPI,
- rozložit celkovou změnu podle vybraných business dimenzí,
- odlišit rozsah zjištěného poklesu od jeho možných příčin,
- vytvořit jednotný analytický podklad pro management,
- podpořit rozhodnutí o prioritách navazující analýzy a obchodních opatření.

## Doporučené datasety

### Global Electronics Retailer

- **Poskytovatel:** Maven Analytics
- **Uvedený zdroj dat:** Microsoft
- **Oficiální zdrojová stránka:** [Global Electronics Retailer — Maven Analytics](https://mavenanalytics.io/data-playground/global-electronics-retailer)
- **Formát:** CSV, více propojitelných tabulek
- **Popis:** Data fiktivního globálního prodejce elektroniky zahrnující transakce, produkty, zákazníky, prodejny a měnové kurzy.
- **Proč je vhodný:** Business oblast i více-tabulková struktura odpovídají projektu zaměřenému na prodej elektroniky. Dataset umožňuje práci s SQL, Power Query, datovým modelem, DAX a Power BI.
- **Omezení:**
  - scénář není zaměřen výhradně na Českou republiku,
  - dostupné období nemusí odpovídat roku 2024,
  - požadované zákaznické segmenty nemusí být přímo definovány,
  - přesné rozlišení prodejních kanálů je nutné ověřit ve stažených souborech,
  - dataset nemusí obsahovat předem připravený pokles ve druhém pololetí,
  - stažení může vyžadovat registraci nebo přihlášení.
- **Nepokryté části zadání:** Český geografický kontext, garantovaný pokles ve druhém pololetí 2024 a případná segmentace zákazníků.
- **Doporučený způsob použití:** Použít jako hlavní datový základ. Případné přemapování období, regionů nebo segmentů musí být transparentně popsáno jako projektová adaptace, nikoli jako vlastnost původního datasetu.

### AdventureWorks

- **Poskytovatel:** Microsoft
- **Oficiální zdrojová stránka:** [AdventureWorks sample databases — Microsoft Learn](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure)
- **Formát:** databázové zálohy a instalační skripty pro varianty OLTP, Data Warehouse a Lightweight
- **Popis:** Oficiální ukázková databáze společnosti Microsoft pro obchodní a datové scénáře. Microsoft poskytuje samostatné varianty pro transakční i analytické použití.
- **Proč je vhodný:** Umožňuje rozsáhlejší procvičení SQL, relačních vazeb a tvorby analytického datového modelu.
- **Omezení:**
  - společnost se nezaměřuje na spotřební elektroniku,
  - business kontext neodpovídá ElectroRetail CZ,
  - časové období neodpovídá roku 2024,
  - projekt by vyžadoval výraznější kontextovou adaptaci,
  - struktura je pro úroveň Junior+ rozsáhlejší, než je pro tento projekt nezbytné.
- **Nepokryté části zadání:** Český retailový kontext, požadované období a přesné členění kanálů a zákaznických segmentů.
- **Doporučený způsob použití:** Alternativa pro studenta, který chce klást větší důraz na SQL a práci s komplexnější databází.

### Doporučení k výběru

Pro základní variantu projektu je vhodnější **Global Electronics Retailer**, protože nejlépe odpovídá prodeji elektroniky a obsahuje více souvisejících business entit.

Žádný z doporučených veřejných datasetů negarantuje celý scénář ElectroRetail CZ včetně roku 2024, českých regionů, zákaznických segmentů a požadovaného poklesu. Před zahájením projektu je proto nutné:

1. ověřit skutečnou strukturu stažených souborů,
2. určit, které požadované dimenze jsou přímo dostupné,
3. zdokumentovat případné úpravy období a klasifikací,
4. vytvořit syntetický doplněk pouze pro údaje, které nelze získat nebo transparentně odvodit.

## Popis datasetu

### Navržený datový model

| Tabulka | Účel | Hlavní sloupce |
|---|---|---|
| `FactSales` | Jednotlivé položky objednávek | OrderID, OrderLineID, OrderDate, ProductID, CustomerID, StoreID, ChannelID, Quantity, UnitPrice, Discount |
| `DimDate` | Časová analýza | Date, Year, HalfYear, Quarter, MonthNumber, MonthName |
| `DimProduct` | Produktová hierarchie | ProductID, ProductName, Subcategory, Category, Brand |
| `DimCustomer` | Zákaznická analýza | CustomerID, CustomerSegment, CustomerLocation |
| `DimStore` | Prodejny a regionální členění | StoreID, StoreName, City, Region |
| `DimChannel` | Rozlišení prodejního kanálu | ChannelID, ChannelName |

Pokud je prodejní kanál uložen přímo v transakční tabulce a obsahuje pouze několik stabilních hodnot, samostatná tabulka `DimChannel` není nezbytná.

### Vztahy

- jedna hodnota v `DimDate` může odpovídat více prodejním položkám,
- jeden produkt může být součástí více prodejních položek,
- jeden zákazník může mít více objednávek,
- jedna prodejna může být spojena s více prodejními položkami,
- jeden prodejní kanál může zahrnovat více objednávek.

Datový model má být vytvořen převážně pomocí vztahů typu **1:N**, tedy vztahů, ve kterých jeden záznam dimenze odpovídá více záznamům faktové tabulky.

### Očekávaná velikost

Pro úroveň Junior+ je vhodný dataset obsahující:

- alespoň několik tisíc prodejních položek,
- stovky až tisíce objednávek,
- více produktových kategorií,
- nejméně dva prodejní kanály,
- několik regionů,
- nejméně dva zákaznické segmenty,
- kompletní období od ledna do prosince 2024.

### Očekávané problémy kvality dat

Dataset může obsahovat:

- duplicitní záznamy,
- chybějící identifikátory,
- nejednotné názvy kategorií nebo regionů,
- nesprávné datové typy,
- neplatná nebo chybějící data objednávek,
- nulové nebo záporné množství,
- neobvyklé ceny nebo slevy,
- objednávky bez odpovídajícího produktu či zákazníka,
- nejednotné označení prodejních kanálů,
- neúplná období.

Tyto problémy nemají být do veřejného datasetu uměle přidávány, pokud nejsou součástí zvolené varianty projektu.

## Zadání projektu

1. **Převzetí a dokumentace dat**
   - Zaznamenej původ, formát a rozsah jednotlivých datových zdrojů.
   - Popiš provedené adaptace veřejného datasetu.
   - Odděl původní data od upravených nebo synteticky doplněných údajů.

2. **Kontrola kvality dat**
   - Ověř úplnost, jedinečnost, platnost a konzistenci klíčových polí.
   - Zkontroluj vazby mezi transakcemi, produkty, zákazníky a prodejnami.
   - Posuď, zda jsou obě pololetí vzájemně srovnatelná.
   - Zdokumentuj nalezené problémy a způsob jejich řešení.

3. **Příprava dat pomocí Power Query**
   - Načti a standardizuj jednotlivé zdroje.
   - Nastav správné datové typy.
   - Sjednoť business klasifikace.
   - Připrav tabulky pro datový model.
   - Zachovej reprodukovatelný transformační postup.

4. **Uložení a analýza dat v SQL**
   - Načti připravená data do relační databáze.
   - Pomocí SQL ověř agregace a datové vazby.
   - Připrav datové výstupy potřebné pro kontrolu hlavních KPI.
   - Zdokumentuj účel jednotlivých analytických skriptů.

5. **Vytvoření datového modelu**
   - Navrhni jednoduché hvězdicové schéma.
   - Odděl faktovou tabulku od analytických dimenzí.
   - Vytvoř samostatnou kalendářní tabulku.
   - Nastav a ověř vztahy mezi tabulkami.
   - Zabraň nejednoznačným filtračním cestám.

6. **Definice metrik v DAX**
   - Vytvoř measures pro hlavní obchodní KPI.
   - Připrav absolutní a procentní porovnání pololetí.
   - Zajisti, aby metriky správně reagovaly na filtry reportu.
   - Ověř shodu klíčových hodnot mezi SQL a Power BI.

7. **Analýza obchodních výsledků**
   - Porovnej první a druhé pololetí roku 2024.
   - Vyhodnoť měsíční vývoj.
   - Rozlož změnu podle produktových kategorií, kanálů, regionů a segmentů.
   - Urči absolutní příspěvek jednotlivých oblastí k celkové změně.
   - Odliš oblasti s největším poklesem v procentech od oblastí s největším dopadem na celkový výsledek.
   - Zkontroluj, zda závěry nejsou ovlivněny rozdílnou velikostí analyzovaných skupin.

8. **Power BI report**
   - Vytvoř přehled hlavních KPI.
   - Připrav pohled na vývoj v čase.
   - Umožni porovnání hlavních business dimenzí.
   - Vytvoř pohled na příspěvek jednotlivých oblastí k celkové změně.
   - Použij pouze vizualizace podporující zadané business otázky.

9. **Interpretace výsledků**
   - Odděl ověřená zjištění od možných vysvětlení.
   - Neoznačuj korelaci nebo souběžný vývoj za příčinný vztah.
   - U každého zásadního zjištění uveď jeho business význam.
   - Identifikuj omezení analýzy a otázky vyžadující další data.

10. **Příprava podkladů pro management**
    - Zpracuj stručný Insight Report.
    - Připrav Executive Summary.
    - Navrhni Data Storytelling Plan pro prezentaci výsledků.
    - Formuluj doporučení pouze v rozsahu podpořeném analýzou.
    - U neověřených příčin navrhni další analytické šetření místo definitivního závěru.

11. **Dokumentace portfoliového projektu**
    - Popiš business problém, datové zdroje, workflow a výstupy.
    - Uveď předpoklady, omezení a provedené kontroly.
    - Připrav instrukce umožňující projekt reprodukovat.

## Business otázky

1. Jak se změnily celkové tržby ve druhém pololetí oproti prvnímu pololetí roku 2024?
2. Jak se změnily počet prodaných kusů, počet objednávek a průměrná hodnota objednávky?
3. Ve kterých měsících byl zaznamenán největší absolutní a relativní pokles?
4. Které produktové kategorie měly největší absolutní příspěvek k celkové změně tržeb?
5. Které kategorie zaznamenaly největší procentní změnu?
6. Jak se výsledky změnily mezi online kanálem a kamennými prodejnami?
7. Které regiony měly největší příspěvek k celkovému poklesu?
8. Jak se výsledky vyvíjely v jednotlivých zákaznických segmentech?
9. Je celkový pokles rozložen mezi více oblastí, nebo je soustředěn do několika kategorií, kanálů, regionů či segmentů?
10. Liší se vývoj tržeb od vývoje počtu prodaných kusů nebo počtu objednávek?
11. Které kombinace hlavních dimenzí mají být prioritou navazující analýzy?
12. Které otázky nelze z dostupných dat spolehlivě zodpovědět?

## Důležité metriky

| Metrika | Účel |
|---|---|
| Tržby | Vyjádření celkové hodnoty prodeje |
| Počet prodaných kusů | Posouzení změny objemu prodeje |
| Počet objednávek | Posouzení změny nákupní aktivity |
| Průměrná hodnota objednávky | Rozlišení změny hodnoty nákupu od změny počtu objednávek |
| Průměrná prodejní cena za kus | Orientační posouzení změny hodnotové skladby prodeje |
| Absolutní změna KPI | Vyjádření rozdílu mezi pololetími v původních jednotkách |
| Procentní změna KPI | Relativní porovnání výsledků mezi pololetími |
| Podíl na tržbách | Posouzení významu analyzované oblasti |
| Absolutní příspěvek ke změně tržeb | Určení oblastí s největším dopadem na celkovou změnu |
| Podíl na celkové změně | Posouzení koncentrace celkového poklesu |

Tržby po slevě lze použít pouze tehdy, pokud dataset obsahuje spolehlivý údaj o slevě. Hrubou marži a ziskovost lze zahrnout pouze při dostupnosti nákladových dat.

## Hlavní analytické dimenze

- datum,
- pololetí,
- čtvrtletí,
- měsíc,
- produktová kategorie,
- produktová podkategorie,
- produkt,
- prodejní kanál,
- region,
- prodejna,
- zákaznický segment.

## Doporučené technologie

| Technologie | Účel |
|---|---|
| SQL | Uložení relačních dat, kontrola vazeb, agregace a nezávislé ověření výsledků |
| Power Query | Načtení, čištění, standardizace a reprodukovatelná transformace dat |
| Power BI | Vytvoření datového modelu, interaktivní analýzy a management reportu |
| DAX | Definice KPI, časových porovnání a kontextově řízených metrik |

**Python není součástí povinného rozsahu.** Základní analytické otázky lze účelně vyřešit pomocí SQL, Power Query, Power BI a DAX. Python je proto zařazen pouze mezi možná rozšíření.

## Požadované výstupy

1. Dokumentované business zadání a rozsah projektu.
2. Přehled datových zdrojů a provedených adaptací.
3. Data Dictionary.
4. Data Quality Report.
5. Vyčištěné a připravené datové tabulky.
6. Dokumentované Power Query transformace.
7. SQL databáze a přehledně uspořádané SQL skripty.
8. Schéma datového modelu.
9. Dokumentace vytvořených DAX measures.
10. Interaktivní Power BI report.
11. Insight Report.
12. Executive Summary pro management.
13. Data Storytelling Plan.
14. README s popisem projektu, workflow, omezeními a instrukcemi ke spuštění.
15. Ukázky hlavních částí reportu vhodné pro prezentaci v portfoliu.

## Hodnocené dovednosti

- porozumění business problému,
- převod business požadavků na analytické otázky,
- posouzení vhodnosti dat,
- data profiling a kontrola kvality dat,
- čištění a transformace dat,
- práce s relační databází a SQL,
- návrh hvězdicového datového modelu,
- tvorba a validace DAX measures,
- časové porovnání obchodních výsledků,
- rozklad změny podle business dimenzí,
- rozlišení absolutní a relativní změny,
- interpretace výsledků bez nepodložené kauzality,
- návrh účelných business vizualizací,
- formulace insightů a omezení analýzy,
- komunikace výsledků managementu,
- dokumentace a reprodukovatelnost projektu.

## Kritéria úspěšného dokončení

Projekt je kvalitně dokončen, pokud:

- analýza odpovídá původnímu business cíli,
- obě pololetí jsou definována a porovnávána konzistentně,
- použitá data mají dohledatelný původ,
- všechny úpravy veřejného datasetu jsou transparentně popsány,
- syntetická data jsou jednoznačně označena,
- problémy kvality dat jsou zdokumentovány a přiměřeně vyřešeny,
- datový model má správné vztahy a odpovídající granularitu,
- KPI mají jednoznačné definice,
- výsledky v SQL a Power BI jsou vzájemně konzistentní,
- report umožňuje určit rozsah a strukturu změny,
- absolutní příspěvek není zaměňován za procentní pokles,
- zjištěné rozdíly nejsou automaticky označovány za příčiny,
- omezení analýzy a chybějící data jsou otevřeně uvedeny,
- management výstupy navazují na analytické výsledky,
- projekt lze podle dokumentace reprodukovat,
- report je čitelný, konzistentní a přiměřený cílovému publiku.

## Jak by projekt hodnotil recruiter

Recruiter nebo hiring manager bude pravděpodobně nejvíce sledovat:

- zda student rozumí business problému a neprezentuje pouze dashboard,
- zda dokáže propojit více tabulek do funkčního datového modelu,
- zda umí ověřit kvalitu dat a správnost výpočtů,
- zda rozlišuje největší procentní pokles od největšího dopadu na celkový výsledek,
- zda dokáže interpretovat výsledky srozumitelně a bez nepodložených tvrzení,
- zda jsou SQL, Power Query, DAX a Power BI použity jako součást jednoho konzistentního workflow,
- zda je projekt dobře zdokumentovaný a reprodukovatelný.

Mezi časté chyby patří:

- zaměření na vzhled dashboardu na úkor analytické správnosti,
- nejasná definice KPI,
- nevhodné vztahy v datovém modelu,
- porovnávání nesrovnatelných období,
- hodnocení pouze procentních změn bez zohlednění velikosti oblasti,
- označování zjištěných rozdílů za příčiny,
- nepřiznané úpravy nebo doplnění veřejného datasetu,
- nesoulad hodnot mezi SQL, Power BI a závěrečným reportem.

Velmi kvalitní portfolio se od průměrného zpracování odlišuje zejména transparentním postupem, ověřenými výpočty, business interpretací, přiměřenou vizualizací a jasným oddělením zjištění, hypotéz a omezení.

## Odhadovaný čas dokončení

- **Uživatel, který již ovládá použité nástroje:** přibližně 35–55 hodin.
- **Uživatel, který se SQL, Power Query, Power BI nebo DAX během projektu učí:** přibližně 70–110 hodin.

Odhad zahrnuje přípravu dat, analýzu, report, kontrolu výsledků a základní portfoliovou dokumentaci. Nezahrnuje rozsáhlou tvorbu syntetického datasetu od začátku.

## Co si student odnese

Student si procvičí realizaci end-to-end analytického projektu v realistickém retailovém prostředí.

Získá zkušenosti s:

- rozkladem nejednoznačného business problému,
- kontrolou a integrací více datových tabulek,
- propojením SQL, Power Query, Power BI a DAX,
- porovnáním výkonnosti mezi obdobími,
- identifikací oblastí s největším příspěvkem k celkové změně,
- validací výsledků mezi různými nástroji,
- objektivní interpretací bez zaměňování souvislosti za příčinu,
- přípravou analytických podkladů pro management,
- dokumentací projektu pro pracovní portfolio.

Výsledkem bude portfolio projekt demonstrující nejen technické schopnosti, ale také analytické myšlení a porozumění obchodnímu kontextu.

## Možná rozšíření projektu

- **Analýza ziskovosti:** Doplnit náklady a vyhodnotit hrubou marži, pokud jsou k dispozici spolehlivá nákladová data.
- **Analýza slev:** Posoudit vztah mezi slevami, prodaným množstvím a tržbami.
- **Noví a vracející se zákazníci:** Rozšířit analýzu o nákupní historii zákazníků a míru opakovaných nákupů.
- **Same-store analýza:** Porovnat pouze prodejny aktivní během obou pololetí a omezit vliv změn prodejní sítě.
- **Dekompozice tržeb:** Podrobněji oddělit změnu počtu objednávek, množství a průměrné prodejní ceny.
- **Statistické ověření:** Pomocí Pythonu posoudit, zda jsou vybrané rozdíly mezi obdobími statisticky významné.
- **Automatizace datových kontrol:** Vytvořit opakovatelnou sadu kontrol kvality a konzistence dat.
- **Scénářová analýza:** Modelovat možné dopady změny počtu objednávek, průměrné hodnoty objednávky nebo výkonnosti vybraných oblastí.
- **Navazující analýza příčin:** Doplnit marketingová, cenová, skladová nebo provozní data a ověřit konkrétní hypotézy vysvětlující pokles.
