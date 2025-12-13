# Break
`break` дозволяє достроково зупинити цикл. Kоли досягається оператор `break`, він негайно виходить з найвнутрішнішого циклу і починає виконувати код після циклу.

`for i in range(10):
	break
print(i)`
Це виводить `0`, оскільки `i` дорівнює `0` у першій ітерації циклу, а потім оператор `break` завершує цикл.

Це також працює з циклами `while`.

`while True:
	if can_harvest():
		break`

Цей код виконує цикл `while`, поки `can_harvest()` не стане `True`. 
Це має той самий ефект, що й

`while not can_harvest():
	pass`

У вкладених циклах `break` завжди виходить з найвнутрішнішого циклу.

`for i in range(10):
	for j in range(10):
		break
		print("this is never printed")
	print("this is printed 10 times")`