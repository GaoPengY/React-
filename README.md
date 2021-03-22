# react

这世界上没有一个前端不想学好react，如果有,那么可能你还没有想明白！
                                    ----修.格拉底.鲁迅.言斯托洛夫斯基

[中文官网]: https://react.docschina.org/
[江湖地位]: https://my.oschina.net/lav/blog/4939049

### 前端主流框架
+ Angular.js：出来最早的前端框架，学习曲线比较陡，NG1学起来比较麻烦，NG2开始，进行了一系列的改革，也开始启用组件化了；在NG中，也支持使用TS（TypeScript）进行编程；
+ Vue.js：最火的一门前端框架，它是中国人开发的，对我们来说，文档要友好一些，去年12月发布了3.0的版本，也开始支持TS；
+ React.js：最流行的一门框架，因为它的设计很优秀，社区很庞大；

### React基本介绍
+ React 起源于 Facebook 的内部项目，因为该公司对市场上所有 JavaScript MVC 框架，都不满意，就决定自己写一套，用来架设 Instagram 的网站。做出来以后，发现这套东西很好用，**就在2013年5月开源了**。
+ 由于 React 的设计思想极其独特，属于革命性创新，性能出众，代码逻辑却非常简单。所以，越来越多的人开始关注和使用，认为它可能是将来 Web 开发的主流工具。

### React与vue.js的对比
#### 组件化方面
1. 什么是模块化：从 **代码** 的角度，去分析问题，把我们编程时候的业务逻辑，分割到不同的模块中来进行开发，这样能够**方便代码的重用**；
2. 什么是组件化：从 **UI** 的角度，去分析问题，把一个页面，拆分为一些互不相干的小组件，随着我们项目的开发，我们手里的组件会越来越多，最后，我们如果要实现一个页面，可能直接把现有的组件拿过来进行拼接，就能快速得到一个完整的页面， 这样方**便了UI元素的重用**；**组件是元素的集合体**；
3. 组件化的好处：
4. Vue是如何实现组件化的：.vue 组件模板文件，浏览器不识别这样的.vue文件，所以，在运行前，会把 .vue 预先编译成真正的组件；
 + template： UI结构
 + script： 业务逻辑和数据
 + style： UI的样式
5. React如何实现组件化：在React中实现组件化的时候，根本没有 像 .vue 这样的模板文件，而是，直接使用JS代码的形式，去创建任何你想要的组件；
 + React中的组件，都是直接在 js 文件中定义的；
 + React的组件，并没有把一个组件 拆分为 三部分（结构、样式、业务逻辑），而是全部使用JS来实现一个组件的；（也就是说：结构、样式、业务逻辑是混合在JS里面一起编写出来的）

#### 开发团队方面
+ React是由FaceBook前端官方团队进行维护和更新的；因此，React的维护开发团队，技术实力比较雄厚；
+ Vue：第一版，主要是有作者 尤雨溪 专门进行维护的，当 Vue更新到 2.x 版本后，也有了一个小团队进行相关的维护和开发；

#### 社区方面
+ 在社区方面，React由于诞生的较早，所以社区比较强大，一些常见的问题、坑、最优解决方案，文档、博客在社区中都是可以很方便就能找到的；
+ Vue是近几年才开始流行，主要在国内使用的比较多，所以，它的社区相对于React来说，要小巧一些，所以，可能有的一些坑，没人踩过；

#### 移动APP开发体验方面
+ Vue，结合 Weex 这门技术，提供了 迁移到 移动端App开发的体验
+ React，结合 ReactNative，也提供了无缝迁移到 移动App的开发体验（RN用的最多，也是最火最流行的）；

## react的环境准备
  * react依赖于node环境,在开始学习前需要先安装node，node版本需要在12以上,
   >地址：\\10.167.23.5\Software\40Tools\node
  * node安装完成后需要修改以下npm 的仓库和网络代理配置
  ```
  npm config set registry https://registry.npm.taobao.org
  npm config set https-proxy http://10.167.32.133:8080/
  npm config set strict-ssl false
  ```

  * 工具：推荐使用VS Code
  * 地址：\\10.167.23.5\Software\30Microsoft\Visual Studio\VSCode
  * 为了拥有更好的开发使用体验还需要安装以下插件
  ```
  ESLint：语法规则和代码风格的检查工具,可以用来保证写出语法正确、风格统一的代码
  IntelliJ IDEA Keybinding： idea的快捷键，看个人习惯
  Code Runner：代码执行插件(比较好用)
  open in browser： 可以在编辑页面指定浏览器打开html文件
  Simple React Snippets：快速生成React代码块
  ```

### react核心依赖的安装
  初始化项目 npm init -y
* npm i --save react 
   > 安装React 用于创建虚拟Dom和组件，其中包含了组件的生命周期
* npm i --save react-dom  
   > 安装React Dom 执行dom操作，进行数据的渲染

### 打包工具的安装
* npm i --save-dev webpack  
   > 安装webpack，打包工具
* npm i --save-dev webpack-cli  
   > 使用 webpack 4+ 版本，还需要安装 webpack-cli
* npm i --save-dev webpack-dev-server  
   > 安装webpack-dev-server，简单的express服务器，主要特性是支持热加载
    
* **注意事项：**
        webpack,webpack-cli,webpack-dev-server之间存在版本的不兼容问题
        在运行时可能出现以下异常
            Error: Cannot find module 'webpack-cli/bin/config-yargs'
        解决的办法是卸载本地安装的webpack-cli,webpack-dev-server
        然后指定具体的依赖版本，使用命令如下
        
        卸载
        npm uninstall webpack-cli -D
        npm uninstall webpack-dev-server -D
        安装指定版本
        npm i webpack-cli@3.3.12 -D
        npm i webpack-dev-server@3.11.0 -D

* npm i --save-dev html-webpack-plugin html-loader  
    > webpack需要 html-webpack-plugin和html-loader这两个组件来处理HTML

### 安装babel
* npm i --save-dev @babel/core
   > 安装babel，用于将ES6代码转为ES5代码，从而可以在现有环境下执行
* npm i --save-dev babel-loader 
   > webpack并不知道如何将ES6语法转换为ES5，不过 webpack 可以使用 loader 来完成
* npm i --save-dev @babel/preset-env 
   > 将JS特性跟特定的babel插件建立映射关系，根据配置的目标浏览器或者运行环境自动将ES2015(ES6)+的代码转换为es5
* npm i --save-dev @babel/preset-react 
   > 用于将JSX语法转化为JavaScript

### 配置文件
#### 修改package.json文件,在scripts中追加如下内容ii
*  "start": "webpack-dev-server --open --mode development",
    用于启动项目(npm start)
*  "build": "webpack --mode production"
    用于打包项目(npm build)

#### webpack的配置，新建webpack.config.js,写入如下内容
```
    const HtmlWebPackPlugin = require("html-webpack-plugin");
    module.exports = {
        module: {
            rules: [
                {
                    //使用babel解析jsx和js文件
                    test: /\.(js|jsx)$/,
                    exclude: /node_modules/,
                    use: {
                        loader: "babel-loader"
                    }
                },
                {   
                    //使用html-loader解析html文件
                    test: /\.html$/,
                    use: [
                        {
                            loader: "html-loader"
                        }
                    ]
                }
            ]
        },
        plugins: [
            new HtmlWebPackPlugin({
                template: "./index.html",
                filename: "./index.html"
            })
        ]
    };
```

#### babel的配置,新建.babelrc文件
    Babel在执行编译的过程中，会从项目的根目录下的 .babelrc文件中读取配置，.babelrc是一个json格式的文件。
    在.babelrc文件中，主要是对预设(presets) 和 插件(plugins) 进行配置
    {
        "presets": [
            "@babel/preset-env",
            "@babel/preset-react"
        ]
    }

## 快速体验(hello world)
### 在项目根目录下创建index.html
```
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>new react project</title>
    </head>
    <body>
        <!-- react组件渲染的位置 --> 
        <div id="app"></div>
    </body>
    </html>
```

### 在根目录下创建src文件夹,然后创建index.js文件
```
    // 导入react,Component,ReactDom
    import React,{Component} from 'react';
    import ReactDom from 'react-dom';

    // 组件  
    class App extends Component {
        //渲染函数
        render() {
            return (
                <h1>
                    Hello World !
                </h1>
            )
        }
    }
    
    // ReactDom将组件渲染到指定位置
    ReactDom.render(
        <App />,
        document.getElementById('app')
    );
```
使用脚手架~~
npm install create-react-app -g
create-react-app [项目名]

## ES6基础
详见[React基础--ES6.pdf]
[es6更多知识(JS 教程)]: https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Classes/extends

补充内容
### class的使用
 + ES6之前
    - 实例的声明(构造函数)
        function Object(){
        }
    - 实例的属性
        Object.prototype.name = 'xiaoming'
    - 实例的静态属性
        Object.age = 111


 + 实例的创建
```
    let obj = new Object();
```

 + ES6中追加了类的使用
 + 类的声明
 ```
    class Object{
        //类的静态属性
        static AGE = 111;
        static staticMethod = function(){
            console.log("静态函数")
            //静态函数无法访问实例,此处的this指构造函数
            console.log(this)
        }
        name = 'xiaoming'
        //类的属性也可以是方法，用来描述类的行为
        show(){
            //此处需要注意的是 下面的this就是对象本身
            //但是如果声明属性时使用箭头函数那么这个this会向上使用别人的(使用前绑定了this的话，未绑定this运行时会出错)，并不是自己
            console.log(this.name);
        }
    }
```
 + 类的实例
```
    let obj = new Object();
    //实例可以访问类的静态属性
    Object.staticMethod();
```

 + 类的继承
    - ES6之前
```
    function o(obj){
        this.obj = obj;
        //实际上是将obj的属性赋值给o
        // this.prototype = obj.prototype;
    }
```
    - ES6
```
    class People{
        //构造器
        constructor(props){
            this.age = props.age;
        }

        age = 100;
    }
    class Student extends People{
        name = "xiaoming";
        //构造器
        constructor(props){
            //必须对父类先进行初始化
            super(props);
            this.name = props.name;
        } 
    }
```

 + 创建对象
```
    let stu = new Student({name:"xiaoming",age:20});
```
[js的原型继承]: https://www.html.cn/archives/10030/

### 导入和导出
 1. 默认导入导出(可导出任意数据)
    * demo.js
    ```
      export default '12345'
    ```
    * 默认导入
    ```
      import demo from './demo.js'
    ```
    * 此时demo的值就是12345
 2. 按需导出
    * demo02.js
    * 先定义再导出
    ```
    let data = "12345";
    export {data}
    ```
    * 定义加导出
    ```
    export let data = "12345";
    ```

    * 按需导入
    ```
    import {data} from './demo02.js'
    ```
 3. 全体导入
     ```
    import * as object from './xxxx.js'
     ```
    * 实际上导入的数据都会被封装为一个对象，
    * 默认导入时会获取对象的默认属性的值
    * 按需导入会获取这个对象对应的属性的值
 4. **注意事项**
    * 导入需要放在文件的最上方
    * 导入语句必须在顶级作用域中，不能包含在条件块里
 5. **ES6 import 和CommonJS require的区别**
    * require的实现主要在node平台，import在浏览器端
    * import的加载机制是，加载前置，需要使用的数据必须在使用前导入
    * require的加载机制是，按需加载，可以在使用的过程中导入数据，代码执行到那一行才进行加载

## React基础
### 基本概念
#### 虚拟DOM（Virtual Document Object Model）
 + DOM的本质是什么：就是用JS表示的UI元素
 + DOM和虚拟DOM的区别：
   - DOM是由浏览器中的JS提供功能，所以我们只能人为的使用 浏览器提供的固定的API来操作DOM对象；
   - 虚拟DOM：并不是由浏览器提供的，而是我们程序员手动模拟实现的，类似于浏览器中的DOM，但是有着本质的区别；
 - 为什么要实现虚拟DOM：
 - 什么是React中的虚拟DOM：
 - 虚拟DOM的目的：
![虚拟DOM - 表格排序案例](./images/ReactDom.png)

#### Diff算法
 - tree diff:新旧DOM树，逐层对比的方式，就叫做 tree diff,每当我们从前到后，把所有层的节点对比完后，必然能够找到那些 需要被更新的元素；
 - component diff：在对比每一层的时候，组件之间的对比，叫做 component diff;当对比组件的时候，如果两个组件的类型相同，则暂时认为这个组件不需要被更新，如果组件的类型不同，则立即将旧组件移除，新建一个组件，替换到被移除的位置；
 - element diff:在组件中，每个元素之间也要进行对比，那么，元素级别的对比，叫做 element diff；
 - key：key这个属性，可以把 页面上的 DOM节点 和 虚拟DOM中的对象，做一层关联关系；
![Diff算法图](./images/Diff.png)

### 核心对象
#### React
 + 用来创建虚拟dom，React组件、组件生命周期等的
 + 使用JS的创建虚拟DOM节点：
    - 在 react中，如要要创建DOM元素了，只能使用 React 提供的 JS API 来创建，不能直接像Vue 中那样，手写 HTML 元素
    - React.createElement() 方法，用于创建 虚拟DOM 对象，它接收 3个及以上的参数
        * 参数1： 是个字符串类型的参数，表示要创建的元素类型
        * 参数2： 是一个属性对象，表示 创建的这个元素上，有哪些属性
        * 参数3： 从第三个参数的位置开始，后面可以放好多的虚拟DOM对象，这些参数，表示当前元素的子节点
        ```
         <div title="this is a div" id="mydiv">这是一个div</div>
         var myH1 = React.createElement('h1', null, '这是一个大大的H1')
         var myDiv = React.createElement('div', { title: 'this is a div', id: 'mydiv' }, '这是一个div', myH1)
        ```

#### ReactDom
 + 封装了和 DOM 操作相关的包，比如，要把组件渲染到页面上
 + 使用 ReactDOM 把元素渲染到页面指定的容器中：
    - ReactDOM.render('要渲染的虚拟DOM元素', '要渲染到页面上的哪个位置中')
        * 注意： ReactDOM.render() 方法的第二个参数，和vue不一样，不接受 "#app" 这样的字符串，而是需要传递一个原生的 DOM 对象
    - ReactDOM.render(myDiv, document.getElementById('app'))

### JSX语法
1. JSX语法的本质：还是以 `React.createElement` 的形式来实现的，并没有直接把用户写的 `HTML`代码，渲染到页面上；
2. 如果要在 JSX 语法内部，书写 JS 代码了，那么，所有的JS代码，必须写到 {} 内部；
3. 当编译引擎，在编译JSX代码的时候，如果遇到了`<`那么就把它当作HTML代码去编译，如果遇到了 `{}` 就把 花括号内部的代码当作普通JS代码去编译；
4. 在{}内部，可以写任何符合JS规范的代码；
5. 在JSX中，如果要为元素添加`class`属性了，那么，必须写成`className`，因为 `class`在ES6中是一个关键字；和`class`类似，label标签   的 `for` 属性需要替换为 `htmlFor`.
6. 在JSX创建DOM的时候，所有的节点，必须有唯一的根元素进行包裹；
7. 如果要写注释，注释必须放到 {} 内部

### Component(组件)
#### 组件的创建方式
+ 使用 class 关键字来创建组件
```
class Person extends React.Component{
    // 通过报错提示得知：在class创建的组件中，必须定义一个render函数
    render(){
        // 在render函数中，必须返回一个null或者符合规范的虚拟DOM元素
        return <div>
            <h1>这是用 class 关键字创建的组件！</h1>
        </div>;
    }
}
```

#### state和props
    组件需要使用数据。可以使用两种不同的方式来组合组件和数据：props和state 。 props和state决定了组件渲染的内容以及行为方式。
+ props
    * 如果组件是普通JavaScript函数，则`props`将是函数输入。 依此类推，组件接受的输入参数`props`，对其进行处理，然后呈现一些JSX代码。
    * `React`的核心思想就是组件化思想，页面会被切分成一些独立的、可复用的组件。
    * 组件从概念上看就是一个函数，可以接受一个参数作为输入值，这个参数就是`props`，所以可以把`props`理解为从外部传入组件内部的数据。由于`React`是单向数据流，所以`props`基本上也就是从服父级组件向子组件传递的数据。
    * `props`是一个从外部传进组件的参数，主要作为就是从父组件向子组件传递数据，它具有可读性和不变性，只能通过外部组件主动传入新的* `props`来重新渲染子组件，否则子组件的props以及展现形式不会改变。尽管`props`中的数据可以被组件访问，但是`React`的哲学是`props`应该是不可变的并且自上而下。所以父组件可以将其想要的任何数据作为`props`传递给子组件，但是子组件不能修改`props`。 
+ state
    * `state`是声明它的组件所拥有的对象。它的范围仅限于当前组件。 组件可以初始化其状态，并在必要时进行更新。 父组件的状态通常最终是子组件的`props`。 当状态超出当前范围时，我们将其称为`props`。
    * 一个组件的显示形态可以由数据状态和外部参数所决定，外部参数也就是`props`，而数据状态就是`state`。
    首先，在组件初始化的时候，通过`this.state`给组件设定一个初始的`state`，在第一次`render`的时候就会用这个数据来渲染组件。
    `setState`

    * `state`不同于`props`的一点是，`state`是可以被改变的。不过，不可以直接通过`this.state=`的方式来修改，而需要通过`this.setState()`方法来修改`state`。
    * 当数据获取完成后，通过`this.setState`来修改数据状态。
    * 当我们调用`this.setState`方法时，`React`会更新组件的数据状态`state`，并且重新调用`render`方法，也就是会对组件进行重新渲染。
    **注意**：通过`this.state=`来初始化`state`，使用`this.setState`来修改`state`，`constructor`是唯一能够初始化的地方。

#### 组件的生命周期
 + 概念：在组件创建、到加载到页面上运行、以及组件被销毁的过程中，总是伴随着各种各样的事件，这些在组件特定时期，触发的事件，统称为组件的生命周期；
 + 组件生命周期分为三部分：
   - **组件创建阶段**：组件创建阶段的生命周期函数，有一个显著的特点：创建阶段的生命周期函数，在组件的一辈子中，只执行一次；
	* componentWillMount: 组件将要被挂载，此时还没有开始渲染`虚拟DOM`
	* render：第一次开始渲染真正的`虚拟DOM`，当`render`执行完，内存中就有了完整的`虚拟DOM`了
	* componentDidMount: 组件完成了挂载，此时，组件已经显示到了页面上，当这个方法执行完，组件就进入都了运行状态

   - **组件运行阶段**：也有一个显著的特点，根据组件的state和props的改变，有选择性的触发0次或多次；
    * componentWillReceiveProps: 组件将要接收新属性，此时，只要这个方法被触发，就证明父组件为当前子组件传递了新的属性值；
    * shouldComponentUpdate: 组件是否需要被更新，此时，组件尚未被更新，但是，`state` 和 `props` 肯定是最新的
    * componentWillUpdate: 组件将要被更新，此时，尚未开始更新，内存中的虚拟DOM树还是旧的
    * render: 此时，又要重新根据最新的 `state` 和 `props` 重新渲染一棵内存中的虚拟DOM树，当 render调用完毕，内存中的旧DOM树，已经被新DOM树替换了！此时页面还是旧的
    * componentDidUpdate: 此时，页面又被重新渲染了，`state` 和 `虚拟DOM` 和 页面已经完全保持同步

   - **组件销毁阶段**：也有一个显著的特点，一辈子只执行一次；
    * componentWillUnmount: 组件将要被卸载，此时组件还可以正常使用；

#### 高阶组件
+ 在事件中绑定this并传参：
```
    <input type="button" value="在事件中绑定this并传参" onClick={this.handleMsg1.bind(this, '🍕', '🍟')} />

    // 在事件中绑定this并传参
    handleMsg1(arg1, arg2) {
        console.log(this);
        // 此时this是个null
        this.setState({
            msg: '在事件中绑定this并传参：' + arg1 + arg2
        });
    }
```
+ 在构造函数中绑定this并传参:
```
    // 修改构造函数中的代码：
    this.handleMsg2 = this.handleMsg2.bind(this, '🚗', '🚚');

    <input type="button" value="在构造函数中绑定this并传参" onClick={this.handleMsg2} />

    // 在构造函数中绑定this并传参
    handleMsg2(arg1, arg2) {
        this.setState({
            msg: '在构造函数中绑定this并传参：' + arg1 + arg2
        });
    }
```
+ 用箭头函数绑定this并传参：
```
    <input type="button" value="用箭头函数绑定this并传参" onClick={() => { this.handleMsg3('👩', '👰') }} />

    // 用箭头函数绑定this并传参
        handleMsg3(arg1, arg2) {
            this.setState({
                msg: '用箭头函数绑定this并传参：' + arg1 + arg2
            });
        }
```

#### react的双向数据绑定
1. 在Vue.js中，默认可以通过`v-model`指令，将表单控件和我们的`data`上面的属性进行双向数据绑定，数据变化和页面之间的变化是同步的！
2. 在React.js中，默认没有提供双向数据绑定这一功能，默认的，只能把`state`之上的数据同步到界面的控件上，但是不能默认实现把界面上数据的改变，同步到`state`之上，需要程序员手动调用相关的事件，来进行逆向的数据传输！
3. 绑定文本框和state的值：
```
    {/*只要将value属性，和state上的状态进行绑定，那么，这个表单元素就变成了受控表单元素，这时候，如果没有调用相关的事件，是无法手动修改表单元素中的值的*/}
    <input style={{ width: '100%' }} ref="txt" type="text" value={this.state.msg} onChange={this.handleTextChange} />

    // 这是文本框内容改变时候的处理函数
    handleTextChange = () => {
        this.setState({
            msg: this.refs.txt.value
        });
    }
```
4. 注意`setState的一个问题`：
```
// 保存最新的state状态值，在保存的时候，是异步进行保存的，所以，如果想要获取最新的，刚刚保存的那个状态，需要通过回掉函数的形式去获取最新state
this.setState({
    msg: this.refs.txt.value
    // msg: e.target.value
}, function () {
    // 获取最新的state状态值
    console.log(this.state.msg);
});
```

## Redux
 + Redux 和 React 没有直接关系，它瞄准的目标是应用状态管理。
 + 核心概念是 Map/Reduce 中的 Reduce。且 Reducer 的执行是同步，产生的 State 是 Immutable 的。
 + 改变 State 只能通过向 Reducer dispatch actions 来完成。

 + State 的不同字段，可以通过不同的 Reducers 来分别维护。combineReducers 负责组合这些 Reducers，前提是每个 Reducer 只能维护自己关心的字段。

 + Action 对象只能是 Javascript Plain Object，但是通过在 store 上装载 middleware，则可以任意定义 action 对象的形式，反正会有特定的 middleware 负责将此 action 对象变为 Javascript Plain Object。可以以middleware 链条为集中点实现很多控制逻辑，例如 Log，Undo, ErrorHandler 等。
 + Redux 仅仅专注于应用状态的维护，reducer、dispatch/middleware 是两个常用扩展点、Higher-order Store 则仅针对需要扩展全部 Store 功能时使用。
 + react-redux 是 Redux 针对 React/React-Native 的 Binding，connect/selector 是扩展点，负责将 store 中的状态添加到 React component 的 props 中。
 + Redux 借用了很多函数式编程的思想，了解函数式编程会利于理解其实现原理，虽然使用它不需要了解很多函数式编程的概念。和 Flux 相比，Redux 的概念更精简、约定更严格、状态更确定、而是扩展却更灵活。

