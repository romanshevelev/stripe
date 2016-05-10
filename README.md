<html>
<body>
<canvas id="maincanvas" height="800" width="1000"></canvas>
<script>
(function(){

	var elem=document.getElementById("maincanvas");
	if (elem && elem.getContext) {
		var context = elem.getContext('2d');
		if (!context) return;
	}

	line=function(x0, y0, x1, y1){
		context.beginPath();
		context.moveTo(x0*this.zoom+0.5, y0*this.zoom+0.5);
		context.lineTo(x1*this.zoom+0.5, y1*this.zoom+0.5);
		context.stroke();
	}.bind(this)

	context.lineWidth = 1;
	zoom=40;

	// Рамка
	context.strokeStyle = '#555';
	context.strokeRect(0.5, 0.5, context.canvas.clientWidth-0.5, context.canvas.clientHeight-0.5);

	// Сетка
	context.strokeStyle = '#ccc';
	for(var i=1;i<=100;i++){
		line(i,0,i,100);
		line(0,i,100,i);
	}


})()
</script>
</body>
</html>
