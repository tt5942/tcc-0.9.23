# This is the first page hosted on github.io
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

