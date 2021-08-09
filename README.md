# L_S_I
## Парсинг данных о курсах
### Coursera
Из кода страниц каталога курсов берем (BeatifulSoup) сами названия всех курсов, ссылки на каждый и авторов (вузы). Для получаения осталной информации такой как язык, рейтниг и тд необходимо заходить непосредственно на страницу какждого курса по отдельности. Поэтому проверка на язык проводится с помощью библиотеки langdetect с предварительно усеченным пулом определяемых языков (среди курсов нет, к примеру, болгарских, поэтому можно заведомо исключить его из потенциальных языков. Как выяснилось, некоторые русские слова библиотека с увернностью 0.99 относит к тому же Болгарскому). /

для до-пасинга...
### Stepik
С API-страниц берем названия всех курсов, сслыки на них, а также язык (не все языки указаны там корректно) для отбора только русскоязычных курсов. Запоминается номер последней страницы каталога, так регулярный до-парсинг начинается с нее: производится проверка на появление новых курсов непосредственно на этой странице, затем проверяется наличие следующих страниц и сбор данных с них.
### OpenEdu
Весь каталог расположен на одной странице, новые курсы, как мы заметили, добавляются не в конец списка, а в произвольное место, поэтому для обновления списка курсов необходимо парсить эту страницу заново.
## Семантический поиск, LSI
### TF_IDF
Пробовал так же BM25, ощутимой разницы не наблюдалось
