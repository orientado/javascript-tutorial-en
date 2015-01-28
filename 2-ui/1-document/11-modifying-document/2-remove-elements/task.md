# Удаление элементов

[importance 5]

Напишите функцию, которая удаляет элемент из DOM.

Синтаксис должен быть таким: `remove(elem)`, то есть, более короткий вариант, чем `parentNode.removeChild(elem)`.

```html
<div>Это</div>
<div>Все</div>
<div>Элементы DOM</div>

<script>
  var elem = document.body.children[0];

  function remove(elem) { /* ваш код */ }
*!*
  remove(elem);   // <-- функция должна удалить элемент
*/!*
</script>
```
