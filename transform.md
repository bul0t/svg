# Трансформации
Трансформации в SVG:
- translate
- scale
- rotate - нужно записывать без deg rad turn grad они работают только в CSS
- skewX
- skewY
- matrix - комплексные перемещения

Задавать трансформацию можно с помощью атрибута `transform=""` или CSS-свойства `transform:`:

    <div class="container" style="padding: 8px;">
      <svg width="350" height="200" style="display: block;">
        <rect x="4" y="4" width="342" height="192" stroke="#2ecc71" stroke-width="8px" />
      </svg>
    </div>

Задаём rect атрибут transform: :

    transform="translate(8, 8)" // переместит еще на 8 пикселей вправо и вниз
    transform="translate(8 8)"  // можно задать через пробел
    transform="translate(8)"    // можно задать одно число и фигура сместится только вправо

transform через CSS, с переходом:

    .rect {
      transition-property: transform;
      transition-duration: 3s;
      transform: translate(20px, 20px);
    }

Одновременно применили несколько значений:

    transform="translate(20 20) scale(2) rotate(-45)"

Масштабировать можно по x и по y `scale(2 0.5)`.

skewX():

    transform="translate(20 20) scale(0.5) skewX(10)"

matrix(), используется редко.
