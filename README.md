# 一点编程理解记录——自我意识记录

### 我是写js的，处于鄙视链低端，从来不鄙视。所以也得出了编程的第一条理解。从此开始记录：

1.编程是思想，结合自己语言优势的思想，简单的转化成其他语言很简单，但是未必精髓。  
2.To C代码做错误处理的时候多输出默认值，让程序可用；To D代码要多报错，明确错误，及时stop！  
3.设计模式也是视情况而定的。  
4.js的数据类型内存模式：原始值和引用型。JS原始值是不可变的，使用上是正常的栈值，复制传递都是用的该值副本，比较也是比较的长的是否一样，其实是不同的值。引用值则是存在堆内存中，复制传递比较都是对其引用的。  
5.测试读写文件比读写数据库更快，与我想的正相反。  
6.文件编码越往底层越大，eg.同一份文件转码为base64要比binary要小。  
7.内存泄漏总结一句话就是：这份内存一直被占引用，并因为程序重复执行这种占用持续增加；程序不释放，垃圾回收也不能释放！  
8.框架~前端框架？什么叫做框架，而jQuery为什么不能叫做框架？我的理解，jQuery是JS它的运行环境是脱离不了JS运营环境的，而React等不一样，它该叫做运行时（RunTime到底是什么，暂时没有深刻理解）或者运行环境，比如V8把js转化为机器码，React是把reactjs转化为react码，再把这个转化为js码,js码跑在了js RunTime上。好像Node一样底层实现是C++，等于定义了一种JS与C++的逻辑关系。如果现在把jsDOM（与浏览器交互的JS简称），放在和C++同级别的地位，那么Reactjs就和js处于同一地位。所以Reactjs可不可以用其他不是js的语言实现哪？当然可以！eg.VUE的指令，完全不是js语言从此验证vue.js和react.js其实真是是像我们广义讲js的语言。其实它完全可以指定自己的语言逻辑！再深一点现在React这个运行时，相对与js运行环境和浏览器环境它有相当于语言，或者它可以直接等同于jQuery这样的语言就是一种封装jsDOM！不对，不是封装，没有封装这个React运行时是直接与浏览器沟通的，它就是jsDOM。优秀的是它在这个沟通上面设置了一层隔离，虚拟DOM,这个去识别Reactjs的语法，所以现在要想实现一个reactjs没有的语法，就像vue一样实现一些指令，其实就是在面向这个虚拟DOM编程，这个虚拟DOM可能翻译一句语法到jsDOM。那么指令是不是可以直接利用现用虚拟DOM的一个函数只是做一下封装！这个如果能找到这个函数应该很简单！更吊一点直接跳过这个虚拟DOM直接与jsDOM沟通，这个层面其实就是相当于jQuery的逻辑了，可能也不符合方法重用的理论，是在重复设计方法。这个可能就是React操作原生DOM留下的后门！所以这套东西的核心在哪？虚拟DOM怎么去执行jsDOM？怎么高效的去执行jsDOM？塑造一套指令系统直接去执行虚拟DOM的方法我感觉不会很难，继续修炼我相信到这个层次还是有可能的！  
9.React.js的更新与不更新？常规讲的React性能优势到底是什么？在我的理解里就是使用者要区分你写的JSX不是真实DOM,也就说你在这个组件里放一个log，每次外部组件渲染内部组件每次就会log出一些东西，但是这些变化是在React优化范围内的，它是在缓存中的，并不会更新真实DOM,怎么优化利用这个缓存的东西哪？就是生命周期shouldComponentUpdata,PureComponent,函数式组件做的 https://juejin.im/post/5a12603f6fb9a0451c39ff9c 同时附录一个字节跳动工程师的掘金文章讲的东西像React的issue被打会的文章！当然并不是讲就可以肆无忌惮的乱干，网络请求，Redux的函数编程式的输出值是真实存在的！（这个还是不完全具体正确的这个利用过程是更细度的，如果不是shouldComponentUpdata,PureComponent,函数式，还是会走协调的对比差异！总之意识中要有JSX或者说React组件不是真实DOM,你看见的打印不要想着这个DOM重新走了一边渲染过程）
