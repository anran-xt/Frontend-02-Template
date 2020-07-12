### 用BNF编写带括号的四则运算

#### 先定义四则运算的例子： 1* 2+（（1+2）*3 +5）)
#### 终结符：+ - * / （ ）Number 
#### 非终结符：MultiplicativeExpression AddtiveExpression GroupExpression

~~~

  <MultiplicativeExpression>::=<Number>|<MultiplicativeExpression>"*"<Number>|<MultiplicativeExpression>"/"<Number>|

  <AddtiveExpression>::=<MultiplicativeExpression>|<AddtiveExpression>"+"<MultiplicativeExpression>|<AddtiveExpression>"-"<MultiplicativeExpression>|

  <GroupExpression>::="("<AddtiveExpression>")"|"("<MultiplicativeExpression>")"|"("<GroupExpression>")"

~~~

> 个人理解( )是基于另外两种表达式基础上进行分组，将可能存在的分组列出来就行，仅当包含( )符号时才满足该分组表达式,

### 尽可能的寻找你所知道的语言，并分类
- 解释型语言：Python,JAVA,Ruby,Php 
(随身携带一个翻译官，天生跨平台，依赖解释器，运行效率低)
- 编译型语言：C，C++，Delphi
(在执行源文件之前，先把源代码编译成目标代码，跨平台性差，执行速度快)

### 用Javascript 设计狗咬人的代码
~~~

  class Animal{
    constructor(name){
      this.name= name
    }
    bite(animal){
      console.log(this.name + 'bite' + animal.name);
      animal.health = bad
    }
  }

  class Dog extends Animal{
    constructor(name){
      super(name)
    }
  }

  class Person extends Animal{
    constructor(name){
      super(name)
      this.health = good
    }
  }

  let dog = new Dog('dog')
  let person= new Dog('person')
  dog.bite(person)

~~~

> 个人理解：咬的动作仅作为基类Animal的一个行为,该行为要涉及到多方对象,被咬对象会有状态改变

### String to UTF Conversion
> em...

### JavaScript 标准里面具有特殊行为的对象
1. Array：Array的length属性根据最大的下标自动发生变化。 
2. Object.prototype：作为所有正常对象的默认原型，不能再给它设置原型了。
3. String：为了支持下标运算，String的正整数属性访问会去字符串里查找。
4. Arguments：arguments的非负整数型下标属性跟对应的变量联动。