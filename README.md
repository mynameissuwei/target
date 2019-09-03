# target;

    2019/1/8 M target read the opend source of create-react-app finish !
    没有webpack的东西 只是看了一下create-react-app源码的东西 我还是需要自己搭建生产环境

    PM 看视频 自己搭建一下react的生产环境。

    2019/1/9
    	争取把ESlint 配置搞定

    2019/1/10
    	配置成功
    	下午的任务开始写项目 熟悉antd

    2019/1/11
    	上午把3~的看完

    2019/1/15
    	今天把5的看完

    2019/1/16
    	上午完成第六章的视频
    	中午去健身
    	下午完成第七章的视频

    2019/1/17
    	上午把config的push上去

    2019/1/18
    	上午把第7章视频完结
    	下午把第8章 和 第9章的 视频完结。

    2019/1/18
    	上午看下rodemap,下午看视频。

2019/1/22
继续用 Gatsby 实现自己的个人博客
垃圾 Gatsby 按照官方文档操作都出现一堆问题
继续看 react 的源码 他那个文档需要搭配视频看,不能单独看。
react 源码 视频 中文文档 英文文档 三个资料 我希望 ok。
所以接下来干什么！
继续 webpack 视频吧。

    2019/4/26
    	上午把我的博客收录给搞定
    	 - 百度收录
    	 - 谷歌收录

    2019/4/29
    	今天把第三章看完,同时把功能给改一下.

## 说下 new 出一个对象的过程

```
function name(name) {
	this.name = name
}
let suwei = name(suwei)
```

1.创建出·一个新对象
2.this 指向这个新对象 3.给 this 赋值
4.return 出来 this

## 变量提升

1.var 变量定义 2.函数声明

## this 几种不同的使用场景

1.在构造函数中使用（构造函数本身） 2.作为对象属性时使用（调用属性的对象） 3.作为普通函数时使用（window）
4.call，apply，bind（执行的第一个参数）

```
var a = {
  name: 'A',
  fun: function() {
    console.log(this.name);
  }
};

a.fun();  //this === a
a.fun.call({ name: 'B' });  //this === { name: 'B' }
var fun1 = a.fun;
fun1(); //this === window
```

## 如何理解作用域

自由变量
作用域链，及自由变量的查找，找不到逐级向上找
闭包的两个场景
函数作为变量传递
函数作为返回值

## 实际开发中闭包的应用

```
// 判断一个数字是否出现过
function isFirst() {
  var _list = [];
  return function(id) {
    if (_list.indexOf(id) >= 0) {
      return false;
    } else {
      _list.push(id);
      return true;
    }
  };
}

var first = isFirst();
first(10);
first(10);
first(20);

```

## 同步和异步的区别

同步会阻塞代码 异部的话不会阻塞代码
alert 是同步 setTimeOut 是异部

```
console.log(1);
setTimeout(function() {
  console.log(2);
}, 0);
console.log(3);
setTimeout(function() {
  console.log(4);
}, 1000);
console.log(5);
// 输出结果：1，3，5，2，4

```

## 前端使用异步的场景

1.定时任务 setTimeout setInterval
2.ajax 发送请求 动态加载 img 图片 3.时间绑定

```
需要等待的情况下都需要异步，因为不会像同步一样阻塞
```

## 常用的数组 api

forEach（遍历所有元素）

var arr = ['a', 'b', 'c', 'd'];
arr.forEach(function (item, index) {
console.log(item + ',' + index);
})

### map（对数组进行重新组装，生成新的数组）

// map，生成新数组，不改变原来数组的格式
var arr = ['a', 'b', 'c', 'd'];
var result = arr.map(function (item, index) {
return index + '/' + item;
})
console.log(result);

### sort（对数组进行排序）

// sort， 会改变原来数组
var arr = [1, 23, 3, 4];
var result = arr.sort(function (a, b) {
// 从小到大排序
return a - b;

// 从大到小排序
// return b - a;
})
console.log(result);

### filter（过滤符合条件的元素）

var arr = [1, 2, 3, 4];
var result = arr.filter(function (item, index) {
if (item < 3) {
return true
}
})
console.log(result);

### every（判断所有元素是否都符合要求）

var arr = [1, 2, 3, 4];
var result = arr.every(function (item, index) {
if (item < 3) {
return true
}
})
console.log(result); // false

### some（判断是否有至少一个元素符合条件）

var arr = [1, 2, 3, 4];
var result = arr.some(function (item, index) {
if (item < 3) {
return true
}
})
console.log(result); // true

### join（根据条件对数组组合成字符串）

var arr = [1, 2, 3, 4];
var result = arr.join(',');
console.log(result);

### reverse（将数组反转）

var arr = [1, 2, 3, 4];
var result = arr.reverse();
console.log(result);

### for...of 和 for...in 的区别

for...in 是取到 key 的值 对象和数组都可以用
for...of 是取到 value 的值 数组可以用 对象不能用

先说结论：

推荐在循环对象属性的时候，使用 for...in,在遍历数组的时候的时候使用 for...of。

for...in 循环出的是 key，for...of 循环出的是 value

注意，for...of 是 ES6 新引入的特性。修复了 ES5 引入的 for...in 的不足

for...of 不能循环普通的对象，需要通过和 Object.keys()搭配使用

假设我们要遍历一个数组的 valuelet aArray = ['a',123,{a:'1',b:'2'}]

使用 for...in 循环：

```
for(let index in aArray){
    console.log(`${aArray[index]}`);
}
```

使用 for...of 循环：

```
for(var value of aArray){
    console.log(value);
}
```

咋一看好像好像只是写法不一样而已，那为什么说 for...of 修复了 for...in 的缺陷和不足。
假设我们往数组添加一个属性 name:
aArray.name = 'demo',再分别查看上面写的两个循环：

```
for(let index in aArray){
    console.log(`${aArray[index]}`); //Notice!!aArray.name也被循环出来了
}
for(var value of aArray){
    console.log(value);
}
```

所以说，作用于数组的 for-in 循环除了遍历数组元素以外,还会遍历自定义属性。

for...of 循环不会循环对象的 key，只会循环出数组的 value，因此 for...of 不能循环遍历普通对象,对普通对象的属性遍历推荐使用 for...in

如果实在想用 for...of 来遍历普通对象的属性的话，可以通过和 Object.keys()搭配使用，先获取对象的所有 key 的数组
然后遍历：

```
var student={
    name:'wujunchuan',
    age:22,
    locate:{
    country:'china',
    city:'xiamen',
    school:'XMUT'
    }
}
for(var key of Object.keys(student)){
    //使用Object.keys()方法获取对象key的数组
    console.log(key+": "+student[key]);
}
```

## 获取随机数，要求长度一致的字符串格式

function randomStr(len) {
var random = Math.random();
random = random + '0000000000'; // 防止自动生成的数字不满足长度报错并且强制转换成字符串
return random.substr(0, len)
}

console.log(randomStr(20));

## 关于 vsocde 的插件 -- 一些工具 js css react 的

https://medium.com/productivity-freak/the-ultimate-vscode-setup-for-js-react-6a4f7bd51a2

## 关于 react 的最佳实践

https://engineering.musefind.com/our-best-practices-for-writing-react-components-dec3eb5c3fc8

Closures
Passing setState a Function
asdf
git reset --soft HEAD@{1}
asdfsasfd
ASDFASDF

THIS IS SUWEI
