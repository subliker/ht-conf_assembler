Разработать ассемблер и интерпретатор для учебной виртуальной машины
(УВМ). Система команд УВМ представлена далее.
Для ассемблера необходимо разработать читаемое представление команд
УВМ. Ассемблер принимает на вход файл с текстом исходной программы, путь к
которой задается из командной строки. Результатом работы ассемблера является
бинарный файл в виде последовательности байт, путь к которому задается из
командной строки. Дополнительный ключ командной строки задает путь к файлулогу, в котором хранятся ассемблированные инструкции в духе списков
“ключ=значение”, как в приведенных далее тестах.
Интерпретатор принимает на вход бинарный файл, выполняет команды УВМ
и сохраняет в файле-результате значения из диапазона памяти УВМ. Диапазон
также указывается из командной строки.
Форматом для файла-лога и файла-результата является yaml.
Необходимо реализовать приведенные тесты для всех команд, а также
написать и отладить тестовую программу.
Загрузка константы
A B C
Биты 0—2 Биты 3—9 Биты 10—20
1 Адрес Константа
Размер команды: 8 байт. Операнд: поле C. Результат: регистр по адресу,
которым является поле B.
Тест (A=1, B=33, C=999):
0x09, 0x9D, 0x0F, 0x00, 0x00, 0x00, 0x00, 0x00
Чтение значения из памяти
A B C
Биты 0—2 Биты 3—9 Биты 10—16
6 Адрес Адрес
Размер команды: 8 байт. Операнд: значение в памяти ппо адресу, которым
является регистр по адресу, которым является поле B. Результат: регистр по
адресу, которым является поле C.
Тест (A=6, B=42, C=95):
0x56, 0x7D, 0x01, 0x00, 0x00, 0x00, 0x00, 0x00
Запись значения в память
A B C
Биты 0—2 Биты 3—9 Биты 10—16
7 Адрес Адрес
Размер команды: 8 байт. Операнд: регистр по адресу, которым является поле
B. Результат: значение в памяти по адресу, которым является регистр по адресу,
которым является поле C.
Тест (A=7, B=57, C=69):
0xCF, 0x15, 0x01, 0x00, 0x00, 0x00, 0x00, 0x00
Унарная операция: popcnt()
A B C
Биты 0—2 Биты 3—26 Биты 27—33
5 Адрес Адрес
Размер команды: 8 байт. Операнд: значение в памяти по адресу, которым
является регистр по адресу, которым является поле C. Результат: значение в
памяти по адресу, которым является поле B.
Тест (A=5, B=439, C=124):
0xBD, 0x0D, 0x00, 0xE0, 0x03, 0x00, 0x00, 0x00
Тестовая программа
Выполнить поэлементно операцию popcnt() над вектором длины 5. Результат
записать в исходный вектор.

# Тестирование
Запуск:\
![image](https://github.com/user-attachments/assets/7ed8ab2c-1e8f-4ebc-906b-65176b039daf)\
Входные данные:\
![image](https://github.com/user-attachments/assets/b3ba06d2-a018-46cb-807f-7c46dc7ac814)\
Логи:\
![image](https://github.com/user-attachments/assets/212d9e46-c3a1-4928-977c-aed88e7b7c8f)\
Результат:\
![image](https://github.com/user-attachments/assets/71975d12-6236-4b48-a974-330d7ff9f625)\
