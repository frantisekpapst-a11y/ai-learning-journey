# Case Study 2 – AI Sentiment Analysis pro e-shop

## Cíl

Navrhnout způsob využití umělé inteligence pro automatickou analýzu zákaznických recenzí s cílem poskytnout managementu kvalitní podklady pro rozhodování.

---

# Business problém

E-shop zpracovává přibližně 50 000 zákaznických recenzí. Ruční analýza všech recenzí není reálně proveditelná, protože:
- je časově náročná,
- zvyšuje personální náklady,
- výsledky mohou být subjektivní,
- opakující se problémy lze snadno přehlédnout.

Cílem projektu je využít AI k automatickému zpracování recenzí a vytvoření podkladů pro management.

---

# Návrh řešení

## Zdroje dat

Recenze budou získávány z několika zdrojů:
- vlastní e-shop,
- Facebook,
- e-mailové dotazníky,
- záznamy zákaznického centra (Customer Care).

Data mohou být získávána pomocí exportů, API nebo web scrapingu.

---

## Příprava dat

Před analýzou bude nutné:
- odstranit duplicity,
- opravit chybné formáty,
- odstranit nekompletní záznamy,
- sjednotit strukturu dat,
- odstranit osobní údaje,
- ověřit aktuálnost dat.

---

## Úloha AI

AI bude:
- klasifikovat sentiment recenzí,
- identifikovat hlavní téma recenze,
- shrnovat nejčastější problémy,
- vytvářet podklady pro dashboardy a reporting.

---

# Návrh kategorií sentimentu

Namísto klasických tří kategorií byly navrženy čtyři.

| Kategorie | Popis |
|-----------|-------|
| Positive | Převážně pozitivní hodnocení |
| Negative | Převážně negativní hodnocení |
| Neutral | Bez výrazného pozitivního nebo negativního postoje |
| Mixed | Současně pozitivní i negativní hodnocení |

### Zdůvodnění

Kategorie **Mixed** umožňuje přesnější klasifikaci recenzí typu:

> „Produkt je kvalitní, ale doprava byla velmi pomalá."

Takové recenze nejsou neutrální, ale obsahují současně pozitivní i negativní informace.

---

# Ukázkový testovací dataset

| Recenze | Sentiment | Hlavní téma |
|----------|-----------|-------------|
| Všechno super, s produktem jsem fakt spokojenej. | Positive | Produkt |
| Cena, produkt i dodání na 100 %. | Positive | Cena / Produkt / Doprava |
| Produkt mi byl doručen po třech týdnech, bída. | Negative | Doprava |
| Musel jsem po dvou dnech reklamovat. | Negative | Reklamace |
| Nevím, ještě jsem nevyzkoušel. | Neutral | Bez zkušenosti |
| Kvalita dobrá, ale v porovnání s konkurencí jste drazí. | Mixed | Produkt / Cena |

---

# Validace AI

Správnost modelu bude ověřována na náhodně vybraném vzorku recenzí.

Navržený postup:
1. náhodný výběr 100 recenzí,
2. manuální klasifikace,
3. porovnání s výsledky AI,
4. analýza rozdílů,
5. úprava pravidel nebo promptů.

Pokud bude AI dlouhodobě chybovat u určitého typu recenzí, bude provedena revize klasifikačních pravidel.

---

# Přístup k neshodám

Pokud AI klasifikuje recenzi jinak než člověk:
1. AI zdůvodní své rozhodnutí.
2. Budou vyhledány podobné recenze.
3. Bude posouzen větší vzorek.
4. Pokud bude většina hodnocení v rozporu s AI, upraví se pravidla klasifikace.

---

# Role datového analytika

Datový analytik:
- připraví data,
- ověří kvalitu výstupů AI,
- interpretuje výsledky,
- připraví dashboardy,
- doporučí další kroky managementu.

---

# Návrh KPI

| KPI | Důvod sledování |
|------|-----------------|
| Náklady na zpracování jedné recenze | Vyhodnocení ekonomického přínosu projektu |
| Počet zpracovaných recenzí | Měření kapacity řešení |
| Přesnost AI | Kontrola kvality klasifikace |
| Podíl pozitivních / negativních / mixed recenzí | Sledování vývoje zákaznické spokojenosti |
| Počet reklamací a stížností | Vyhodnocení obchodního dopadu projektu |

---

# Navržený workflow

```text
Nová recenze
      │
      ▼
Načtení dat
      │
      ▼
Čištění dat
      │
      ▼
AI klasifikace
      │
      ├───────────────┐
      │               │
Positive          Negative / Mixed
      │               │
      ▼               ▼
Reporting      Customer Care + Marketing
      │               │
      └───────► Ověření člověkem
                      │
                      ▼
               Nápravná opatření
                      │
                      ▼
                Dashboard / Management
```

---

# Přínosy projektu
- výrazné snížení času potřebného pro analýzu recenzí,
- snížení nákladů na manuální zpracování,
- rychlejší identifikace problémů,
- jednotnější klasifikace recenzí,
- lepší podklady pro rozhodování managementu,
- možnost průběžného sledování sentimentu zákazníků.

---

# Závěr

Tato případová studie ukazuje, že role datového analytika nespočívá pouze ve využití AI, ale především v návrhu celého analytického procesu.
AI zde funguje jako nástroj pro automatizaci a podporu rozhodování. Odpovědnost za interpretaci výsledků, validaci modelu a obchodní rozhodnutí zůstává na datovém analytikovi a managementu.
