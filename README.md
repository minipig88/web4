# web4
Работа с базой данных уже налажена, так что перейдем к самой популярной реализации JPA - Hibernate.

Сегодня мы будем симулировать работу автосалона. В нашем автосалоне будут находиться машины, описанные классом `Car` и отчеты по продажам за день - класс `DailyReport`.

Html страницы нам не потребуются, приложение будет RESTful. Скачайте приложение по ссылке.

Каждый день в салон поступают машины разных марок. Машин одной марки может быть не более 10ти штук. Покупатели могут запросить список имеющихся машин по url `/customer` используя GET запрос.  Купить машину можно отправив POST запрос на тот же url, и передав в параметрах марку машины, название машины и госномер.

Новые поступления происходят в течение дня. Каждое новое поступление - это POST запрос на url `/producer`. На POST запрос, отправленный на url `/producer` с параметрами, по названию аналогичными полям класса `Car`, нужно ответить 200-ым статусом, если машина принята, и 403-ым, если нет.

Смена дней происходит при отправке GET запроса на `/newday`. После смены дня, салон обязан сформировать отчет, в котором содержится суммарная выручка за день и количество проданных машин.

Начальство может потребовать отчет GET запросом по url `/report/last` за прошедший день, либо же за все дни, отправив GET запрос на `/report/all`.  Так же есть возможность удалить все данные об отчетах и машинах, отправив DELETE запрос на url `/report`.

Примечания:
1) Для решения задачи вы можете использовать любые дополнительные классы и методы.
2) Отличным решением будет считаться такое решение, в котором большая часть логики завязана на взаимодействии с базой данных.
3) По проекту разбросаны фрагменты кода, опираясь на которые, вы можете дописать недостающую логику.
4) Для передачи данных в `responce` вам нужно использовать библиотеку GSON. 
5) Обратите внимание, что номерной знак не является уникальным идентификатором

Последние цифры хэша - `...a8c4`
