- import函数返回一个Promise对象。
- import函数为异步加载，node的require函数为同步加载。
- 条件加载的时候很有用。
- 模块路径可动态生成，而import不支持动态路径
- import支持同时加载多个模块
- es6模块中自动启用严格模式，严格模式规则：
    + 变量必须声明后再使用
    + 函数的参数不能有同名属性，否则报错
    + 不能使用with语句
    + 不能对只读属性赋值，否则报错
    + 不能使用前缀 0 表示八进制数，否则报错
    + 不能删除不可删除的属性，否则报错
    + 不能删除变量delete prop，会报错，只能删除属性delete global[prop]
    + eval不会在它的外层作用域引入变量
    + eval和arguments不能被重新赋值
    + arguments不会自动反映函数参数的变化
    + 不能使用arguments.callee
    + 不能使用arguments.caller
    + 禁止this指向全局对象
    + 不能使用fn.caller和fn.arguments获取函数调用的堆栈
    + 增加了保留字（比如protected、static和interface）
- export * from '' 会忽略 export default输处接口
- export和import之间为接口动态绑定，输入接口中不能对变量重新赋值，否则会报语法错误。但是可以对输入的对象属性做修改，
这时其他模块也可以读到改写后的值。（不建议这么做。不利于查错）。
- import 在代码编译时执行，也就是先于其他代码执行。所以import具有提升效果，哪怕写在模块最后也是可以的。
- export default 在模块中只能使用一次

### javaScript标签异步加载
- defer 异步加载javascript文件，等页面渲染完成在执行，多个defer按页面出现顺序执行。
- async 异步加载javascript文件，加载完成会中断页面渲染，执行完再继续页面渲染，多个async不保证执行顺序。

- es6模块加载的是输出模块输出值的只读引用。所有模块import得到的值时一样的，并且不会缓存，实时获取，就是说，值变了，引用得到的值随之改变。
- CommonJS是运行时加载，返回的是值的拷贝，原有模块值改变在引用模块不会体现。加载多次也只会运行一次模块，后续的加载会从缓存中取值，除非手动清理系统缓存。
- es6模块中顶层对象指向undefined
- CommonJS发生循环加载时只输出已执行代码的值，未执行部分不会输出
- es6循环加载。。。。。本质上与CommonJS不同，开发者需自己保证在使用引用时能找到值。使用函数声明可以解决一些循环依赖问题（因为函数声明具有提升性）。
