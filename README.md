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

=======================================
=======================================
<h2>Результаты доразметки</h2>

<h3>Совсем дополнительная разметка от LLM</h3>
"dirty new items*.parquet" - Грязный вариант, но многократность генерации, возможно, дает антигаллюционный эффект. (Если галлюцинация повторяется, то галлюцинация ли она?)

<h3>Доразметка из unlabeled</h3>
Нетути. Йок (на тюркский языках означает «нет» в значении отсутствия).
