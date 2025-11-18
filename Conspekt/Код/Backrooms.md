backrooms_people = dict()

earth_people = dict()

  

list_of_people = [

    [1, "Мухаммад Ахмедов"],

    [2, "Артем Белов"],

    [3, "Павел Герасин"]

    [4, "Алексей Репин"]

    [5, "Максим Северюхин"]

    [6, "Андрей Сорокин"]

    [7, "Владислав Кондратьев"]

    [8, "Николай Похвищев"]

    [9, "Тимофей Екимов"]

]

  

backrooms_people = { }

earth_people = dict(list_of_people)

  

print(types(list_of_people))

print(type(earth_people))

  

'''for key, value in earth_people.items():

    print(key, value)'''

  

for i in range(len(earth_people)):

    if i % 2 == 0:

        backrooms_people[i] = earth_people.get()