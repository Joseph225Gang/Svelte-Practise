<script>
	let name = 'Joseph';
	let beltColour = 'black';
	let magicColor = 'blue';
	let firstName = 'Josh';
	let lastName = 'Wang';

	$: fullName = `${firstName} ${lastName}`;
	$: console.log(beltColour);

	const handleClick = () => {
		beltColour = 'orange';
		alert(name);
	};

	const handleInput = (e) => {
		beltColour = e.target.value;
	};
</script>

<main>
	<h1>Hello {name}!</h1>
	<h1>{fullName} belt</h1>
	<h1>{beltColour} belt</h1>
	<h1>{magicColor}</h1>
	<p style="color:{magicColor}">aaaa</p>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<button on:click={handleClick}>Let's Click</button>
	<input type="text" on:input={handleInput} value={beltColour}>
	<input type="text" bind:value={magicColor}>
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