# 《jQuery 的功能》
1. jQuery 如何获取元素
jQuery的基本设计思想和主要用法，就是"选择某个网页元素，然后对其进行某种操作"。
如何获取某个网页元素:
```
    //给jQuery添加一个别名window.$ = window.jQuery
    $('#xxx') 返回值并不是元素，而是一个 api 对象
    $('#xxx').find('.red') 查找 #xxx 里的 .red 元素
    $('#xxx').parent() 获取爸爸
    $('#xxx').children() 获取儿子
    $('#xxx').siblings() 获取兄弟
    $('#xxx').index() 获取排行老几（从0开始）
    $('#xxx').next() 获取弟弟
    $('#xxx').prev() 获取哥哥
    $('.red').each(fn) 遍历并对每个元素执行 fn

```
---

2. jQuery 的链式操作是怎样的

jQuery的链式操作就是最终选中网页元素以后，可以对它进行一系列操作，并且所有操作可以连接在一起，以链条的形式写出来，比如：
```
    $('div').find('h3').eq(2);
    //查找div里面的第二个 h3 元素
```
---

3. jQuery 如何创建元素

```
    $('<div><span>1</span></div>') 创建 div
    .appendTo(document.body) 插入到 body 中

```
tips：创建的标签默认处于JS线程中，必须插入到 head 或  body 中，才会在页面生效。

---

4. jQuery 如何移动元素

两组方法，来操作元素在网页中的位置移动。一组方法是直接移动该元素，另一组方法是移动其他元素，使得目标元素达到我们想要的位置。

假定我们选中了一个div元素，需要把它移动到p元素后面。

第一种方法是使用.insertAfter()，把div元素移动p元素后面：
```
    $('div').insertAfter($('p'));
    //返回 div 元素
```
第二种方法是使用.after()，把p元素加到div元素前面：
```
    $('p').after($('div'));
    //返回 p 元素
```
表面上看，这两种方法的效果是一样的，唯一的不同似乎只是操作视角的不同。但是实际上，它们有一个重大差别，那就是返回的元素不一样。

---

5. jQuery 如何修改元素的属性
```
    $div.text(?) 读写文本内容
    $div.html(?) 读写 HTML 内容
    $div.attr('title', ?) 读写属性
    $div.css({color: 'red'}) 读写 style
    $div.addClass('blue')
    $div.on('click', fn) 
    $div.off('click', fn)

```