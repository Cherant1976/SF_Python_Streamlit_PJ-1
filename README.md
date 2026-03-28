# <center> Учебный проект курса Python-разработка платформы [Skillfactory](http://skillfactory.ru). </center>

## Оглавление  
[1. Описание учебного проекта](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Описание-учебного-проекта)   
[2. Запуск приложения](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Запуск-приложения)  
[3. Используемые библиотеки python](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Используемые-библиотеки-python)  
[4. Структура страницы приложения](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Структура-страницы-приложения)  
[5. Вкладка Работа с таблицей](https://github.com/Cherant1976SF_Python_Streamlit_PJ-1#Вкладка-Работа-с-таблицей**)  
[6. Вкладка Статистические данные](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Вкладка-Статистические-данные)  
[7. Вкладка Прогноз](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Вкладка-Прогноз)   


### Описание учебного проекта   
В проекте реализована обработка данных погоды из предоставленного файла <span style="font-size:18px;">**weather.db**</span>, построение статистических графиков и построение графика прогноза погоды.

:arrow_up:[к оглавлению](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Оглавление)


### Запуск приложения
* Для работы приложения испоьзуются код написанный в шести файлах
    * **weather.db** файл с данными (**путь:data\weather.db**)    
    * **app.py** основной модуль для запуска код
    * **show_data.py** в файле код, отвечающий за отображение таблицы
    * **show_statistic.py** в модуле код, отвечающий за изображение статистических графиков
    * **predict.py**  в модуле код, отвечающий за изображение прогноза графиков
     * **default_data.py**  модуль с сзаданными значениями, используемыми в других модулях

* Для запуска приложения нужно сохранить указанные файлы в одной папке (файл **weather.db** должен быть в папке **data** по отношению к расположению других файлов) и в этой папке в терминале запустить команду 
**streamlit run main.py**

:arrow_up:[к оглавлению](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Оглавление)


### Используемые библиотеки *python*:  
```python
import streamlit as st
import sqlite3
import polars as pl
import pandas as pd
import numpy as np
from datetime import datetime, timedelta, time
import plotly.express as px
```

:arrow_up:[к оглавлению](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Оглавление)


### Структура страницы приложения
На странице есть вкладки **Работа с таблицей**, **Статистические данные** и **Прогноз**.  

:arrow_up:[к оглавлению](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Оглавление)


### Вкладка **Работа с таблицей**.
На вкладке можно выбрать столбцы таблицы, для которых будут сформированы соответсвующие им фильтры. Ниже на вкладке отображается Таблица с учётом применённых фильтров. Для удобства можно настроить просмотр таблицы. Можно настроить ***Число строк на странице*** и ***Номер страницы просмотра***

![ Вкладка **Работа с таблицей**](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1/blob/master/Screenshots/tab_work_table.jpg)

:arrow_up:[к оглавлению](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Оглавление)


### Вкладка **Статистические данные**.
На вкладке есть возможность выбора **городов**, **параметра погоды** и **вида графика** для отображения статистических данных.

![Вкладка **Статистические данные**](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1/blob/master/Screenshots/tab_statistic.jpg)

:arrow_up:[к оглавлению](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Оглавление)


### Вкладка **Прогноз**.
На вкладке есть возможность выбора **города**, **параметра погоды**,  **количество дней, используемых для построения прогноза**, **дату прогноза** и **количество дней, на которое нужно сделать прогноз**.  
Прогнозные значения, соответсвующие заданным параметрам, для удобства сравнения отображаются на графике вместе с фактическими данными.  
Для построения прогноза испозуется Линейная регрессия ([Метод Наименьших Квадратов](https://ru.wikipedia.org/wiki/Метод_наименьших_квадратов?ysclid=mn9xs1p2uf30869991)), построенная на данных [скользящей средней](https://ru.wikipedia.org/wiki/Скользящая_средняя). Период скольжения 7 дней задан в модуле **default_data.py**.

![Вкладка **Прогноз**](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1/blob/master/Screenshots/tab_predict.jpg)

:arrow_up:[к оглавлению](https://github.com/Cherant1976/SF_Python_Streamlit_PJ-1#Оглавление)