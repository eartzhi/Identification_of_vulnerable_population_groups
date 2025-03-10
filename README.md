# Итоговый проект. “Определение уязвимых групп населения”

## Оглавление   
[1. Описание проекта](#оглавление)  
[2. Какой кейс решаем?](#какой-кейс-решаем)  
[3. Краткая информация о данных](#краткая-информация-о-данных)  
[4. Этапы работы над проектом](#этапы-работы-над-проектом)  
[5. Результат](#результаты)    

### Описание проекта    
Итоговый проект первого года обучения "Определение уязвимых групп населения".

Файл main.ipynb - итоговый расчет.

Согласно опросу «инФОМ» от декабря 2021 года, у 27 % россиян хватает денег только на еду, а ещё 9 % не могут позволить себе полноценное питание. Эти люди особенно внимательно следят за ценами, а темп роста цен на продукты обычно превышает средний темп инфляции. При этом Росстат считает, что расходы на продукты питания должны составлять примерно 36 % от среднемесячных расходов россиянина (ещё около 10 % приходится на услуги ЖКХ и жильё, 4 % — на лекарства). До 2021 года «черта бедности» (жизнь на сумму ниже прожиточного минимума) в России определялась стоимостью минимальной продуктовой корзины. В том же году правительство «отвязало» уровень бедности от цен на базовые продукты: с 2021 года прожиточный минимум рассчитывается как 44.2 % от медианного дохода граждан РФ за прошлый год.

:arrow_up:[к оглавлению](#оглавление)


### Какой кейс решаем?    
- кластеризовать регионы России и определить, какие из них наиболее остро нуждаются в помощи малообеспеченным/неблагополучным слоям населения;
- описать группы населения, сталкивающиеся с бедностью;
- определить:
    - влияет ли число детей, пенсионеров и других социально уязвимых групп на уровень бедности в регионе;
    - связаны ли уровень бедности/социального неблагополучия с производством и потреблением в регионе;
    - какие ещё зависимости можно наблюдать относительно социально незащищённых слоёв населения.

**Метрика качества**     
Это исследовательская задача и как таковой метрики качества у проекта нет.

В качестве критерия качества модели кластеризации выбрана метрики:
Коэффициент силуэта, Мера того, насколько объект похож на объекты из своего собственного кластера по сравнению с объектами из других кластеров.


**Что практикуем**     
- Использовать основные конструкции и структуры данных Python.
- Получать данные из веб-источников или по API.
- Анализировать и предобрабатывать данные с помощью специализированных библиотек (Pandas, Seaborn, Matplotlib).
- Создавать модели для решения DS-задач с помощью машинного обучения и оценивать их качество.
- Применять методы математического анализа, линейной алгебры, статистики и теории вероятности для обработки данных.
- Строить модели с использованием временных рядов.
- Применять алгоритмы для рекомендательных систем.
- Интегрировать решение в продакшн.


### Краткая информация о данных

Все использованые в исследовании данные выложены в репозитории вместе с проектом.  


Данные :
- child_mortality_rural_1990_2021.xls — число умерших на первом году жизни детей за год, по всем регионам, в сельской местности.
- child_mortality_urban_1990_2021.xls — число умерших на первом году жизни детей за год, по всем регионам, в городской местности.
- disabled_total_by_age_2017_2022.csv — число людей с инвалидностью по регионам, по месяцам, по возрастным группам.
- morbidity_2005_2020_age_disease.xls — заболеваемость на 100 тыс. человек населения, по возрастным группам и группам заболеваний.
- poverty_percent_by_regions_1992_2020.csv — процент людей, живущих за чертой бедности (с денежными доходами ниже величины прожиточного минимума), оценка за год по регионам. 
- welfare_expense_share_2015_2020 — расходы на социальную политику от общих расходов бюджета региона, % в год*.
- cash_real_income_wages_2015_2020 — среднедушевые и реальные денежные доходы населения, номинальная и реальная начисленная зарплата, по регионам*.
- poverty_socdem_20*.xls — распределение малоимущего населения по социально-демографическим группам (дети, трудящиеся, пенсионеры) за 2017–2020 гг., по регионам.
- housing_2020 — характеристика жилищных условий домохозяйств. Оценка домохозяйствами состояния занимаемого ими жилого помещения, обследование 2020 года*.
- population.xlsx — численность населения по регионам и федеральным округам на 1 января каждого года за 1999–2022 гг.
- gross_regional_product_1996_2020.xls — валовой региональный продукт на душу населения, в рублях.
- regional_production_*_*.csv — объём отгруженных товаров собственного производства или работ/услуг, выполненных собственными силами, по видам деятельности за 2005–2016 гг., 2017–2020 гг. (в тысячах рублей, значение показателя за год, полный круг).
- retail_turnover_per_capita_2000_2021.xls — оборот розничной торговли на душу населения, в рублях.

Папка crimes — сведения о преступлениях, совершённых отдельными
категориями лиц за 2016–2022 гг., по месяцам, регионам, категориям лиц,
категориям преступлений:
1. В папке содержатся файлы о расследованных преступлениях (число
преступлений).
2. Файлы представлены в том виде, в котором их предоставляет
Генпрокуратура. С ними требуется поработать, чтобы привести их в
пригодный для анализа вид.
Пример представления:



:arrow_up:[к оглавлению](#оглавление)

### Этапы работы над проектом  
Работа разбита на 6 этапов:

1. Сбор данных
2. Предобработка и очистка данных
3. Разведывательный анализ данных  
    3.1. Основной датасет  
    3.2. Дополнительный датасет (преступность)   
4. Построение модели  
    4.1. Kmeans  
    4.2. GaussianMixture  
    4.3. AgglomerativeClustering  
    4.4. Итоговая кластеризация  
5. Итоговый анализ данных
    5.1. Бедность  
    5.2. Влияние благополучности региона на детей  
    5.3. Влияние благополучности региона на пенсионеров  
    5.4. Влияние производства на благополучие региона  
    5.5. Влияние благополучия региона на преступность  
    5.6. Влияние расходов на социальную политику на благополучие региона  
    5.7. Влияние благополучия региона на жилищные условия  
6. Итоговые выводы


:arrow_up:[к оглавлению](#оглавление)


### Вывод:  
Рамках работы выб выявлен кластер неблагополучных регионов, требующих финансовых вливаний для улучшения условий жизни населения. Неблагополучными за 2020 год можно признать следующие регионы: Карачаево-черкесская республика, Курганская обл., Псковская обл., Чувашская республика.  
Как следствие низких доходов населения и высокого уровня бедности в этих регионах происходит рост тяжких и особо тяжких преступлений и падение рождаемости. Сами низкие доходы населения порождены предположительно низким уровнем производства и оборотом розничной торговли в регионе. Увеличение процента средств, выделяемых на социальное развитие не оказывает сильного влияния (или не успел оказать) на уровень бедности.  
Для улучшения ситуации в регионах требуется увеличение уровня производств, который моожет проявиться только как вложение средств в производства в регионах.  

:arrow_up:[к оглавлению](#оглавление)
