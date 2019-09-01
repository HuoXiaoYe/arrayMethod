
### forEach()方法的实现
> forEach()：无返回值，单纯的遍历数组。
```javascript
Array.prototype.myForEach = function(cb){ // 在Array对象的原型上添加 myForEach()方法， 接受一个回调函数
	for(let i=0; i<this.length; i++){ // this指的是当前实例化的数组对象
		let item = this[i]; // 定义回调函数接受的三个参数
		let index = i;
		let array = this;
		cb(item,index,array) // 调用
	}
}
```


### map()方法的实现
> map()：有返回值，无论返回什么都添加到新数组中。
```javascript
Array.prototype.myMap = function(cb) {
	let newArr = []; // 定义一个新的数组，用来接受返回值
	for (let i = 0; i < this.length; i++) {
		let item = this[i];
		let index = i;
		let array = this;
		let result = cb(item, index, array);
		newArr.push(result) // 将回到函数的结果push到新的数组中
	}
	return newArr // 返回这个新的数组
}
```

### filter()方法的实现
> filter(): 有返回值，将返回结果为true的每一项push到一个新的数组中。
```javascript
Array.prototype.myFilter = function(cb) {  // 实现方法和map()方法差不多
	let newArr = [];
	for (var i = 0; i < this.length; i++) {
		let item = this[i];
		let index = i;
		let array = this;
		let result = cb(item, index, array); 
		if (result) { // 判断回调函数的结果否为true，为true则将 该项的item push到新的数组中
			newArr.push(item);
		}
	}
	return newArr; // 返回新的数组
}

```

### every()方法的实现
> every(): 有返回值，如果数组中的每一项都通过了测试，则返回true，反之返回false.
```javascript
Array.prototype.myEvery = function(cb){
	let bool = true;
	for (var i = 0; i < this.length; i++) {
		let item = this[i];
		let index = i;
		let array = this;
		let result = cb(item, index, array);
		if (!result) {
			bool = false;
			return bool;
		}
	}
}
```
