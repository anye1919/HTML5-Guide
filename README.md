HTML5-Guide
===========

一个典型的 html 文件结构

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

    <!-- Some Javascript here -->

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
<video src="movie.ogg" width="320" height="240" controls="controls">
Your browser does not support the video tag.
</video>	
```

*video 元素允许多个 source 元素，source 元素可以链接不同的视频文件，浏览器将使用第一个可识别的格式*

```html
<video width="320" height="240" controls="controls">
  <source src="movie.ogg" type="video/ogg">
  <source src="movie.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
```

