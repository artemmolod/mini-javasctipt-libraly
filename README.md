JavaScript libraly - Dooli
====================

Мини библиотека, реализованная на ES6.
Пример: 
```javascript
Dooli("dooli")
    .css("color: #F00", "font-size: 23px")
    .addClass("test", "test-new-dooli")
    .removeClass("dooli", "test")
    .attr("data-type=0", "data-start=hi!")
    .html()
```
__________
<h2>Методы библиотеки:</h2>
<i>css</i> - применяет стили к элементу <br/>
<i>html</i> - принимает один необязятельный параметр. Если параметр установлен, то задает новое содержимое элемента, иначе возвращает его настоящее<br/>
<i>addClass</i> - добавляет один или несколько классов к элементу. Классы указываются через запятую<br/>
<i>removeClass</i> - удалает один или несколько классов к элементу. Классы указываются через запятую<br/>
<i>focus</i> - задает фокус элементу<br/>
<i>attr</i> - задает 1 или несколько новых аттрибутов элементу.  <br/>
<i>get</i> - получает 1 или несколько аттрибутов элемента. <br/>
<i>show</i> - показывает элемент<br/>
<i>hide</i> - скрывает элемент<br/>
<i>width</i> - возвращает ширину элемента<br/>
<i>height</i> - возвращает высоту элемента<br/>
<i>prepend</i> - добавляет 1 или несколько элементов в начало блока<br/>
<i>append</i> - добавляет 1 или несколько элементов в конец блока<br/>
<i>click</i> - устанавливает или вызывает обработчик элемента<br/>
<i>clone</i> - клонирует элемент<br/>

Методы, которые не возвращают результата можно чейнить.

<h2>Ajax запросы созданы с помощью <i>Promise</i></h2>
Пример <b>post</b>-запроса:
```javascript
D.post(url, data)
 .then(
    result => {
        //обработка ответа
    },
    error => {
        //обработка ошибки
    }
 );
```
Пример <b>get</b>-запроса:
```javascript
D.get(url)
 .then(
    result => {
        //обработка ответа
    },
    error => {
        //обработка ошибки
    }
 );
```
Работа с шаблонами:
-------
Пусть есть такая разметка:
```html
<div id="tpl">
    <div ...>
        My name is {name}
    </div>
</div>
```
То такой скрипт заменит все найденные **name** на Artem
```javascript
let tpl = TPL_("tpl");
tpl.parse("name", "Artem");
``` 
Также разметку можно продублировать нужное количество раз, например:
```javascript
tpl.each(3).parse("name", "Artem");
```
И она будет такой:
```html
<div id="tpl">
    <div ...>
        My name is Artem
    </div>
    <div ...>
        My name is Artem
    </div>
    <div ...>
        My name is Artem
    </div>
</div>
```
Дублирование можно производить без метода **parse**.
___________
Стороннее расширение библиотеки:
```javascript
class MyDooli extends DooliObject {
  constructor(e) {
    super(e);
  }
  
  /**
   * update method html
   * */
  html(v) {
    return v == undefined ? this.el.innerHTML : this.el.innerHTML = v; 
  }
  
  ...
}
```
Таким образом Вы можете расширить основной функционал библиотеки.