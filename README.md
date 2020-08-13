<!DOCTYPE html>
<html>
<head>
	<title></title>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.3/Chart.min.js"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.3/Chart.bundle.js"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.3/Chart.bundle.min.js"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.3/Chart.css"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.3/Chart.js"></script>
	<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.3/Chart.min.css"></script>
	<script src="https://cdn.jsdelivr.net/npm/chartjs-plugin-datalabels"></script>

	
</head>
<body>
<style>
	h2{color:red; text-align:center; width:300px;}
	p {color:blue; text-align:center; width:300px;}
</style>
<div style="width: 400px; height: 400px;">
	<canvas id="myChart" width="400px" height="400px"></canvas>	
</div>

<script>
var ctx = document.getElementById('myChart').getContext('2d');
var labels = ['LG', '', 'Yellow', 'Green', 'Purple', 'Orange']; // 라벨 값들
var bgcolor = [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
              ];
Chart.defaults.global.legend.display = true;

var myChart = new Chart(ctx, {
    type: 'pie',
    data: {
        labels: labels,
        datasets: [{
            label: '# of Votes',
            data: [49.99, 35, 12.5, 1.95],
            backgroundColor: bgcolor,
            borderColor: [
                'rgba(255, 99, 132, 1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
       responsive : true,
       plugins : {
       	 datalabels:{
       	 	color : '#000',
       	 	align : 'start',
       	 	offset: -10,
       	 	borderWidth : 2,
       	 	borderRadius : 25,
       	 	backgroundColor : (context) => {
       	 		return context.dataset.backgroundColor;
       	 	},
       	 	font : {
       	 		width : 'bold',
       	 		size: '20'
       	 	},
       	 	formatter: (context) =>{
       	 		return context.dataset + context +'%'   ;
       	 	}
       	 }
       },
       
       //pieceLabel: { mode:"label", position:"outside", fontSize: 11, fontStyle: 'bold' }
    }
});
</script>

</body>
</html>
