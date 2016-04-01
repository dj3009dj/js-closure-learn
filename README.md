# js-closure-learn
take me three ours!

学习javascript的闭包原则
闭包：子函数可以使用函数中的局部变量
例子：
<script>
var a=(function(){
var count=0;
var b=function(){
count++;
return count;
};
return b;
}());

function myfun(){
document.getElementById("demo").innerHTML=a();
}
</script>
在子函数myfun中调用了匿名函数的局部变量count，
虽然该匿名函数是立即执行的，但是由于在外面调用了a(),
所以count不会立即死掉。
