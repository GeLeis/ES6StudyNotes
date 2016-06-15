# ES6StudyNotes
ES6StudyNotes
#ES6StudyNotes
1.ES6新增let命令，和var不同的是，let声明的变量作用域为括号内，var可以在括号外使用
```js
{
let a = 10 
var b = 1
}
a // ReferenceError
b //1
```

2.暂时性死区,在es6中，作用域内如果有let,const修饰的变量，在这声明之前都不能使用,在es5中存在函数提升，在es6中不存在，函数提升就是在函数内声明的变量，作用域都会提升到最顶层
```js
if (true) {
  // TDZ开始
  tmp = 'abc'; // ReferenceError
  console.log(tmp); // ReferenceError

  let tmp; // TDZ结束
  console.log(tmp); // undefined

  tmp = 123;
  console.log(tmp); // 123
}
```

3.不能在相同作用域内重复声明一个变量，但是可以在一个作用域的字作用域中另外声明一个名字相同的变量
```js
function func(arg) {
  let arg; // 报错
}

function func(arg) {
  {
    let arg; // 不报错
  }
}
```

4.const声明的常量不能重复声明

5.声明变量时解析赋值不能使用圆括号，包括函数参数，（函数参数也是声明变量），不能将整个模式或者嵌套中的一层放入括号中

6.字符串中嵌入变凉
```js
// 字符串中嵌入变量
var name = "Bob", time = "today";
`Hello ${name}, how are you ${time}?`
```

7.[正则表达式](http://www.runoob.com/regexp/regexp-syntax.html)

8.javascript中整数和浮点数是相同的存储方式，3和3.0被视为同一个值
