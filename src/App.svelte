<script>
	let firstName = "Ray";
	let lastName = "Agas";
	let beltColour = "blue"

	// Simplified value / reactive value
	$: fullName = `${firstName} ${lastName}`
	// reactive statement
	$: {
		console.log(beltColour)
		console.log(fullName)
	}

	const handleClick = () => {
		beltColour = 'red'
	}

	const handleInput = (e) => {
		beltColour = e.target.value
	}
</script>

<main>
	<p>{fullName} - {beltColour} belt</p>
	<input type="text" bind:value={firstName}/>
	<input type="text" bind:value={lastName}/>
	<input type="text" bind:value={beltColour}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>