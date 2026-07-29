# Case Study 01 – AI Assisted Executive Summary for Quarterly Sales Analysis

## Přehled

**Oblast:** Data Analytics, AI Productivity

**Nástroj:** ChatGPT

**Cíl:** Ukázat, jak lze AI využít při převodu technického analytického reportu do stručného Executive Summary určeného pro vedení společnosti.

---

# Zadání

Management společnosti požádal analytický tým o vyhodnocení výsledků za **2. čtvrtletí 2025**.

Analýza byla dokončena, ale vedení nechce číst několikastránkový technický report. Potřebuje pouze:

- hlavní zjištění,
- klíčové KPI,
- hlavní rizika,
- doporučení,
- další kroky.

Cílem bylo využít AI k vytvoření profesionálního Executive Summary.

---

# Vstupní analytický report

## Přehled

Společnost dosáhla ve **2. čtvrtletí 2025** celkových tržeb ve výši **5,2 milionu €**, což představuje **nárůst o 8 %** oproti předchozímu čtvrtletí.

Objem prodeje vzrostl o **5 %**, zatímco průměrná hodnota objednávky se zvýšila z **118 € na 122 €**.

Počet nově získaných zákazníků zůstal stabilní, avšak počet opakovaných nákupů vzrostl o **14 %**, což naznačuje vyšší loajalitu zákazníků.

### Výkonnost produktů

- Notebooky (+18 %)
- Herní příslušenství (+22 %)
- Zařízení pro chytrou domácnost (+15 %)
- Tablety (-9 %)

### Výkonnost regionů

- Západní Evropa (+12 %)
- Střední Evropa (stabilní)
- Jižní Evropa (-6 %)

### Přehled zákazníků

- Spokojenost zákazníků: **4,3 → 4,5**
- Průměrná doba doručení: **3,6 → 2,9 dne**
- Míra vrácení zboží: **2,1 %**

### Rizika

- Klesající prodeje tabletů
- Nižší marketingová aktivita v jižní Evropě
- Nízké skladové zásoby herního příslušenství

### Doporučení

- Navýšit marketingový rozpočet pro jižní Evropu.
- Rozšířit skladové zásoby herního příslušenství.
- Přehodnotit produktové portfolio tabletů.
- Pokračovat v investicích do aktivit zaměřených na udržení zákazníků.
  
---

# Workflow

## Prompt 1 – První návrh

### Cíl

Navrhnout strukturu Executive Summary pro vrcholový management.

```text
Pomoz mi určit, jaké informace by měly být součástí Executive Summary pro vedení společnosti na základě následující analýzy.

Management požádal analytický tým o vyhodnocení výsledků za 2. čtvrtletí 2025. Analýza byla dokončena, ale vedení nechce číst dlouhý technický report.

Potřebuje pouze:

- hlavní zjištění,
- klíčové KPI,
- největší problémy,
- doporučení,
- další kroky.
```

---

## Výsledek

AI vytvořila přehlednou strukturu obsahující:

- Executive Summary,
- KPI,
- rizika,
- doporučení,
- další kroky.

Výstup byl dobře strukturovaný, ale obsahoval několik nedostatků.

---

# Kontrola výstupu

Při kontrole byly nalezeny následující problémy:

- chyběla část důležitých KPI,
- AI zaměnila mezikvartální a meziroční ukazatele,
- některá doporučení vytvořila sama,
- některé závěry byly příliš kategorické.

To ukazuje, že výstupy AI je vždy potřeba kriticky ověřit.

---

## Prompt 2 – Revize návrhu

### Cíl

Opravit nalezené chyby.

```text
Přepracuj svůj předchozí návrh.

- Doplň všechny chybějící KPI.
- Rozlišuj QoQ a YoY ukazatele.
- Používej pouze informace obsažené ve vstupním reportu.
- Doporučení vytvořená AI označ jako „AI Recommendation“.
- Nepřidávej nepodložené závěry.
- Executive Summary omez na maximálně 200 slov.
```

---

## Prompt 3 – Business úpravy

### Cíl

Zpřesnit doporučení a odstranit příliš silná tvrzení.

```text
Uprav doporučení a závěrečnou část Executive Summary.

Zdůrazni doporučení týkající se zásob Gaming Accessories, revize portfolia Tablets a investic do retence zákazníků.

Formulaci o Southern Europe uprav tak, aby bylo zřejmé, že vztah mezi marketingovou aktivitou a regionálním poklesem je potřeba ověřit další analýzou.
```

---

## Prompt 4 – Finální úpravy

### Cíl

Proveď poslední stylistické úpravy.

```text
Aktualizuj AI Recommendation.

Uprav závěrečné doporučení.

Zachovej stručný a profesionální styl určený pro vrcholový management.
```

---

# Finální Executive Summary

Ve 2. čtvrtletí 2025 dosáhla společnost tržeb €5,2 mil., což představuje mezikvartální růst (QoQ) o 8 % oproti Q1 2025. Objem prodeje vzrostl o 5 %, průměrná hodnota objednávky se zvýšila ze €118 na €122 a počet opakovaných nákupů vzrostl o 14 %.

Nejvýkonnějšími kategoriemi byly Gaming Accessories (+22 %), Laptops (+18 %) a Smart Home Devices (+15 %). Prodej Tablets naopak poklesl o 9 %. Nejvyššího regionálního růstu dosáhla Western Europe (+12 %), Central Europe zůstala stabilní a Southern Europe poklesla o 6 %. Pokles se časově shodoval s omezením marketingové aktivity; skutečný vliv je potřeba ověřit další analýzou.

Zákaznická spokojenost vzrostla ze 4,3 na 4,5 hvězdičky, průměrná doba doručení se zkrátila z 3,6 na 2,9 dne a míra vrácení zůstala stabilní na 2,1 %.

Pro udržení současného růstu by vedení mělo prioritně rozšířit zásoby Gaming Accessories, přezkoumat portfolio Tablets a pokračovat v investicích do retence zákazníků.

**AI Recommendation:** Před navýšením marketingového rozpočtu v Southern Europe provést podrobnější analýzu, která ověří, zda je omezení marketingové aktivity skutečně hlavní příčinou regionálního poklesu.

---

# Získané poznatky

- AI dokáže výrazně urychlit tvorbu manažerských souhrnů.
- První výstup AI není vhodné považovat za finální.
- Kritická kontrola analytikem je nezbytná.
- Iterace promptů vede ke kvalitnějším výsledkům.
- AI by měla být používána jako asistent.

---

# Klíčová dovednost

Tato případová studie neukazuje pouze práci s prompty, ale celý analytický proces:

1. Analýza vstupních dat.
2. Vytvoření prvního návrhu pomocí AI.
3. Kritické zhodnocení výstupu.
4. Identifikace chyb.
5. Iterace promptů.
6. Vytvoření finálního Executive Summary.

## Související dovednosti

- AI Productivity,
- Prompt Engineering,
- Business Communication,
- Executive Reporting,
- Critical Thinking,
- Data Storytelling.
