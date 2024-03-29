Лабораторная работа №2
======================

**Цель работы**
-----------

Освоение методов использования динамической памяти, изучение свойства полиморфизма, реализуемого перегрузкой функций и операций в классах C++.

**Задание к лабораторной работе**
-----------------------------

Составить описание класса для объектов прямоугольных матриц, задаваемых
массивом вещественных чисел типа **double**, располагающегося в памяти
по строкам. Компоненты матрицы должны быть скрыты (инкапсулированы) в
объекте.

Предусмотреть применение конструкторов:

1. по умолчанию;

2. для инициализации квадратной матрицы заданного размера с заданными компонентами;

3. для инициализации прямоугольной матрицы заданных размеров с заданными компонентами;

4. копирования.

Можно использовать параметры по умолчанию для сокращения количества конструкторов.

Конструкторы должны создавать объекты в динамической памяти (оператор **new**), а деструктор - освобождать память (оператор **delete**). Способ размещения объекта в динамической памяти (в виде одномерного или двумерного динамического массива, либо комбинированный вариант - одномерный массив с массивом указателей на начало каждой строки матрицы) выбрать самостоятельно. Все эти способы имеют как достоинства, так и недостатки.

Организовать в конструкторах и деструкторе вывод на экран информационных сообщений, например, «Конструктор матрицы ХХХ», «Деструктор матрицы ХХХ» и т.д. Вместо «ХХХ» указывать некоторый уникальный идентификатор матрицы.

1. С помощью функций-элементов класса обеспечить:

    1. проверку возможности умножения двух матриц;

    2. проверку возможности сложения двух матриц;

    3. поиск максимального элемента матрицы;

    4. поиск минимального элемента матрицы.

2. С помощью операторов-элементов класса обеспечить:

    1. доступ к элементам матрицы по индексу строки и столбца (чтение/запись), т.е. переопределить оператор [];

    2. математические действия над матрицами *A* и *B* без получения новых матриц, т.е. переопределить операторы

        1. *A* = *B*;

        2. *A* += *B*;

        3. *A* -= *B*;

        4. *A* *= *B*;

        5. а также умножение матрицы на скаляр *k*.

3. C помощью внешних операторов обеспечить:

    1. двуместные операции над матрицами *A* и *B* с получением новой матрицы *C*:

        1. сложение (*C* = *A* + *B*);

        2. вычитание (*C* = *A* - *B*);

        3. произведение (*С* = *A* * *B*);

        4. а также умножение матрицы на скаляр *k*.

    2. вывод на экран матрицы в построчной форме, т.е. переопределить оператор вывода на поток (<<).

Выполнению операций сложения, вычитания и умножения матриц должна предшествовать проверка возможности их выполнения над данными объектами.

*УКАЗАНИЕ*: Для выравнивания позиций при выводе матрицы на экран можно использовать функции-манипуляторы потока (библиотека **iomanip**) либо методы класса ostream (библиотека **iostream**):

| Манипуляторы потока                   | Методы класса ostream                           |
|---------------------------------------|-------------------------------------------------|
| fixed                                 |setf(ios_base::fixed, ios_base::floatfield)      |
| scientific                            |setf(ios_base::scientific, ios_base::floatfield) |
| setprecision(int n)                   | precision(int n)                                |
| setw(int n)                           |width(int n)                                     |
| resetiosflagsios_base::fmtflags flag) |setf(0, ios_base::fmtflags flag)                 |
| setiosflags(ios_base::fmtflags flag)  |setf(ios_base::fmtflags flag)                    |
