# JavaScript之原型到原型链

 ##### 每个函数都有一个 prototype 属性;并且prototype是函数才会有的属性
 函数的 prototype 属性指向了一个对象，这个对象正是调用该构造函数而创建的实例的原型；每一个对象都会从原型"继承"属性
```shell
function Cat() {

}
Cat.prototype.name = '布丁';
var cat1 = new Cat();
var cat2 = new Cat();
console.log(cat1.name) // 布丁
console.log(cat2.name) // 布丁
```
 函数的prototype 属性指向了一个对象，这个对象正是调用该构造函数而创建的实例的原型，也就是上面例子重中的cat1和cat2的原型；即Cat.prototype是原型。那么，实例化出来的对象与原型什么关系呢？
每一个JavaScript对象(除了 null )都具有的一个属性，叫`__proto__`，这个属性会指向该对象的原型。即
```shell
	cat1.__proto__ === Cat.prototype
```
 
 	原型都有一个 constructor 属性指向关联的构造函数，即：
  ```shell
  	Cat === Cat.prototype.constructor
  ```

  当读取实例的属性时，如果找不到，就会查找与对象关联的原型中的属性，如果还查不到，就去找原型的原型，一直找到最顶层为止。

##### 简而言之的总结：
 - 	Cat.prototype === cat1.__proto__ 	//该对象原型得出的相等关系
 - 	Cat === Cat.prototype.constructor		//方法等于原型的构造器
 - 	读取实例的属性时会去去找原型的原型，一直找到最顶层为止；原型也是对象
 - 	Function.prototype 和 Object.prototype 是两个特殊的对象等于null，由引擎来创建

 > 博客地址：[smileyqp's Blog](https://blog.csdn.net/qq_34273059/article/details/100124501)