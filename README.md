# Визуальное программирование

Совместный репозиторий

- Данилюк А.Ю.
- Карасев М.А.
- Абабий Г.В.


# Преобразование из декартовой системы координат в сферическую
## Проделанная работа

Для данной лабораторной работы пришлось прошерстить большое количество ресурсов.
Все необходимые формулы (о них ниже) были взяты с данного [сайта](https://www.nosco.ch/mathematics/en/earth-coordinates.php).
## Предлагалась следующая модель сферы:
![Graphics](https://www.nosco.ch/mathematics/inc/img/spherical02.png)

#### Где
1. Проведена прямая OP от центра сферы к искомой точке (поверхности сферы)
2. От нее на ось, параллельную "экватору", опущена проекция OP'
3. Угол между ними - искомый latitude
4. Далее на ось X опущена проекция от OP'
5. Угол между ними - искомый longitude

#### Формулы
Согласно [источнику](https://www.nosco.ch/mathematics/en/earth-coordinates.php), для нахождения величины latitude используется следующая формула:
φ = arcsin(z/R), 
где z - прямая, проведенная из точки P до прямой OP' под углом 90°, а R - радиус Земли, принятый для задания как R = 6371.
Для нахождения величины longitude используется формула
λ = atan2(y, x),
где y, x - координаты точки.
Данные значения принято выражать в градусах, поэтому использовалось следующее правило перевода из радиан в градусы:
1 degree = (1 rad * 180)/Pi  
Так как значение прямой z не дано условием, ее необходимо рассчитать по теореме Пифагора со следующими параметрами: 
- OP = 6371, так как OP - радиус сферы (Земли)
- OP' - расстояние центра сферы до проекции точки на ось, было принято использовать в качестве оси параметр x
Тогда:
z = sqrt(R^2 - x^2)

Теперь формула для latitude приобрела вид:
φ = (arcsin (sqrt(R^2 - x^2) / R) * 180) / Pi
Для longitude:
λ = (atan2 (y, x) * 180)/Pi;
С помощью этих формул были полученые точные значения, проверенные на данном [сайте](https://www.apsalin.com/cartesian-to-geodetic-on-ellipsoid/?).
