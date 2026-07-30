# SQL analýza zákazníků podle objednávek

## Zadání

### Business scénář

Společnost provozuje e-commerce platformu a ukládá data o zákaznících, objednávkách a produktech do relační databáze. Obchodní oddělení potřebuje pravidelně analyzovat prodeje podle zákazníků, produktů a časového období.

### Databázový systém

Microsoft SQL Server

### Datový model

#### Customers

| Sloupec      | Popis                             |
| ------------ | --------------------------------- |
| `CustomerID` | Jedinečný identifikátor zákazníka |
| `FirstName`  | Jméno                             |
| `LastName`   | Příjmení                          |
| `City`       | Město                             |
| `Country`    | Země                              |

#### Orders

| Sloupec       | Popis                              |
| ------------- | ---------------------------------- |
| `OrderID`     | Jedinečný identifikátor objednávky |
| `CustomerID`  | Identifikátor zákazníka            |
| `OrderDate`   | Datum objednávky                   |
| `TotalAmount` | Celková hodnota objednávky         |

#### OrderItems

| Sloupec     | Popis                    |
| ----------- | ------------------------ |
| `OrderID`   | Identifikátor objednávky |
| `ProductID` | Identifikátor produktu   |
| `Quantity`  | Množství                 |
| `UnitPrice` | Cena za kus              |

#### Products

| Sloupec       | Popis                            |
| ------------- | -------------------------------- |
| `ProductID`   | Jedinečný identifikátor produktu |
| `ProductName` | Název produktu                   |
| `Category`    | Kategorie produktu               |

### Vazby

* `Customers.CustomerID = Orders.CustomerID`
* `Orders.OrderID = OrderItems.OrderID`
* `OrderItems.ProductID = Products.ProductID`

### Úkol

Vytvoř SQL dotaz, který zobrazí:

* jméno zákazníka,
* příjmení zákazníka,
* město,
* počet objednávek,
* celkovou hodnotu objednávek,
* datum poslední objednávky.

Do výsledku zahrň pouze zákazníky:

* kteří uskutečnili alespoň 5 objednávek,
* jejichž celková hodnota objednávek přesahuje 50 000 Kč.

Výsledek seřaď podle celkové hodnoty objednávek sestupně.

---

## 1. Shrnutí řešení

SQL dotaz propojí tabulky `Customers` a `Orders` podle identifikátoru zákazníka. Následně seskupí data podle jednotlivých zákazníků a vypočítá:

* počet objednávek,
* celkovou hodnotu objednávek,
* datum poslední objednávky.

Podmínky na minimální počet objednávek a jejich celkovou hodnotu jsou aplikovány pomocí klauzule `HAVING`. Výsledek je seřazen podle celkové hodnoty objednávek sestupně.

## 2. Předpoklady

Pro vytvoření SQL dotazu nejsou nutné žádné dodatečné předpoklady. Zadání obsahuje potřebné tabulky, sloupce, vazby, podmínky i databázový systém.

Tabulky `OrderItems` a `Products` nejsou použity, protože všechny požadované výsledky lze získat přímo z tabulek `Customers` a `Orders`.

## 3. SQL řešení

```sql
SELECT
    c.FirstName,
    c.LastName,
    c.City,
    COUNT(o.OrderID) AS OrderCount,
    SUM(o.TotalAmount) AS TotalOrderAmount,
    MAX(o.OrderDate) AS LastOrderDate
FROM Customers AS c
INNER JOIN Orders AS o
    ON c.CustomerID = o.CustomerID
GROUP BY
    c.CustomerID,
    c.FirstName,
    c.LastName,
    c.City
HAVING
    COUNT(o.OrderID) >= 5
    AND SUM(o.TotalAmount) > 50000
ORDER BY
    TotalOrderAmount DESC;
```

## 4. Stručné vysvětlení řešení

* `INNER JOIN` propojí zákazníky s jejich objednávkami prostřednictvím sloupce `CustomerID`.
* `GROUP BY` vytvoří samostatnou skupinu pro každého zákazníka.
* `CustomerID` je zahrnut do seskupení, aby byli správně rozlišeni zákazníci se stejným jménem, příjmením a městem.
* `COUNT(o.OrderID)` vypočítá počet objednávek každého zákazníka.
* `SUM(o.TotalAmount)` vypočítá celkovou hodnotu objednávek zákazníka.
* `MAX(o.OrderDate)` určí datum poslední objednávky.
* `HAVING` filtruje seskupené výsledky podle vypočítaných agregovaných hodnot.
* `ORDER BY TotalOrderAmount DESC` seřadí zákazníky od nejvyšší celkové hodnoty objednávek.

Použití klauzule `HAVING` je nezbytné, protože podmínky pracují s výsledky agregačních funkcí `COUNT` a `SUM`. Klauzule `WHERE` se používá před agregací, a proto by pro tyto podmínky nebyla vhodná.

## 5. Alternativní řešení

Navržené řešení je pro dané zadání nejjednodušší, nejčitelnější a snadno udržovatelné.

Zapojení tabulek `OrderItems` a `Products` by nepřineslo žádnou potřebnou informaci. Navíc by mohlo způsobit vícenásobné započítání hodnoty objednávky, protože jedna objednávka může obsahovat více položek.

Alternativní řešení pomocí poddotazu nebo společného tabulkového výrazu (`CTE`) by bylo možné, ale pro tento úkol by bylo zbytečně složité.

## 6. Ověření splnění zadání

| Požadavek                                                     | Splněno | Způsob splnění                                         |
| ------------------------------------------------------------- | :-----: | ------------------------------------------------------ |
| Zobrazit jméno zákazníka                                      |   Ano   | `c.FirstName`                                          |
| Zobrazit příjmení zákazníka                                   |   Ano   | `c.LastName`                                           |
| Zobrazit město                                                |   Ano   | `c.City`                                               |
| Vypočítat počet objednávek                                    |   Ano   | `COUNT(o.OrderID)`                                     |
| Vypočítat celkovou hodnotu objednávek                         |   Ano   | `SUM(o.TotalAmount)`                                   |
| Zobrazit datum poslední objednávky                            |   Ano   | `MAX(o.OrderDate)`                                     |
| Zahrnout pouze zákazníky s alespoň 5 objednávkami             |   Ano   | `COUNT(o.OrderID) >= 5`                                |
| Zahrnout pouze zákazníky s hodnotou objednávek přes 50 000 Kč |   Ano   | `SUM(o.TotalAmount) > 50000`                           |
| Seřadit výsledek podle celkové hodnoty sestupně               |   Ano   | `ORDER BY TotalOrderAmount DESC`                       |
| Použít syntaxi kompatibilní s Microsoft SQL Serverem          |   Ano   | Použitá syntaxe je podporována v Microsoft SQL Serveru |
| Nevytvářet databázové objekty, testovací data ani změny dat   |   Ano   | Řešení obsahuje pouze požadovaný příkaz `SELECT`       |
