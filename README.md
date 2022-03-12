## Как запустить
1. В Google Chrome открываем https://www.tinkoff.ru/maps/atm/
2. Открыть DevTools: Правой кнопкой вне карты, Inpsect
3. Переходим на вкладу Sources/Snippets
4. +New Snippet, копируем код из https://github.com/dgarkavenko/usd_atm_in_the_area/blob/main/snippet, сохраняем (Command+S/Ctrl+S) 
5. Правой кнопкой по новому сниппету: Run
6. Оставить страницу открытой в бэкграунде.

Через минуту придет нотификация со всеми доступными банкоматами.
Дальше буду приходить нотификации, в двух случаях:
  1. когда будут появляются новые банкоматы c более чем $100 (можно поменять в коде: var min_usd_amount = 100;)
  2. когда количество $ в банкомате увеличится (то же ограничение > $100).

При получении нотификации, переходим на страницу где запущен сниппет. Новые банкоматы проверяются каждые 90 секунд и добавляются в лог.

## Если нужно сменить зону поиска
1. Перезагрузить страницу, если сниппет был запущен (Ctrl+R)
2. Настроить карту на нужный масштаб и позицию. Указать валюту поиска.
3. В DevTools на вкладке Network найти в списке последний запрос clusters. Правой кнопкой Copy -> Copy as fetch
4. Заменить соответствующий код в сниппете.
