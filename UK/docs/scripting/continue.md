# Continue
`continue` дозволяє зупинити поточну ітерацію циклу та перейти до наступної ітерації найглибшого циклу.

`for i in range(10):
	continue
    print("this is never printed")`

Це виконує всі `10` ітерацій циклу, але `print` після `continue` завжди пропускається.

Він також працює з циклами `while`.

`while True:
	if not can_harvest():
		continue
    
    harvest()`

Цей код викликає `harvest()` лише тоді, коли `can_harvest()` є `True`.
Це має такий самий ефект, як

`while True:
	if can_harvest():
		harvest()`

У вкладених циклах `continue` завжди впливає на найглибший цикл.

`for i in range(10):
	for j in range(10):
	    print("this is printed 100 times")
		continue
		print("this is never printed")
	print("this is printed 10 times")`
