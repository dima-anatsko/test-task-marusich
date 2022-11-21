## Это CLI приложение, которое:

1) Получает на вход N строк.
2) Итерируется по этим строкам и определяет, является ли эта строка ссылкой или нет.
3) Если эта строка не ссылка, выводится уведомление: Строка "X" не является ссылкой.
4) Если является ссылкой, то
	1) Приложение должно определить какие методы доступны по этой ссылке
		1) Проверяются все http методы.
		2) Доступным считается метод, обработка которого завершилась не 405 ошибкой.
	3) Передаваемые данные и ошибки от сервера не важны.
	4) Выполнив запрос приложение сохраняет код ответа.
6) Результатом работы приложением будет словарь, состоящий из ссылок и информации о доступных методах.


```json
// Пример консольного ответа от программы
{
	"https://google.com": {
		"GET": 301,
	},
	"https://www.facebook.com": {
		"GET": 200,
		"OPTIONS": 200,
	}
}
```
## Покрытие тестами:

```commandline
Name                    Stmts   Miss  Cover   Missing
-----------------------------------------------------
source/__init__.py          0      0   100%
source/url_checker.py      42     13    69%   56-66, 70-72, 76
tests/__init__.py           0      0   100%
tests/app_test.py          21      0   100%
-----------------------------------------------------
TOTAL                      63     13    79%
```
## Затраченное время

Время выполнения задания: 8ч.
