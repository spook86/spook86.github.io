---
title: ' localStorage存储'
date: 2017-02-08
tags: '技术'
---
localStorage 是 web Storage API 提供的一个本地存储机制，相比 cookie 的4k 的存储，Storage 的可以存大约5MB 的数据 而且不会失效，兼容 IE8+ chrome4+ firefox 3.5+ 实在是优点不少。
与 Storage 相似的还有一个session 用法差不多。那么就以 lcaStorage 介绍一下使用方法。
语法为：myStorage = window.localStorage，这样就能获取到该对象，对像有两个方法来得到和存取值
myStorage.setItem(key,value)
这样就能给 storage 对象里添加指定的键值对
举个粟子：
var storage = window.localStorage;
storage.setItem(‘one’,’1’);
storage.setItem(‘two’,’2’);
如图所示：enter image description here
这样的话，值就被存进去了。
获取值呢，用另一个方法，举粟说明：
var a = storage.getItem(‘one’);
传入键值 这样就能获取到对应的值
如图：enter image description here
这样就得到了键为 one 的值
Storate 对象还有一个 key()方法,传入一个 number 就可以获取对应的键值。这样可以用一个 for 循环获取所有的key 再用 key 所有的键值对，同时可以用removeItem(key)将得到的key 传进去就可以删除对应的内容；
当然了，还有一个大招儿。就是 storage.clear()方法，这样一下就所该网址下所有的storate 内容全部删除了。
storage 对象也遵守 同源策略，如果用来做购物车数据存储，或者代替 cookie 是不是很方便呢？小伙用起来吧。
下边的链接是我用 VUE2.0+做了一个小今天例子，感兴趣的童鞋可以clone 下来试一下
我是传送门

后记：删除的时候因为我用的数字自增，所以从前边开始删除的话就会碰到读取不到的情况。这个如果用其它的键值来代替或者获取 的 JSON 数据就不会有这个问题。做示例 望知晓。
这段时间用一个 storage 插件写了一个 纯前端 小应用 用到一个插件 sotre.js github 链接。功能简单，但是特别灵活。兼容到了 IE6 哈哈，Opera 10、Firefox 3.5，特别不错。因为 localStorage
存蓄的数据多，思想前卫的人就想用着这些来缓存网站上的 JS css 等一些资源文件。倒是一个不错的办法。哈哈~