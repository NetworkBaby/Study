# Class

- 1、Class基本语法
- 2、Class的继承
- 3、原生构造函数的继承
- 4、Class的取值函数（getter）和存值函数（setter）
- 5、Class的Generator方法
- 6、Class的静态方法
- 7、Class的静态属性
- 8、new.target属性
- 9、Mixin模式的实现

### 1、Class基本语法

#### （1）概述

JavaScript语言的传统方法是通过构造函数，定义并生成新对象。下面是一个例子。

	function Point(x,y){
	  this.x = x;
	  this.y = y;
	}
	
	Point.prototype.toString = function () {
	  return '(' + this.x + ', ' + this.y + ')';
	}

上面这种写法跟传统的面向对象语言（比如C++和Java）差异很大，很容易让新学习这门语言的程序员感到困惑。

ES6提供了更接近传统语言的写法，引入了`Class`（类）这个概念，作为对象的模板。通过`class`关键字，可以定义类。基本上，ES6的class可以看作只是一个语法糖，它的绝大部分功能，ES5都可以做到，新的class写法只是让对象原型的写法更加清晰、更像面向对象编程的语法而已。上面的代码用ES6的“类”改写，就是下面这样。

	//定义类
	class Point {
	
	  constructor(x, y) {
	    this.x = x;
	    this.y = y;
	  }
	
	  toString() {
	    return '(' + this.x + ', ' + this.y + ')';
	  }
	}

上面代码定义了一个“类”，可以看到里面有一个`constructor`方法，这就是构造方法，而this关键字则代表实例对象。也就是说，ES5的构造函数Point，对应ES6的Point类的构造方法。

Point类除了构造方法，还定义了一个toString方法。注意，定义“类”的方法的时候，前面不需要加上function这个保留字，直接把函数定义放进去了就可以了。另外，方法之间不需要逗号分隔，加了会报错。

ES6的类，完全可以看作构造函数的另一种写法。

	class Point{
	  // ...
	}
	
	typeof Point // "function"
	Point === Point.prototype.constructor // true

上面代码表明，类的数据类型就是函数，类本身就指向构造函数。

构造函数的`prototype`属性，在ES6的“类”上面继续存在。事实上，类的所有方法都定义在类的`prototype`属性上面。

	class Point {
	  constructor(){
	    // ...
	  }
	
	  toString(){
	    // ...
	  }
	
	  toValue(){
	    // ...
	  }
	}
	
	// 等同于
	
	Point.prototype = {
	  toString(){},
	  toValue(){}
	}

在类的实例上面调用方法，其实就是调用原型上的方法。
	
	class B {}
	let b = new B();
	
	b.constructor === B.prototype.constructor // true

上面代码中，b是B类的实例，它的constructor方法就是B类原型的`constructor`方法。

由于类的方法（除`constructor`以外）都定义在`prototype`对象上面，所以类的新方法可以添加在`prototype`对象上面。`Object.assign`方法可以很方便地一次向类添加多个方法。

	class Point {
	  constructor(){
	    // ...
	  }
	}
	
	Object.assign(Point.prototype, {
	  toString(){},
	  toValue(){}
	})

`prototype`对象的`constructor`属性，直接指向“类”的本身，这与ES5的行为是一致的。
	
	Point.prototype.constructor === Point // true

另外，类的内部所有定义的方法，都是不可枚举的（`enumerable`）。
	
	class Point {
	  constructor(x, y) {
	    // ...
	  }
	
	  toString() {
	    // ...
	  }
	}
	
	Object.keys(Point.prototype)
	// []
	Object.getOwnPropertyNames(Point.prototype)
	// ["constructor","toString"]

上面代码中，`toString`方法是Point类内部定义的方法，它是不可枚举的。这一点与ES5的行为不一致。
	
	var Point = function (x, y){
	  // ...
	}
	
	Point.prototype.toString = function() {
	  // ...
	}
	
	Object.keys(Point.prototype)
	// ["toString"]
	Object.getOwnPropertyNames(Point.prototype)
	// ["constructor","toString"]

上面代码采用ES5的写法，`toString`方法就是可枚举的。

类的属性名，可以采用表达式。

	let methodName = "getArea";
	class Square{
	  constructor(length) {
	    // ...
	  }
	
	  [methodName]() {
	    // ...
	  }
	}

上面代码中，Square类的方法名getArea，是从表达式得到的。

#### （2）constructor方法

`constructor`方法是类的默认方法，通过new命令生成对象实例时，自动调用该方法。一个类必须有`constructor`方法，如果没有显式定义，一个空的`constructor`方法会被默认添加。
	
	constructor() {}

`constructor`方法默认返回实例对象（即this），完全可以指定返回另外一个对象。

	class Foo {
	  constructor() {
	    return Object.create(null);
	  }
	}
	
	new Foo() instanceof Foo
	// false

上面代码中，`constructor`函数返回一个全新的对象，结果导致实例对象不是Foo类的实例。

#### （3）实例对象

生成实例对象的写法，与ES5完全一样，也是使用new命令。如果忘记加上new，像函数那样调用Class，将会报错。
	
	// 报错
	var point = Point(2, 3);
	
	// 正确
	var point = new Point(2, 3);

与ES5一样，实例的属性除非显式定义在其本身（即定义在this对象上），否则都是定义在原型上（即定义在class上）。

	//定义类
	class Point {
	
	  constructor(x, y) {
	    this.x = x;
	    this.y = y;
	  }
	
	  toString() {
	    return '('+this.x+', '+this.y+')';
	  }
	
	}
	
	var point = new Point(2, 3);
	
	point.toString() // (2, 3)
	
	point.hasOwnProperty('x') // true
	point.hasOwnProperty('y') // true
	point.hasOwnProperty('toString') // false
	point.__proto__.hasOwnProperty('toString') // true

上面代码中，x和y都是实例对象point自身的属性（因为定义在this变量上），所以`hasOwnProperty`方法返回true，而`toString`是原型对象的属性（因为定义在Point类上），所以`hasOwnProperty`方法返回false。这些都与ES5的行为保持一致。

与ES5一样，类的所有实例共享一个原型对象。
	
	var p1 = new Point(2,3);
	var p2 = new Point(3,2);
	
	p1.__proto__ === p2.__proto__
	//true

上面代码中，p1和p2都是Point的实例，它们的原型都是Point，所以`__proto__`属性是相等的。

这也意味着，可以通过实例的`__proto__`属性为Class添加方法。
	
	var p1 = new Point(2,3);
	var p2 = new Point(3,2);
	
	p1.__proto__.printName = function () { return 'Oops' };
	
	p1.printName() // "Oops"
	p2.printName() // "Oops"
	
	var p3 = new Point(4,2);
	p3.printName() // "Oops"

上面代码在p1的原型上添加了一个`printName`方法，由于p1的原型就是p2的原型，因此p2也可以调用这个方法。而且，此后新建的实例p3也可以调用这个方法。这意味着，使用实例的`__proto__`属性改写原型，必须相当谨慎，不推荐使用，因为这会改变Class的原始定义，影响到所有实例。

#### （4）name属性

由于本质上，ES6的Class只是ES5的构造函数的一层包装，所以函数的许多特性都被Class继承，包括name属性。
	
	class Point {}
	Point.name // "Point"

`name`属性总是返回紧跟在class关键字后面的类名。

#### （5）Class表达式

与函数一样，Class也可以使用表达式的形式定义。

	const MyClass = class Me {
	  getClassName() {
	    return Me.name;
	  }
	};

上面代码使用表达式定义了一个类。需要注意的是，这个类的名字是MyClass而不是Me，Me只在Class的内部代码可用，指代当前类。

	let inst = new MyClass();
	inst.getClassName() // Me
	Me.name // ReferenceError: Me is not defined

上面代码表示，Me只在Class内部有定义。

如果Class内部没用到的话，可以省略Me，也就是可以写成下面的形式。
	
	const MyClass = class { /* ... */ };

采用Class表达式，可以写出立即执行的Class。
	
	let person = new class {
	  constructor(name) {
	    this.name = name;
	  }
	
	  sayName() {
	    console.log(this.name);
	  }
	}("张三");
	
	person.sayName(); // "张三"

上面代码中，person是一个立即执行的Class的实例。

#### （6）不存在变量提升

Class不存在变量提升（hoist），这一点与ES5完全不同。
	
	new Foo(); // ReferenceError
	class Foo {}

上面代码中，Foo类使用在前，定义在后，这样会报错，因为ES6不会把变量声明提升到代码头部。这种规定的原因与下文要提到的继承有关，必须保证子类在父类之后定义。
	
	{
	  let Foo = class {};
	  class Bar extends Foo {
	  }
	}

如果存在Class的提升，上面代码将报错，因为let命令也是不提升的。

#### （7）严格模式

类和模块的内部，默认就是严格模式，所以不需要使用`use strict`指定运行模式。只要你的代码写在类或模块之中，就只有严格模式可用。

考虑到未来所有的代码，其实都是运行在模块之中，所以ES6实际上把整个语言升级到了严格模式。

### 2、Class的继承

#### 基本用法

Class之间可以通过extends关键字实现继承，这比ES5的通过修改原型链实现继承，要清晰和方便很多。
	
	class ColorPoint extends Point {}

上面代码定义了一个`ColorPoint`类，该类通过extends关键字，继承了Point类的所有属性和方法。但是由于没有部署任何代码，所以这两个类完全一样，等于复制了一个Point类。下面，我们在ColorPoint内部加上代码。

	class ColorPoint extends Point {
	
	  constructor(x, y, color) {
	    super(x, y); // 调用父类的constructor(x, y)
	    this.color = color;
	  }
	
	  toString() {
	    return this.color + ' ' + super.toString(); // 调用父类的toString()
	  }
	}

上面代码中，`constructor`方法和`toString`方法之中，都出现了`super`关键字，它指代父类的实例（即父类的this对象）。

子类必须在`constructor`方法中调用super方法，否则新建实例时会报错。这是因为子类没有自己的this对象，而是继承父类的this对象，然后对其进行加工。如果不调用super方法，子类就得不到this对象。
	
	class Point { /* ... */ }
	
	class ColorPoint extends Point {
	  constructor() {
	  }
	}
	
	let cp = new ColorPoint(); // ReferenceError

上面代码中，`ColorPoint`继承了父类Point，但是它的构造函数没有调用super方法，导致新建实例时报错。

ES5的继承，实质是先创造子类的实例对象this，然后再将父类的方法添加到this上面（`Parent.apply(this)`）。ES6的继承机制完全不同，实质是先创造父类的实例对象this（所以必须先调用super方法），然后再用子类的构造函数修改this。

如果子类没有定义constructor方法，这个方法会被默认添加，代码如下。也就是说，不管有没有显式定义，任何一个子类都有constructor方法。
	
	constructor(...args) {
	  super(...args);
	}

另一个需要注意的地方是，在子类的构造函数中，只有调用super之后，才可以使用this关键字，否则会报错。这是因为子类实例的构建，是基于对父类实例加工，只有super方法才能返回父类实例。
	
	class Point {
	  constructor(x, y) {
	    this.x = x;
	    this.y = y;
	  }
	}
	
	class ColorPoint extends Point {
	  constructor(x, y, color) {
	    this.color = color; // ReferenceError
	    super(x, y);
	    this.color = color; // 正确
	  }
	}

上面代码中，子类的`constructor`方法没有调用super之前，就使用this关键字，结果报错，而放在super方法之后就是正确的。

下面是生成子类实例的代码。
	
	let cp = new ColorPoint(25, 8, 'green');
	
	cp instanceof ColorPoint // true
	cp instanceof Point // true

上面代码中，实例对象cp同时是ColorPoint和Point两个类的实例，这与ES5的行为完全一致。

#### 类的prototype属性和__proto__属性

大多数浏览器的ES5实现之中，每一个对象都有`__proto__`属性，指向对应的构造函数的`prototype`属性。Class作为构造函数的语法糖，同时有`prototype`属性和`__proto__`属性，因此同时存在两条继承链。

- （1）子类的`__proto__`属性，表示构造函数的继承，总是指向父类。

- （2）子类`prototype`属性的`__proto__`属性，表示方法的继承，总是指向父类的`prototype`属性。

	class A {
	}
	
	class B extends A {
	}
	
	B.__proto__ === A // true
	B.prototype.__proto__ === A.prototype // true

上面代码中，子类B的`__proto__`属性指向父类A，子类B的`prototype`属性的`__proto__`属性指向父类A的`prototype`属性。

这样的结果是因为，类的继承是按照下面的模式实现的。
	
	class A {
	}
	
	class B {
	}
	
	// B的实例继承A的实例
	Object.setPrototypeOf(B.prototype, A.prototype);
	
	// B继承A的静态属性
	Object.setPrototypeOf(B, A);

《对象的扩展》一章给出过`Object.setPrototypeOf`方法的实现。
	
	Object.setPrototypeOf = function (obj, proto) {
	  obj.__proto__ = proto;
	  return obj;
	}

因此，就得到了上面的结果。
	
	Object.setPrototypeOf(B.prototype, A.prototype);
	// 等同于
	B.prototype.__proto__ = A.prototype;
	
	Object.setPrototypeOf(B, A);
	// 等同于
	B.__proto__ = A;

这两条继承链，可以这样理解：作为一个对象，子类（B）的原型（`__proto__`属性）是父类（A）；作为一个构造函数，子类（B）的原型（`prototype`属性）是父类的实例。
	
	B.prototype = new A();
	// 等同于
	B.prototype.__proto__ = A.prototype;

#### Extends 的继承目标

`extends`关键字后面可以跟多种类型的值。
	
	class B extends A {
	}

上面代码的A，只要是一个有`prototype`属性的函数，就能被B继承。由于函数都有`prototype`属性，因此A可以是任意函数。

下面，讨论三种特殊情况。

**第一种特殊情况，子类继承Object类**
	
	class A extends Object {
	}
	
	A.__proto__ === Object // true
	A.prototype.__proto__ === Object.prototype // true

这种情况下，A其实就是构造函数`Object`的复制，A的实例就是`Object`的实例。

**第二种特殊情况，不存在任何继承**
	
	class A {
	}
	
	A.__proto__ === Function.prototype // true
	A.prototype.__proto__ === Object.prototype // true

这种情况下，A作为一个基类（即不存在任何继承），就是一个普通函数，所以直接继承`Funciton.prototype`。但是，A调用后返回一个空对象（即`Object`实例），所以`A.prototype.__proto__`指向构造函数`（Object）`的`prototype`属性。

**第三种特殊情况，子类继承null**
	
	class A extends null {
	}
	
	A.__proto__ === Function.prototype // true
	A.prototype.__proto__ === undefined // true

这种情况与第二种情况非常像。A也是一个普通函数，所以直接继承`Funciton.prototype`。但是，A调用后返回的对象不继承任何方法，所以它的`__proto__`指向`Function.prototype`，即实质上执行了下面的代码。
	
	class C extends null {
	  constructor() { return Object.create(null); }
	}

#### Object.getPrototypeOf()

`Object.getPrototypeOf`方法可以用来从子类上获取父类。
	
	Object.getPrototypeOf(ColorPoint) === Point
	// true

因此，可以使用这个方法判断，一个类是否继承了另一个类。

#### super关键字

上面讲过，在子类中，`super`关键字代表父类实例。
	
	class B extends A {
	  get m() {
	    return this._p * super._p;
	  }
	  set m() {
	    throw new Error('该属性只读');
	  }
	}

上面代码中，子类通过`super`关键字，调用父类的实例。

由于，对象总是继承其他对象的，所以可以在任意一个对象中，使用`super`关键字。

	var obj = {
	  toString() {
	    return "MyObject: " + super.toString();
	  }
	}
	
	obj.toString(); // MyObject: [object Object]

#### 实例的__proto__属性

子类实例的`__proto__`属性的`__proto__`属性，指向父类实例的`__proto__`属性。也就是说，子类的原型的原型，是父类的原型。

	var p1 = new Point(2, 3);
	var p2 = new ColorPoint(2, 3, 'red');
	
	p2.__proto__ === p1.__proto__ // false
	p2.__proto__.__proto__ === p1.__proto__ // true

上面代码中，`ColorPoint`继承了Point，导致前者原型的原型是后者的原型。

因此，通过子类实例的`__proto__.__proto__`属性，可以修改父类实例的行为。
	
	p2.__proto__.__proto__.printName = function () {
	  console.log('Ha');
	};
	
	p1.printName() // "Ha"

上面代码在`ColorPoint`的实例p2上向Point类添加方法，结果影响到了Point的实例p1。
	
### 3、原生构造函数的继承



### 4、Class的取值函数（getter）和存值函数（setter）



### 5、Class的Generator方法



### 6、Class的静态方法



### 7、Class的静态属性



### 8、new.target属性



### 9、Mixin模式的实现

















