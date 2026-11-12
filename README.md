**Analiza klientów i skuteczności kampanii marketingowych**


**Opis projektu**

Projekt przedstawia analizę klientów oraz skuteczności kampanii marketingowych z wykorzystaniem narzędzia Microsoft Power BI.

Raport został podzielony na trzy obszary analityczne:

•	Customer & Marketing Overview

•	RFM Customer Segmentation

•	Marketing Campaign Analysis



**Cel projektu**

Celem analizy było zidentyfikowanie najcenniejszych grup klientów, zrozumienie ich zachowań zakupowych oraz ocena efektywności prowadzonych kampanii marketingowych. W projekcie wykorzystano segmentację RFM (Recency, Frequency, Monetary), która pozwala ocenić wartość klientów i wspierać podejmowanie decyzji marketingowych opartych na danych. Dodatkowo analiza miała na celu odpowiedź na pytania:

Którzy klienci generują największe przychody?

Jakie segmenty klientów mają największą wartość biznesową?

Które kampanie marketingowe osiągają najlepsze wyniki?

Którzy klienci najchętniej reagują na działania marketingowe?

Jak dochód oraz wiek wpływają na zachowania zakupowe?



**Źródło danych**

Wykorzystano zbiór danych Marketing Analysis z Kaggle obejmujące 2240 klientów. Dane były zawarte w pliku CSV w jednej tabeli.


Kolumny zawarte w danych:

ID- unikalny identyfikator klienta.

Year_Birth- rok urodzenia klienta.

Education- wykształcenie klienta.

Marital_Status- stan cywilny.

Income- roczny dochód gospodarstwa

Kidhome- liczba małych dzieci w domu.

Teenhome- liczba nastolatków w domu.

Dt_Customer- data dołączenia klienta do firmy.

Recency- liczba dni od ostatniego zakupu.

Complain- czy klient złożył reklamację.

MntWines- wydatki na wino.

MntFruits- wydatki na owoce.

MntMeatProducts- wydatki na mięso.

MntFishProducts- wydatki na ryby.

MntSweetProducts- wydatki na słodycze.

MntGoldProds- wydatki na produkty premium.

NumWebPurchases- liczba zakupów przez stronę.

NumCatalogPurchases- liczba zakupów przez katalog.

NumStorePurchases- liczba zakupów w sklepie stacjonarnym.

NumWebVisitsMonth- liczba wizyt na stronie w ostatnim miesiącu.

AcceptedCmp1- akceptacja kampanii nr 1

AcceptedCmp2- akceptacja kampanii nr 2

AcceptedCmp3- akceptacja kampanii nr 3

AcceptedCmp4- akceptacja kampanii nr 4

AcceptedCmp5- akceptacja kampanii nr 5

Response- czy klient zaakceptował ostatnią kampanię marketingową.

NumDealsPurchases- liczba zakupów dokonanych podczas promocji lub z wykorzystaniem rabatu.



**Przygotowanie danych**

Przed rozpoczęciem analizy przeprowadzono proces czyszczenia i transformacji danych w SQL oraz Power Query.


SQL:

-Dodanie kolumn i ich wypełnienie:

Age- wiek

Age Group- grupa wiekowa

Children- liczba dzieci

Total Spend- łączne wydatki

Total Purchases- łączna liczba zakupów

Average Purchases Value- średnia wartość zamówienia

Income Group- grupy według dochodu



POWER QUERY:

-Usunięcie kolumn: Year_Birth, Kidhome, Teenhome, z_costcontact, z_revenue.

-Zmiana typów danych.

-Wykonanie zaokrągleń.

Część rekordów nie zawierała informacji o dochodzie klientów. Zamiast usuwać te rekordy lub przypisywać arbitralną wartość, brakujące wartości pozostawiono jako NULL, a klientów zaklasyfikowano do kategorii Unknown. Pozwoliło to zachować ich pozostałe dane do dalszej analizy.



POWER BI:

-Utworzenie odpowiednich miar- wszystkie miary są dostępne w pliku miaryDAX.

-Dodanie tabel- Customer Spending(ID, Product Category, Spend), Campaign, Purchases Channel (ID, Purchase Channel, Purchases).

-Dodanie kolumny Campaign Response.

-Dodanie segmentacji RFM:

Recency (R)- Analiza czasu, jaki upłynął od ostatniego zakupu klienta.

Frequency (F)- Analiza częstotliwości dokonywania zakupów.

Monetary (M)- Analiza wartości wydatków klientów.


Na podstawie wyników klienci zostali przypisani do sześciu segmentów:

Champions- Najbardziej wartościowi klienci o wysokiej aktywności zakupowej i wysokiej wartości wydatków.

Loyal Customers- Klienci regularnie dokonujący zakupów i generujący wysoką wartość biznesową.

Potential Loyalists- Klienci z potencjałem do przejścia do grupy lojalnych klientów.

Regular Customers- Klienci o przeciętnej aktywności i średniej wartości zakupów.

At Risk- Klienci, którzy wcześniej byli aktywni, jednak od dłuższego czasu nie dokonują zakupów.

Hibernating- Klienci nieaktywni, o niskiej częstotliwości zakupów i niskiej wartości wydatków.



**Wykorzystane technologie:**

-SQL Server Managment Studio

-Microsoft Power BI Desktop

-Power Query

-DAX (Data Analysis Expressions)

-Model relacyjny danych

-Wizualizacjie interaktywne



**Dashboard**

Customer & Marketing Overview

Strona zapewnia ogólny przegląd klientów oraz wyników sprzedażowych.


KPI

•	Total Customer Spend

•	Total Customers

•	Average Customer Spend

•	Average Purchases per Customer

•	Last Campaign Acceptance



Zakres analizy

•	Average Spend by Income

•	Average Spend by Age Group

•	Customer Spend by Product Category

•	Purchases by Channel

•	Customer Value: Purchases vs Spend

•	Campaign Acceptance by Income



Kluczowe obserwacje

•	Klienci o najwyższych dochodach osiągają najwyższe średnie wydatki.

•	Kategoria Wines generuje największą część sprzedaży.

•	Największa liczba zakupów realizowana jest w kanale Store.

•	Wyższe dochody mają pozytywny wpływ na akceptację kampanii marketingowych. 



RFM Customer Segmentation

Strona prezentuje analizę segmentacji klientów i ich wartości biznesowej.


KPI:

•	Top Segment: Champions

•	Largest Segment: At Risk (24,7%)

•	Highest Spend Segment: At Risk

•	 Average Recency: 49,11 days



Zakres analizy

•	Customers by RFM Segment

•	Total Spend by RFM Segment

•	Average Days Since Last Purchase

•	Average Spend per Customer

•	Customer Share vs Spend Contribution

•	RFM Segment Performance



Kluczowe obserwacje

•	Segment At Risk stanowi największą grupę klientów.

•	Segment Champions odpowiada za znaczącą część przychodów mimo relatywnie niewielkiego udziału w liczbie klientów.

•	Klienci Hibernating generują minimalny udział w sprzedaży.

•	Najwyższą średnią wartość klienta osiąga segment Champions.


Marketing Campaign Analysis

Strona poświęcona ocenie skuteczności kampanii marketingowych.


KPI:

•	Overall Campaign Acceptance Rate: 7%

•	Best Performing Campaign: Last Campaign

•	Worst Performing Campaign: Campaign 2

•	Best Responding Segment: Champions



Zakres analizy

•	Last Campaign Acceptance Rate by RFM Segment

•	Campaign Acceptance Rate

•	Average Spend by Response

•	Campaign Performance Heatmap



Kluczowe obserwacje

•	Last Campaign osiągnęła najwyższy wskaźnik akceptacji (14,91%).

•	Campaign 2 była najmniej skuteczną kampanią.

•	Segment Champions reaguje na działania marketingowe najczęściej.

•	Klienci odpowiadający na kampanie wydają średnio niemal dwukrotnie więcej niż klienci nieodpowiadający na kampanie. 



**Najważniejsze wnioski**

Klienci o wysokich dochodach generują najwyższą wartość sprzedaży.

Największy udział w sprzedaży mają produkty z kategorii Wines.

Segment Champions generuje ponadprzeciętną wartość biznesową.

Segment At Risk wymaga działań retencyjnych.

Ostatnia kampania była najskuteczniejsza.

Respondenci kampanii osiągają znacznie wyższe średnie wydatki niż pozostali klienci.



**Rekomendacje biznesowe**

Wdrożenie kampanii retencyjnych dla segmentu At Risk- segment ten posiada wysoką wartość zakupową i powinien być objęty działaniami zapobiegającymi odpływowi klientów.

Rozwój programów lojalnościowych dla Champions- najbardziej wartościowi klienci powinni otrzymywać spersonalizowane oferty oraz dodatkowe benefity.

Intensyfikacja działań wobec Potential Loyalists- segment ten posiada potencjał do zwiększenia wartości i przejścia do grupy Loyal Customers.

Koncentracja kampanii na klientach o wysokich dochodach- grupy te wykazują najwyższy poziom wydatków oraz ponadprzeciętną responsywność.

Analiza mechanizmów wykorzystanych w Last Campaign- najskuteczniejsza kampania powinna stanowić punkt odniesienia przy planowaniu kolejnych działań marketingowych.


