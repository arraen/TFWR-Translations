# Continue
continue дозволяє зупинити поточну ітерацію циклу і перейти до наступної ітерації найвнутрішнішого циклу.

`for i in range(10):
	continue
    print("this is never printed")`

Це виконує всі `10` ітерацій циклу, але оператор `print` після `continue` завжди пропускається.

Це також працює з циклами `while`.

`while True:
	if not can_harvest():
		continue
    
    harvest()`

Цей код викликає `harvest()` тільки тоді, коли `can_harvest()` дорівнює `True`.
Він має той самий ефект, що й

`while True:
	if can_harvest():
		harvest()`

У вкладених циклах `continue` завжди впливає на найвнутрішніший цикл.

`for i in range(10):
	for j in range(10):
	    print("це надруковано 100 разів")
		continue
		print("це ніколи не друкується")
	print("це надруковано 10 разів")`