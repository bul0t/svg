# Паттерн
Паттерн это элемент, который можно использовать в качестве заливки или обводки.

Содержимое паттерна:
- фигуры
- символы
- текст
- растровые изображения

Пример паттерна, не виден:

    <pattern id="bg" width="50" height="50">
      <path d="M 0,0 L 10,10 10,40 40,40 z" fill="red" stroke="orange" stroke-width="3"></path>
    </pattern>

Паттерн виден только в тот момент когда он подключается к основному изображению:

    <svg>
      <pattern id="bg" width="40" height="40">
        <path d="M 4,4 L 10,20 15,30 40,4 Z" fill="red" stroke="orange" stroke-width="3"></path>
      </pattern>
      <rect width="150" height="100" fill="url(#bg)" stroke="red"></rect>
    </svg>

Атрибут `patternTransform` применяет трансформации к паттерну:

    <pattern patternTransform="translate(100) ...

Один и тот же паттерн можно применить к разным фигурам одновременно:

    <svg width="400" height="300">
      <pattern id="bg" width="40" height="40" patternTransform="translate(32)">
        <path d="M 10,10 L 10,30 40,10 Z" fill="red" stroke="orange" stroke-width="3"></path>
      </pattern>
      <rect x="8" y="8" width="150" height="100" fill="url(#bg)" stroke="red" stroke-width="8"></rect>
      <rect x="8" y="124" width="150" height="100" fill="url(#bg)" stroke="red" stroke-width="8"></rect>
    </svg>

## Применяем паттерн к обводке

    <rect x="174" y="8" width="150" height="100" fill="none" stroke="url(#bg)" stroke-width="20"></rect>

## Размножаем паттерн
Для этого нам понадобится добавить в тег `<pattern>` атрибут `viewbox="0 0 10 10"` а ширину и высоту задать в процентах `width="10%" height="10%"`:

    <svg width="400" height="300">
      <pattern viewbox="0 0 10 10" id="bg" width="10%" height="10%">
        <path d="M 4,4 L 4,20 30,4 Z" fill="red" stroke="orange" stroke-width="4"></path>
      </pattern>
      <rect x="8" y="8" width="150" height="100" fill="url(#bg)" stroke="red" stroke-width="8"></rect>
      <rect x="8" y="124" width="150" height="100" fill="url(#bg)" stroke="red" stroke-width="8"></rect>
      <rect x="174" y="8" width="150" height="100" fill="none" stroke="url(#bg)" stroke-width="24"></rect>
    </svg>

## Добавляем изображение

    <svg>
      <pattern id="bg" width="40" height="40">
        <image xlink:href="url" width="150" height="100" />
      </pattern>
      <rect width="150" height="100" fill="url(#bg)" stroke="red"></rect>
    </svg>
