# Таблиця лідерів
Якщо ви зайшли так далеко, ви подолали багато випробувань. Але чи вирішили ви їх ефективно?
Ви можете змагатися з іншими гравцями в різних таблицях лідерів за найбільш ефективні методи фермерства.

Ви можете почати забіг на таблицю лідерів, викликавши `leaderboard_run(leaderboard, filename, speedup)`.
Це запускає симуляцію(docs/unlocks/simulation.md), подібну до `simulate()`, за винятком того, що початкові умови є фіксованими. Кожна категорія таблиці лідерів має різні умови старту та успіху.

Забіг вважається успішним, якщо умова успіху є `True`, коли симуляція закінчується.

Симуляція НЕ закінчиться автоматично, коли ціль досягнута. Ви повинні переконатися, що програма завершується.
Якщо забіг успішний, ваш час буде додано до таблиці лідерів.

Щоб зменшити дисперсію, усі забіги повинні тривати щонайменше 2 години (Ви можете прискорити це, тому це не займе так багато часу в реальності). Якщо забіг завершено раніше, він повторюватиметься, доки загальний час не досягне 2 годин. Середнє значення всіх забігів потім завантажується як ваш рахунок.

Ось приклад налаштування, яке дозволить вам потрапити до таблиці лідерів по сіну.
![](LeaderboardSetup400)

## Найшвидше скидання
Найшвидше скидання — найпрестижніша категорія. Повністю автоматизуйте гру від однієї ділянки ферми до розблокування таблиць лідерів знову.

Вам не потрібно розблоковувати все, просто спробуйте розблокувати `Unlocks.Leaderboard` якомога швидше.

Пам'ятайте, що ви можете використовувати `num_unlocked(unlock) > 0`, щоб перевірити, чи щось розблоковано, і ви можете використовувати `get_cost()` на unlocks, щоб побачити їхню вартість і автоматично фармити потрібні предмети.

Виклик функції:
`leaderboard_run(Leaderboards.Fastest_Reset, filename, speedup)`

Еквівалентна симуляція:
`unlocks = {}
items = {}
globals = {}
#від'ємне значення seed означає випадковий seed
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Умова успіху:
`num_unlocked(Unlocks.Leaderboard) > 0`

## Лабіринт
Почніть з усім розблокованим і нафарміть `9863168` золота якомога швидше. Це саме та кількість золота, яку ви заробите, повторно використавши один лабіринт 32x32 `300` разів.

Виклик функції:
`leaderboard_run(Leaderboards.Maze, filename, speedup)`

Еквівалентна симуляція:
`unlocks = Unlocks
items = {Items.Weird_Substance : 1000000000, Items.Power: 1000000000}
globals = {}
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Умова успіху:
`num_items(Items.Gold) >= 9863168`

## Динозавр
Почніть з усім розблокованим і нафарміть `33488928` кісток якомога швидше. Це саме та кількість кісток, яку ви отримаєте, якщо заповните площу 32x32 хвостом динозавра.

Виклик функції:
`leaderboard_run(Leaderboards.Dinosaur, filename, speedup)`

Еквівалентна симуляція:
`unlocks = Unlocks
items = {Items.Cactus : 1000000000, Items.Power: 1000000000}
globals = {}
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Умова успіху:
`num_items(Items.Bone) >= 33488928`

## Інші таблиці лідерів ресурсів
Кожна рослина має власну таблицю лідерів для фарму саме цієї рослини якомога швидше. Ви починаєте з усіма розблокуваннями, ресурсами, необхідними для вирощування рослини, та великою кількістю енергії. Мета — нафармити встановлену кількість ресурсу, що виробляється рослиною.

Як завжди, ви повинні переконатися, що ваша програма завершується, коли ви досягаєте мети. Забіг не закінчується, доки програма не завершиться, навіть якщо ціль досягнута.

### `Leaderboards.Cactus`
`leaderboard_run(Leaderboards.Cactus, filename, speedup)`
Умова успіху: `num_items(Items.Cactus) >= 33554432`

### `Leaderboards.Sunflowers`
`leaderboard_run(Leaderboards.Sunflowers, filename, speedup)`
Умова успіху: `num_items(Items.Power) >= 100000`

### `Leaderboards.Pumpkins`
`leaderboard_run(Leaderboards.Pumpkins, filename, speedup)`
Умова успіху: `num_items(Items.Pumpkin) >= 200000000`

### `Leaderboards.Wood`
`leaderboard_run(Leaderboards.Wood, filename, speedup)`
Умова успіху: `num_items(Items.Wood) >= 10000000000`

### `Leaderboards.Carrots`
`leaderboard_run(Leaderboards.Carrots, filename, speedup)`
Умова успіху: `num_items(Items.Carrot) >= 2000000000`

### `Leaderboards.Hay`
`leaderboard_run(Leaderboards.Hay, filename, speedup)`
Умова успіху: `num_items(Items.Hay) >= 2000000000`

## Таблиці лідерів для одного дрона
Існують також таблиці лідерів для фарму з одним дроном. Ви отримуєте лише один дрон і ферму 8x8, і вам потрібно нафармити певну кількість ресурсів якомога швидше.

### `Leaderboards.Maze_Single`
`leaderboard_run(Leaderboards.Maze_Single, filename, speedup)`
Умова успіху: `num_items(Items.Gold) >= 616448`

### `Leaderboards.Cactus_Single`
`leaderboard_run(Leaderboards.Cactus_Single, filename, speedup)`
Умова успіху: `num_items(Items.Cactus) >= 131072`

### `Leaderboards.Sunflowers_Single`
`leaderboard_run(Leaderboards.Sunflowers_Single, filename, speedup)`
Умова успіху: `num_items(Items.Power) >= 10000`

### `Leaderboards.Pumpkins_Single`
`leaderboard_run(Leaderboards.Pumpkins_Single, filename, speedup)`
Умова успіху: `num_items(Items.Pumpkin) >= 10000000`

### `Leaderboards.Wood_Single`
`leaderboard_run(Leaderboards.Wood_Single, filename, speedup)`
Умова успіху: `num_items(Items.Wood) >= 500000000`

### `Leaderboards.Carrots_Single`
`leaderboard_run(Leaderboards.Carrots_Single, filename, speedup)`
Умова успіху: `num_items(Items.Carrot) >= 100000000`

### `Leaderboards.Hay_Single`
`leaderboard_run(Leaderboards.Hay_Single, filename, speedup)`
Умова успіху: `num_items(Items.Hay) >= 100000000`
