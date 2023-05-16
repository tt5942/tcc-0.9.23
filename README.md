<<<<<<< HEAD
# This is the first page hosted on github.io

<!DOCTYPE html>
<html>
    <head>
    <!-- Title -->
    
    <title>
        HTML5动态时钟 | FelixZhang&#39;s Blog
    </title>
    
    <!-- Favicons -->
    <link rel="icon shortcut" type="image/ico" href="/img/favicon.png">
    <link rel="icon" sizes="192x192" href="/img/favicon.png">
    <link rel="apple-touch-icon" href="/img/favicon.png">
    
    <!-- Meta & INfo -->
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="theme-color" content="#0097A7">
    <meta name="author" content="Felix">
    <meta name="description" content="null">
    <meta name="keywords" content="null">
    
    <!--iOS -->
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
    <meta name="apple-mobile-web-app-title" content="Title">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black">
    <meta name="HandheldFriendly" content="True">
    <meta name="MobileOptimized" content="480">
    
    <!-- Add to homescreen for Chrome on Android -->
    <meta name="mobile-web-app-capable" content="yes">
    
    <!-- Add to homescreen for Safari on iOS -->
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black">
    <meta name="apple-mobile-web-app-title" content="FelixZhang&#39;s Blog">
    
    <!-- The Open Graph protocol -->
    <meta property="og:url" content="http://felixzhang00.github.io">
    <meta property="og:type" content="blog">
    <meta property="og:title" content="HTML5动态时钟 | FelixZhang&#39;s Blog">
    <meta property="og:description" content="null">
    
     <!--[if lte IE 9]>
        <link rel="stylesheet" href="/css/ie-blocker.css">
        
        
            <script src="/js/ie-blocker.zhCN.js"></script>
        
    <![endif]-->
    
    <!-- Import CSS -->
    <link rel="stylesheet" href="/css/material.min.css">
    <link rel="stylesheet" href="/css/style.min.css">
    <!-- Config CSS -->


<!-- Other Styles -->



<!-- Theme Background Related-->

    <style>
        body{
            background-color: #F5F5F5
        }
		
		/* blog_info bottom background */
        #scheme-Paradox .material-layout .something-else .mdl-card__supporting-text{
            background-color: #fff;
        }
    </style>





    
    <!-- Custom Head -->
    
</head>

<body id="scheme-Paradox">

		
        <div class="material-layout  mdl-js-layout has-drawer is-upgraded">
				
			
			
            <!-- Main Container -->
            <main class="material-layout__content" id="main">
			
			<!-- Random Thumbnail -->
			<div class="post_thumbnail-random mdl-card__media mdl-color-text--grey-50">
				<script>
    
    var randomNum;
    randomNum = Math.floor(Math.random() * 5 + 1);
    
    $(".post_thumbnail-random").css('background-image', 'url(' + '/img/random/' + randomNum + '.png' + ')');
    
</script>

		
	
        <p class="article-headline-p">
            HTML5动态时钟
        </p>
    </div>
	
	<!-- Post Content -->
                <div id="post-content" class="markdown-Github mdl-color-text--grey-700 mdl-card__supporting-text fade out">
	
		<p>##效果图</p>
<p><canvas id="mycanvas" width="500" height="500" style="background: #B0D141"></canvas></p>
<script>
            var mycanvas = document.getElementById("mycanvas");
            var context = mycanvas.getContext("2d");

            function drawClock() {
                //每次调用函数都要对指定区域清屏
                context.clearRect(0, 0, 500, 500);
                var date = new Date();
                var hour = date.getHours();
                var min = date.getMinutes();
                var sec = date.getSeconds();
                hour = (hour >= 12) ? hour - 12 : hour;
                hour = hour + min / 60;
                min = min + sec / 60;

                //画圆
                context.lineWidth=10;
                context.strokeStyle='#000';
                context.beginPath();
                context.arc(250, 250, 200, 0, 360, false);
                context.closePath();
                context.stroke();



                //画时刻度

                for (var i = 0; i < 12; i++) {
                    context.save();
                    context.strokeStyle='black';
                    context.beginPath();
                    context.translate(250, 250);
                    context.rotate(i * 30 * Math.PI / 180);
                    context.beginPath();
                    context.moveTo(0, -190);
                    context.lineTo(0, -170);
                    context.closePath();
                    context.stroke();
                    context.restore();
                }


                //画分刻度
                context.beginPath();
                for (var i = 0; i < 60; i++) {
                    context.save();
                    context.strokeStyle='black';
                    context.beginPath();
                    context.translate(250, 250);
                    context.rotate(i * 6 * Math.PI / 180);
                    context.moveTo(0, -190);
                    context.lineTo(0, -180);
                    context.closePath();
                    context.stroke();
                    context.restore();
                }


                //画时针
                context.save();
                context.lineWidth=12;
                context.beginPath();
                context.translate(250, 250);
                context.rotate(hour * Math.PI * 30 / 180);
                context.moveTo(0, -135);
                context.lineTo(0, 10);
                context.closePath();
                context.stroke();
                context.restore();

                //画分针
                context.save();
                context.lineWidth=8;
                context.beginPath();
                context.translate(250, 250);
                context.rotate(min * Math.PI * 6 / 180);
                context.moveTo(0, -160);
                context.lineTo(0, 10);
                context.closePath();
                context.stroke();
                context.restore();

                //画秒针
                context.save();
                context.lineWidth=5;
                context.strokeStyle='red';
                context.beginPath();
                context.translate(250, 250);
                context.rotate(sec * Math.PI * 6 / 180);
                context.moveTo(0, -182);
                context.lineTo(0, 16);
                context.closePath();
                context.stroke();
                context.restore();
            }
            setInterval(drawClock, 1000);
        </script>
	
	
</div>


<!-- MathJax Load-->

            </main>
        </div>
		
    </body>
		
	
</html>
=======
# This is the first page hosted on github.io , now with a clock
 <body>
	<canvas id="mycanvas" width="500" height="500" style="background: #B0D141"></canvas>
	<script>
			var mycanvas = document.getElementById("mycanvas");
			
			var context = mycanvas.getContext("2d");
			
			function drawClock () 
			{
				//每次调用函数都要对指定区域清屏
				context.clearRect(0, 0, 500, 500);
				
				var date = new Date ();
				var hour = date.getHours ();
				var min = date.getMinutes ();
				var sec = date.getSeconds ();
				
				hour = (hour >= 12)   hour - 12 : hour;
				hour = hour + min / 60;
				min = min + sec / 60;
				
				//画圆
				context.lineWidth=10;
				context.strokeStyle='#000';
				context.beginPath ();
				context.arc(250, 250, 200, 0, 360, false);
				context.closePath ();
				context.stroke ();
				
				
				//画时刻度
				for (var i = 0; i < 12; i++) 
				{
					context.save ();
					context.strokeStyle='black';
					context.beginPath ();
					context.translate(250, 250);  // translate() 方法重新映射画布上的 (0,0) 位置。
					context.rotate(i * 30 * Math.PI / 180);
					context.beginPath ();
					context.moveTo(0, -190);
					context.lineTo(0, -170);
					context.closePath ();
					context.stroke ();
					context.restore ();
				}
				
				//画分刻度
				context.beginPath ();
				for (var i = 0; i < 60; i++) 
				{
					context.save ();
					context.strokeStyle='black';
					context.beginPath ();
					context.translate(250, 250);
					context.rotate(i * 6 * Math.PI / 180);
					context.moveTo(0, -190);
					context.lineTo(0, -180);
					context.closePath ();
					context.stroke ();
					context.restore ();
				}
				
				//画时针
				context.save ();
				context.lineWidth=12;
				context.beginPath ();
				context.translate(250, 250);
				context.rotate(hour * Math.PI * 30 / 180);
				context.moveTo(0, -135);
				context.lineTo(0, 10);
				context.closePath ();
				context.stroke ();
				context.restore ();
				
				//画分针
				context.save ();
				context.lineWidth=8;
				context.beginPath ();
				context.translate(250, 250);
				context.rotate(min * Math.PI * 6 / 180);
				context.moveTo(0, -160);
				context.lineTo(0, 10);
				context.closePath ();
				context.stroke ();
				context.restore ();
				
				//画秒针
				context.save ();
				context.lineWidth=5;
				context.strokeStyle='red';
				context.beginPath ();
				context.translate(250, 250);
				context.rotate(sec * Math.PI * 6 / 180);
				context.moveTo(0, -182);
				context.lineTo(0, 16);
				context.closePath ();
				context.stroke ();
				context.restore ();
			}
			setInterval(drawClock, 1000);
		</script>
		
		<body/>

>>>>>>> dd814b0e5a16e450fc26fd7d767d89592ac77bf7
