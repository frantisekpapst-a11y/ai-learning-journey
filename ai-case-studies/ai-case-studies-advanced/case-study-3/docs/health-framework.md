[← Zpět na hlavní stránku projektu](../README.md)

---

# AI Personal Advisor Framework – Zdraví

> **Důležité upozornění:** AI může pomoci s orientací ve zdravotních informacích, podporou zdravého životního stylu a přípravou na konzultaci. Nenahrazuje však lékařské vyšetření, diagnózu ani odborně stanovenou léčbu.

---

## 1. Úvod

### S čím AI pomůže

AI lze využít například pro:

- vysvětlení zdravotních pojmů a lékařských zpráv,
- vytvoření orientačního jídelníčku nebo pohybového plánu,
- zlepšení spánkového režimu a denní rutiny,
- uspořádání příznaků a naměřených hodnot,
- přípravu otázek pro lékaře nebo jiného odborníka.

### Hlavní přínosy

- **Dostupnost:** Poskytuje rychlou základní orientaci.
- **Personalizace:** Na základě poskytnutých informací může přizpůsobit odpověď situaci a cílům uživatele.
- **Srozumitelnost:** Převádí odborné informace do běžného jazyka.
- **Struktura:** Pomáhá uspořádat informace a navrhnout další kroky.

### Hlavní limity

Běžné veřejně dostupné AI nástroje obvykle nemají přístup k úplné zdravotní dokumentaci ani ke všem okolnostem zdravotního stavu uživatele. Nemohou provést fyzické vyšetření a jejich odpovědi mohou být nepřesné nebo zastaralé. Výstupy je proto nutné posuzovat kriticky a důležité informace ověřovat.

---

## 2. Jak vytvořit kvalitní prompt

Kvalita odpovědi závisí na poskytnutém kontextu. Uživatel by měl uvést pouze informace, které jsou pro konkrétní požadavek relevantní.

| Skupina informací | Co může obsahovat a proč je důležitá |
|---|---|
| **Základní informace** | Věk, případně pohlaví nebo relevantní biologické souvislosti. Mohou ovlivnit zdravotní potřeby a rizika. |
| **Tělesné údaje** | Výška, hmotnost nebo jiné relevantní hodnoty. Pomáhají přizpůsobit návrh jídelníčku či pohybu. |
| **Životní styl** | Stravování, fyzická aktivita, spánek, zaměstnání, kouření, alkohol nebo stres. Poskytují širší kontext. |
| **Zdravotní stav a omezení** | Onemocnění, alergie, intolerance, úrazy, operace nebo jiná omezení. Mohou ovlivnit vhodnost doporučení. |
| **Léky a doplňky** | Pravidelně i příležitostně užívané přípravky. Mohou ovlivňovat zdravotní stav nebo výsledky vyšetření. |
| **Aktuální situace** | Popis problému, jeho začátek, trvání, intenzita, vývoj, další příznaky a naměřené hodnoty včetně jednotek. |
| **Cíl** | Například porozumění zprávě, sestavení plánu nebo příprava otázek pro lékaře. |
| **Požadovaná forma výstupu** | Stručné shrnutí, tabulka, plán, kontrolní seznam nebo seznam otázek. |

### Ochrana osobních údajů

Do AI zadávejte pouze nezbytné informace. Nevkládejte zejména:

- jméno, rodné číslo nebo přesné datum narození,
- adresu a kontaktní údaje,
- číslo pojištěnce,
- jiné údaje umožňující jednoznačnou identifikaci.

Před vložením lékařské zprávy nebo výsledků vyšetření odstraňte či nahraďte osobní a identifikační údaje. Zkontrolujte také, zda člověka nelze rozpoznat z kombinace dalších informací v dokumentu. Vkládejte pouze části nezbytné pro konkrétní požadavek a respektujte interní pravidla organizace i podmínky používaného AI nástroje.

---

## 3. Univerzální šablona promptu

~~~text
Jsi informační asistent pro oblast zdraví. Pomoz mi zorientovat se
v následující situaci.

## Můj cíl

[Čeho chci dosáhnout nebo čemu potřebuji porozumět.]

## Relevantní informace

- Věk:
- Relevantní tělesné údaje:
- Životní styl a denní režim:
- Zdravotní stav a omezení:
- Alergie a intolerance:
- Užívané léky a doplňky:
- Relevantní zdravotní historie:

## Aktuální situace

- Popis problému:
- Začátek a dosavadní průběh:
- Intenzita a související příznaky:
- Naměřené hodnoty, jednotky a referenční rozmezí:
- Dosavadní vyšetření nebo doporučení:

## Požadovaný výstup

[Stručné vysvětlení / tabulka / plán / kontrolní seznam /
otázky pro odborníka.]

Postupuj následovně:

1. Shrň situaci.
2. Zeptej se na chybějící informace.
3. Jasně rozliš informace uvedené uživatelem, obecné zdravotní informace,
   možné interpretace a nejistoty.
4. Navrhni pouze obecné kroky, které nezasahují do diagnózy, léčby
   ani užívání léků, a uveď, co je vhodné ověřit se zdravotnickým
   odborníkem.
5. U důležitých zdravotních tvrzení uveď aktuální důvěryhodné zdroje
   a jasně označ informace, které nelze spolehlivě ověřit.

## Omezení a bezpečnost

Nestanovuj diagnózu, neurčuj léčbu a nenahrazuj lékařské vyšetření.
Nevymýšlej si chybějící údaje a nedoporučuj změnu léků bez konzultace
s příslušným zdravotnickým odborníkem.
~~~

Nevyužité položky není nutné vyplňovat.

---

## 4. Praktické příklady

### 4.1 Zdravější životní styl

#### Situace

Uživatel chce zlepšit stravování, pohyb, spánek a celkový denní režim.

#### Kvalitní prompt

~~~text
Je mi 42 let, měřím 180 cm a vážím 96 kg. Pracuji převážně vsedě
od 8:00 do 16:30. Pohybuji se nepravidelně, chodím pozdě spát
a večer mívám málo energie.

Mým cílem je během čtyř týdnů vytvořit udržitelnější režim. Navrhni:

- jednoduchou strukturu jídelníčku,
- pravidelné časy jídla a spánku,
- realistické zařazení pohybu během pracovního dne i týdne,
- způsob průběžného vyhodnocení.

Použij běžně dostupné potraviny a malé, postupné změny. Výstup připrav
jako týdenní plán. Pokud chybí důležité informace, nejprve se zeptej.
~~~

#### Očekávaný výstup

- praktický týdenní režim,
- základní zásady stravování a spánku,
- realistické zařazení pohybu,
- jednoduchý způsob sledování pokroku.

---

### 4.2 Cvičební plán

#### Situace

Uživatel se po delší pauze vrací k pohybu a potřebuje přiměřeně nastavit počáteční zátěž.

#### Kvalitní prompt

~~~text
Je mi 38 let, pracuji v kanceláři a poslední dva roky jsem pravidelně
necvičil. Mohu cvičit třikrát týdně 30 minut doma. Mám podložku
a odporovou gumu. V minulosti mě občas bolela bederní část zad,
ale nyní nemám akutní bolest.

Navrhni orientační plán na čtyři týdny pro zlepšení kondice, mobility
a posílení středu těla. U cviků stručně popiš provedení, počet
opakování, jednodušší variantu a situace, kdy cvičení přerušit.
Chybějící informace si nejprve vyžádej.
~~~

#### Očekávaný výstup

- postupný čtyřtýdenní plán,
- stručný popis provedení cviků a doporučeného počtu opakování,
- jednodušší varianty,
- bezpečnostní upozornění.

---

### 4.3 Vysvětlení laboratorních hodnot

#### Situace

Uživatel chce před konzultací se zdravotnickým odborníkem porozumět anonymizovaným výsledkům krevního vyšetření.

#### Kvalitní prompt

~~~text
Pomoz mi porozumět následujícím výsledkům krevního vyšetření:

- Hemoglobin: [hodnota a jednotka], rozmezí: [referenční rozmezí]
- Hematokrit: [hodnota a jednotka], rozmezí: [referenční rozmezí]
- Leukocyty: [hodnota a jednotka], rozmezí: [referenční rozmezí]
- CRP: [hodnota a jednotka], rozmezí: [referenční rozmezí]

Odběr proběhl dne [datum] za podmínek [nalačno / po jídle / neuvedeno].

U každé položky stručně vysvětli její význam, porovnej ji s uvedeným
referenčním rozmezím a uveď možné obecné souvislosti odchylky.
Jasně rozliš zadané hodnoty, obecné zdravotní informace, možné
interpretace a nejistoty. Nevydávej jednotlivou odchylku laboratorní
hodnoty za potvrzení konkrétního onemocnění. Připrav také otázky
pro lékaře.
~~~

#### Očekávaný výstup

- srozumitelné vysvětlení hodnot,
- porovnání s rozmezím konkrétní laboratoře,
- jasné označení možných interpretací a nejistot,
- otázky pro ošetřujícího lékaře.

---

### 4.4 Vysvětlení lékařské zprávy

#### Situace

Uživatel potřebuje vysvětlit odborné výrazy a připravit se na další konzultaci.

#### Kvalitní prompt

~~~text
Níže vkládám anonymizovaný text lékařské zprávy:

[ANONYMIZOVANÝ TEXT]

Vysvětli zprávu srozumitelným jazykem a rozděl odpověď na:

1. hlavní zjištění,
2. vysvětlení odborných pojmů,
3. doporučení uvedená ve zprávě,
4. nejasnosti nebo chybějící informace,
5. otázky pro ošetřujícího lékaře.

Jasně rozliš informace uvedené ve zprávě, obecné zdravotní informace,
možné interpretace a nejistoty. Nepřidávej závěry, které ze zprávy
přímo nevyplývají.
~~~

#### Očekávaný výstup

- srozumitelné shrnutí zprávy,
- vysvětlení odborné terminologie,
- rozlišení uvedených informací, možných interpretací a nejistot,
- seznam otázek pro další konzultaci.

---

## 5. Doporučený postup práce s AI

1. **Poskytněte relevantní kontext**  
   Uveďte informace, které přímo souvisejí s požadavkem. Nadbytečné citlivé údaje vynechte.

2. **Formulujte konkrétní cíl**  
   Jasně popište, zda chcete vysvětlení, plán, porovnání nebo přípravu otázek pro odborníka.

3. **Využijte doplňující otázky**  
   Požádejte AI, aby si před odpovědí vyžádala důležité chybějící informace.

4. **Rozlišujte jednotlivé typy informací**  
   Požadujte jasné rozlišení informací uvedených uživatelem, obecných zdravotních informací, možných interpretací a nejistot.

5. **Ověřujte důležité informace**  
   Čím větší může mít odpověď dopad na zdraví, tím důkladněji ji ověřte u odborníka a v aktuálních důvěryhodných zdrojích.

Podle potřeby požadujte přímé odkazy na zdroje a praktickou formu výstupu, například tabulku, plán nebo kontrolní seznam. Ověřte, že uvedené zdroje skutečně existují a podporují dané tvrzení.

---

## 6. Rizika a kdy kontaktovat odborníka

### Hlavní rizika a omezení

1. **Nepřesnosti a halucinace**  
   AI může vytvořit věrohodně působící, ale nesprávnou informaci, hodnotu nebo zdroj.

2. **Neúplný kontext**  
   AI zná pouze zadané informace a nemůže zohlednit skutečnosti, které uživatel neuvedl, ani provést fyzické vyšetření.

3. **Zastaralé nebo nesprávně interpretované informace**  
   Odpověď nemusí odpovídat aktuálním odborným doporučením. AI může také zaměnit možnou souvislost za skutečnou příčinu problému.

4. **Ohrožení citlivých údajů**  
   Údaje o zdravotním stavu patří podle GDPR mezi zvláštní kategorie osobních údajů. Do AI zadávejte pouze nezbytné informace zbavené přímých identifikátorů a dodržujte pravidla uvedená v kapitole 2.

5. **Nevhodné zdravotní rozhodnutí**  
   Přesvědčivá odpověď může uživatele vést k nesprávné změně léčby, odkladu vyšetření nebo podcenění zdravotního stavu.

### Kdy kontaktovat odborníka

Okamžitou odbornou pomoc je nutné vyhledat při akutním nebo rychle se zhoršujícím stavu.

Konzultace se zdravotnickým odborníkem je vhodná zejména:

- pokud potíže přetrvávají nebo se opakují,
- pokud je potřeba stanovit nebo potvrdit diagnózu,
- při interpretaci výsledků v celkovém klinickém kontextu,
- před zahájením, ukončením nebo změnou léčby,
- před změnou dávkování předepsaných léků.

Pokud se zdravotní problém nebo plánovaná změna týká dítěte, těhotné osoby, seniora nebo člověka se závažným chronickým onemocněním, je vhodné upřednostnit konzultaci se zdravotnickým odborníkem.

> **Při akutním ohrožení zdraví nebo života nepoužívejte AI. V České republice volejte zdravotnickou záchrannou službu na čísle 155, případně tísňovou linku 112.**

---

## 7. Závěrečné pravidlo

> AI je vhodná pro orientaci, vysvětlení a organizaci zdravotních informací. Nenahrazuje však lékaře ani jiného kvalifikovaného zdravotnického odborníka. Stanovení diagnózy, zahájení nebo změnu léčby a změny v užívání předepsaných léků je nutné řešit se zdravotnickým odborníkem.

---

[← Zpět na hlavní stránku projektu](../README.md)
