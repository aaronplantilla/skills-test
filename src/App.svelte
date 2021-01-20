<script>
	function getStarted(){
		let start = document.getElementById("start-page");
		let login = document.getElementById("login-page")
		start.style.visibility = "hidden";
		login.style.visibility = "visible";
	}

	let textVal = ""
	let textVal2 = ""

	function disablePwd(textVal){
		return textVal == ""
	}

	function disableButton(textVal2){
		return textVal2 == ""
	}

	function loggedIn(){
		let login = document.getElementById("login-page");
		let home = document.getElementById("home-page")
		alert('Welcome User!')
		login.style.visibility = "hidden";
		home.style.visibility = "visible";
	}
</script>

<main>
	<!-- Start Page -->
	<div id="start-page">
		<h1>CA<span class="shack">SHACK</span></h1>
		<button on:click={getStarted}>Get Started</button>
	</div>
	
	<!-- Login Page -->
	<div id="login-page">
		<h1>Login</h1>
		Username: <input type="text" bind:value={textVal}>
		<br>
		Password: <input type="password" bind:value={textVal2} disabled='{disablePwd(textVal)}'>
		<br>
		<button disabled = '{disableButton(textVal2)}' on:click={loggedIn}>Login</button>
	</div>
	
	<!-- Home Page -->
	<div id="home-page">
		<h1>Hello!</h1>
	</div>

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
	.shack{
		color: red;
	}

	#start-page{
		margin-top: 200px;
		visibility: visible;
		position: static;
		opacity: 1;
	}

	#login-page{
		margin-top: -150px;
		position: static;
		visibility: hidden;
	}

	#home-page{
		margin-top: -150px;
		position: static;
		visibility: hidden;
	}
</style>