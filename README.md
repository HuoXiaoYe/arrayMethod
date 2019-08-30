```javascript
Array.prototype.myForEach = function(cb){
	for(let i=0; i<this.length; i++){
		let item = this[i];
		let index = i;
		let array = this;
		cb(item,index,array)
	}
}

let arr = [1,2,3,4,5,6]

arr.myForEach((itemindex,array)=>{
	if(item %2 ==0){
		console.log(item)
	}
})
```