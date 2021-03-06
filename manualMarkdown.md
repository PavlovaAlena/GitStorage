# Описание синтаксиса языка разметки Markdown

1.Заголовки
----
______
Язык разметки Markdown поддерживает 2 стиля обозначения заголовков: подчеркивание (== или -- следующей строкой за заголовком) и выделение символом («#»). Например,

\#  Заголовок первого уровня

\### Заголовок третьего уровня

\###### Заголовок шестого уровня

Будет выглядеть следующим образом

#  Заголовок первого уровня
### Заголовок третьего уровня
###### Заголовок шестого уровня


2.Списки
---
___
Markdown поддерживает нумерованные и ненумерованные списки. Для формирования неупорядоченный списков используются такие маркеры, как звездочки, плюсы и дефисы. Все перечисленные маркеры могут использоваться взаимозаменяемо. Для формирования упорядоченных списков в качестве маркеров используются числа с точкой.

Упорядоченные списки выглядят следующим образом:

"1.	Первый"

"2.	Второй"

"3.	Третий"

Неупорядоченные списки выглядят следующим образом:

\* Элемент

\+ Еще элемент

\- Последний элемент

На экран выводится следующее:
1.	Первый
2.	Второй
3.	Третий

или
* Элемент
+ Еще элемент
- Последний элемент

Вложенный список

Для оформления вложенных неупорядоченных списоков, используют отступ в начале строк с элементами вложенного списка.

* Элемент
  * Элемент вложен


3.Выделение текста
---
___
Markdown воспринимает звёздочки «*» и символы подчёркивания «_» как признаки смыслового выделения текста. Т.о., текст, окруженный одинарными символами, выделяется курсивным шрифтом, а текст, окруженный двойными символами, выделяется полужирным шрифтом.

\*Пример*
*Пример*

\*\*Пример**
**Пример**

\*\*\*Пример***
***Пример***

4.Ссылки
---
___
Оформление в Markdown ссылки состоит из двух частей:
* [текст] — текст ссылки.
* (ссылка "Необязательная подсказка") — URL или путь до файла, на который делается ссылка.

\[Переход на GB](https://gb.ru/ "Нажми меня") будет отображаться: 
[Переход на GB](https://gb.ru/ "Нажми меня")

3.Изображения
---
___
В Markdown вставка изображений в документ состоит из следующих элементов:
* восклицательный знак;
* квадратные скобки, в которых указывается альтернативный изображению текст (он станет содержимым атрибута в элементе img);
* круглые скобки, содержащие URL-адрес или относительный путь изображения, а также (необязательно) всплывающую подсказку, заключённуе в двойные или одиночные кавычки.:

\!\[Альтернативный текст](/путь/к/изображению.jpg "Подсказка")

Будет: 

![Логотип git](/hqdefault.jpg "Это картинка git")