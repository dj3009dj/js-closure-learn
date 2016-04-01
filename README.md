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

其次,需要特别清楚的是,javascript中的()的作用！
对于上面的例子而言，虽然匿名函数是一个self-invoking方法，会立即执行。
然而执行到子函数时,这个子函数不会立即执行，即此时子函数还是一个statement
所以执行完毕之后变量a实际上就是 function(){count++; return count;}这一句话
最终使用a()时，这个statement就会变成expression,去执行上面所说的语句。
