Формат BM
=========

Файл, предназначенный для хранения изображений.

Расширение - ``bm``.

Структура файла
---------------

Структура файла представлена в таблице 1. Целые числа хранятся в Little Endian 
(LE).

Таблица 1
~~~~~~~~~

+----------+-------------------------+
| Смещение | Тип                     | 
+==========+=========================+
| 0x00     | MAGIC константа         |
+----------+-------------------------+
| 0x04     | Ширина (uint16)         |
+----------+-------------------------+
| 0x06     | Высота (uint16)         |
+----------+-------------------------+
| 0x08     | Данные                  |
+----------+-------------------------+

MAGIC
-----
Константа для идентификации типа файла 0х534b42d4 ("SKBM").

Данные
------

Размер поля = ``ширина`` * ``высота`` * 2.

Растр хранится в виде 16 бит на точку в формате ``RRRRRGGG GGGBBBBB`` 
(5 бит красный, 6 - зелёный, 5 - синий), начиная с верхней строки. 

