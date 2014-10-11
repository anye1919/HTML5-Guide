HTML5-Guide
===========

##一个典型的 html5 文件结构

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Meta, title, CSS, favicons, etc. -->
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description" content="">
    <meta name="keywords" content="">
    <title></title>
    <link href="../assets/css/app.min.css" rel="stylesheet">
    <!-- HTML5 shim and Respond.js IE8 support of HTML5 elements and media queries -->
    <!--[if lt IE 9]>
    <script src="https://oss.maxcdn.com/html5shiv/3.7.2/html5shiv.min.js"></script>
    <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
    <!-- Favicons -->
    <link rel="apple-touch-icon" sizes="57x57" href="/apple-touch-icon-114.png">
    <link rel="apple-touch-icon-precomposed" href="/apple-touch-icon-precomposed.png">
    <link rel="icon" href="/favicon.ico">
  </head>
  <body>
    <header></header>
    <main></main>
    <footer></footer>
    <!-- Some JavaScript here -->
    <script src=""></script>
  </body>
</html>
```

##input元素 

```html
<input type="email" placehold="只能输入邮件地址"> 
<input type="number" min="0" max="4" step="1">
```

##video元素

```html
<video src="movie.ogg" width="320" height="240" controls="controls"></video>	
```

- video 元素允许多个 source 元素，source 元素可以链接不同的视频文件，浏览器将使用第一个可识别的格式，各浏览器支持的视频格式列表见[这里](http://www.w3school.com.cn/html5/html_5_video.asp)

```html
<video width="320" height="240" controls="controls">
  <source src="movie.ogg" type="video/ogg">
  <source src="movie.mp4" type="video/mp4">
</video>
```

- video 元素更多属性见[这里](http://www.w3school.com.cn/tags/tag_video.asp)

- 使用 DOM 控制 video 控件见[这里](http://www.w3school.com.cn/html5/html_5_video_dom.asp)

##audio元素

- audio 元素和 video 元素用法类似，就不赘述了，详情见[这里](http://www.w3school.com.cn/html5/html_5_audio.asp)

##拖放

```html
<html>
  <head>
    <script>
      // 允许元素被拖动
      function allowDrop(e) {
        e.preventDefault();
      }
      // 拖动时的处理
      function drag(e) {
        e.dataTransfer.setData("DATA", e.target.id);
      }
      // 放置时的处理
      function drop(e) {
        e.preventDefault();
        var data = e.dataTransfer.getData("DATA");
        e.target.appendChild(document.getElementById(data));
      }
    </script>
  </head>
  <body>
    <!-- 
      为img元素设置属性 draggable=true，让它可拖动
      ondragstart规定拖动时调用了drag函数，该函数设置了一个数据DATA    
    -->
    <img id="drag1" src="image.gif" draggable="true" ondragstart="drag(event)">    
    <!--
      ondragover规定在何处放置被拖动元素，由于浏览器默认不可以把元素放到其他元素中，在allowDrop函数中阻止对元素的默认处理
      当放置被拖数据时，会发生drop事件，触发drop函数，在此函数中把被拖动元素放到目标位置
    -->
    <div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>
  </body>
</html>
```

- 来回拖动的例子见[这里](http://www.w3school.com.cn/tiy/t.asp?f=html5_draganddrop2)

##canvas元素

canvas 元素使用 JavaScript 在网页上绘制图像

```html
<canvas id="myCanvas" width="200" height="100"></canvas>
```

###绘制矩形

```JavaScript
<script>
  // 获取画布元素
  var c = document.getElementById('myCanvas');
  // 创建tontext对象，context对象是内建的HTML5对象，拥有绘制路径、矩形、圆形以及添加图像等方法
  var ctx = c.getContext('2d');
  // 从左上角(0,0)开始，绘制一个长宽为(150,75)的矩形，tontext对象的fillStyle属性设置矩形为红色
  ctx.fillStyle = '#FF0000';
  ctx.fillRect(0,0,150,75);
</script>
```

###绘制线条

```JavaScript
<script>
  // 获取画布元素
  var c = document.getElementById('myCanvas');
  // 创建tontext对象，context对象是内建的HTML5对象，拥有绘制路径、矩形、圆形以及添加图像等方法
  var ctx = c.getContext('2d');
  // 通过指定从何处开始，在何处结束，来绘制一条线
  ctx.moveTo(10, 10);
  ctx.lineTo(150, 50);
  ctx.lineTo(10, 50);
  ctx.stroke();
</script>
```