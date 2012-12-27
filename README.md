# jClip.js - 兼容多浏览器的文本复制插件

### jQuery插件，兼容IE、Chrome、Firefox等。
### 封装自[zeroclipboard.js](http://http//code.google.com/p/zeroclipboard/  "zeroclipboard.js project")，感谢原作者。

# 使用方法

## 1. 部署jClip
- 所需文件目录结构如下
  --ZeroClipboard.swf
  --jquery.jclip.js

## 2. 引入jquery.jclip.js

````php 
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js"></script>
<script>window.jQuery || document.write('<script src="js/jquery-1.8.3.min.js"><\/script>')</script>
<script src="js/jquery.jclip.js"></script>
````

## 3. HTML代码

````php 
<p class="text">Hello world! </p>
<a href="###" class="btn_copy">点击复制</a>
<br/><br/>
<a href="###" class="btn_ajax_text">复制ajax返回数据</a>
<br/><br/>
<a href="###" class="btn_func_text">复制function返回数据</a>
````

## 4. Javascript调用代码

````javascript 
<script type="text/javascript" >
$(function(){
    //复制静态文本
    $(".btn_copy").jclip({
        path:'js/ZeroClipboard.swf',
        copy:$(".text").text()
    });

    //复制ajax返回的数据
    $.get("text.php", function(data){
        $(".btn_ajax_text").jclip({
            path:'js/ZeroClipboard.swf',
            copy:data
        });
    });

    //复制函数返回的数据
    function retText(){
        return "return by function";
    }
    $(".btn_func_text").jclip({
        path:'js/ZeroClipboard.swf',
        copy:retText
    });
});
</script>
````

## 5. 修改复制成功提示语

在jquery.jclip.js文件中Line 62.

# 相似项目 

[zclip.js](http://www.steamdev.com/zclip  "zclip.js project")

