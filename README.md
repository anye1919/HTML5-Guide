HTML5-Guide
===========

##input元素 

```html
<input type="email" placehold="只能输入邮件地址"> 
<input type="number" min="0" max="4" step="1">
```


##video元素

```html
<video src="movie.ogg" width="320" height="240" controls="controls">
Your browser does not support the video tag.
</video>	
```

*video 元素允许多个 source 元素。source 元素可以链接不同的视频文件。浏览器将使用第一个可识别的格*

```html
<video width="320" height="240" controls="controls">
  <source src="movie.ogg" type="video/ogg">
  <source src="movie.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
```