<script>

export default {
	el: '#app',
	data() {
		return {
		input_weight: '',
		input_height: '',
		BMI: '',
		toggle: false
		}
	}
}


</script>


<template>

	<main class="app">
		
		<div class="title">
			<h2>Calculate your BMI</h2>
		</div>


			<div class="weight">
				<h3>Weight: <input id="weight" type="number" placeholder="your weight here" 
					v-model="input_weight"  /> kg </h3>
			</div>
			<div class="height">
				<h3>Height: <input id="height" type="number" placeholder="your height here" 
					v-model="input_height" /> m </h3>
			</div>
			<button class="BMI-btn" @click="BMI = Math.round((input_weight / input_height ** 2) *100)/100">Calculate BMI</button>

			<h2 class="BMI-result">BMI: {{ BMI }}</h2>

			<button @click="toggle=!toggle" class="btn-checkBMI">Check if your BMI is correct</button>

			<div v-if="toggle" class="checkBMI">
				<p>less than 16 - starvation</p>
				<p>16 - 16.99 - emaciation</p>
				<p>17 - 18.49 - underweight</p>
				<p>18.5 - 24.99 - correct weight</p>
				<p>25 - 29.99 - overweight</p>
				<p>30 - 34.99 - I degree of obesity</p>
				<p>35 - 39.99 - II degree of obesity</p>
				<p>over 40 - extreme obesity</p>
			</div>
	        <h1 v-else></h1>

                
	</main>

</template>

<style scoped>


main {
	position: absolute;
	text-align: center;
	margin:0 auto; 
	top: 0px;
	left: 0px;
	bottom: 0px;
	left: 0px;
	width: 100%;
	box-sizing: border-box;
	background: linear-gradient(to right, #00d2ff, #928dab);
	padding: 30px 40px 40px 40px;
	font-family: 'montserrat', sans-serif;
	zoom: 110%;
}

.title {
	margin: 20px 0 20px 0;
	color: white;
	
}

.weight {
	margin-bottom: 5px;
	color: white;
}
#weight {
	padding: 2px 4px 2px 4px;
	
}
.height {
	margin-top: 10px; 
	color: white;
}
#height {
	padding: 2px 4px 2px 4px;
}
.BMI-btn {
	margin-top: 20px;
	padding: 8px 20px 8px 20px;
	transition-duration: 0.4s;
	color: rgb(252, 252, 252);
	background-color: rgb(69, 86, 236);
	border: none;
 	display: inline-block;
  	font-size: 14px;
	border-radius: 4px;
}
.BMI-btn:hover {
	background-color: #3c31a2; /* Green */
  	color: white;
}

.BMI-result {
	margin: 30px 5px 5px 5px;
	color: white;
}

.btn-checkBMI {
	margin-top: 20px;
	padding: 8px 20px 8px 20px;
	transition-duration: 0.4s;
	color: rgb(252, 252, 252);
	background-color: rgb(193, 49, 49);
	border: none;
 	display: inline-block;
  	font-size: 14px;
	border-radius: 4px;
}
.btn-checkBMI:hover {
	background-color: #a2102b; /* Green */
  	color: white;
}
.checkBMI {
	margin-top: 20px;
	padding: 8px 20px 8px 20px;
	margin:20px auto; 
	color: white;
	background-color: rgb(69, 86, 236);
	border: none;
  	font-size: 14px;
	border-radius: 4px;
	width: 50%;
	text-align: center;
}




</style>