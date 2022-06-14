# node 回调函数
```
//阻塞代码实例
// var fs = require("fs");

// var data = fs.readFileSync('input.txt');

// console.log(data.toString());
// console.log("program ending!");

// 非阻塞代码实例

var fs = require("fs");

fs.readFile("input.txt",function(err,data){
    if (err) return console.error(err);
    console.log(data.toString());
})
console.log("program is ending!")
```
