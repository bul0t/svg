# SVG иконки и спрайты
SVG иконки можно сделать самому или скачать с инета. Воспользуемся сервисом: https://icons.getbootstrap.com/

Скопируем оттуда иконку `android`:

    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-android" viewBox="0 0 16 16">
      <path d="M2.76 3.061a.5.5 0 0 1 .679.2l1.283 2.352A8.94 8.94 0 0 1 8 5a8.94 8.94 0 0 1 3.278.613l1.283-2.352a.5.5 0 1 1 .878.478l-1.252 2.295C14.475 7.266 16 9.477 16 12H0c0-2.523 1.525-4.734 3.813-5.966L2.56 3.74a.5.5 0 0 1 .2-.678ZM5 10a1 1 0 1 0 0-2 1 1 0 0 0 0 2Zm6 0a1 1 0 1 0 0-2 1 1 0 0 0 0 2Z"/>
    </svg>

Разобраться с шриной обводки и выходом за пределы viewBox:

    .android-ico {
      width: 300px;
      height: 300px;
      padding: 16px;
    }
    .android-ico path {
      fill: none;
      stroke: #e74c3c;
      stroke-width: 0.3;
    }

## Спрайт SVG
Спрайты создаются чтобы объединить их в определённый файл и подключать изображения в нем по мере необходимости без создания дополнительных запросов к серверу.

sprite.svg:

    <svg display="none" xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink">
      <symbol id="one" viewBox="такой же как и у иконки">
        code svg
      </symbol>
      <symbol id="two" viewBox="такой же как и у иконки">
        code svg
      </symbol>
    </svg>

index.html:

    <svg class="icon">
      <use xlink:href="sprite.svg#one"></use>
    </svg>
    <svg class="icon">
      <use xlink:href="sprite.svg#two"></use>
    </svg>

Разобраться действительно ли оборачивать `code svg` тегом `<g>`.
