# Методы отображения SVG на сайте
SVG на сайт можно поместить в виде:
- исходного кода тег `<svg></svg>`
- внутри тега `<img src="my.svg" />`, нельзя изменять свойства SVG через CSS, JS
- через `background-image: url(my.svg)` в CSS, спрайты, нельзя изменять свойства SVG через CSS, JS
- через `<object data="my.svg" type="image/svg+xml"></object>`, нельзя изменять свойства SVG через CSS, JS

## svg
Поддерживает: CSS манипуляции, JS манипуляции, SVG анимации, интерактивные SVG анимации.  
Остальные виды внедрения поддерживают это либо частично либо не поддерживают вовсе.

## background

    .svg-background {
      height: 100px;
      width: 100px; /* установи 80px для пропорции */
      background-image: url(amongus-background.svg);
      background-size: cover; /* или contain чтобы изображение поместилось полностью */
      background-repeat: no-repeat;
    }

## object
Выглядит как `background-size: contain;`.

## Разное
- https://vecta.io/blog/best-way-to-embed-svg
