# Комп'ютерні системи імітаційного моделювання
## СПм-22-3, Меженський Олександр Олександрович
### Лабораторна робота №**1**. Опис імітаційних моделей та проведення обчислювальних експериментів

<br>

### Варіант 1, модель у середовищі NetLogo:
[Traffic Grid](https://www.netlogoweb.org/launch#http://www.netlogoweb.org/assets/modelslib/Sample%20Models/Social%20Science/Traffic%20Grid.nlogo)

<br>

### Вербальний опис моделі:
Симуляція руху автомобілів по грід-системі доріг та перехресть. Кожен автомобіль у моделі представлений агентом, який слідує простим набором правил, регулюючи свою швидкість та рух. Розглядає взаємодію автомобілів на дорогах та перехрестях з метою вивчення впливу різних факторів на руховий потік та час очікування. Автомобілі взаємодіють між собою та реагують на світлофори на перехрестях.

### Керуючі параметри:
- **grid-size-x** визначає кількість вертикальних доріг.
- **grid-size-y** визначає кількість горизонтальних доріг.
- **num-cars** визначає автомобілів у симуляції.
- **power** визначає наявність світлофора.
- **ticks-per-cycle** визначає кількість тактів, які минуть для кожного цикл.
- **speed-limit** визначає максимальну швидкість для автомобілів.
- **current-auto** перемикає поточне світло між автоматичним режимом і ручним.
- **current-phase** визначає коли поточне світло змінюється, якщо воно в автоматичному режимі.

### Показники роботи системи:
- зупіненні автомобілі - відображає кількість зупинених автомобілів за час.
- середня швидкість автомобілів - відображає середню швидкість автомобілів за час.
- середний час очікування автомобілів - відображає середній час зупинки автомобілів за певний час.

### Примітки:
Кожного кроку автомобілі намагаються рухатися вперед із поточною швидкістю. Якщо їхня поточна швидкість менша за обмеження швидкості і прямо перед ними немає автомобіля, вони прискорюються. Якщо попереду є повільніша машина, вони зрівняються зі швидкістю повільнішої машини та сповільнюються. Якщо перед ними червоне світло або зупинилася машина, вони зупиняються.

### Недоліки моделі:
Модель не враховує ситуації злиття рядів автомобілів, що може вплинути на реалістичність руху в умовах міста. Модель не враховує вплив погодних умов, дорожньої обстановки або інших факторів, які можуть впливати на рух транспорту в реальному місті. Поведінка автомобілів обмежена простим набором правил, і вони реагують тільки на автомобілі безпосередньо перед ними. Поведінка автомобілів моделюється простою логікою "гальмуй або прискорюй". Це може не враховувати більш складних аспектів руху в реальному місті.

<br>

## Обчислювальні експерименти
### 1. Вплив завантаженості дороги на кількість зупиненних автомобілів, середньої швидкісті автомобілів та середнього часу очікування автомобілів
Досліджується залежність кількості зупиненних автомобілів, середньої швидкісті автомобілів та середнього часу очікування автомобілів протягом певної кількості тактів (200) від числа машин на трасі, зазначеного на початку симуляції.
Експерименти проводяться при 25-200 автомобілях, з кроком 25, усього 8 симуляцій.  
Інші керуючі параметри мають значення за замовчуванням:
- **grid-size-x**: 5
- **grid-size-y**: 5
- **power**: On
- **ticks-per-cycle**: 20
- **speed-limit**: 1

<table>
<thead>
<tr><th>Кількість автомобілів</th><th>Кількість зупиненних</th><th>Середня швидкість</th><th>Середній час очікування</th></tr>
</thead>
<tbody>
<tr><td>25</td><td>9,84</td><td>0,502</td><td>3,33</td></tr>
<tr><td>50</td><td>21,10</td><td>0,473</td><td>3,81</td></tr>
<tr><td>75</td><td>33,14</td><td>0,443</td><td>4,12</td></tr>
<tr><td>100</td><td>45,85</td><td>0,421</td><td>4,40</td></tr>
<tr><td>125</td><td>59,44</td><td>0,385</td><td>4,68</td></tr>
<tr><td>150</td><td>81,78</td><td>0,301</td><td>6,86</td></tr>
<tr><td>175</td><td>91,35</td><td>0,274</td><td>5,28</td></tr>
<tr><td>200</td><td>124,48</td><td>0,187</td><td>9,02</td></tr>
<tr><td>225</td><td>162,62</td><td>0,118</td><td>16,46</td></tr>
<tr><td>250</td><td>192,08</td><td>0,082</td><td>20,58</td></tr>
</tbody>
</table>

![Залежність кількість зупиненних автомобілів від завантаженості траси](stopped-cars.png)

![Залежність кількість зупиненних автомобілів від завантаженості траси](average-speed-of-cars.png)

![Залежність кількість зупиненних автомобілів від завантаженості траси](average-wait-time-of-cars.png)

Графік наочно показує, що значне зростання кількісті зупиненних автомобілів, зменшення середньої швидкісті автомобілів та зростання середнього часу очікування автомобілів відбувається прі завантаженості більше 125 машин.
