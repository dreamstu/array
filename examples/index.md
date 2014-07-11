# Demo

---
array 是一个对数组操作的模块，提供一些常用的操作数组的功能。

## 使用说明


### indexOf `object.indexOf(arr, obj, fromIndex)`

正向查找数组元素在数组中的索引下标，返回正向查找的索引编号*Number*。

     * @param {Array} arr 要执行操作的数组
     * @param {Object} obj 要查找的数组元素
     * @param {Number} fromIndex 开始的索引编号

示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5);
	console.info('indexOf:1 result:'+array.indexOf(arr,1));
	console.info('indexOf:2 result:'+array.indexOf(arr,2));
	console.info('indexOf:3 result:'+array.indexOf(arr,3));
	console.info('indexOf:4 result:'+array.indexOf(arr,4));
	console.info('indexOf:5 result:'+array.indexOf(arr,5));
});
````

执行后结果：
````html
<span id="indexOf">请查看console控制台</span>
````

---




### lastIndexOf `object.lastIndexOf(arr, obj, fromIndex)`

反向查找数组元素在数组中的索引下标，返回反向查找的索引编号*Number*。

     * @param {Array} arr 要执行操作的数组
     * @param {Object} obj 要查找的数组元素
     * @param {Number} fromIndex 开始的索引编号
示例：	
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5,5,4,3,2,1);
	console.info('lastIndexOf:1 result:'+array.lastIndexOf(arr,1));
	console.info('lastIndexOf:2 result:'+array.lastIndexOf(arr,2));
	console.info('lastIndexOf:3 result:'+array.lastIndexOf(arr,3));
	console.info('lastIndexOf:4 result:'+array.lastIndexOf(arr,4));
	console.info('lastIndexOf:5 result:'+array.lastIndexOf(arr,5));
});
````

执行后结果：
````html
<span id="indexOf">请查看console控制台</span>
````
---



### forEach `object.forEach(arr, fun ,[thisp])`

遍历数组，把每个数组元素作为第一个参数来执行函数。

     * @param {Array} arr 要执行操作的数组
     * @param {Function} fun 要执行的函数
     * @param {Object} contextObj 执行函数时的上下文对象，可以省略
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5,5,4,3,2,1);
	array.forEach(arr,function(value,index,arr){
		console.info('forEach:'+index+' result:'+value+' = '+arr);
	});
});
````

执行后结果：
````html
<span id="indexOf">请查看console控制台</span>
````
---


### filter `object.filter(arr, fun ,[thisp])`

用一个自定义函数来过滤数组,返回筛选出的新数组*Array*

     * @param {Array} arr 要执行操作的数组
     * @param {Function} fun 过滤函数
     * @param {Object} contextObj 执行函数时的上下文对象，可以省略
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5,5,4,3,2,1);
	arr = array.filter(arr,function(value,index,arr){
		if(value>2){
			return true;
		}
	});
	document.getElementById('filter_result').innerHTML= arr;
});
````

执行后结果：
````html
<span id="filter_result"></span>
````
---


### some `object.some(arr, fun ,[thisp])`

遍历数组，把每个数组元素作为第一个参数来执行函数，如果有任意一个或多个数组成员使得函数执行结果返回 true，
则最终返回 true，否则返回 false。*Boolean*

     * @param {Array} arr 要执行操作的数组
     * @param {Function} fun 要执行的函数
     * @param {Object} contextObj 执行函数时的上下文对象，可以省略
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5,5,4,3,2,1);
	var isPass = array.some(arr,function(value,index,arr){
		if(value>5){
			return true;
		}else{
			return false;
		}
	});
	document.getElementById('some_result').innerHTML= isPass;
});
````

执行后结果：
````html
<span id="some_result"></span>
````
---

### map `object.map(arr, fun ,[thisp])`

遍历数组，把每个数组元素作为第一个参数来执行函数，并把函数的返回结果以映射的方式存入到返回的数组中，返回映射后的新数组*Array*

     * @param {Array} arr 要执行操作的数组
     * @param {Function} fun 要执行的函数
     * @param {Object} contextObj 执行函数时的上下文对象，可以省略
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5,5,4,3,2,1);
	arr = array.map(arr,function(value,index,arr){
		if(value==5 || value==2){
			return 100;
		}else{
			return 0;
		}
	});
	document.getElementById('map_result').innerHTML= arr;
});
````

执行后结果：
````html
<span id="map_result"></span>
````
---

### every `object.every(arr, fun ,[thisp])`

遍历数组，把每个数组元素作为第一个参数来执行函数，如果所有的数组成员都使得函数执行结果返回 true，则最终返回 true，否则返回 false *Boolean*

     * @param {Array} arr 要执行操作的数组
     * @param {Function} fun 要执行的函数
     * @param {Object} contextObj 执行函数时的上下文对象，可以省略
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5,5,4,3,2,1);
	var isPass = array.every(arr,function(value,index,arr){
		if(value==0){
			return true;
		}else{
			return false;
		}
	});
	document.getElementById('every_result').innerHTML= isPass;
});
````

执行后结果：
````html
<span id="every_result"></span>
````
---


### reduce `object.reduce(arr, fun ,[contextObj])`

对该数组的每项和前一次调用的结果运行一个函数，收集最后的结果。*Boolean*

     * @param {Array} arr 要执行操作的数组
     * @param {Function} fun 要执行的函数
     * @param {Object} contextObj 执行函数时的上下文对象，可以省略
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5,5,4,3,2,1);
	var isPass = array.reduce(arr,function(rv, value, index, arr){
		console.info(rv, value, index, arr);
		if(value>2){
			return true;
		}else{
			return false;
		}
	});
	document.getElementById('reduce_result').innerHTML= isPass;
});
````

执行后结果：
````html
<span id="reduce_result"></span>
````
---


### reduceRight `object.reduceRight(arr, fun ,[contextObj])`

同上，但从右向左执行 *Boolean*。

     * @param {Array} arr 要执行操作的数组
     * @param {Function} fun 要执行的函数
     * @param {Object} contextObj 执行函数时的上下文对象，可以省略
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5,5,4,3,2,1);
	var isPass = array.reduceRight(arr,function(rv, value, index, arr){
		console.info(rv, value, index, arr);
		if(value>2){
			return true;
		}else{
			return false;
		}
	});
	document.getElementById('reduceRight_result').innerHTML= isPass;
});
````

执行后结果：
````html
<span id="reduceRight_result"></span>
````
---


### toArray `object.toArray(o)`

将任意变量转换为数组的方法 *Array*

     * @memberOf array
     * @param {Mixed} o 任意变量
     * @return {Array} 返回转换后的数组
示例：
````javascript
seajs.use(['btrjslibs-base','index'], function(base,array) {
	var object = "12,123,1234";
	var arr = array.toArray(object);
	var type = base.$typeof(arr);
	document.getElementById('toArray_result').innerHTML=type+"|"+arr;
});
````

执行后结果：
````html
<span id="toArray_result"></span>
````
---


### remove `object.remove(arr, members)`

从数组中移除一个或多个数组成员,找到并移除, 返回 true *Boolean*

     * @memberOf array
     * @param {Array} arr 要移除的数组成员，可以是单个成员也可以是成员的数组
     * @return {Boolean} 找到并移除, 返回 true	
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5);
	var isRemove = array.remove(arr,5);
	document.getElementById('remove_result').innerHTML=isRemove;
});
````

执行后结果：
````html
<span id="remove_result"></span>
````
---


### replace `object.replace(arr, oldValue, newValue)`

替换一个数组成员

     * @memberOf array
     * @param {Object} oldValue 当前数组成员
     * @param {Object} newValue 要替换成的值
     * @return {Boolean} 如果找到旧值并成功替换则返回 true，否则返回 false
示例：
````javascript
seajs.use('index', function(array) {
	var arr = new Array(1,2,3,4,5);
	var isReplace = array.replace(arr,5,100);
	document.getElementById('replace_result').innerHTML=isReplace+"|"+arr;
});
````

执行后结果：
````html
<span id="replace_result"></span>
````
---


### bubbleSort `object.bubbleSort(arr, compareFunc)`

冒泡排序,默认从小到大排序

     * @memberOf array
     * @param {Array} arr 需要排序的数组
     * @param {Function} compareFunc 比较方法, 传入两个参数 a,b, 若返回 大于0 则表示 a > b, 小于 0 则 a < b
     *  可选, 默认返回 a - b的结果
     * @return {Array} 排序后的数组
示例：
````javascript
seajs.use('index', function(array) {
	arr = array.bubbleSort([3,5,6,2], function(a, b){
		return a - b;
	});
	document.getElementById('bubbleSort_result').innerHTML=arr;
});
````

执行后结果：
````html
<span id="bubbleSort_result"></span>
````
---



### binarySearch `object.binarySearch(arr, item, compareFunc)`

二叉搜索

     * @memberOf array
     * @param {Array} arr 源数组
     * @param {Object} item 查找的目标
     * @param {Function} compareFunc 比较方法, 传入两个参数 a,b, 若返回 大于0 则表示 a > b, 小于 0 则 a < b
     * @return {Number} item 所处的 index
示例：
````javascript
seajs.use('index', function(array) {
	var index = array.binarySearch([3,5,6,2], 5, function(a, b){
		return a - b;
	});
	document.getElementById('binarySearch_result').innerHTML=index;
});
````

执行后结果：
````html
<span id="binarySearch_result"></span>
````
---


### contains `object.contains(arr, o)`

判断arr是否包含元素o

     * @memberOf array
     * @name contains
     * @function
     * @param {Array} arr
     * @param {Obejct} o
     * @return {Boolean}
示例：
````javascript
seajs.use('index', function(array) {
	var contains = array.contains([3,5,6,2], 5);
	document.getElementById('contains_result').innerHTML=contains;
});
````

执行后结果：
````html
<span id="contains_result"></span>
````
---

### uniquelize `object.uniquelize(arr)`

唯一化一个数组

     * @memberOf array
     * @param {Array} arr
     * @return {Array} 由不重复元素构成的数组
示例：
````javascript
seajs.use('index', function(array) {
	var arr = array.uniquelize([3,5,5,6,3,2,2]);
	document.getElementById('uniquelize_result').innerHTML=arr;
});
````

执行后结果：
````html
<span id="uniquelize_result"></span>
````
---


### intersect `object.intersect(a, b)`

求两个集合的交集

     * a ∩ b
     * @memberOf array
     * @param {Array} a
     * @param {Array} b
     * @return {Array} a ∩ b
示例：
````javascript
seajs.use('index', function(array) {
	var arr = array.intersect([3,5,5,6,3,2,2],[5,100,200,300]);
	document.getElementById('intersect_result').innerHTML=arr;
});
````

执行后结果：
````html
<span id="intersect_result"></span>
````
---


### minus `object.minus(a, b)`

求两个集合的差集

     * a - b
     * @memberOf array
     * @param {Array} a
     * @param {Array} b
     * @return {Array} a - b
示例：
````javascript
seajs.use('index', function(array) {
	var arr = array.minus([3,5,5,6,3,2,2],[5,100,200,300]);
	document.getElementById('minus_result').innerHTML=arr;
});
````

执行后结果：
````html
<span id="minus_result"></span>
````
---


### union `object.union(a, b)`

求两个集合的并集

     * a U b
     * @memberOf array
     * @param {Array} a
     * @param {Array} b
     * @return {Array} a U b
示例：
````javascript
seajs.use('index', function(array) {
	var arr = array.union([3,5,5,6,3,2,2],[5,100,200,300]);
	document.getElementById('union_result').innerHTML=arr;
});
````

执行后结果：
````html
<span id="union_result"></span>
````
---