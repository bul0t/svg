# Заливка и обводка (fill, stroke)

## fill
- fill
- fill-rule
- fill-opacity

`fill` - по-умолчанию у фигур черный цвет заливки.  
Значением у fill выступает название цвета или 16-ричное число, также паттерны и градиенты.  
Значение цвета можно задавать в svg коде или в CSS.

Градиенты лучше создавать в графических редакторах или онлайн сервисах.

`fill-rule` - определяет как будут заливаться сложные фигуры имеющие пересечения внутри себя.  
Может принимать два значения `nonzero`, `evenodd`.

`fill-opacity` - управляет прозрачностью заливки.  
В качестве значений могут выступать числа от 0.0 (.5) до 1 или проценты.


## stroke, stroke-dasharray, stroke-dashoffset, stroke-linecap, stroke-linejoin, stroke-opacity, stroke-width
- stroke
- stroke-width
- stroke-dasharray
- stroke-dashoffset
- stroke-linecap
- stroke-linejoin
- stroke-opacity

`stroke` - по-умолчанию у обводки нет заливки и толщины.  
Значением у stroke выступает название цвета или 16-ричное число, также паттерны и градиенты.  
Значение цвета можно задавать в svg коде или в CSS.  

`stroke-width` - по-умолчанию, ширина обвоки равна 1px, можно еще записывать в процентах.

`stroke-linecap` - определяет как будут выглядеть концы линий: butt, round, square.

`stroke-linejoin` - определяет как будет выглядеть соединение двух линий: miter, round, bevel, miter-clip, arcs.

`stroke-dasharray` - определяет вид пунктирной обводки можно указывать в числах или процентах:
  - stroke-dasharray="1" - множество отрезков длиной в 1 и пробелов между ними длиной в 1
  - stroke-dasharray="4 4" - множество отрезков длиной в 4 и пробелов между ними длиной в 4
  - stroke-dasharray="4 4 10 20"

`stroke-dashoffset` - смещение пунктирной обводки относительно первоначального положения, значение по-умолчанию 0

`stroke-opacity` - определяет прозрачность обводки например `0.4`

## Пример
Сверху появляется анимация обводки и обходит всю фигуру:

    .selector {
      width: 400px;
      height: 400px;
      fill: #e74c3c;
      stroke: #f39c12;
      stroke-width: 8px;
      stroke-dasharray: 0 620;
      stroke-dashoffset: 350;
    }
    .selector:hover {
      animation-name: roll;
      animation-duration: 3s;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    }

    @keyframes roll {
      100% {
        stroke-dasharray: 620 0;
      }
    }