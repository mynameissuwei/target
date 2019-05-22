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
