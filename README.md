
### forEach()方法的实现
```javascript
Array.prototype.myForEach = function(cb){ // 在Array对象的原型上添加 myForEach()方法， 接受一个回调函数
	for(let i=0; i<this.length; i++){ // this指的是当前实例化的数组对象
		let item = this[i]; // 定义回调函数接受的三个参数
		let index = i;
		let array = this;
		cb(item,index,array) // 调用
	}
}
// 测试代码
let arr = [1,2,3,4,5,6]
arr.myForEach((itemindex,array)=>{
	if(item %2 ==0){
		console.log(item)
	}
})
```
