// Class equivalent
function Person(){
	this.name = 'default name';
};

Person.prototype.country = 'China';

Person.prototype.methodA = function(){
	console.log('methodA');
};

// 'new' operator equivalent. 
// var c = new Person();
// Example 1
var c = {};
Person.apply(c); //将构造函数的作用域赋给新对象（因此this指向了这个新对象）
c.__proto__ = Person.prototype;

// 'new' operator equivalent.  
// Example 2
var d = {};
Person.prototype.constructor.call(d);
c.__proto__ = Person.prototype;

//foo.call(this, arg1,arg2,arg3) == foo.apply(this, arguments)==this.foo(arg1, arg2, arg3)
//call, apply都属于Function.prototype的一个方法,它是JavaScript引擎内在实现的,因为属于Function.prototype,


##Reference
[new的原理](http://www.cnblogs.com/purediy/archive/2012/09/12/2682490.html)
[JavaScript this、new、apply和call详解](http://www.cnblogs.com/sharpxiajun/p/4148932.html)