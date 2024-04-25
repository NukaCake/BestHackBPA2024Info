# BestHackBPA2024Info

В данной задаче нам необходимо обрабатывать третий тип вопросов (те, которые сотрудники техподдержки передают инженерам)
Выполнение задачи мы разделили на 3 основных этапа.
I этап (планирование и создание "скелета" решения)
Предположим, что внутренний мессенджер, через который передается информация - это телеграм.
Тогда нам нужно создать телеграм бота на python. Опишем, как будет происходить процесс:
Сотрудники Техподдержки авито, которым нужна консультация с программистами, заходят в этот бот и заполняют "Форму поддержки", отвечая на уточняющие вопросы бота. Например:
— СТАРТ
— Выберите категорию вопроса *появляется контекстное меню тг с вариантами "Завис статус заказа заказа", "Не вернулись деньги", "Другое" и т. д.*
— "Завис статус заказа заказа"
— Введите номер заказа
— 38914628
— Введите текущий статус заказа
— confirmed
— ...

Когда форма полностью заполнена, специалист её проверяет и подтверждает. Если похожий вопрос уже был решён, то бот предлагает готовое решение. Если же нет, то форма как сообщение отправляется в специально отведённый закрытый тг канал. Любой из программистов может выбрать любую проблему, в которой он разбирается, и в комментарии к посту с отправленной формой дать ответ / решение проблемы / сказать, что он исправил ошибку.

II этап (реализация алгоритма абработки данных)
Далее мы обработали json файл с примерами вопросов. Затем, используя модуль YAKE на python, мы выделили ключевые словосочетания, которые чаще всего встречаются в примерах. И затем, используя chatGPT, мы раскидали по общему содержанию эти словосочетания по 4м основным группам. 

III этап (интеграция алгоритма в работу бота и визуализация данных)
Мы разработали алгоритм бота, анализирующий поступающее сообщение сотрудника техподдержки и опредяляющий его в одну из 4х групп. Таким же образом мы обрабатываем данные из json'a и с помощью Mathplotlib визуализируем распределение сообщений по группам.


