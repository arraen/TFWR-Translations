# Цикл For
Цикл `for` працює так само, як у Python. (У деяких мовах називається циклом foreach, не плутати з циклом for у стилі C, що є іншою річчю).

`for i in sequence:
	#do something with i`

Подібно до циклу `while`, цикл `for` також неодноразово викликає блок коду. Замість циклу на основі умови, він виконує тіло циклу один раз для кожного елемента в послідовності.

## Синтаксис
Цикл for виглядає так:

`for variable_name in sequence:
	#code block`

`variable_name` може бути будь-яким ім'ям, яке ви виберете. Це змінна, яка зберігає поточний елемент у послідовності. `sequence` має бути значенням, яке можна ітерувати, наприклад, діапазоном чисел. Блок коду виконується для кожного елемента, при цьому змінна циклу присвоюється цьому елементу.

## Sequences (Послідовності)
[Ranges](functions/range)      <unlock=lists>[Lists](docs/scripting/lists.md)      </unlock><unlock=functions>[Tuples](docs/scripting/tuples.md)      </unlock><unlock=dicts>[Dictionaries](docs/scripting/dicts.md)      </unlock><unlock=sets>[Sets](docs/scripting/sets.md)</unlock>

## Приклад
`for i in range(5):
    harvest()`

Цей цикл виконує тіло фіксовану кількість разів. Це по суті те саме, що написати

`i = 0
harvest()
i = 1
harvest()
i = 2
harvest()
i = 3
harvest()
i = 4
harvest()`

Отже, він викликає `harvest()` 5 разів.

Дивіться також [Break](docs/scripting/break.md) та [Continue](docs/scripting/continue.md)
