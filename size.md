# Размеры в SVG
- viewport
- viewBox
- width
- height
- preserveAspectRatio

Ширину и высоту обычно задают в пикселях и тогда `px` писать не обязатольно, если задаёте в процентах, то тогда нужно прописывать `%` также размеры заданные в процентах адаптируются, viewBox тоже позволяет адаптировать.

## viewport
viewport - область для отрисовки SVG изображений. По-умолчанию viewport у `<svg>` занимает `width="300"` и `height="150"` поэтому если мы создадим rect с размерами `width="500"` и `height="500"` то увидим лишь часть квадрата:

    <svg>
      <rect x="0" y="0" width="500" height="500" />
    </svg>

Чтобы увидеть весь квадрат, нужно ширину и высоту установить и тегу svg, либо через CSS:

    <svg width="500" height="500">
      <rect x="0" y="0" width="500" height="500" />
    </svg>

## viewBox
С помощью viewBox можно адаптировать размеры: `viewBox="число число число число"`

    <svg viewBox="0 0 200 200">
      <rect x="0" y="0" width="150" height="150" />
    </svg>

- svg - займет всё доступное пространство, при это соблюдает адаптивность
  - если записать другие пропорции viewBox="0 0 200 150"> то адаптироваться будет в этих пропорциях
- rect - займет 75% места от доступного пространства (150 это 75% от 200)

`viewBox="число число число число"` первые два числа это обозначение координат по оси x и по оси y (положительные отрицательные числа).  
Последние два число это значения по ширине и высоте.

## preserveAspectRatio
`preserveAspectRatio="none"` сохранять пропорции не нужно, получим овал.

    <svg width="300" height="300" class="circle" viewBox="0 0 200 300" preserveAspectRatio="none">
      <circle r="50" cx="50" cy="50" />
    </svg>