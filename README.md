# DetectiveScroll

Плагин остлеживает скролл и может переключать классы в зависимости от высоты скролла

```js
var scroll_top = new DetectiveScroll({
     trigger: {
      el: $('.fixed_header'),
      scroll: $('.main-header').outerHeight()
     }
   })
   
// если нужна задержка или вызов своих коллбеков
var fixed_header = new DetectiveScroll({
     wait: 300,
     onUpdate: function(scrollTop){
       console.log(scrollTop);
     },
     trigger: {
      el: $('.js-scroll_top'),
      scroll: $(window).height() / 3
    }
   })
```

## Настройки

`onUpdate` (function) - срабатывает при каждом скролле.

`wait` (number) - задержка перед срабатыванием события скролла, точнее мы устанавливаем промежутки в которых будет срабатывать колбек `onUpdate`.

`trigger` (object) - данное свойство отвечает за переключение классов у елемента.

`trigger.el` (jquery element) - например $('.fixed_header').

`trigger.scroll` (number) - точка после скролла которой будет переключение классов.

`trigger.enabled` (string) - класс когда скролл ниже указанного в `trigger.scroll`.

`trigger.disabled` (string) - класс когда скролл выше указанного в `trigger.scroll`.

