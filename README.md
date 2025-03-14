# data-fusion-2025-competitions1
Data Fusion Contest 2025 - <a href='https://ods.ai/competitions/data-fusion2025-labelcraft' target='_blank'>Задача 1 "Label Craft"</a>
====================================

<b>ОСТОРОЖНО! Возможны галлюцинации!</b>

0001.ipynb - наброски для дополнительной разметки.

0002.ipynb - первая итерация для одного уровня. 

0002a.ipynb - формирование дополнительного списка

====================

0003.ipynb - фильтрация дополнительного списка, сформированного более болтливой LLM, с использованием другой менее сильной LLM. 
Очистка от галлюцинаций.  (Если у <del>ChatGPT и DeepSeek</del> Пети и Васи <del>сны</del> галлюцинации одинаковые, то … . Либо есть <del>утечка</del> связь между Петей и Васей, либо это не галлюцинации.)

====================

Возможные сюрпризы:
1) Категория может быть пустой не только на labeled, но и на unlabeled.
2) Дважды пустая категория может быть не одна.
3) Пустышками могут оказаться самые перспективные.

====================

0005.ipynb - быстро, минимально.  

====================

Искать то что выгодно или извлекать выгоду из того что мешается под ногами?<br>
Можно доразметить: <br>
unlabeled = pl.read_parquet("unlabeled_train.parquet").rename({"source_name":"name"})<br>
lst=["cd)","lp)","sp)","ep)"]<br>
unlabeled.filter(pl.col("name").str.to_lowercase().str.contains_any(lst))

====================

dirty new items4?.parquet - дополнение для категорий 4 уровня<br>
dirty new items3?.parquet - дополнение для категорий 3 уровня<br>
dirty new items2?.parquet - дополнение для категорий 2 уровня<br>

====================

0007.ipynb - заход на атрибуты

====================

0008p.ipynb - раз катбуст, два катбуст

====================

0009.ipynb - окромя бустингов. (XC - eXtreme Classification)

====================

Trivialproductname

====================

pymorphy, pymystem, ... 

====================

0008a.ipynb - Оценка (до кросс-валидации и optuna-тюнинга)

====================

Отипизация атрибутов

====================

Продолжение следует..... Особенно если будут звезды.

=======================================
=======================================
<h2>Результаты доразметки (предварительные)</h2>

<h3>Совсем дополнительная разметка от LLM</h3>
"dirty new items*.parquet" - Грязный вариант, но многократность генерации, возможно, дает антигаллюционный эффект. (Если галлюцинация повторяется, то галлюцинация ли это?)

<h3>Самая быстрая дополнительная разметка</h3>
0005.ipynb - не оставляет пустых категорий. 

<h3>Доразметка из unlabeled</h3>
<del>Нетути. Йок (на тюркский языках означает «нет» в значении отсутствия).</del><br>
dop460_3of3_18859.parquet - доразметка категории 460. 18859 строк. Уровень доверия 3 из 3.<br>
dop460_23of3_39313.parquet - доразметка категории 460. 39313 строки. Уровень доверия 2 из 3 и выше.<br>
dop460_123of3_49292.parquet - доразметка категории 460. 49292 строки. Осторожно! Уровень доверия 1 из 3 и выше.<br>
