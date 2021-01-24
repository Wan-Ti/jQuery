# jQuery

jQuery用于获取对应的元素，但是它却不返回这些元素。jQuery返回一个对象，称为jQuery构造出来的对象，该对象可以操作对应的元素。

jQuery是构造函数，但它是一个不需要加new的构造函数。

jQuery对象代指jQuery函数构造出来的对象。(口头约定)

学习路线:</br>
理解jQuery原理;</br>
使用jQuery做一两个项目;</br>
总结一篇博客，然后再也不碰jQuery;</br>


## DOM事件与事件委托

浏览器支持两种调用顺序:</br>
按爷爷=>爸爸=>儿子顺序看有没有函数监听；</br>
按儿子=>爸爸=>爷爷顺序看有没有函数监听；</br>

从外向内找监听函数，叫事件捕获；</br>
从内向外找监听函数，叫事件冒泡；</br>

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/169d39667270453e934cd84cde822a00~tplv-k3u1fbpfcp-watermark.image)

### addEventListener

#### · 事件绑定API

IE：baba.attachEvent('onclick',fn);//冒泡</br>
网景：baba.addEventListener('click',fn)；//捕获</br>
W3C:baba.addEventListener('click',fn,bool)

若bool不传或为falsy:</br>
使用fn走冒泡，当浏览器在冒泡阶段发现baba有fn监听函数，就会调用fn,并提供时间信息;

若bool为true:</br>
使用fn走捕获。即当浏览器在捕获阶段发现baba有fn监听函数，就会调用fn，并提供时间信息。

target和currentTarget:</br>
一个是用户点击的，一个是开发者监听的；

取消冒泡：</br>
e.stopPropagation()

事件的特性：</br>
Bubbles表示是否冒泡；</br>
Cancelable表示是否支持开发者取消冒泡；</br>
