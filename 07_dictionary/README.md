#07 Dictionary

##7.1 Dictionary 클래스

```js
function Dictionary(){
    this.datastore = new Array();
}
```

```js
function add(key , value){
    this.datastore[key] = value;
}
```

```js
function find(key){
    return this.datastore[key];
}
```

```js
function remove(key){
    delete this.datastore[key];
}
```

```js
function showAll(){
    for each (var key in Object.keys(this.datastore)){
        console.log(key+ " -> " + this.datastore[key]);
    }
}
```

[예제 7-1] Dictionary 클래스

```js
function Dictionary(){
    this.add = add;
    this.datastore = new Array();
    this.find = find;
    this.remove = remove;
    this.showAll = showAll;
}

function add(key , value){
    this.datastore[key] = value;
}

function find(key){
    return this.datastore[key];
}

function remove(key){
    delete this.datastore[key];
}

//function showAll(){
//    for each (var key in Object.keys(this.datastore)){
//        console.log(key+ " -> " + this.datastore[key]);
//    }
//}

function showAll(){
    var thisDataStore = this.datastore;
    Object.keys(thisDataStore).forEach(function(key){
       console.log(key+ " -> " + thisDataStore[key]);
    })
}
```

[예제 7-2] Dictionary 클래스 사용하기

```js
var pbook = new Dictionary();
pbook.add("Mike","123");
pbook.add("David","345");
pbook.add("Cynthia","456");
console.log("David's extension : "+ pbook.find("David"));
```

##7.2 Dictionary 클래스의 부가 함수

```js
 function count(){
   var n = 0;
   for(var key in Object.keys(this.datastore)){
      n++;
    }
    return n;
 }
```
```js
 var nums() = new Array();
 nums[0] = 1;
 nums[1] = 2;
 console.log(nums.length); // 2출력
 var pbook = new Array();
 pbook["David"] = 1;
 pbook["Jennifer"] = 2;
 console.log(pbook.length); // 0출력
```
```js
 function clear(){
   for(var key in Object.keys(this.datastore)){
     delete this.datastore[key];
   }
 }
```

[예제 7-3] 추가 기능을 포함하는 Dictionary 클래스 정의

```js
 function Dictionary(){
   this.add = add;
   this.datastore = new Array();
   this.find = find;
   this.remove = remove;
   this.showAll = showAll;
   this.count = count;
   this.clear = clear
 }
 
 function add(key,value){
   this.datastore[key] = value;
 }
 
 function find(key){
   return this.datastore[key];
  
 }
 
 function remove(key){
   delete this.datastore[key];
 }
 
 function showAll(){
   for(var key in Object.keys(this.datastore)) {
     console.log(key + "->" + this.datasotre[key]);
   }
 }
 
  function count(){
   var n = 0;
   for(var key in Object.keys(this.datastore)){
      n++;
    }
    return n;
 }
 
 function clear(){
   for(var key in Object.keys(this.datastore)){
     delete this.datastore[key];
   }
 }
```

[예제 7-4] count(), clear()함수 사용하기 

```js 
  //require("Dictionary.js");
  var pbook = new Dictionary();
  pbook.add("Raymond","123");
  pbook.add("David","345");
  pbook.add("Cynthia","456");
  
  console.log("Number of entries : " + pbook.count());
  console.log("David's extension : " + pbook.find("David"));
  
  pbook.showAll();
  pbook.clear();
  console.log("Number of entries : " + pbook.count());
```

##7.3 Dictionary 클래스에 정렬 기능 추가하기

```js
  var a = new Array();
  a[0] = "Mike";
  a[1] = "David";
  console.log(a); // Mike, David 출력
  a.sort();
  console.log(a); // David , Mike 출력
```

```js 
  function showAll(){
    for(var key in Object.keys(this.datastore).sort()){
      console.log(key + " -> " + this.datastore[key]);
    }
  }
```

[예제 7-5] 정렬된 딕셔너리 출력

```js
  //require("Dictionary.js")
  var pbook = new Dictionary();
  pbook.add("Raymond","123");
  pbook.add("David","345");
  pbook.add("Cynthia","456");
  pbook.add("Mike","723");
  pbook.add("Jennifer","987");
  pbook.add("Danny","012");
  pbook.add("Jonathan","666");
  
  pbook.showAll();
  
```
