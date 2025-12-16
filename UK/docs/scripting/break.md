# Break
`break` дозволяє зупинити цикл достроково. Коли досягається ключове слово `break`, він негайно виходить із найглибшого циклу та продовжує виконання коду після нього.

`for i in range(10):
	break
print(i)`
Це надрукує `0`, тому що `i` дорівнює `0` у першій ітерації циклу, а потім `break` завершує цикл.

Він також працює з циклами `while`.

`while True:
	if can_harvest():
		break`

Цей код виконує цикл `while`, доки `can_harvest()` не стане `True`.
Це має такий самий ефект, як

`while not can_harvest():
	pass`

У вкладених циклах `break` завжди виходить із найглибшого циклу.

`for i in range(10):
	for j in range(10):
		break
		print("this is never printed")
	print("this is printed 10 times")`
