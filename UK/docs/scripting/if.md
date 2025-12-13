# If
Ви можете використовувати if, elif та else для умовного виконання коду.

`if condition1:
	do_a_flip()
elif condition2:
	harvest()
else:
	do_a_flip()
	harvest()`

## Синтаксис
`if` дозволяє виконувати код тільки в тому випадку, якщо деяка умова є `True`. Вони схожі на цикл `while`, який не повторюється.
`if` приймає умову, як і цикл `while`, і виконує блок коду if, якщо умова оцінюється як `True`:

`#do a flip if condition is True
if condition:
	do_a_flip()`

Ви також можете додати `else` після if, що визначає код, який буде виконано, якщо умова має значення `False`.

Виконайте перевертання, якщо `умова` є істинною, інакше зберіть урожай.
`if condition:
	do_a_flip()
else:
	harvest()`

`elif` — це скорочення від else if.

`if condition1:
	#a
else:
	if condition2:
		#b
	else:
		#c`

можна скоротити до:

`if condition1:
	#a
elif condition2:
	#b
else:
	#c`
