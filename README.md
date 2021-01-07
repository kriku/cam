
# Table of Contents

1.  [Железо](#orgfff9137)
    1.  [Рука](#orgd46a099)
        1.  [Подвес](#orgc540435)
    2.  [Камера 1](#org03c2ddf)
        1.  [Raspberry Camera IMX477](#org9919d7a)
    3.  [Камера 2](#org6b9dd6e)
        1.  [Intel Realsense D435](#orgdc1e270)
    4.  [Датчики](#org8ddf2c7)
        1.  [IMU 9DOF](#orgb428fc9)
        2.  [Одометрия фокуса / диафрагмы](#orgb545640)
2.  [Софт](#org0ecc6aa)
    1.  [Управление рукой](#orgc9759d4)
        1.  [Подвес](#orgc30efdb)
    2.  [Данные](#org3f65f5a)
        1.  [Геометрия / Стереометрия](#org4706c73)
        2.  [Видео](#org4b5da45)
    3.  [Физическая симуляция](#org7032772)
        1.  [ROS](#org3144920)
    4.  [Автономный оператор?](#org82e1dab)
        1.  [ML](#org6ade308)


<a id="orgfff9137"></a>

# Железо


<a id="orgd46a099"></a>

## Рука


<a id="orgc540435"></a>

### Подвес

2x30KG, 3x20KG сервоприводы
<https://aliexpress.ru/item/1-X-Waterproof-servo-20KG-25KG-30-KG-and-high-speed-metal-gear-digital-servo-baja/1943129663.html?spm=a2g0s.9042311.0.0.9e2c33edEMgnKQ&_ga=2.140767989.615710377.1609895547-576746756.1603032031>

один шаговый для движению по троссу
<https://aliexpress.ru/item/Short-Body-Nema-17-Stepper-Motor-20mm-16Ncm-1A-Nema17-Step-Motor-4-Lead-17HS08-1004S/32585429251.html?spm=a2g0s.9042311.0.0.9e2c33edEMgnKQ&_ga=2.140767989.615710377.1609895547-576746756.1603032031>

мелочевка, провода
<https://aliexpress.ru/item/3D-Printer-Parts-A4988-DRV8825-Stepper-Motor-Driver-With-Heat-sink-For-SKR-V1-3-1/32965199683.html?spm=a2g0s.9042311.0.0.9e2c33edEMgnKQ&_ga=2.215719632.615710377.1609895547-576746756.1603032031>
<https://aliexpress.ru/item/1pcs-16-Channel-12-bit-PWM-Servo-Driver-I2C-interface-Module/32945308126.html?spm=a2g0s.9042311.0.0.9e2c33edEMgnKQ&_ga=2.238772039.615710377.1609895547-576746756.1603032031>
<https://aliexpress.ru/item/5M-16-feet-22AWG-26awg-30-60-Core-3-way-Twist-Servo-Extension-Cable-JR-Futaba/4000287024568.html?spm=a2g0s.9042311.0.0.9e2c33edEMgnKQ&_ga=2.215719632.615710377.1609895547-576746756.1603032031>

по предварительным соображениям:

-   1 x 20KG - поворот башни
-   1 x 30KG - поднятие дула
-   1 x 30KG - второго колена
-   1 x 20KG - третьего колена
-   1 x 20KG - осевой поворот вершины манипулятора

но возможно комбинация с двумя коленами:

-   1 x 30KG - поворот башни
-   2 x 20KG - поднятие дула
-   1 x 30KG - поворот второго колена
-   1 x 20KG - осевой поворот вершины манипулятора

в вершине манипулятора крепежи для монтирования камер

-   2 x 1/4" крепежный винт


<a id="org03c2ddf"></a>

## Камера 1


<a id="org9919d7a"></a>

### Raspberry Camera IMX477

два объектива C/CS-mount, для них шаговые двигатели и шестерни
<https://aliexpress.ru/item/Raspberry-Pi-HQ-Camera-Module-12-3-Megapixel-Sony-IMX477-Sensor-with-Adjustable-Back-Focus-6mm/1005001343210492.html?spm=a2g0s.9042311.0.0.264d33edIQaF16&_ga=2.238704583.615710377.1609895547-576746756.1603032031&sku_id=12000015763734542>
<https://aliexpress.ru/item/5pcs-New-Brand-ULN2003-28BYJ-48-5V-Reduction-Step-Motor-Gear-Stepper-Motor-4-Phase-Step/32869969097.html?spm=a2g0s.9042311.0.0.9e2c33edEMgnKQ&_ga=2.237736775.615710377.1609895547-576746756.1603032031>
<https://aliexpress.ru/item/2M-1M-50CM-30CM-for-Raspberry-Pi-3-Camera-Cable-Ribbon-FFC-15pin-0-5mm-Pitch/32955914001.html?spm=a2g0s.9042311.0.0.9e2c33edEMgnKQ&_ga=2.238772039.615710377.1609895547-576746756.1603032031>

для объективов требуется печать приводов фокуса / диафрагмы

-   управление - с платы teensy?
-   хотя возить и jetson придётся - длина кабеля камеры - 2m
-   одометрия - возможно оптопара


<a id="org6b9dd6e"></a>

## Камера 2


<a id="orgdc1e270"></a>

### Intel Realsense D435

камера глубины, для обучения подвеса операторской работе


<a id="org8ddf2c7"></a>

## Датчики


<a id="orgb428fc9"></a>

### IMU 9DOF

два гироскопа/акселерометра, для восстановления векторов в пространстве
<https://aliexpress.ru/item/GY-BNO080-AR-VR-IMU-High-precision-9DOF-AHRS-sensor-module/32910814295.html?spm=a2g0s.9042311.0.0.9e2c33edEMgnKQ&_ga=2.179532899.615710377.1609895547-576746756.1603032031>


<a id="orgb545640"></a>

### Одометрия фокуса / диафрагмы

&#x2026; TBD


<a id="org0ecc6aa"></a>

# Софт


<a id="orgc9759d4"></a>

## Управление рукой


<a id="orgc30efdb"></a>

### Подвес

прошивки для управления сервами / мотором
есть плата teensy 3.2

-   PWM
-   stepper motor driver

нужно будет собрать прошивки, для управления
ROS, platformio, #TBD

-   возможно управление gamepad'ом


<a id="org3f65f5a"></a>

## Данные


<a id="org4706c73"></a>

### Геометрия / Стереометрия

стриминг данных для последующей обработки / анализа

-   повороты серв / фокуса / одометрия / пространственное положение
-   значения датчиков IMU
-   point cloud с камеры глубины


<a id="org4b5da45"></a>

### Видео

стриминг на сервер / youtube / twitch


<a id="org7032772"></a>

## Физическая симуляция


<a id="org3144920"></a>

### ROS

\#TBD


<a id="org82e1dab"></a>

## Автономный оператор?


<a id="org6ade308"></a>

### ML

на основе данных датчиков / камеры глубины
требуется разработать алгоритм, благодаря которому:

-   вершина манипулятора сможет держать вектор в пространстве
-   перемещаться в доступные точки пространства
-   вектор вершины сохраняется, либо изменяется на заданную величину
-   фокус камеры акцентируется на объекте наблюдения

в любом случае потребуется достаточно точная 3д симуляция

-   тренировка на физической симуляции
-   обучение на обобщение шумов
-   аугментация на реальном манипуляторе

