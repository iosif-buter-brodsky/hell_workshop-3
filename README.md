# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #3 выполнил(а):
- Цюприк Егор Васильевич 
- РИ220936
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Разработать оптимальный баланс для десяти уровней игры Dragon Picker

## Задание 1
### Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице. 

Ход работы:
- Ознакомьться с презентацией третьей лекции, оценить структуры игры Dragon Picker. Скачать и ознакомься с прототипом игры Dragon Picker на движке Unity. Запустить игровую сцену, проанализировать движение дракона.

## Переменные ответсвенные за перемещение дракона  
### Speed 
- Speed - скорость передвижения дракона по сцене. Начальное значение 4. Для усложнения требуется постепенно ее увеличивать.
### TimeBetweenEggDrops 
- TimeBetweenEggDrops - время между сбрасыванием яйц. Начальное значение 2 секунды. Для усложнения требуется постепенное уменьшать это значение.
### LeftRightDistance
- leftRightDistance - растояние коротое может пройти дракон влево или вправо. Начальное значение 10. Для усложнения требуется постепеное увеличивать значение.

## Визуализация изменения уровня сложности в google таблице
![2023-11-14 14 06 59 docs google com ed6e904e9cd9](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/80c2031a-88bf-4aba-872c-3ae908660667)


## 
## Задание 2
### Создайте 10 сцен на Unity с изменяющимся уровнем сложности.
- Созданные 10 сцен на Unity

![Снимок](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/7e43c744-2941-4336-86b3-78530633b254)

### Сцена 1
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/76d759de-112d-4f57-895b-a2bc55c8efee)

### Сцена 2
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/b2520125-4fc1-4df0-adec-b24f60ee35aa)

### Сцена 3
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/9549d74c-c826-4e1f-98e6-b45053b05694)

### Сцена 4
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/4c12d3e5-23c0-40f0-80ac-da3ccba2e6f9)

### Сцена 5
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/39dcc976-c57e-4954-96c7-f0c94afc9806)

### Сцена 6
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/814a77c4-cfd9-4eb6-8f23-863975566c83)

### Сцена 7
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/95b3d8c8-d9d8-40a8-b184-be3547053341)

### Сцена 8
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/ae10e94b-f212-4034-ab16-9a9067679fbc)

### Сцена 9
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/8e3ae31f-537d-4afb-becc-cfb7bc08e95c)

### Сцена 10
![image](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/202838ea-edff-470d-9969-752a7274046b)


## Задание 3
###  Решение в 80+ баллов должно заполнять google-таблицу данными из Python. В Python данные также должны быть визуализированы.
Ход работы:
- Был написан код на python заполняющий google таблицу данными и визуализирующий их. 
```py
import gspread
import numpy as np
import math
import matplotlib.pyplot as plt

gc = gspread.service_account(filename='unity-urfu-hell-from-gamedev-8ad8352a35bf.json')
sh = gc.open("workshop#3")

steps = 10
speed, max_speed = 4.0, 20.0
distance, max_distance = 10.0, 22.0
time, max_time = 2.0, 0.2

base_distance = math.exp((math.log(max_distance) - math.log(distance)) / steps)
base_speed = math.exp((math.log(max_speed) - math.log(speed)) / steps)
base_time = math.exp((math.log(max_time) - math.log(time)) / steps)

speed_data, distance_data, time_data = [], [], []

i = 0
while i <= steps:
    if i == 0:
        i += 1
        continue
    else:
        speed_data.append(speed)
        distance_data.append(distance)
        time_data.append(time)
        print(f'Step {i}: speed = {speed:.2f}', f'distance = {distance:.2f}', f'time = {time:.2f}')
        sh.sheet1.update(('A' + str(i+1)), str(i))
        sh.sheet1.update(('B' + str(i+1)), round(speed,2))
        sh.sheet1.update(('C' + str(i+1)), round(distance,2))
        sh.sheet1.update(('D' + str(i+1)), round(time,2))
        speed *= base_speed
        distance *= base_distance
        time *= base_time
        i += 1

steps_array = np.arange(1, steps + 1)
plt.figure(figsize=(8, 5))
plt.plot(steps_array, speed_data, label='Speed')
plt.plot(steps_array, distance_data, label='Distance')
plt.plot(steps_array, time_data, label='Time')
plt.xlabel('Steps')
plt.ylabel('Values')
plt.title('Data over Steps')
plt.legend()
plt.grid(True)
plt.show()

```
![2023-11-14 14 09 00 localhost 3a9975884ac5](https://github.com/iosif-buter-brodsky/hell_workshop-3/assets/146319327/506290f0-a00d-4bd5-ab73-c91a59e3027c)
скрин из Jupyter Notebook

В коде используются математические функции math.log() и math.exp(). math.log() возвращает натуральный логарифм числа, а math.exp() возвращает экспоненту числа (то есть число e в степени этого числа).

В данном случае:

base_distance, base_speed и base_time вычисляются как результат преобразования разности логарифмов максимальных и текущих значений переменных, деленной на количество шагов.
Далее, в цикле переменные speed, distance и time умножаются на соответствующие базовые значения для каждого шага.
Это позволяет постепенно изменять значения speed, distance и time от их первоначальных значений до максимальных за определенное количество шагов, задаваемое переменной steps.
## Выводы

Мы поработали и разобрались с балансом в игре, а также научились генерировать и визуализировать данные при помощи Python.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
