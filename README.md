# angularJS
这个仓库提供git使用教程 gulp使用教程 angularJS入门->进阶 的教程

## dialogue
学完本周期可能的疑问
```
Superficial°  21:25:07 
老师  我想问问脏检查  简单点咋说啊 
 
杉  21:25:50 
比较scope中改变前后两次的值是否一样 
 
Superficial°  21:26:18 
就这么点啊 
 
杉  21:26:25 
不一样则是脏的需要更新否则不更新ui 
 
Superficial°  21:58:53 
老师  你听听我的理解对不对哈  就是一个model层  和view层   model的数据越多  view层监听到的数据也就越多  就形成了脏检查  造成了性能消耗   
 
杉  22:02:52 
嗯 对 
 
Superficial°  22:03:12 
哈哈哈哈哈   好吧 
 
Superficial°  22:03:32 
就是看面试书上写了一大堆  看不进去   
 
杉  22:03:51 
然后呢 model 层上 的改变会 触发脏检查机制  
 
杉  22:04:27 
脏检查机制 仅会在 数据层发生改变的时候 更新 view层 
 
Superficial°  22:05:36 
哦哦  然后就形成了脏检查 
 
杉  22:06:01 
方式是 通过遍历 与 scope 进行了双向绑定的 的dom 的引用 是引用 不是遍历dom  从而大大降低的 直接遍历整个dom树的性能开销 
 
杉  22:06:47 
脏检查的触发 是需要 调用 $scope.$apply() 来触发的 并不是自动的 
 
Superficial°  22:07:14 
如果要销毁脏检查呢  用啥啊 
 
杉  22:07:48 
之所以 angular 看起来会触发脏检查 是因为 每当angular运行完 controller 或者其他相关函数的时候 会自动帮你调用 $rootScope.$apply() 
 
Superficial°  22:07:49 
还有$apply.dejest()是干嘛的啊 
 
杉  22:10:10 
至于 $digest  与 $apply()的区别 可以用一句话形容 那就是 digest  只检查当前的 作用域 以及子作用域 而apply 则会全局脏检查 也就是说 无论哪个scope 调用apply 都会从$rootScope 自顶向下进行全局脏检查 
 
Superficial°  22:12:44 
哦哦   那如果销毁脏检查  是放在定时器里面销毁么 
 
杉  22:13:26 
销毁 只需要 减少不必要的scope变量即可 (这不是销毁但是可以减少性能开销)
 
杉  22:13:49 
减少在 html 使用不必要的 scope变量 
```