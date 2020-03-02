# Сorewar
Давным-давно,
в далекой-далекой галактике...

<img width="1435" alt="Screen Shot 2020-03-02 at 15 45 50" src="https://user-images.githubusercontent.com/61384057/75677612-cd1e2f00-5c83-11ea-8085-eecb9cf5d2e5.png">

# History
Отрывок из википедии.


Бой в памяти (англ. Core War) — разновидность компьютерной игры «Дарвин», разработанная Александром К. Дьюдни. Помогал разрабатывать игру Дэвид Джонс, студент кафедры информатики университета Западной Онтарио, где преподавал Дьюдни.

В данной игре игроки разрабатывают компьютерные программы на специальном языке программирования, похожем на ассемблер — Redcode. Программы размещаются в циклически замкнутом участке памяти (core), состоящей из 8000 ячеек и зацикленной в кольцо. Каждая команда занимает одну ячейку. Redcode-программы работают под управлением MARS (англ. Memory Array Redcode Simulator — Симулятор Массива Памяти Redcode). Программы загружаются по случайным адресам в памяти.

Каждая программа (начиная со стандарта ICWS'1988) может иметь несколько активных потоков, причём поток может порождать другие потоки с помощью инструкции SPL. Потоки, принадлежащие одной программе, выполняются по очереди, поэтому скорость их выполнения обратно пропорциональна количеству потоков. Поток завершается, если пытается выполнить некорректную инструкцию. Программа, все потоки которой завершились, считается проигравшей.

Статьи, посвящённые игре, публиковались в журнале Scientific American в 1984—1987, в колонке Computer Recreations (Занимательный компьютер). Игра вызвала значительный интерес у читателей, и впоследствии было основано международное общество International Core War Society (ICWS) со штаб-квартирой в США и отделениями во многих странах мира, включая СССР.

ICWS проводила ежегодные международные турниры, начиная с 1986 года. Соревнования проводились по круговой системе. Первые два турнира были по сути чемпионатами Северной Америки. Турнир же 1988 года, проводившийся по новому стандарту игры ICWS'88, привлёк многочисленных участников из разных стран и стал де-факто первым чемпионатом мира. Победителями стали Евгений Лилитко (СССР) – 1-ое место, Luca Crosara (Италия) – 2-ое место и третьим стал Douglas McDaniels (США)[1]. Ещё один советский участник – Александр Бурцев занял пятое место. В настоящее время соревнования проводятся в основном по системе "King of the hill".

Разработать «Бой в памяти» Дьюдни побудила история о двух противоборствующих программах CREEPER и REAPER (см. компьютерный вирус). Обстоятельства разработки CREEPER/REAPER дошли до Дьюдни в несколько искажённом виде, так, по словам Р. Томлинсона, ни заражения ARPANet, ни «поединка» между двумя программами в действительности не было.

# Введение в курс дела
Небольшай экскурс: файлы

1) .s - файлы с кодом псевдо-ассемблера. Так называемый файл-чемпион, который будет потом биться на арене виртуальной машины

2) .cor - файлы с байткодом.

После выполнения мейка скомпилируются такие исполняемые файлы как asm(перевод файлов из разрешения *.s в *.cor), dasm(перевод из *.cor в *.s) и corewar(виртуальная машина с ограниченной и зацикленной областью памяти в виде карты, где и происходит вся битва)

# Цель
..программы определить игрока, который продержался в битве дольше всех.

# Флаги программы
Флаги имеет только лишь corewar:

1)-n[номер игрока] - Так как игроки выполняют свои действия последовательно, то последовательность первого выполнения будет подобна той хронологии, с которой будут подаваться игроки. И чтобы искусственно изменять хронологию, не меняя порядок расположения аргументов, можно возпользоваться этим флагом. Также витруальная машина принимает от 1-го и до 4-х игроков.

2)-d [номер цикла] - Выводит арену в том виде, какая она будет на этапе подаваемого цикла, в 64 октета. Перед началом битвы все игроки будут расположены по своим местам равноудаленно друг от друга(а точнее их исполняемый код). Это лишь начало. После расположения виртуальная машина начинает выполнять действия, прописанные у каждого игрока. В связи с этим вид карты будет изменяться послепенно с течением времени.

3)-dump [номер цикла] - Все то же самое, что и с предыдущим флагом. Отличие лишь в том, что выводит арену в 32 октета.

4)-а - Есть такое интересное действие, которое поддерживает виртуалка, как вывод смволов(До сих пор не знаю, для чего оно вообще нужно, может, забавы ради :D)

# Визуальное представление принципа программы
Вот тут 4 игрока борятся за звание лучшего в памяти. 

<img width="972" alt="Screen Shot 2020-03-02 at 16 17 31" src="https://user-images.githubusercontent.com/61384057/75679827-43249500-5c88-11ea-8948-1bbe9f58afbc.png">

# Правила и тому подобное..
Их можно прочесть в сабджекте формата pdf.
