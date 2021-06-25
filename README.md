<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>課題１</title>
		<link rel="stylesheet" href="style.css" >
		<script src="https://cdn.jsdelivr.net/npm/vue@2.5.17/dist/vue.js"></script>
	</head>
	
	<body>
		<h1>身長と体重を入力してください</h1>
		<div id="app">
			<input v-model.number="A" type="number">m x 
			<input v-model.number="B" type="number">kg
			<h4>BMI　{{ sum }} </h4>
			<h4>適正体重　{{ sum2 }} </h4>
            <p v-if="sum>25"><br>ダイエットしましょう</br><img src="太ってる人.jpg" title="太ってる人"></p>
			<p v-else><br>いい感じです</br><img src="痩せてる人.jpg" title="痩せてる人"></p>
		</div>

		<script>
			new Vue({
				el: '#app',
				data: {
					A: 1.6,
					B: 50
				},
				computed: {
					// AかBが変わったら、BMIを算出する
					sum: function () {
						return Math.round (this.B / (this.A * this.A));
					},
					sum2: function(){
						return Math.round(this.A * this.A) * 22;
					}
                }

			})
           
		</script>
	</body>
</html>
