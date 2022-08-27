# Градиент
Создание градиента в SVG. В SVG можно создавать двачтипа градиентов: линейный и радиальный.

- `<linearGradient>` - линейный градиент
- `<radialGradient>` - радиальный градиент
- `<stop>` - оттенок градиент
- `<stop offset="0%">` - оттенок градиента начинается с края фигуры
- `<stop offset="0%" stop-color="">` - цвет оттенка градиента
- `<linearGradient id="circle-gradient">` - идентификатор гардиента
- `fill="url(#circle-gradient)"` - заливка фигуры ссылается на идентификатор градиента

Пример кода с градиентом у круга:

    <svg class="circle" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
      <linearGradient id="circle-gradient">
        <stop offset="0%" stop-color="#f1c40f"></stop>
        <stop offset="100%" stop-color="#f39c12"></stop>
      </linearGradient>
      <circle r="75" cx="100" cy="100" fill="url(#circle-gradient)"></circle>
    </svg>

Остальные атрибуты:
- `stop-opacity="0.3"` - прозрачность оттенка градиента
- оттенков градиента `<stop>` можно задать сколько угодно
- границу оттенка градиента можно расширить, добавив еще один `<stop>` с таким же цветом и увеличив процент в offset
- изменяем направление градиента (сверху вниз, линейный): `<linearGradient id="circle-gradient" x1="0" y1="0" x2="0" y2="1">`
- изменяем направление градиента (центр сверху слева, радиальный): `<radialGradient id="circle-gradient" r="0.25" cx="0.25" cy="0.25">`, еще есть атрибуты `fx` и `fy`

Пример с прозрачностью и направлением градиента:

    <svg class="circle" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
      <linearGradient id="circle-gradient" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#f1c40f" stop-opacity="0.3"></stop>
        <stop offset="100%" stop-color="#f39c12"></stop>
      </linearGradient>
      <circle r="75" cx="100" cy="100" fill="url(#circle-gradient)"></circle>
    </svg>
