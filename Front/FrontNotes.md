###Emmet

- div>p>span
- ul>li*5
- div+p
- p[title="value"]
- p{HelloWorld}


###Atom
- alt-d delete to the end of the word
- alt-h delete to the begining of the word
- ctrl-e move to the end of the line
- ctrl-a move to the begining of the line


###ES6
- Babel转码器
	- 配置文件 .babelrc > 设置转码规则和插件
	- babel-register > 改写require命令，为它加上一个钩子。对require的文件转码。
	- babel-core > 调用Babel的API进行转码
	- babel-polyfill > 转换新的API

- let和const
	- let和const不会发生变量提升的现象
	- let和const会形成暂时性死区 > 如果区块中存在let和const命令，这个区块对变量形成封闭作用域
	- const声明一个只读的常量
	- 冻结对象 > const foo = Object.freeze({})

- 块级作用域
	- 一个大括号代表一个块级作用域，大括号内的变量在外面无法访问。

- 数组的解构赋值
	- let [a,b,c] = [1,2,3];
	- let [head, ...tail] = [1,2,3,4] > head=1, tail=[2,3,4]	- 用途
		- 交换变量的值 > [x,y] = [y,x]
		- 函数返回多个值 > return [1,2,3]
		- 提取JSON数据 > var jsonData= {id:42,status:"OK",data:[23,45]}; let [id,status,data:number] = jsonData;
		- 遍历map结构

- 字符串的扩展
	- padStart(),padEnd() > 'x'.padEnd(5,'ab') // 'xabab'
	- includes(),startWith(),endsWith();
	- repeat() > 'x'.repeat(3) // 'xxx

- 数组的扩展
	- find() > [3,4,-2,5].find((n) => n<0) // -2
	- findIndex()
	- includes()

- 函数的扩展
	- 参数可以设置默认值 (可以和解构赋值综合使用)
	- 默认值通常只给尾部参数设置
	- 函数的length属性，返回没有指定默认值的参数个数 > (function (a) {}).length = 1

- 对象的扩展
	- 对象可以只写属性名，不写属性值
	- Object.is()，与===的行为基本一致，不同的是，+0与-0不相等，NaN与NaN相等。
	- Object.assign()，用于对象的合并，是浅拷贝。

- 编程风格
	- 静态字符串一律使用单引号。动态字符串使用反引号
	- 优先使用解构赋值
	- 单行定义的对象，最后一个成员不加逗号。多行定义的对象，最后一行加逗号。
	- 使用...拷贝数组。
	- let { x: aa, y: bb}= { x: {name: 'kdot', age:12} , y: [2,3,4] , z: 123 }




###React.js


###Redux

- 单一数据源：state维护在唯一的object tree中，且这个tree只存在于唯一的一个store中
- state是只读的(immutable tree)，改变state的唯一方法是触发action。
- reducer用来描述action是如何改变state tree的
- reducer是一个纯函数，接收旧的state和action，返回新的state
- 不要在reducer做这些操作：
	- 修改传入参数
	- 执行有副作用的操作，如API请求和路由跳转
	- 调用非纯函数，如Date.now()或Math.random()
- 在reducer中不要修改state，使用Object.assign({},state,newState})新建一个副本。

- Action > 一个Object，必备type属性。
- 当你给store dispatch一个action的时候，store会自己调用内部的reducer来更新state。
- react-redux > 建立component和store之间的联系，做两件事：
	- mapping the store state into component input props
	- mapping actions into component output callback props
- react-redux的Provider，连接component tree和store，在最外层，是所有component的祖先。
- Middleware > 一个function，在action被dispatch的时候触发，对action做一些包装处理。（记载日志，处理异常，修改action，缓存results，改变action到达store的时间和方式。）
- Currying > 单个参数function的嵌套使用，提高function的可配置性。
-






###Full-Stack-Tutorial-Of-Redux
- Mocha > a test framework
- Chai > an assertion/expectation library used in tests
- Immutable > provide a number of data structures
- chai-immutable > extend Chai to add support for comparing Immutable data structures
- PureRenderMixin > 如果component的state和props比较简单，没有复杂的数据结构，可以加上这个mixin，当组件state或props发生变化时，只做shallow compare
-




###Webpack

####Compared with others

#####Gulp
-
