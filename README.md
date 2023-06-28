# Задача 22: Даны два неупорядоченных набора целых чисел (может быть, с повторениями). 
# Выдать без повторений в порядке возрастания все те числа, которые встречаются в обоих наборах.
# Пользователь вводит 2 числа. n — кол-во элементов первого множества. m — кол-во элементов второго множества. 
# Затем пользователь вводит сами элементы множеств.


n = (int(input("Введите число n элементов: ")))
count_list_n = []
for i in range(n):
    num = int(input("Введите число: "))
    count_list_n.append(num)
print(count_list_n)

m = (int(input("Введите число m элементов: ")))
count_list_m = []
for i in range(m):
    num = int(input("Введите число: "))
    count_list_m.append(num)
print(count_list_m)

count_list3 = count_list_n + count_list_m

print(count_list3)
for i in count_list3:
    if count_list3.count(i) > 1:
        print(i)







# Задача 24: В фермерском хозяйстве в Карелии выращивают чернику. Она растёт на круглой грядке, причём кусты высажены только по окружности. 
# Таким образом, у каждого куста есть ровно два соседних. Всего на грядке растёт N кустов.
# Эти кусты обладают разной урожайностью, поэтому ко времени сбора на них выросло различное число ягод — на i-ом кусте выросло ai ягод.
# В этом фермерском хозяйстве внедрена система автоматического сбора черники. 
# Эта система состоит из управляющего модуля и нескольких собирающих модулей. 
# Собирающий модуль за один заход, находясь непосредственно перед некоторым кустом, собирает ягоды с этого куста и с двух соседних с ним.
# Напишите программу для нахождения максимального числа ягод, которое может собрать за один заход собирающий модуль, 
# находясь перед некоторым кустом заданной во входном файле грядки.


n = int( input( "количество кустов: = " ) )
bush = [ int(x) for x in input( " кол-во ягод на кустах: " ).split() ]
n = len(bush)
bush = bush + bush[:2]
m = 0
for i in range(n):
    m = max( m, bush[i] + bush[i+1] + bush[i+2] )
print(f"собрано ягод->: {m}")






# Искусственный интеллект Антон, созданный Гилфойлом, взломал сеть умных холодильников. 
# Теперь он использует их в качестве серверов "Пегого дудочника". Помогите владельцу фирмы отыскать все зараженные холодильники.
# Для каждого холодильника существует строка с данными, состоящая из строчных букв и цифр,
#  и если в ней присутствует слово "anton" (необязательно рядом стоящие буквы, главное наличие последовательности букв), 
#  то холодильник заражен и нужно вывести номер холодильника, нумерация начинается с единицы
# Формат входных данных
# В первой строке подаётся число n – количество холодильников. В последующих n строках вводятся строки,
#  содержащие латинские строчные буквы и цифры, в каждой строке от 5 до 100 символов.
# Формат выходных данных:
# Программа должна вывести номера зараженных холодильников через пробел. Если таких холодильников нет, ничего выводить не нужно.
# примеры:
# osfjwoiergwoignaewpjofwoeijfnwfonewfoignewtowenffnoeiwowjfninoiwfen
# anton
# aoooooooooontooooo
# elelelelelelelelelel
# ntoneeee
# tonee
# 253235235a5323352n25235352t253523523235oo235523523523n
# antoooooooooooooooooooooooooooooooooooooooooooooooooooon
# unton
# """


count = int(input())
chars = ['a', 'n', 't', 'o', 'n']
result = []
for n in range(count):
    str_fridge = input()
    try:
        last_position = -1
        for s in chars: 
            last_position = str_fridge.index(s, last_position + 1)
        result.append(n + 1)
    except ValueError:
        continue
print(*result)